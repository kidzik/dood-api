# Test Cases - Authentication #

Content:

  * [Session Start Test](TestCasesAuthentication#Session_start_test.md)
  * [Login Success Test](TestCasesAuthentication#Login_Success_Test.md)
  * [Login Fail Wrong Login Test](TestCasesAuthentication#Login_Fail_Wrong_Login_Test.md)
  * [Login Fail Wrong Password Test](TestCasesAuthentication#Login_Fail_Wrong_Password_Test.md)
  * [Logout Valid Test](TestCasesAuthentication#Logout_Valid_Test.md)
  * [Logout Invalid Test](TestCasesAuthentication#Logout_Invalid_Test.md)

## Session start test ##
| test name | `sessionStartTest` |
|:----------|:-------------------|
| request | `http://dood.pl/api/session/start` |
| response HTTP code | 200 |

response data (JSON):
```
{
  "code" = 0x000000
  "session_key" = "TEST_SESSION_KEY_01"
}
```

## Login Success Test ##
| test name | `loginSucessTest` |
|:----------|:------------------|
| request | `http://dood.pl/api/session/login` |
| parameters (GET) | `email=TEST_ACCOUNT@dood.pl&password=TEST_ACCOUNT_VALID_PASSWORD` |
| response HTTP code | 200 |

response data (JSON):
```
{
  "code" = 0x000000
  "session_key" = "TEST_SESSION_KEY_01"
}
```


## Login Fail Wrong Login Test ##

| test name | `loginFailWrongLoginTest` |
|:----------|:--------------------------|
| request | `http://dood.pl/api/session/login` |
| parameters (GET) | `email=TEST_ACCOUNT_INVALID@dood.pl&password=TEST_ACCOUNT_VALID_PASSWORD` |
| response HTTP code | 401 |

response data (JSON):
```
{
  "code" = 0x000020
}
```

## Login Fail Wrong Password Test ##

| test name | `loginFailWrongPasswordTest` |
|:----------|:-----------------------------|
| request | `http://dood.pl/api/session/login` |
| parameters (GET) | `email=TEST_ACCOUNT@dood.pl&password=TEST_ACCOUNT_INVALID_PASSWORD` |
| response HTTP code | 401 |

response data (JSON):
```
{
  "code" = 0x000021
}
```

## Logout Valid Test ##

| test name | `logoutValidTest` |
|:----------|:------------------|
| request | `http://dood.pl/api/session/logout` |
| parameters (GET) | `session_key=TEST_SESSION_KEY_VALID` |
| response HTTP code | 200 |

## Logout Invalid Test ##

| test name | `logoutInvalidTest` |
|:----------|:--------------------|
| request | `http://dood.pl/api/session/logout` |
| parameters (GET) | `session_key=TEST_SESSION_KEY_INVALID` |
| response HTTP code | 401 |