# Promotion requests #

Content:
  * [Promotion get](RequestsPromotion#Promotion_Get.md)

## Promotion Get ##

| request URL | **(HTTP)** `/promotion/get/` |
|:------------|:-----------------------------|
| method | **POST** |

**Prameters:**
| **parameter** | **type** | **description** |
|:--------------|:---------|:----------------|
| `latitude` (optional) | `Double` | Latitude of position to get promotions from |
| `longtitude` (optional) | `Double` | Longitude of position to get promotions from |
| `city` (optional) | `String` | City to get promotions from |
| `only_open` (optional) | `Boolean` | Get only offers from currently open businesses.  |
| `categories` (optional) | `List<Long>` | CSV with IDs of categories. Filters search results. <font>Currently unsuported</font> |

**Returns data:**

[Promotions](DatatypesPromotion.md) objects are returned.

<a href='Hidden comment: chyba nie warto pisac o tym w requestach
<font color="red">
_*note:*_ first version of API will send all Business objects from the list in [DatatypesAdvertProximity AdvertProximity]. Later on we will support addmitting system (users will be able to admit having certain object with certain version).


Unknown end tag for &lt;/font&gt;


'></a>

**Error codes:**

| **API CODE** | **meaning** |
|:-------------|:------------|
| `MSG_OK` | new location has been set |
| `ERR_REGION_NOT_SUPPORTED` | coordinates are to far from any database entry. `default_city` parameter has been considered. |

<a href='Hidden comment: O tym tez nie warto pisac bo dla kazdego requesta jest identycznie
*Returns HTTP code*

|| *HTTP code* || *meaning*||
|| `200 || server understood request ||
|| `401` || session_key not present or expired ||
|| `any other` || server unreachable, unable to respond ||

_warning: data array can be empty (but data field should be present in the reponse)._

_warning 2: ERR_REGION_NOT_SUPPORTED response looks the same except for the API code. We simply change users"s position to default_city. If default city is not supported (recognized) we take Warsaw (PL) as default_

_*Note:*_

* Pole get_advert definiuje czy klient chce w odpowiedzi dostać obiekt [DatatypesAdvertProximity AdvertProximity]. Serwer decyduje o tym co przesłać klientowi. Klient biernie wyświetla dane przychodzące od serwera.

* Dane przesłane przez serwer mogą nie zawierać obiektu Proximity Advertisemenet a jedynie obiekty typu [DatatypesBusiness Business]. W takim wypadku serwer uznał, że w okolicy nie ma żadnych ofert do pokazania i po prostu przesyła wybrane (wg ewentualnych ograniczeń) dane businessów (klient może je pokazać lub nie).

* Pola only_open, categories nie mają sensu jeśli nie ma flagi get_advert=true.

* W pierwszej wersji implementacji API w polu data w przypadku ustawienia flagi get_advert zwracane są zawsze wszystkie obiekty [DatatypesBusiness Business] z listy businesses w _AdvertProximity_. W przyszłości będzie można wykorzystać mechanizm przyznawania się do posiadania określonych obiektów.
'></a>