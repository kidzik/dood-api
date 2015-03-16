# Test Cases - Registration #

Content:

  * [Register Success Test](TestCasesRegistration#Register_Success_Test.md)
  * [Register Fail Login Busy Test](TestCasesRegistration#Register_Fail_Login_Busy_Test.md)
  * [Register Fail Login Format Test](TestCasesRegistration#Register_Fail_Login_Format_Test.md)
  * [Register Fail Password Format Test](TestCasesRegistration#Register_Fail_Password_Format_Test.md)

## Register Success Test ##

| test name | `registerSuccessTest` |
|:----------|:----------------------|
| request | `http://dood.pl/api/session/register` |
| parameters (GET) | `email=TEST_REGISTER_ACCOUNT@dood.pl&password=TEST_ACCOUNT_VALID_PASSWORD&sex=F& nickname=TEST_NICK&name=TEST_NAME&surname=TEST_SURNAME&birthdate=01011986&default_city=WARSZAWA` |
| response HTTP code | 200 |

response data (JSON):
```
{
   "code" = 0x000000
   "session_key" = "TEST_SESSION_KEY_01"
}
```

## Register Fail Login Busy Test ##

| test name | `registerFailLoginBusyTest` |
|:----------|:----------------------------|
| request | `http://dood.pl/api/session/register` |
| parameters (GET) | `email=TEST_REGISTER_ACCOUNT_BUSY@dood.pl&password=TEST_ACCOUNT_VALID_PASSWORD&sex=F& nickname=TEST_NICK&name=TEST_NAME&surname=TEST_SURNAME&birthdate=01011986&default_city=WARSZAWA` |
| response HTTP code | 401 |

response data (JSON):
```
{
   "code" = 0x000022
}
```

## Register Fail Login Format Test ##

| test name | `registerFailLoginFormatTest` |
|:----------|:------------------------------|
| request | `http://dood.pl/api/session/register` |
| parameters (GET) | `email=TEST_REGISTER_ACCOUNT_WRONG&password=TEST_ACCOUNT_VALID_PASSWORD&sex=F& nickname=TEST_NICK&name=TEST_NAME&surname=TEST_SURNAME&birthdate=01011986&default_city=WARSZAWA` |
| response HTTP code | 401 |

response data (JSON):
```
{
   "code" = 0x000023
}
```

## Register Fail Password Format Test ##

| test name | `registerFailPasswordFormatTest` |
|:----------|:---------------------------------|
| request | `http://dood.pl/api/session/register` |
| parameters (GET) | `email=TEST_REGISTER_ACCOUNT@dood.pl&password=w&sex=F& nickname=TEST_NICK&name=TEST_NAME&surname=TEST_SURNAME&birthdate=01011986&default_city=WARSZAWA` |
| response HTTP code | 401 |

response data (JSON):
```
{
   "code" = 0x000023
}
```