# PYTANIA
## JAVA
#### Co to jest JVM?
#### Co to jest Garbage Collector?
#### Jakie rzeczy są zapisywane na stercie, a jakie na stosie?
#### Jakie znasz typy w JAVIE
#### Omów typy BigDecimal / BigInteger. Po co się je stosuje?
#### Czym są Unboxing i autoboxing w JAVIE?
#### Omów typy: String, StringBuilder. 
#### Czym charakteryzują się obiekty Immutable?
#### Omów jakie znasz klasyfikatory dostępu w JAVIE (są 4)

## PORÓWNYWANIE OBIEKTÓW
#### Jak porównywane są obiekty w JAVIE, z jakich metod korzystają.
#### Do czego służy metoda hashCode() ?
#### Omów interfejsy Comparable i Comparator.
#### BONUS: Skoro == porównuje **referencje** a nie wartości, to dlaczego w poniższym kodzie:

## KOLEKCJE
#### Jakie znasz kolekcje w JAVA. Podstawowy podział
#### Czym różni się ArrayList od LinkedList?
#### Czym różni się HashSet od TreeSet? 
#### Wyjaśnij jak działa HashMap.

## WYJĄTKI
#### Omów podstawowe klasy wyjątków i ich hierarchię
#### Czym różni się **Exception** od **Error**? 
#### Co to są wyjątki "checked" i "unchecked" ?
#### Czym różni się **RuntimeException** od **IOException**? 

## TYPY GENERYCZNE
#### Co to są typy generyczne? Omów je

## WĄTKI
#### Co to są wątki? Co to są procesy?
#### Jak utworzyć wątek? Jak go zatrzymać? 
#### Jak synchronizować wątki? Omów słowo kluczowe **synchronized**
#### Jak działają metody **wait()**, **notify()**, **notifyAll()**
  
## Git
#### Jak pobrać to repozytorium na komputer? 
#### Co to jest: commit, branch, merge, push, fetch ? 
#### Jak zrobić merge (jakiego narzędzia użyjesz?)
#### Czym różni się merge od rebase? Kiedy użyć rebase, a kiedy merge? 
#### Jak dopisać zmiany do ostatniego commita? 
#### Jak połączyć 5 ostatnich commitów w jeden?
#### Omów Git flow - Posklejaj pojęcia: (branch, develop, master, tag, feature, version, hotfix, release)

## OOP
#### Co to jest polimorfizm?
#### Co to jest dziedziczenie?
#### Po co stosować enkapsulację?
#### Omów znane Tobie wzorce projektowe i omów je
#### Dziedziczenie vs Kompozycja - czym się różni, kiedy się jakie stosuje?
#### Interfejs vs klasa abstrakcyjna
#### Omów zasady SOLID
#### Omów KISS

## ALGORYTMY
#### Problem diamentowy w JAVIE
#### Omów problem pięciu filozofów
#### Omów problem producenta i konsumenta
#### Napisz algorytm liczący silnię (bez rekurencji)
#### Napisz algorytm liczący kolejne elementy ciągu Fibonacciego
#### Sprawdź czy liczba jest potęgą 2

## SELENIUM i AUTOMATYZACJA
#### Omów jakie znasz rodzaje selektorów. 
#### Czym się różni XPATH od CSS?
#### Kiedy używać jakich selektorów?
#### Co znajdą poniższe selektory CSS: 
- div#content
- .img
- .img.first
- .img .first
- .img:first-child
- .img > div

## JavaScript / TypeScript ES6+
#### Czy w JS są klasy? 
#### Omów dziedziczenie przez prototypy w JS
#### na co wskazuje **this** ?
#### Co pojawi się na konsoli po wykonaniu poniższego kodu: 
```javascript
setTimeout(0, () => console.log("First"));
console.log("Second");
```
#### I dlaczego?

#### Jak zmienić kontekst wykonania w JavaScript?
#### Co to Promise's w JavaScript? Po co je stosować (zamiast callbacków)?
#### Co zwraca funkcja ze słowem kluczowym **async**? 

#### Co robi operator **await** wewnątrz funkcji asynchronicznej?

#### Czy znasz TypeScript?
#### Jakie korzyści przynosi stosowanie TypeScript'u w projekcie?
#### Co to jest Event Loop?
#### Czy JavaScript jest asynchroniczny?
#### Czy JavaScript jest jednowątkowy?
#### [ZADANIE] Napisz funkcję ```hello(name)``` zwracającą obietnicę (Promise), która po 1 sekundzie rozwiązuje się do wartości ```name```.
#### [ZADANIE] Za pomocą konsoli przeglądarki mając otwartą stronę wyników wyszukiwania z Google wypisz wszystkie znalezione linki.


# Teoria testowania
#### Dostajesz błąd zgłoszony na produkcji od użytkownika co z tym robisz? 
#### Wymień rodzaje dokumentacji w projekcie
#### Co powinien zawierać plan testów? 
#### Co powinien zawierać przypadek testowy? 
#### Jak tworzyć przypadki testowe?
#### Jak tworzyć przypadki testowe, kiedy nie ma zdefiniowanych wymagań? 
#### Co to są wymagania funkcjonalne? 
#### Co to są wymagania niefunkcjonelne (podaj przykłady)? 
#### Wymień rodzaje testów: 
#### Co to są testy jednostkowe, funkcjonalne, systemowe, akceptacyjne? 
#### Co to są testy regresyjne?
#### Omów metodologię TDD
#### Omów podejście BDD
#### Omów różnice pomiędzy testami czarnoskrzynkowymi, a białoskrzynkowymi
#### Omów cykl życia błędu
#### Czym się różni się defekt od błędu?
#### Co powinno zawierać zgłoszenie błędu? 
#### Po co stosować mock'owanie podczas testów? 


# Zarządzanie projektami
#### Co to jest SCRUM? Omów jego założenia.
#### Omów role w SCRUM'ie (Scrum master, Product owner, zespół, klient)
#### Wymień i omów zdarzenia w SCRUM'ie
#### Wyjaśnij proces tworzenia oprogramowania w SCRUMIE
#### Omów metodologię Waterfall

# SIECI
#### Omów protokół HTTPS: 
#### Po co sięgo stosuje?
#### Na czym polega komunikacja? Krok po kroku (w uproszczeniu).
#### Klucze publiczne i prywatne
#### Szyfrowanie asymetryczne i symetryczne
#### Z czego się składa adres IP?
#### Co to jest maska podsieci
#### Jak znając maskę podsieci i IP wyliczyć ilość dostępnych adresów w sieci?
#### Ile jest dostępnych adresów przy masce 0.0.0.0
#### Omów ogólnie czego dotyczy model OSI

# HTTP / REST
#### Czym jest SOAP?
#### Czym jest REST?
#### Jakie znasz metody HTTP? Do czego służy każda z nich?
#### Jak wygląda request i response HTTP?
#### Jaki jest główny podział statusów odpowiedzi HTTP?
#### Co oznaczają kody odpowiedzi 1xx, 2xx, 3xx, 4xx, 5xx
#### Konkretnie co oznaczają kody: 200, 201, 400, 404
#### Czym chararakteryzują się metody idempotentne? Które z metod HTTP w REST są idempotentne, a które nie?
#### Jakiej metody HTTP użyć gdy pobierasz zasób
#### Jakiej metody HTTP użyć gdy tworzysz zasób
#### Jakiej metody HTTP użyć gdy edytujesz cały zasób
#### Jakiej metody HTTP użyć gdy edytujesz jedno pole w zasobie
#### Czym są Headery i do czego się je stosuje? 
#### Jakie znasz Headery? Podaj przykłady.
#### Co to są ciasteczka? Do czego się je stosuje?
#### Co się dzieje pod spodem, kiedy użytkownik wpisze adres w przeglądarkę i kliknie enter -> 

# BEZPIECZEŃSTWO
#### Jakie znasz rodzaje ataków na serwisy WWW?
#### Co oznacza skrót CORS?
#### Czy Kod JS na stronie może wywołać zapytanie do innej domeny?
#### Co to jest Same Origin policy?
#### Czym się różni autoryzacja od autentykacji?
#### Co to jest OAuth2
#### Czy znasz OWASP? Co to jest?
#### Rozszyfruj skróty i krótko omów ataki: SQL Injection, XSS, XSRF, SSRF, XXE

# Bash
#### Jakie znasz skróty klawiszowe w IDE z którym pracujesz?
#### Omów działanie komend pod linuxem: 
- kill -9 0
- ls
- touch xd.dd
- cd ..
- cd .
- cat
- head
- tail
- ps aux | grep node
#### Jak wypisać 10 ostatnich linijek z pliku testowego?
#### Jak wypisać pierwszych 10 linijek z pliku?
#### Jak wyszukać w pierwszych 100 linijkach pliku xd.dd linii zawierających słowo ```lol``` ?
```bash
head -100 xd.dd | grep lol
```


## BAZY DANYCH
#### Jak działa LEFT JOIN? 
#### Co zwróci funkcja max z kolumny tekstowej? 
#### Jak zsumować płace wg. działów. Masz tablicę z listą pracowników z wynagrodzeniami i przypisanym działem.
#### JOIN vs FULL JOIN 
#### Jak można wyciągnąć tylko niektóre wyniki po GROUP BY ?\
#### Co to jest Primary key
#### Omów Unique index
#### Czym się różnią Clustered Index i Non Clustered index
#### Kiedy używać indeksów w bazie danych a kiedy nie powinno się?
#### Kiedy indeksy przyspieszają działanie bazy, a kiedy spowalniają?
#### Omów SQL: INNER JOIN, OUTER JOIN, HAVING, GROUP BY, ORDER BY
#### Jakie znasz funkcje agregujące? 
#### Omów co to (i po co) jest ACID?
#### Omów poziomy izolacji