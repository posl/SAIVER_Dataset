URL: https://github.com/perwendel/spark/

Original revision: https://github.com/perwendel/spark/commit/5f767420ed43379d2034115513ef4c60567e0868

Fixed revision: https://github.com/perwendel/spark/commit/a2320ef3dce20b631d6141f14fe679f409cdcd01

Refactoring Operation:
```
- public static void protectAgainstForExternal(String path) {
+ public static void protectAgainstForExternal(String path, String externalFolder) {
```

1. src/main/java/spark/resource/ExternalResourceHandler.java#82
    - before
       - DirectoryTraversal.protectAgainstForExternal(resource.getPath());
    - developer's repair
       - DirectoryTraversal.protectAgainstForExternal(resource.getPath(), baseResource);
    - our repair 
       - DirectoryTraversal.protectAgainstForExternal(resource.getPath(), baseResource);
