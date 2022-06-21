URL: https://github.com/adamfisk/LittleProxy/

Original revision: https://github.com/adamfisk/LittleProxy/commit/dfdb37536891062c4d0364f590fd7af878461961

Fixed revision: https://github.com/adamfisk/LittleProxy/commit/4ab98298795ea60bd58205d6551e63f7e14a4034

Where added: src/main/java/org/littleshoot/proxy/impl/DefaultHttpProxyServer.java#607
What added: boolean allowRequestToOriginServer

1. src/main/java/org/littleshoot/proxy/impl/DefaultHttpProxyServer.java#385
    - before
       - new DefaultHttpProxyServerBootstrap(serverGroup,transportProtocol, determineListenAddress(),sslEngineSource, authenticateSslClients,proxyAuthenticator, chainProxyManager, mitmManager,filtersSource, transparent,idleConnectionTimeout, activityTrackers, connectTimeout,serverResolver, readThrottleBytesPerSecond, writeThrottleBytesPerSecond,localAddress, proxyAlias, maxInitialLineLength, maxHeaderSize, maxChunkSize);
    - developer's repair
       - new DefaultHttpProxyServerBootstrap(serverGroup,transportProtocol,new InetSocketAddress(requestedAddress.getAddress(),requestedAddress.getPort() == 0 ? 0 : requestedAddress.getPort() + 1),sslEngineSource,authenticateSslClients,proxyAuthenticator,chainProxyManager,mitmManager,filtersSource,transparent,idleConnectionTimeout,activityTrackers,connectTimeout,serverResolver,globalTrafficShapingHandler != null ? globalTrafficShapingHandler.getReadLimit() : 0,globalTrafficShapingHandler != null ? globalTrafficShapingHandler.getWriteLimit() : 0,localAddress,proxyAlias,maxInitialLineLength,maxHeaderSize,maxChunkSize, allowRequestsToOriginServer);
    - our repair 
       - new DefaultHttpProxyServerBootstrap(serverGroup,transportProtocol,new InetSocketAddress(requestedAddress.getAddress(),requestedAddress.getPort() == 0 ? 0 : requestedAddress.getPort() + 1),sslEngineSource,authenticateSslClients,proxyAuthenticator,chainProxyManager,mitmManager,filtersSource,transparent,idleConnectionTimeout,activityTrackers,connectTimeout,serverResolver,globalTrafficShapingHandler != null ? globalTrafficShapingHandler.getReadLimit() : 0,globalTrafficShapingHandler != null ? globalTrafficShapingHandler.getWriteLimit() : 0,localAddress,proxyAlias,maxInitialLineLength,maxHeaderSize,maxChunkSize, allowRequestsToOriginServer);
