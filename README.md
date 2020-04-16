# highfructose
An exploit for the CVE-2019-5782 vulnerability affecting Google's JavaScript Engine V8's optimizing compiler Turbofan.
# The Vulnerability
It is assumed that a function can have at most (1 << 16)−2 arguments whereas in reality there can be more. Thus TurboFan evaluates the calculation arguments.length >> 16 to be always zero. One can then instantiate an array on which a store operation is called for an index dependant on the latter. This will lead to an unsafe optimization in which TurboFan prunes away a bound-check which it considers to be always satisﬁed (wrong assumption). This opens up the opportunity to trigger an Out-of-Bounds error.
# Setting Up V8
[Building V8](https://v8.dev/docs/build)
[Building old revisions](https://chromium.googlesource.com/chromium/src.git/+/master/docs/building_old_revisions.md)

