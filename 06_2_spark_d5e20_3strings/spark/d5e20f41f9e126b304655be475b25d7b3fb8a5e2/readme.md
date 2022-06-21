URL: https://github.com/perwendel/spark/

Original revision: https://github.com/perwendel/spark/commit/99aaaed33ade23b47955ac593796a036b6045883

Fixed revision: https://github.com/perwendel/spark/commit/d5e20f41f9e126b304655be475b25d7b3fb8a5e2

Where added: src/main/java/spark/route/SimpleRouteMatcher.java#235

What added: String acceptedType

1. src/main/java/spark/route/SimpleRouteMatcher.java#228
    - before
       - addRoute(method, url, target);
    - developer's repair
       - addRoute(method, url, target, acceptType);
    - our repair 
       - addRoute(method, url, target, httpMethod);
