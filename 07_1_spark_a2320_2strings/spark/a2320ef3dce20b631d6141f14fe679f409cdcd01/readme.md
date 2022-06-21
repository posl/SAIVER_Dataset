URL: https://github.com/perwendel/spark/

Original revision: https://github.com/perwendel/spark/commit/5f767420ed43379d2034115513ef4c60567e0868

Fixed revision: https://github.com/perwendel/spark/commit/a2320ef3dce20b631d6141f14fe679f409cdcd01

Where added: src/main/java/spark/staticfiles/DirectoryTraversal.java#12

What added: String localFolder

1. src/main/java/spark/resource/ClassPathResourceHandler.java#83
    - before
       - DirectoryTraversal.protectAgainstInClassPath(resource.getPath());
    - developer's repair
       - DirectoryTraversal.protectAgainstInClassPath(resource.getPath(), baseResource);
    - our repair 
       - DirectoryTraversal.protectAgainstInClassPath(resource.getPath(), welcomeFile);
