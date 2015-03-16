# Test Cases - Localization #

Content:

  * [Set Location Without Advert](TestCasesLocalization#Set_Location_Without_Advert.md)

## Set Location Without Advert ##

we don't want to reveal locations of users hence we use https and POST method.

| test name | `setLocationWithoutAdvertTest` |
|:----------|:-------------------------------|
| request | `https://dood.pl/api/location/set` |
| parameters (POST) | `session_key=TEST_SESSION_KEY&latitude=55.55&longtitude=22.22` |
| response HTTP code | 200 |

response data (JSON):
```
{
   "code" = 0x000000
}
```
