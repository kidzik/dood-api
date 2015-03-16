# Proximity Advertisement #


| Numer typu | **51** |
|:-----------|:-------|
| Nazwa typu | **`AdvertProximity`** |


| businesses | `List<Long>` | Lista ID businessów w tej promocji. Lista powinna zawierać co najmniej jeden element (maksymalnie 50) |
|:-----------|:-------------|:--------------------------------------------------------------------------------------------------------|
| expires | 	`Long`	| Data wygaśnięcia promocji (ms. od 1.01.1970) |
| latitude | 	`Double` | Szerokość geograficzna środka promocji |
| longtitude | `Double` | Długość geograficzna środka promocji |
| radius | `Long` | 	Promień funkcjonowania promocji (w metrach) |
| city	| `String` | 	Miasto z którego zostały wybrane reklamy |

  * Należy zwrócić uwagę, że pole businesses nie ma pola total\_businesses. Przesyłamy od razu wszystkie obiekty na raz i nie można dopytać się o pozostałe obiekty na liście.

  * It is advisable that client application refreshes `AdvertProximity` object whenever  hearbeat function detects that:
    1. user has escaped radius of `AdvertProximity`
    1. `AdvertProximity` has expired
    1. `force refresh` has been sent from client application.

  * Please refer to [location set](RequestsLocation#Location_Set.md) request for details about handling this object.