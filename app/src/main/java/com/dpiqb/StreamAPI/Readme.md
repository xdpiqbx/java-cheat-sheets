# Stream API

Streams can be obtained in a number of ways. Some examples include:

- From a `Collection` via the `stream()` and `parallelStream()` methods;
- From an array via `Arrays.stream(Object[])`;
- From static factory methods on the stream classes, such as `Stream.of(Object[])`, `IntStream.range(int, int)` or `Stream.iterate(Object, UnaryOperator)`;
- The lines of a file can be obtained from `BufferedReader.lines()`;
- Streams of file paths can be obtained from methods in `Files`;
- Streams of random numbers can be obtained from `Random.ints()`;
- Numerous other stream-bearing methods in the JDK, including `BitSet.stream()`, `Pattern.splitAsStream(java.lang.CharSequence)`, and `JarFile.stream()`.

[Stream operations and pipelines](https://docs.oracle.com/javase/8/docs/api/java/util/stream/package-summary.html#StreamOps)

Interface Stream<T>

Последовательность элементов, поддерживающих последовательные и параллельные агрегатные операции.

Stream operations are divided into:

- intermediate operations
- terminal operations

Operations combined to form stream pipelines

Intermediate operations return a new stream.
