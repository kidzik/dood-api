# API for developers #


---


version: **2.0.0**

project wiki: [click here](TableOfContents.md)


---


API for developers who want to use data from [neib.org](http://neib.org/) website.

<a href='Hidden comment: API serwisu dood.pl definiuje format komunikacji oparty o wzorzec REST. Dokument nie określa adresu konkretnego serwera, który odpowiada w sposób poprawny na nadchodzące requesty. Użytkownik tego protokołu może wystawić własny serwer i połączyć go z dowolną bazą danych. Jedynym wymogiem jest zachowanie formatu ścieżek requestów po adresie serwera. Zaleca się również skorzystanie z pakowania danych przy użyciu GZIPa. Dane bazy dood.pl zostały wystawione na serwerze http://api.neib.org zgodnie z opisanym w tym dokumencie API.

==Podstawowe dane==

|| adres serwera || *http(s)://api.dood.pl* ||
|| sposób pakowania || *GZIP* ||
|| protokół || *HTTP* ||


==Ograniczenia==

Serwer dood.pl ogranicza dopuszczalną liczbę zapytań do 1.000 dziennie na jedną sesję w celu zabezpieczenia się przed wykradaniem danych.

==Założenia==

# Protokół opiera się na architekturze centralnego serwera i wielu łączących się z nim klientów, implementuje wzorzec wymiany danych o obiektach REST.
# Protokół ma minimalizować transfer danych po sieci.
# Protokół ma minimalizować liczbę wymian danych (szeregowych zapytań i odpowiedzi) potrzebnych na wykonanie określonej akcji. Np. przejście z widoku Businessu do widoku Listy Recenzji tego Businessu.
# Protokół ma wspierać mechanizmy cache’owania po stronie
# Protokół ma wspierać monitorowanie i ograniczanie rozmiaru przesyłanych danych po obydwu stronach poprzez mechanizm „przyznawania się” do
# Klienci protokołu mogą prezentować użytkownikom dane lekko nieaktualne. Decyzja o danych pokazywanych użytkownikowi leży po stronie klienta.
# Klient może (wykorzystując mechanizm cache’owania) pokazywać użytkownikom dane nieaktualne. Można to ograniczać poprzez usuwanie obiektów o określonym wieku (czasie od ostatniej synchronizacji)


==Nazewnictwo==

* Nazwy pól są pisane małymi literami, złączone znakiem _ np. default_city
* Nazwy klas i modeli pisane są małymi literami za wyjątkiem wszystkich pierwszych liter słów wchodzących w skład nazwy, bez odstępów. Np. BusinessShort
'></a>