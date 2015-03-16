# Introduction #

API for [dood.pl](http://dood.pl/) defines communication based on REST methodology. This document do not assume any specific server (or client) implementation, but we try to ensure that API works correctly on:

  * **[http://dood.pl/api/](http://dood.pl/api/)**

# Convention #

According to REST convention all requests are stated in the following form
```
/object/action/
```

All responses have JSON format. Please refer to [Response Structure](DataExchangeStructure#Response_format.md) for details about data exchange structures.

**Pre-Assumptions:**

  1. If error code is 0 than HTTP response has code 200. Otherwise it may be different than 200. We try to support [standard HTTP error codes](http://en.wikipedia.org/wiki/List_of_HTTP_status_codes) and don't change their meanings.
  1. All sessions must start with `/session/start/` for retriving `session_key`.
  1. All requests except those mentioned above must contain `session_key` as parameter. Otherwise 401 HTTP error code is returned (this error is also returned if session expires).
  1. All retrived structures have header. Please refer to [header structure](Datatypes#Header.md).

**In following documentation we assume those conditions and we may not include them in each structure or request.**