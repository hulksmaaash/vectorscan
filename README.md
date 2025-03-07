# Vectorscan?

A fork of Intel's Hyperscan, modified to run on more platforms. Currently ARM NEON/ASIMD
is 100% functional, and Power VSX are in development. ARM SVE2 will be implemented when
harwdare becomes accessible to the developers. More platforms will follow in the future,
on demand/request.

Vectorscan will follow Intel's API and internal algorithms where possible, but will not
hesitate to make code changes where it is thought of giving better performance or better
portability. In addition, the code will be gradually simplified and made more uniform and
all architecture specific -currently Intel- #ifdefs will be removed and abstracted away.

# Why the fork?

Originally, the ARM porting was supposed to be merged into Intel's own Hyperscan, and 2 Pull
Requests had been made to the project for this reason ([1], [2]). Instead of a review on technical
issues, Intel outright rejected any multi-architecture support for Hyperscan, for now and the
forseeable future and we were forced to fork. However, we are firm open source believers and
in the end this can only be a good thing, as it gives us the opportunity to make further
modifications and optimizations in the code, which could not be done otherwise.

# What is Hyperscan?

Hyperscan is a high-performance multiple regex matching library. It follows the
regular expression syntax of the commonly-used libpcre library, but is a
standalone library with its own C API.

Hyperscan uses hybrid automata techniques to allow simultaneous matching of
large numbers (up to tens of thousands) of regular expressions and for the
matching of regular expressions across streams of data.

Vectorscan is typically used in a DPI library stack, just like Hyperscan.

# Documentation

Information on building the Hyperscan library and using its API is available in
the [Developer Reference Guide](http://intel.github.io/hyperscan/dev-reference/).

# License

Vectorscan, like Hyperscan is licensed under the BSD License. See the LICENSE file in the
project repository.

# Versioning

The `master` branch on Github will always contain the most recent release of
Hyperscan. Each version released to `master` goes through QA and testing before
it is released; if you're a user, rather than a developer, this is the version
you should be using.

Further development towards the next release takes place on the `develop`
branch.

# Get Involved

The official homepage for Vectorscan is at [www.github.com/VectorCamp/vectorscan](https://www.github.com/VectorCamp/vectorscan).

# Original Hyperscan links
The official homepage for Hyperscan is at [www.hyperscan.io](https://www.hyperscan.io).

If you have questions or comments, we encourage you to [join the mailing
list](https://lists.01.org/mailman/listinfo/hyperscan). Bugs can be filed by
sending email to the list, or by creating an issue on Github.

If you wish to contact the Hyperscan team at Intel directly, without posting
publicly to the mailing list, send email to
[hyperscan@intel.com](mailto:hyperscan@intel.com).

[1]: https://github.com/intel/hyperscan/pull/272
[2]: https://github.com/intel/hyperscan/pull/287
