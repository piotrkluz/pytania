# Pytania na rozmowy kwalifikacyjne

Zamieszczam tutaj pytania z którymi się spotkałem na rozmowach kwalifikacyjnych i na które odpowiedzi warto znać. 
W przyszłości będą tu też odpowiedzi. 

# 1. PYTANIA
### JAVA 8
- Wyrażenie Lambda
- Functional interfaces https://www.geeksforgeeks.org/functional-interfaces-java/
- Streams API https://winterbe.com/posts/2014/07/31/java8-stream-tutorial-examples/
- Optional https://www.baeldung.com/java-optional

## JAVA
- Co to jest JVM?
- Co to jest Garbage Collector? 
- Czym różni się stos od sterty? 
- Jakie rzeczy są zapisywane na stercie, a jakie na stosie?
- Porównaj typy float/double/BigDecimal w JAVIE
  - Omów problemy związane z przeliczeniami wartości korzystając z ww. typów
- Czym są Unboxing i autoboxing w JAVIE?
- Omów typy: String, StringBuilder. 
  - Czemu do konkatenacji stringów używa się StringBuilder'a ?
#### PORÓWNYWANIE OBIEKTÓW
- Jak porównywane są obiekty w JAVIE, z jakich metod korzystają
- Różnica pomiędzy '==' i .equals()
- Do czego służy metoda hashCode() ?
- Omów interfejsy Comparable i Comparator.
- Pytanie: Skoro == porównuje *referencje* a nie wartości, to dlaczego:
```java
"test" == "test" //taki kod zwrca true
"test" == new String("test") // A taki kod zwraca false?
new String("test") == new String("test") // I taki też zwraca false?

//WTF? 
```

<details><summary>Template</summary>
  ...
</details>


#### KOLEKCJE
<details><summary>Omów kolekcje w JAVIE. Podstawowe interfejsy i ich implementacje</summary>
  ##### Podstawowy podział:
              Collection                Map
         /     /    \      \            |
        /      /      \     \           |
     Set    List    Queue  Dequeue   SortedMap
     /
    /
 SortedSet 
  
  
  ##### Implementacje: 
  https://fresh2refresh.com/wp-content/uploads/2013/08/Java-Framework.png
</details>
<details><summary>Czym różni się ArrayList od LinkedList?</summary>
  Sposobem implementacji. ArayList przechowuje elementy w Arrayu (bardzo szybkie operacje wstawiania na końcu / początku i losowy dostęp, LinkedList w każdym elemencie posiada wskaźnik do następnego elementu, bardzo szybkie wstawianie na dowolną pozycję, powolny losowy dostęp do danych)
</details>
<details><summary>Czym różni się HashSet od TreeSet? </summary>
  HashSet - nie gwarantuje kolejności wstawiania
  TreeSet - gwarantuje kolejność wstawiania
</details>
<details><summary>Wyjaśnij jak działa HashMap.</summary>
  ...
</details>
<details><summary>po co implementować metody **hashCode()** i **equals()** ?</summary>
  - Metody te służą do porównywania obiektów - a co za tym idzie ułatwiają i przyspieszają działania m.in. na kolekcjach.
</details>


#### WYJĄTKI
<details><summary>Omów podstawowe klasy wyjątków i ich hierarchię</summary>
  ...
</details>
<details><summary>Czym różni się **Exception** od **Error**? </summary>
  ...
</details>
<details><summary>Czym różni się **RuntimeException** od **IOException**? </summary>
  ...
</details>
<details><summary>Co to są wyjątki "checked" i "unchecked" ?</summary>
  ...
</details>

#### TYPY GENERYCZNE
- Co to są typy generyczne? Omów je
#### WĄTKI
- Co to są wątki? 
- Co to są procesy? 
- Jak utworzyć wątek? Jak go zatrzymać? 
- Jak synchronizować wątki?
- omów słowo kluczowe **synchronized**
- Jak działają metody **wait()**, **notify()**, **notifyAll()**
  
## OOP
- Co to jest polimorfizm?
- Co to jest dziedziczenie?
- Po co stosować enkapsulację?
- Omów jakie znasz klasyfikatory dostępu w JAVIE (są 4)
- 
- Jakie znasz wzorce projektowe? 
  - Omów znane Tobie wzorce projektowe i omów je
  - Przykłady wzorców (lista niekompletna):
    - Builder, Factory method, Abstract factory, Prototype
    - Dekorator, Obserwator, Proxy
    - PageObject, PageFactory, Fluent Interface, MVC
- Dziedziczenie vs Kompozycja - czym się różni, kiedy się jakie stosuje? 
- Omów zasady SOLID
- Omów DRY, KISS
  
  
## ALGORYTMY
- Omów problem pięciu filozofów
- Omów problem producenta i konsumenta
- Napisz algorytm liczący silnię (bez rekurencji)
- Napisz algorytm liczący kolejne elementy ciągu Fibonacciego
- Sprawdź czy liczba jest potęgą 2

## SELENIUM i AUTOMATYZACJA
- Omów jakie znasz rodzaje selektorów. 
- Czym sięróżni XPATH od CSS? Co jest lepsze?
- Kiedy używać jakich selektorów?
- Co znajdą poniższe selektory CSS: 
  - div#content
  - .img
  - .img.first
  - .img .first
  - .img:first-child
  - .img > div  

## JavaScript ES6+, ESNext
- Omów dziedziczenie przez prototypy w JS
- na co wskazuje **this** ?
### Arrays
- 

### Promisy, callbacki
- Co pojawi się na konsoli po wykonaniu tego:
```
setTimeout(0, () => console.log("First"))
console.log("Second");
```
- Co to są obiecanki (Promises) w JavaScript? 
  - Po co je stosować (zamiast callbacków)?
- Jak działa API **async-await** w JavaScript? 
  - Jaki ma związek z **Promises**
  - Co zwraca funkcja ze słowem kluczowym **async**? 
  - Co robi operator **await** wewnątrz funkcji?
- Po co kompilować kod JS?
  - Jakie znasz kompilatory?
- Co to jest Event Loop?
  - Czy JavaScript jest asynchroniczny?
  - Czy JavaScript jest jednowątkowy?
  - Co się dzieje w Event Loop kiedy wykonamy ```setTimeout(0, () => console.log("First"))``` ?
- [ZADANIE] Za pomocą konsoli przeglądarki mając otwartą stronę wyników wyszukiwania z Google wypisz wszystkie znalezione linki.

## Teoria testowania
- Wymień rodzaje dokumentacji w projekcie
- Co powinien zawierać plan testów? 
- Co powinien zawierać przypadek testowy? 
- Jak tworzyć przypadki testowe?
- Jak tworzyć przypadki testowe, kiedy nie ma zdefiniowanych wymagań? 
- Co to są wymagania funkcjonalne? 
- Co to są wymagania niefunkcjonelne (podaj przykłady)? 
- Wymień rodzaje testów: 
  - Ze względu na typy i poziomy testów. 
- Co to są testy jednostkowe, funkcjonalne, systemowe, akceptacyjne? 
- Co to są testy regresyjne? 
- Co to sątesty jednostkowe? 
- Omów metodologię TDD
- Omów podejście BDD
- Omów różnice pomiędzy testami czarnoskrzynkowymi, a białoskrzynkowymi
- Omów cykl życia błędu
- Czym się różni się defekt od błędu?
- Co powinno zawierać zgłoszenie błędu? 
- Po co stosować mock'owanie podczas testów? 


## Zarządzanie projektami
- Co to jest SCRUM? Omów jego założenia.
- Omów role w SCRUM'ie (Scrum master, Product owner, zespół, klient)
- Omów zdarzenia w SCRUM'ie
- Wyjaśnij proces tworzenia oprogramowania w SCRUMIE
- Omów metodologię Waterfall

## SIECI i HTTP
#### SIECI
- Omów protokół HTTPS: 
  - Po co sięgo stosuje?
  - Na czym polega komunikacja? Krok po kroku.
  - Klucze publiczne i prywatne
  - Szyfrowanie asymetryczne i symetryczne
    - Kiedy jakie jest wykorzystywane
    - Jakie są wady i zalety każdego z nich
- Z czego się składa adres IP?
- Co to jest maska podsieci
- Jak znając maskę podsieci i IP wyliczyć ilość dostępnych adresów w sieci?
- Ile jest dostępnych adresów przy masce 0.0.0.0
- Omów ogólnie czego dotyczy model OSI

#### HTTP / REST
- Czym jest SOAP?
- Czym jest REST?
- Jakie znasz metody HTTP?
  - Do czego służy każda z nich?
- Jak wygląda request i response HTTP?
- Jaki jest główny podział statusów odpowiedzi HTTP?
  - Co oznaczają kody 1xx, 2xx, 3xx, 4xx, 5xx
- Jakie znasz statusy odpowiedzi? Wymień kilka (np. 200, 201, 301, 400, 404, 500)
- Czym chararakteryzują się metody idempotentne? Które są idempotentne, a które nie?
- Jakiej metody HTTP użyć gdy: 
  - Pobierasz zasób
  - Tworzysz zasób
  - Edytujesz cały zasób
  - Edytujesz jedno pole w zasobie
- Czym są Headery i do czego się je stosuje? 
- Jakie znasz Headery? 
- Co to są ciasteczka?


## BEZPIECZEŃSTWO
- Jakie znasz rodzaje ataków na serwisy WWW?
- Co oznacza skrót CORS?
  - Czy Kod JS na stronie może wywołać zapytanie do innej domeny?
  - Czym jest Same Origin policy?
- Czym się różni autoryzacja od autentykacji?
- Co to jest OAuth2
- Czy znasz OWASP?
- Na czym polegają ataki i jak się przed nimi zabezpieczać:
  - SQL Injection
  - XSS
  - XSRF
  - SSRF
  - XXE

## Inne
- Jakie znasz skróty klawiszowe w IDE z którym pracujesz?
- Omów działanie komend pod linuxem: 
  - kill -9 0
  - ls
  - touch xd.dd
  - cd ..
  - cd .
  - cat
  - head
  - tail
  - ps aux | grep node
- Jak wypisać 10 ostatnich linijek z pliku testowego?
- Jak wypisać pierwszych 10 linijek z pliku?
- Jak wyszukać w pierwszych 100 linijkach pliku xd.dd linii zawierających słowo ```lol``` ?


## BAZY DANYCH
- Omów pojęcia: 
  - Primary key
  - Unique index
  - Clustered Index i Non Clustered index
- Kiedy używać indeksów w bazie danych a kiedy nie powinno się?
  - Kiedy indeksy przyspieszają działanie bazy, a kiedy spowalniają?
- Omów SQL: 
  - INNER JOIN
  - OUTER JOIN
  - HAVING
  - GROUP BY
  - ORDER BY
- Jakie znasz funkcje agregujące? 
- Omów co to (i po co) jest ACID?
- Omów poziomy izolacji


# 2. OPRACOWANIA

##Frameworki JAVA: 
- Wiremock http://wiremock.org/ - Mockowanie API.
- Mockito https://site.mockito.org/ - Mockowanie Unit tests
- TestNG, JUnit5 - uruchamianie testów
- Cucumber - uruchamianie testów BDD
- RESTAssured - Testowanie API REST, fluent interface.

## LINKI:
http://toolsqa.com - Baza wiedzy o selenium




## CLEAN CODE W PIGUŁCE
1. Znaczące nazwy:
  - nazwy funkcji/zmiennych/klas przedstawiające intencję
  - unikanie dezinformacji
  - wymawialne nazwy
  - nazwy łatwe do wyszukania
2. Funkcje:
  - możliwie jak najkrótsze (max 20 wierszy)
  - najlepiej bez lub jedno argumentowe
  - pojedyncza odpowiedzialność
  - jeden poziom abstrakcji
  - bloki try{} catch{} w osobnej funkcji
  
3. Komentarze:
  - Im mniej tym lepiej. (Nazwy funkcji powinny mówić co robi kod)
  - dozwolone komentarze:
    - komentarz z rodzajem licencji
    - TODO
    - komentarze ostrzegające
  - nie komentujmy na siłę
  - nie zostawiajmy za komentowanych fragmentów kodu
4. Formatowanie:
  - małe pliki (klasy) są lepsze niż duże
  - u góry klas najogólniejsze metody poniżej coraz bardziej szczegółowe
  - pionowe odstępy między segmentami kodu
  - funkcja wywoływana (zaraz) pod funkcją wywołującą
  - wiersze maksymalnie 120 znakowe
  - spacje wokół operatorów
  - wcięcia poziome oddzielające bloki kodu
  - spójne formatowanie w całym zespole
5. Obiekty i struktury danych:
  - NIE dodawać na ślepo setterów i getterów
  - przestrzegajmy prawa Demeter
  - unikanie „wraków pociągów”, czyli kodu postaci: a.getB().getC().getD().getZ().doSth();
  - unikać hybryd (trochę obiekt, trochę struktura danych)
6. Obsługa błędów:
  - wyjątki zamiast kodów powrotu
  - NIE zwracamy null
  - NIE przekazujemy null
  - tworzenie komunikatów błędów z informacją o typie awarii i co miało się wykonać oraz przesłanie ich w wyjątku
7. Granice:
  - separacja obcego kodu od naszego
  - testy „uczące” obcego kodu
  - wzorzec Adapter
8. Testy jednostkowe:
  - kod testów jest tak samo ważny jak kod produkcyjny
  - czytelność testów
  - w testach nie jest tak istotna wydajność
  - jedna asercja na test – niekoniecznie
  - jedna koncepcja na test
  - testy powinny spełniać zasady F.I.R.S.T.
    - Fast – szybkie
    - Independent – niezależne
    - Repeatable – powtarzalne
    - Self-Validating – samo kontrolujące się
    - Timely – o czasie
9. Klasy:
  - organizacja klas (od góry):
    - publiczne stałe statyczne
    - prywatne zmienne statyczne
    - prywatne zmienne instancyjne
    - publiczne metody
    - prywatne metody



## BAZY DANYCH
//TODO
**primary key** - 
**unique index** - 
**Clustered index** - 
**Non clustered index** - 
**Kiedy używać indeksów, a kiedy nie powinno się** - 
<style>
  details > summary {
    font-weight: bold;
}
</style>

