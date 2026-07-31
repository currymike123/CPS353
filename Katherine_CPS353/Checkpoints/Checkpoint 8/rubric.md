### Out of 13 points

### Functionality

2 - Benchmark test

2 - Made an improvement for the computation speed

2 - Documented the improvement in the README


### Process:

-1 - Any github checks failing

1 - Good commit messages for merge commits

3 - Gave a code review: must leave at least one suggested improvement on a specific line in a file

3 - Received a code review: should be sending out between 50-200 lines of code

### Important Notes:

Common errors: changing something without verifying it's a bottleneck and trying to fake the performance numbers (tests that run in <5 ms, using nanos to try to hide that, excessively fake data for the benchmark test, careful ordering of the tests to just pick up jvm cache warming, etc).

I let them get away with "google a fancy version of this algorithm" even though it has nothing to do with the performance tuning we talked about in class, though I do sometimes leave pointed comments about how they could make the for-demo-purposes algorithm 30% faster by applying the actual course material.