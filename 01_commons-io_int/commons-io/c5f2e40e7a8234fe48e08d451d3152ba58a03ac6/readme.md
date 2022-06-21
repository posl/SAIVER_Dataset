URL: https://github.com/apache/commons-io/

Original revision: https://github.com/apache/commons-io/commit/9e2b2c09732ca596331f7ca34ba4e0f03d70093d

Fixed revision: https://github.com/apache/commons-io/commit/c5f2e40e7a8234fe48e08d451d3152ba58a03ac6

Refactoring Operation:

   private DeferredFileOutputStream(final int threshold, final File outputFile, final String prefix,
-                                     final String suffix, final File directory) {
+                                    final String suffix, final File directory, final int initialBufferSize) {

Results:
1. src/main/java/org/apache/commons/io/output/DeferredFileOutputStream.java#102
   - before
      - this(threshold, outputFile, null, null, null);
   - developer's repair
      - this(threshold, outputFile, null, null, null, ByteArrayOutputStream.DEFAULT_SIZE);
   - our repair 
      - this(threshold, outputFile, null, null, null, 0);

2. src/main/java/org/apache/commons/io/output/DeferredFileOutputStream.java#127
   - before
      - this(threshold, null, prefix, suffix, directory);
   - developer's repair
      - this(threshold, null, prefix, suffix, directory, ByteArrayOutputStream.DEFAULT_SIZE);
   - our repair 
      - this(threshold, null, prefix, suffix, directory, 0);
