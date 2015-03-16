# Session requests #

Content:

  * [Session Start](RequestsSession#Session_Start.md)
  * [Session Login](RequestsSession#Session_Login.md)
  * [Session Logout](RequestsSession#Session_Logout.md)
  * [Session Register](RequestsSession#Session_Register.md)


---


## Session Start ##
| request URL | `/session/start/` |
|:------------|:------------------|
| method | GET |
| description | Starts anonymous session. |

**Parameters**

_system_ .. values:
  * **android**
  * **ios**
  * **symbian**

**Returns data**

[API Session](Datatypes#API_Session.md) structures.

**Error codes**
| **ERROR CODE** | **meaning** |
|:---------------|:------------|
| MSG\_OK | successfuly started anonymous session |



---


## Session Login ##
| request URL | **(HTTPS)** `/session/login/` |
|:------------|:------------------------------|
| method | **POST** |
| description | Logins user and starts authenticated session |

<font color='red'> <b>Warning:</b> currently we support HTTP and GET method in this request</font>

**Prameters**
| **parameter** | **type** | **description** |
|:--------------|:---------|:----------------|
| `email` | `String` | User's email. Must be valid email in format name@domain. |
| `password` | `String` | User's password. At least 6 characters. |
| `system` | `String` | operating system values: android, ios, symbian... |

**Returns data**

1 [API Session](Datatypes#API_Session.md) structure.

**Error codes**

| **API CODE** | **meaning** |
|:-------------|:------------|
| MSG\_OK | successfuly logged in and started authenticated session |
| ERR\_WRONG\_LOGIN | wrong email address was as login |
| ERR\_WRONG\_PASS | wrong password (means login exists in a database) |

**Returns HTTP code**

| **HTTP code** | **meaning**|
|:--------------|:-----------|
| 200 | server understood request (login process could have failed though) |
| 401 | loging failed. There is no guarantee that response has data with API error code |
| any other | server unreachable, unable to respond |


---


## Session Logout ##
| request URL | `/session/logout/` |
|:------------|:-------------------|
| method | GET |
| description | Logouts user. |


**Prameters (GET)**

| **parameter** | **type** |**description** |
|:--------------|:---------|:---------------|
| session\_key | String |current user's session key (anonymous or authenticated) |

**Returns data**

Nothing

**Error codes**

| **API CODE** | **meaning** |
|:-------------|:------------|
| MSG\_OK | successful logut |



---


## Session Register ##
| request URL | **(HTTPS)** `/session/register/` |
|:------------|:---------------------------------|
| method | **POST** |
| description | Registration of new dood user. |

<font color='red'> <b>Warning:</b> currently we support HTTP and GET method in this request </font>

**Prameters**
| **parameter** | **type** | **description** |
|:--------------|:---------|:----------------|
| `email` | `String` | User's email |
| `password` | `String` | User's password |
| `sex` | `String` | `M` or `F` for Male or Female (non case-sensitive) default `M` |
| `name` | `String` | User's name |
| `surname` | `String` | User's surname |
| `nickname` | `String` | User's nickname |
| `birthdate` | `String` | User's birthdate. Format `DDMMYYYY` |
| `default_city` | `String` | User's default\_city (non case-sensitive) default `WARSZAWA` |

**Returns data**

1 [API Session](Datatypes#API_Session.md) structure.

**Error codes (for HTTP code 200)**

| **API CODE** | **meaning** |
|:-------------|:------------|
| MSG\_OK | successfuly registered and started authenticated session |
| ERR\_LOGIN\_EXISTS | email (login) is busy (registration failed) |
| ERR\_PASS\_TOO\_SIMPLE | password is too simple (registration failed) |
| ERR\_WRONG\_EMAIL | wrong format of email (for instance no `@`) |

**Returns HTTP code**

| **HTTP code** | **meaning**|
|:--------------|:-----------|
| 200 | server understood request (registration process could have failed though) |
| any other | server unable to respond |

_**Note**_
  * Field verifier (for email and password) should be also implemented on client-side for optimizing transfer.