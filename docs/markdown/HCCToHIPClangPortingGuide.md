### [WIP] HIP/HCC To HIP-Clang Porting Guide

## Overview

HCC and HIP-Clang are both Clang compilers.

HCC is an out-of-tree branch of Clang which
implements HCC language. HCC implements HIP
language on top of HCC language. HIP/HCC
runtime is implemented on top of HCC runtime.

HIP-Clang is mostly in Clang master branch.
Its development is in Clang master branch.
If a review takes too long, it may land first
in amd-stg-open branch. It is called HIP-Clang
to emphasize its support of HIP. Its runtime
is HIP/ROCclr.

## Language

HCC supports both HIP language and HCC
language syntax. HIP-Clang only supports
HIP language syntax.

One major difference between HCC and
HIP-Clang is host/device check. If a
function does not have device and host
attributes, usually HIP-Clang will treat
it as a host function, therefore it
cannot be called by a device function.
However HCC will allow it to be called
by a device or host function.

