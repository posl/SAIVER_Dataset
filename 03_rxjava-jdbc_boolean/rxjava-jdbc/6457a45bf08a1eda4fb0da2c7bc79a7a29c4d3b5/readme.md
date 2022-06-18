URL: https://github.com/davidmoten/rxjava-jdbc/

Original revision: https://github.com/davidmoten/rxjava-jdbc/commit/36670ac159faa10dcf8057180b6e88cf64090cff

Fixed revision: https://github.com/davidmoten/rxjava-jdbc/commit/6457a45bf08a1eda4fb0da2c7bc79a7a29c4d3b5

1. src/main/java/com/github/davidmoten/rx/jdbc/QuerySelectOnSubscribe.java#108
    - before
       - Util.setParameters(state.ps, parameters);
    - developer's repair
       - Util.setParameters(state.ps, parameters, query.names());
    - our repair 
       - Util.setParameters(state.ps, parameters, stateProvided);

2. src/main/java/com/github/davidmoten/rx/jdbc/QueryUpdateOnSubscribe.java#217
    - before
       - Util.setParameters(state.ps, parameters);
    - developer's repair
       - Util.setParameters(state.ps, parameters, query.names());
    - our repair 
       - Util.setParameters(state.ps, parameters, false);
