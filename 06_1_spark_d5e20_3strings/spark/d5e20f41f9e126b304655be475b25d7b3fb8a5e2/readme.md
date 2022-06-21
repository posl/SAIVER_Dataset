URL: https://github.com/perwendel/spark/

Original revision: https://github.com/perwendel/spark/commit/99aaaed33ade23b47955ac593796a036b6045883

Fixed revision: https://github.com/perwendel/spark/commit/d5e20f41f9e126b304655be475b25d7b3fb8a5e2

Where added: src/main/java/spark/route/SimpleRouteMatcher.java#214

What added: String acceptType

1. src/main/java/spark/Spark.java#285
    - before
       - routeMatcher.parseValidateAddRoute(httpMethod + " '" + route.getPath() + "'", route);
    - developer's repair
       - routeMatcher.parseValidateAddRoute(httpMethod + " '" + route.getPath() + "'", route, route.getAccessType());
    - our repair 
       - routeMatcher.parseValidateAddRoute(httpMethod + " '" + route.getPath() + "'", route, ipAddress);

2. src/main/java/spark/Spark.java#290
    - before
       - routeMatcher.parseValidateAddRoute(httpMethod + " '" + filter.getPath() + "'", filter);
    - developer's repair
       - routeMatcher.parseValidateAddRoute(httpMethod + " '" + filter.getPath() + "'", filter, filter.getAccessType());
    - our repair 
       - routeMatcher.parseValidateAddRoute(httpMethod + " '" + filter.getPath() + "'", filter, ipAddress);
