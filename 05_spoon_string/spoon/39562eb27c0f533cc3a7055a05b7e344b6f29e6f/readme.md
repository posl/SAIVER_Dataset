URL: https://github.com/INRIA/spoon/

Original revision: https://github.com/INRIA/spoon/commit/49657bb1d3e57f5148fe21b307cb3bf0c624ed78

Fixed revision: https://github.com/INRIA/spoon/commit/39562eb27c0f533cc3a7055a05b7e344b6f29e6f

Refactoring Operation:
```
- public JDTSnippetCompiler(Factory factory) {
+ public JDTSnippetCompiler(Factory factory, String contents) {
```

1. src/main/java/spoon/support/compiler/SnippetCompilationHelper.java#122
    - before
       - new JDTSnippetCompiler(f);
    - developer's repair
       - new JDTSnippetCompiler(f, contents);
    - our repair 
       - new JDTSnippetCompiler(f, contents);
