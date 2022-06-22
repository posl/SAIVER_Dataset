URL: https://github.com/davidmoten/rxjava-jdbc/

Original revision: https://github.com/davidmoten/rxjava-jdbc/commit/2014f620b855fbf69fffb2e11bbd017cfce8c5ab

Fixed revision: https://github.com/davidmoten/rxjava-jdbc/commit/ade68394d4bfad0492ae84151ce8e5421cbbc556

Refactoring Operation:
```
- public QueryContext(Database db, int batchSize) {
+ public QueryContext(Database db, int batchSize, int fetchSize) {
```

1. src/main/java/com/github/davidmoten/rx/jdbc/QueryContext.java#19
    - before
       - this(db, 1);
    - developer's repair
       - this(db, 1, 0);
    - our repair 
       - this(db, 1, 0);

2. src/main/java/com/github/davidmoten/rx/jdbc/QueryContext.java#75
    - before
       - new QueryContext(db, batchSize);
    - developer's repair
       - new QueryContext(db, batchSize, fetchSize);
    - our repair 
       - new QueryContext(db, batchSize, fetchSize);
