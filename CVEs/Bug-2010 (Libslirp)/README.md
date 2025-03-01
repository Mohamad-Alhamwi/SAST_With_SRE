# BUG-2010 (Libslirp)

## Installing The Vulnerable Version

1. We clone the repository:

```C
git clone https://gitlab.freedesktop.org/slirp/libslirp.git Libslirp
```

2. We navigate into the project directory:

```C
cd Libslirp
```

3. We find the commit related to the vulnerability (using the first 7 characters of the commit ID provided above). I would like to view the 5 lines before and after the concerned commit for better context:

```C
git log --graph --oneline --all | grep -B 5 -A 5 "a6ecd0f"
```

> \* 2e635d3 Qemu's internal TFTP server breaks lock-step-iness of TFTP
>
> \* 7a63190 Handle TFTP ERROR from client
>
> \* b9c52bb slirp/misc.c: fix warning with _FORTIFY_SOURCE
>
> \* 4a90db9 fix networking on win32 host
>
> \* 1e784fd Don't leak file descriptors
>
> \* **a6ecd0f** slirp: fix use-after-free
>
> \* 6842ff5 slirp: fix unmatched bracket in if 0
>
> \* 0829ff6 Fix sys-queue.h conflict for good
>
> \* 53852ea Fix Sparse warnings: add "static"
>
> \* 34d29d5 Fix compiler warnings
>
> \* ce220b6 slirp: Read host DNS config on demand


Now, we should see the commit `a6ecd0f` for **BUG-2010**.

4. We `checkout` the commit before the patch to retrieve the vulnerable version. Note that we `checkout` the `6842ff5` commit, not the `1e784fd` commit, because the git graph is read vertically from bottom to top:

```C
git checkout 6842ff5
```

Eventually, we have the vulnerable version of **Libslirp** before the fix for **BUG-2010** was applied. Now, we are ready to dive in.
