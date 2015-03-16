Content:

  * [Standard HTTP Codes](ErrorCodes#Standard_HTTP_Codes.md)
  * [API Error Codes](ErrorCodes#API_Error_Codes.md)

# Standard HTTP Codes #

We try to keep [standard meaning of all HTTP status codes](http://en.wikipedia.org/wiki/List_of_HTTP_status_codes).

| **HTTP code** | **meaning** |
|:--------------|:------------|
| **200** | **SC\_OK**. it DOES NOT mean that operation was successful. It basically means that you need to look at API code to get information about error. It means only that server undestood your request properly. |
| **401** | Authentication problems. The result data should still (but don't have to) be passed in the response.|
| **any other** | server is down, unable respond. no data is passed (nothing is guaranteed) |

Be aware of other HTTP errors which may occur. Especially errors >500.


# API Error Codes #

## Success ##

| **Code** | **Name** | **Description** |
|:---------|:---------|:----------------|
| `0x000000` | `MSG_OK` | Success |

## General server errors ##

| **Code** | **Name** | **Description** |
|:---------|:---------|:----------------|
| `0x000010` | `ERR_SERVICE_UNAVAILABLE` | Service is temporary unavaible |
| `0x000011` | `ERR_SESSION_EXPIRED` | Sesion expired |
| `0x000012` | `ERR_NOT_AUTHORISED` | User is not authorised for given request |
| `0x000013` | `ERR_NEED_LOGIN` | Cleint need to login for this request |
| `0x000014` | `ERR_NEED_UPDATE`| Client need update |
| `0x000015` | `ERR_WRONG_API_KEY` | 	API key is not authorised in dood.pl |
| `0x000016` | `ERR_LIMIT_EXCEEDED` | Daily access limit has been exceeded |



## Authentication errors ##

| **Code** | **Name** | **Description** |
|:---------|:---------|:----------------|
| `0x000020` | `ERR_WRONG_LOGIN` | Incorrect e-mail |
| `0x000021` | `ERR_WRONG_PASS` | Incorrect password |
| `0x000022` | `ERR_LOGIN_EXISTS` | E-mail (login) exists |
| `0x000023` | `ERR_WRONG_EMAIL` | Email in wrong format. |
| `0x000024` | `ERR_PASS_TOO_SIMPLE` | Password is too simple. |

## Data access errors ##

| **Code** | **Name** | **Description** |
|:---------|:---------|:----------------|
| `0x000030` | `ERR_OBJECT_NOT_FOUND` |  Object does not exist |
| `0x000031` | `ERR_INCONSISTENCE` | Client has newer version of object than server. This should never happen because server decides about objects versions. |

## Localization errors ##

| **Code** | **Name** | **Description** |
|:---------|:---------|:----------------|
| `0x000040` | `ERR_ADDRESS_TRANSLATION` |  Can't find location from given phraze |
| `0x000041` | `ERR_REGION_NOT_SUPPORTED` | There is no data for given position.  |

## Synchronization and concurency errors ##

| **Code** | **Name** | **Description** |
|:---------|:---------|:----------------|
| `0x000050` | `ERR_UPDATE_FAILED` | Object hasn't been updated |
| `0x000051` | `ERR_OBJECT_EXISTS` | Object does not exist |
| `0x000062` | `ERR_CANT_CREATE_OBJECT` | Object can't be created |