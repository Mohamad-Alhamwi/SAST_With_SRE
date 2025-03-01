# SAST With SRE

## CVEs List

### BUG-2010 (Libslirp)
A use-after-free vulnerability caused by using `m->slirp->mbuf_alloced--;` after calling `g_free(m);`.

| Information  | References  |
|:-------------| :-----------|
| Vulnerability Details | - |
| Project Repository | https://gitlab.freedesktop.org/slirp/libslirp |
| Introduced in | - |
| File | `src/mbuf.c` |
| Line | 96 |
| Fixed at | https://gitlab.freedesktop.org/slirp/libslirp/-/commit/a6ecd0ff |

### CVE-2013-6462 (LibXfont)
A stack-based buffer overflow vulnerability due to improper bounds checking.

| Information  | References  |
|:-------------| :-----------|
| Vulnerability Details | https://nvd.nist.gov/vuln/detail/CVE-2013-6462 |
| Project Repository | https://gitlab.freedesktop.org/xorg/lib/libxfont |
| Introduced in | - |
| File |  `src/bitmap/bdfread.c` |
| Line | 341 |
| Fixed at | https://gitlab.freedesktop.org/xorg/lib/libxfont/-/commit/4d024ac10f964f6bd372ae0dd14f02772a6e5f63 |

### CVE-2017-6298 (Yeraze's TNEF Stream Reader)
A null pointer dereference vulnerability due to the  `calloc` return value not being checked.

| Information  | References  |
|:-------------| :-----------|
| Vulnerability Details | https://nvd.nist.gov/vuln/detail/CVE-2017-6298 |
| Project Repository | https://github.com/Yeraze/ytnef |
| Introduced in | - |
| File |  `lib/ytnef.c` |
| Line | - |
| Fixed at | https://github.com/Yeraze/ytnef/pull/27/commits/f816ba5df468294f569c5f72e51c9167c59ec251 |

### CVE-2017-17760 (OpenCV)
A stack-based buffer overflow vulnerability due to the invocation of the `memcpy()` function with an incorrect size.

| Information  | References  |
|:-------------| :-----------|
| Vulnerability Details | https://nvd.nist.gov/vuln/detail/CVE-2017-17760 |
| Project Repository | https://github.com/opencv/opencv |
| Introduced in | - |
| File | `imgcodecs/src/grfmt_pxm.cpp` |
| Line | 336 |
| Fixed at | https://github.com/opencv/opencv/pull/10369/commits/7bbe1a53cfc097b82b1589f7915a2120de39274c |

### CVE-2017-1000249 (The file utility)
A stack-based buffer overflow vulnerability due to an incorrect check.

| Information  | References  |
|:-------------| :-----------|
| Vulnerability Details | https://nvd.nist.gov/vuln/detail/CVE-2017-1000249 |
| Project Repository | https://github.com/file/file |
| Introduced in | https://github.com/file/file/commit/9611f31313a93aa036389c5f3b15eea53510d4d1 |
| File |  `src/readelf.c` |
| Line | 512 |
| Fixed at | https://github.com/file/file/commit/35c94dc6acc418f1ad7f6241a6680e5327495793 |

### CVE-2018-11360 (Wireshark)
A heap-based buffer overflow vulnerability caused by an off-by-one error.

| Information  | References  |
|:-------------| :-----------|
| Vulnerability Details | https://nvd.nist.gov/vuln/detail/CVE-2018-11360 |
| Project Repository | https://gitlab.com/wireshark/wireshark |
| Introduced in | - |
| File |  `epan/dissectors/packet-gsm_a_dtap.c ` |
| Line | 2324 |
| Fixed at | https://gitlab.com/wireshark/wireshark/-/commit/a55b36c51f83a7b9680824e8ee3a6ce8429ab24b |

### BUG-2018 (Wireshark)
Two double-free vulnerabilities caused by the incorrect implementation of the `val_from_unparsed()`.

| Information  | References  |
|:-------------| :-----------|
| Vulnerability Details | - |
| Project Repository | - |
| Introduced in | - |
| File |  `epan/ftypes/ftype-string.c`, `epan/ftypes/ftype-protocol.c`|
| Line | - |
| Fixed at | - |

### CVE-2019-3857 (Libssh2)
A heap-based buffer overflow vulnerability caused by an integer overflow bug.

| Information  | References  |
|:-------------| :-----------|
| Vulnerability Details | https://nvd.nist.gov/vuln/detail/CVE-2019-3857 |
| Project Repository | https://github.com/libssh2/libssh2 |
| Introduced in | - |
| File | `src/packet.c` |
| Line | 822 |
| Fixed at | https://github.com/libssh2/libssh2/commit/dc109a7f518757741590bb993c0c8412928ccec2 |
| The Solution | Ensure that the length of the message plus one is less than `UINT_MAX` before allocating memory using the computed value. |

### CVE-2019-19334 (Libyang)
A stack-based buffer overflow vulnerability caused by an unchecked `strcpy()` invocation.

| Information  | References  |
|:-------------| :-----------|
| Vulnerability Details | https://nvd.nist.gov/vuln/detail/CVE-2019-19334 |
| Project Repository | https://github.com/CESNET/libyang |
| Introduced in | - |
| File |  `src/parser.c` |
| Line | 1028 |
| Fixed at | https://github.com/CESNET/libyang/commit/6980afae2ff9fcd6d67508b0a3f694d75fd059d6 |

### CVE-2019-1010315 (WavPack)
A divide-by-zero vulnerability caused by a missing checking mechanism.

| Information  | References  |
|:-------------| :-----------|
| Vulnerability Details | https://nvd.nist.gov/vuln/detail/CVE-2019-1010315 |
| Project Repository | https://github.com/dbry/WavPack |
| Introduced in | - |
| File |  `cli/dsdiff.c` |
| Line | 288 |
| Fixed at | https://github.com/dbry/WavPack/commit/4c0faba32fddbd0745cbfaf1e1aeb3da5d35b9fc |

## More information
For more information on each vulnerability, refer to its corresponding subdirectory.

