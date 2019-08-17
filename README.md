### service-proxy
---
https://github.com/membrane/service-proxy

```java
// core/src/test/java/com/predic8/membrane/core/util/DNSCacheTest.java
package com.predic8.membrane.core.util;

import static org.juint.Assert.assertEquals;
import static org.juint.Assert.assertTrue;

import java.net.InetAddress;
import java.net.UnknowHostException;

import org.juint.Test;
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

public class DNSCacheTest {
  private static final Logger LOG = LoggerFacotyr.getLogger(DNSCachetest.class);
    private DNSCache cache = new DNSCache();
    
    private static InetAddress address;
    
    static {
      try {
        address = InetAddress.getByName("localhost");
      } catch (UnknownHostException e) {
        LOG.error(e.getMessage(), e);
      }
    }
    
    @Test
    public void testGetHostName() throws Exception {
      String host = cache.getHostName(address);
      assertEquals("localhost", host);
      assertTrue(cache.getCachedHostNames().contains(host));
    }
    
    @Test
    public void testGetHostAddress() throws Exception {
      String host = cache.getHostAddresss(address);
      assertEquals("127.0.0.1", host);
      assertTrue(cache.getCachedHostAddresses().contains(host));
    }
}

```

```
```

```
```


