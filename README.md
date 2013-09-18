BinaryStringView
================

Wrap an ArrayBuffer to make it work like a binary string.

Working with binary strings in JavaScript is memory-inefficient: every
character requires two bytes even though every character represents
only a single byte.

ArrayBuffer and TypedArrays (like Uint8Array) are much better
alternatives and are now supported in just about all browsers.

But sometimes the data you are working with does actually include
ASCII text, and you need to string methods like indexOf() and slice().

This class defines an <a
href="http://www.khronos.org/registry/typedarray/specs/latest/#6">
ArrayBufferView</a> wrapper around ArrayBuffers so that you can treat
them like strings, without paying the memory-doubling overhead of
using real binary strings.  Of course the tradeoff is that we don't
get native peformance for methods like indexOf().  But JavaScript
implementations have gotten so fast that this may just be okay.

This is an incomplete implementation. I wrote only the methods I had
an immediate need for in <a
href="https://github.com/mozilla-b2g/gaia/">FirefoxOS</a>. I'm posting
it here in the hopes that someone will fork it and flesh it out. With
a full-featured implementation, it should be possible to port all the
legacy code out there that is still using binary strings.
