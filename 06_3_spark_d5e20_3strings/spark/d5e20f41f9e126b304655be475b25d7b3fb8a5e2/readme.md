URL: https://github.com/perwendel/spark/

Original revision: https://github.com/perwendel/spark/commit/99aaaed33ade23b47955ac593796a036b6045883

Fixed revision: https://github.com/perwendel/spark/commit/d5e20f41f9e126b304655be475b25d7b3fb8a5e2

Refactoring Operation:
```
- public RouteMatch(HttpMethod httpMethod, Object target, String matchUri, String requestUri) {
+ public RouteMatch(HttpMethod httpMethod, Object target, String matchUri, String requestUri, String acceptType) {
```

1. src/test/java/spark/RequestTest.java#36
    - before
       - new RouteMatch(HttpMethod.get,null,"/hi","/hi"); 
    - developer's repair
       - new RouteMatch(HttpMethod.get,null,"/hi","/hi", "text/html"); 
    - our repair 
       - null
