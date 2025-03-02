# BUG-2018 (Wireshark)

## Root Cause Analysis

Two double-free vulnerabilities in the files `epan/ftypes/ftype-string.c` and `epan/ftypes/ftype-protocol.c`. These vulnerabilities occur due to improper handling of memory deallocation, resulting in the potential for double-free errors.

The double-free vulnerabilities are caused by the interaction of three functions:

- `string_fvalue_free` (line 37),
- `val_from_string` (line 90), and
- `val_from_unparsed` (line 100).

The following are the relevant function definitions:

```C
static void string_fvalue_free(fvalue_t *fv)
{
	g_free(fv->value.string);
}

```

```C
static gboolean val_from_string(fvalue_t *fv, const char *s, gchar **err_msg _U_)
{
	/* Free up the old value, if we have one */
	string_fvalue_free(fv);

	fv->value.string = g_strdup(s);
	return TRUE;
}
```

```C
static gboolean val_from_unparsed(fvalue_t *fv, const char *s, gboolean allow_partial_value _U_, gchar **err_msg)
{
	fvalue_t *fv_bytes;

	/* Free up the old value, if we have one */
	string_fvalue_free(fv);

	/**
	 * Reduced for space reasons.
	 **/

	/* Just turn it into a string */
	return val_from_string(fv, s, err_msg);
}
```

The function `val_from_unparsed` calls `string_fvalue_free`, which is a wrapper for the `g_free` function that ensures that the memory pointed to by the provided parameter is freed. However, `val_from_unparsed` also returns the result of  `val_from_string`. The function `val_from_string`, in turn, also calls `string_fvalue_free` (the same memory deallocation function). As a result, the same memory area is freed twice by `val_from_unparsed` and again by `val_from_string`, leading to to a double-free vulnerability.

## Installing The Vulnerable Version
