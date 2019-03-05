# PYTANIA
#### Co to jest JVM?
Java Virtual Machine. Środowisko uruchomieniowe dla języka JAVA, możliwie do zainstalowania różnych systemach operacyjnych (umożliwia działania aplikacji JAVA na większości systemów
operacyjnych). Interpretuje JAVA Bytecode - język pośredni będący wynikiem kompilacji kodu JAVA.

Odpowiedniki dla C#:
- Bytecode -> MSIL
- JVM -> CLR

#### Co to jest Garbage Collector?
KRÓTKO: Garbage Collector (część środowiska JVM) - algorytm, który odpowiada za usuwanie
nieużywanych obiektów z pamięci.

W języku JAVA nie ma funkcji "zwolnienia pamięci" - bezpośrednio z poziomu języka.
Spowodowane jest to faktem, że łatwo tutaj popełnić błąd i doprowadzić do krytycznego błędu systemu
(np. gdy program odniesie się do adresu pamięci, gdzie nie ma nic albo co gorsza są dane innego
programu).
Po to jest Garbage Collector - część środowiska nad którą programista ma tylko pośrednią kontrolę.
Działa on tak, że co jakiś czas podczas działania programu zatrzymuje bieżący wątek i sprawdza,
które obiekty na stercie nie mają żadnej referencji w programie.
Jeśli nie ma referencji - usuwa obiekt zwalniając pamięć.

#### Czym różni się stos od sterty? 
- STOS - na nim przechowywane są typy proste, oraz referencje do obiektów na stercie.
- STERTA - obszar pamięci gdzie przechowywane są Obiekty i inne bardziej skomplikowane struktry
danych.

#### Jakie rzeczy są zapisywane na stercie, a jakie na stosie?
Sterta - obiekty, Stos - referencje do obiektów i typy proste.

#### Porównaj typy float/double/BigDecimal w JAVIE
Ogólnie typy danych: 
- Całkowite: byte (8bit) - short (16bit) - int (32bit) - long (64bit)
- Zmiennoprzecinkowe: float (32bit) - double (64bit)
- boolean (1bit) true-false
- char - (8-16bit UTF8)
- String
- BigDecimal - wielkie liczby zmiennoprzecinkowe.
- BigInteger - wielkie liczny całkowite


Odpowiadając na pytanie: Typy różnią się precyzją (float-double), a klasa BigDecimal jest
dedykowana do obliczeń finansowych.

##### Omów problemy związane z przeliczeniami wartości korzystając z ww. typów
Przy float - double będą problemy z zaokrąglaniem. BigDecimal zapewnia nad tym kontrolę.

#### Czym są Unboxing i autoboxing w JAVIE?
Boxing - pakowanie - odpakowanie obiektów np. Integer -> int.
Unboxing - odpakowanie typu obiektowego na odpowiadający mu typ prosty.
Autoboxing - automatyczne opakowywanie obiektów przez kompilator.

#### Omów typy: String, StringBuilder. 
String - łańcuch znaków. Jest obiektem Immutable (niezmienialnym).
Dlatego aby doawać do siebie wiele String'ów uzywamy klasy StringBuilder ze względu na wydajność.
W przypadku dodawania String'ów zwyczajnie tj. "str1" + "str2" + "str3".
Każda operacja kopiuje poprzedni string. Gdy jest bardzo długi ma to wpływ na wydajność i zajętość
pamięci. W ww. przykładzie jest skopiowany 2 razy.


#### Omów jakie znasz klasyfikatory dostępu w JAVIE (są 4)
Dotyczą pól / klas / metod
- public - dostęp publiczny
- protected - dostęp tylko z poziomu klas dziedziczących
- private - dostęp prywatny
- //BRAK// - dostęp z obrębu pakietu (namespace)

#### PORÓWNYWANIE OBIEKTÓW
#### Jak porównywane są obiekty w JAVIE, z jakich metod korzystają
Korzystają z .equals() i hashCode();

#### Różnica pomiędzy '==' i .equals()
'==' - porównuje referencję
- obj1.equals(obj2) porównuje zawartość obiektów

#### Do czego służy metoda hashCode() ?
Oblicza hashCode obiektu. Jest to liczba int.
Jeśli hashCode się różnią - obiekty nie są takie same
Jeśli hashCode są takie same - obiekty MOGĄ LECZ NIE MUSZĄ być identyczne

#### Omów interfejsy Comparable i Comparator.
Udostępniają metody pozwalające porównać obiekty.
Zwracają liczbę int -1 mniejszy // 0 równy // 1 większy
Comparable - udostępnia metodę obj1.compare(obj2) - Porównuje obiekty.

#### Pytanie: Skoro == porównuje *referencje* a nie wartości, to dlaczego w poniższym kodzie:
```java
"test" == "test" //taki kod zwrca true
"test" == new String("test") // A taki kod zwraca false?
new String("test") == new String("test") // I taki też zwraca false?
```
Kompilator optymalizuje kod podczas kompilacji zapisując jawnie utworzone Stringi w jednym obiekcie. Stąd pierwszy przykład zwraca true.


## KOLEKCJE
<img src="https://fresh2refresh.com/wp-content/uploads/2013/08/Java-Framework.png"/>

#### Czym różni się ArrayList od LinkedList?
Sposobem implementacji. ArayList przechowuje elementy w Arrayu (bardzo szybkie operacje wstawiania na końcu / początku i losowy dostęp, LinkedList w każdym elemencie posiada wskaźnik do następnego elementu, bardzo szybkie wstawianie na dowolną pozycję, powolny losowy dostęp do danych)

#### Czym różni się HashSet od TreeSet? 
- HashSet - nie gwarantuje kolejności wstawiania
- TreeSet - gwarantuje kolejność wstawiania
  
#### Wyjaśnij jak działa HashMap.

#### po co implementować metody **hashCode()** i **equals()** ?
Metody te służą do porównywania obiektów - a co za tym idzie ułatwiają i przyspieszają działania m.in. na kolekcjach.
  

## WYJĄTKI
#### Omów podstawowe klasy wyjątków i ich hierarchię
<img src="https://www.tutorialspoint.com/java/images/exceptions1.jpg">

#### Czym różni się **Exception** od **Error**? 
Error zwykle nie zależy od programisty.

#### Czym różni się **RuntimeException** od **IOException**? 
Pierwsze jest unchecked, drugie checked.

#### Co to są wyjątki "checked" i "unchecked" ?
- checked - wyjątki sprawdzane w trakcie kompilacji. Program się nie skompiluje bez ich obsłużenia lub zadeklarowania.
- unchecked - nie są sprawdzane w trakcie kompilacji.

#### TYPY GENERYCZNE
#### Co to są typy generyczne? Omów je
https://www.tutorialspoint.com/java/java_generics.htm

#### WĄTKI
#### Co to są wątki? 
- Obsługiwane przez system operacyjny.
- Reprezentuje zasoby procesora do równoległego wykonywania obliczeń.
- Jeden wątek - maks. jeden rdzeń procesora.
- Jednocześnie jeden rdzeń może obsługiwać wiele wątków (sytem operacyjny przydziela ułąmek czasu
procesora per każdy wątek)
- Wszystkie wątki dzielą jedną pamięć w ramach tego samego procesu. Dlatego są łatwiejsze/szybsze
do utworzenia / zamknięcia.

#### Co to są procesy? 
Obsługiwane przez system operacyjny.
- Każdy proces posiada conajmniej jeden wątek reprezentujący zasoby procesora i mający dostęp do
zasobów procesu.
- Proces reprezentuje zasoby procesora, pamięci i innych zasobówo zarezerwowane dla uruchomionej
instancji aplikacji.
- Proces może posiadać podprocesy. Każdy podproces ma swoje zasoby. Proces rodzic ma dostęp do
zasobów wszystkich swoich podprocesów.
#### Jak utworzyć wątek? Jak go zatrzymać? 
https://winterbe.com/posts/2015/04/07/java8-concurrency-tutorial-thread-executor-examples/

#### Jak synchronizować wątki? Omów słowo kluczowe **synchronized**
https://winterbe.com/posts/2015/04/30/java8-concurrency-tutorial-synchronized-locks-examples/

#### Jak działają metody **wait()**, **notify()**, **notifyAll()**
- wait() - zatrzymuje wątek w danym miejscu (celem synchronizacji)
- notify() - uruchamia zatrzymany wątek.
- notifyAll() - uruchamia wszystkie zatrzymane wątki
  
## OOP
#### Co to jest polimorfizm?
Mechanizmy umożliwiające programiście używać ogólnych nie zdefiniowanych w momencie pisania metod / klas, których wybór nastąpi później w trakcie kompilacji / uruchomienia programu.  

#### Co to jest dziedziczenie?
Rozszerzanie funkcjonalności klas poprzez ich rozszerzanie / nadpisanie.

#### Po co stosować enkapsulację?
Aby ograniczyć powiązania w aplikacji do minimum. Ułatwia to późniejsze utrzymanie kodu.

#### Omów znane Tobie wzorce projektowe i omów je
https://refactoring.guru/design-patterns/catalog

**PRZYKŁADY:**
- KREACYJNE (creational)
  - Singleton
  - Factory method
  - Abstract factory
  - Builder
- STRUKTURALNE (structural)
  - Facade
  - Proxy
  - Decorator
  - Composite
- CZYNNOŚCIOWE (behavioral)
  - Observer
  - Visitor
  - Iterator
  - Strategy

#### Dziedziczenie vs Kompozycja - czym się różni, kiedy się jakie stosuje? 
- Dziedziczenie - patrz wyżej.
- Kompozycja - dodanie funkcjonalności do klasy wstawiając do niej pole innej klasy.
#### Interfejs vs klasa abstrakcyjna
- Interfejs umożliwia wielodziedziczenie.
- Klasa abstrakcyjna stanowi zwykle szablon dla danej klasy obiektów.
- Interfejs zwykle stanowi kontrakt do zaimplementowania.

#### Omów zasady SOLID
https://hackernoon.com/solid-principles-made-easy-67b1246bcdf
- **S**ingle Responsibility Principle - Każda klasa powinna posiadać dokładnie jedną odpowiedzialność i robić tę jedną rzecz najlepiej jak się da. Nigdy nie powinien istnieć więcej niż jeden powód do modyfikacji klasy.
- **O**pen-Closed Principle - Projekt powinien być otwarty na rozszerzanie i zamknięty na modyfikacje / rozbudowę. Po polsku zamiast modyfikować klasę raczej powinniśmy ją rozszerzać, jednocześnie bazując na abstrakcji zamiast na konkretnych implementacjach.
- **L**iskov Substitution Principle - Jeśli w danym miejscu programu oczekujemy jakiegośkonkretnego typu obiektu (np. Animal), to powinniśmy mieć możliwość użycia tam dowolnego jego podtypu np. Cat, Mouse itp.
- **I**nterface Segregation Principle - Krótko: Użytkownik nie powinien byćzmuszony do implementowania metod których nie używa. Lepiej więcej małych niż jeden duży. Dlatego należy tworzyć proste i krótkie interfejsy przeznaczone do jednego celu (SRP). Ograniczy to powstawanie niepotzebnych zależności w projekcie.
- **D**ependency Inversion Principle - Opieraj sięna abstrakcjach, zamiast konkretnych implementacjach. Moduły wysokopoziomowe NIE POWINNY zależeć od modułów niskopoziomowych. Przekłądając na polski: Interfejsy powinny stać wyżej w hierarchii niż ich konkretne implementacje, które mogą się zmieniać. Ten wzorzec jest powszechnie implementowany przez kontenery Dependency Injection, gdzie w kodzie używa się nazw interfejsów, a za dostarczenie konkretnych instancji obiektów odpowiada centralnie kontener DI.

#### Omów KISS
**Keep It Simple, Stupid!**
KOD POWINIEN BYĆ:
- czytelny i zrozumiały (nie buduj hack'ów)
- możliwie najkrótszy (wszystkie nieużywane funkcje - OUT )
- Jak coś nie jest konieczne w kodzie to tego ma tam nie być! 80% czasu przy programowaniu to czytanie (nie pisanie) kodu!. Zadbaj, by było go jak najmniej.
  
  
## ALGORYTMY
#### Problem diamentowy w JAVIE
Problem powstał w JAVA 8 i dotyczy wielodziedziczenia. W końcu interfejcy mogą posiadać domyślne implementacje. Jednocześnie można zaimplementować kilka interfejsów i przypadkowo podziedziczyć kilka implementacji funkcji o tej samej nazwie i parametrach np. boo(). Którą zatem wybrać? W implementacji trzeba zaimplementować metodę z odpowiedniego interfejsu np. Interface1.boo()

#### Omów problem pięciu filozofów
#### Omów problem producenta i konsumenta
#### Napisz algorytm liczący silnię (bez rekurencji)
```javascript
function silnia(level) {
    if (level < 0) {
        throw new Error("Level should not be negative.")
    }
    
    if (level == 0) {
        return 1;
    }
    
    let actual = 1;
    for (i = 2; i <= level; i++) {
        actual = actual * i;
    }
    
    return actual;
}
```

#### Napisz algorytm liczący kolejne elementy ciągu Fibonacciego
#### Sprawdź czy liczba jest potęgą 2

## SELENIUM i AUTOMATYZACJA
#### Omów jakie znasz rodzaje selektorów. 
#### Czym się różni XPATH od CSS? Co jest lepsze?
To zależy. 
- CSS - Selektory bardziej zwięzłe, bardziej zrozumiałe dla frontendowców. Nie wszystko da się zrobić w CSS, co da się w XPATH
- XPATH - daje największe możliwości

#### Kiedy używać jakich selektorów?
#### Co znajdą poniższe selektory CSS: 
  ##### div#content
  ##### .img
  ##### .img.first
  ##### .img .first
  ##### .img:first-child
  ##### .img > div

## JavaScript / TypeScript ES6+
#### Czy w JS są klasy
Tak i nie. Są przede wszystkim obiekty. Dziedziczy się przez prototypy.
W ES6 doszła składnia definicji "klasy", która pod spodem niczym się nie różni od opierania się na prototypach.

#### Omów dziedziczenie przez prototypy w JS
#### na co wskazuje **this** ?
this -> Aktualny kontekst wykonania. This jest przypisywany np. podczas tworzenia nowego obiektu poprzez operator new.


### Promisy, callbacki
#### Co pojawi się na konsoli po wykonaniu tego:
```javascript
setTimeout(0, () => console.log("First"))
console.log("Second");
```
> Second
> First

#### Co to są obiecanki (Promises) w JavaScript? Po co je stosować (zamiast callbacków)?
#### Jaki ma związek z **Promises**

#### Co zwraca funkcja ze słowem kluczowym **async**? 
#### Co robi operator **await** wewnątrz funkcji?

#### Po co kompilować kod JS? Jakie znasz kompilatory?
#### Co to jest Event Loop?
#### Czy JavaScript jest asynchroniczny?
#### Czy JavaScript jest jednowątkowy?
#### Co się dzieje w Event Loop kiedy wykonamy taki kod
```javascript 
setTimeout(0, () => console.log("First"))
```
#### [ZADANIE] Za pomocą konsoli przeglądarki mając otwartą stronę wyników wyszukiwania z Google wypisz wszystkie znalezione linki.
```javascript
const elements = Array.from(document.querySelectorAll(".r > a:first-child"))
elements.forEach(link => console.log(link.href))
```

## Teoria testowania
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


## Zarządzanie projektami
#### Co to jest SCRUM? Omów jego założenia.
#### Omów role w SCRUM'ie (Scrum master, Product owner, zespół, klient)
#### Omów zdarzenia w SCRUM'ie
#### Wyjaśnij proces tworzenia oprogramowania w SCRUMIE
#### Omów metodologię Waterfall

## SIECI
#### Omów protokół HTTPS: 
#### Po co sięgo stosuje?
#### Na czym polega komunikacja? Krok po kroku.
#### Klucze publiczne i prywatne
#### Szyfrowanie asymetryczne i symetryczne
#### Z czego się składa adres IP?
#### Co to jest maska podsieci
#### Jak znając maskę podsieci i IP wyliczyć ilość dostępnych adresów w sieci?
#### Ile jest dostępnych adresów przy masce 0.0.0.0
#### Omów ogólnie czego dotyczy model OSI

#### HTTP / REST
#### Czym jest SOAP?
#### Czym jest REST?
#### Jakie znasz metody HTTP? Do czego służy każda z nich?
#### Jak wygląda request i response HTTP?
#### Jaki jest główny podział statusów odpowiedzi HTTP?
#### Co oznaczają kody odpowiedzi 1xx, 2xx, 3xx, 4xx, 5xx
#### Co oznacza kod: 200, 201, 400, 404
#### Czym chararakteryzują się metody idempotentne? Które są idempotentne, a które nie?
#### Jakiej metody HTTP użyć gdy pobierasz zasób
#### Jakiej metody HTTP użyć gdy tworzysz zasób
#### Jakiej metody HTTP użyć gdy edytujesz cały zasób
#### Jakiej metody HTTP użyć gdy edytujesz jedno pole w zasobie
#### Czym są Headery i do czego się je stosuje? 
#### Jakie znasz Headery? Podaj przykłady.
#### Co to są ciasteczka? Do czego się je stosuje?


## BEZPIECZEŃSTWO
#### Jakie znasz rodzaje ataków na serwisy WWW?
#### Co oznacza skrót CORS?
#### Czy Kod JS na stronie może wywołać zapytanie do innej domeny?
#### Co to jest Same Origin policy?
#### Czym się różni autoryzacja od autentykacji?
#### Co to jest OAuth2
#### Czy znasz OWASP? Co to jest?
#### Rozszyfruj skróty i krótko omów ataki: SQL Injection, XSS, XSRF, SSRF, XXE

## Inne
#### Jakie znasz skróty klawiszowe w IDE z którym pracujesz?
#### Omów działanie komend pod linuxem: 
  ##### kill -9 0
  ##### ls
  ##### touch xd.dd
  ##### cd ..
  ##### cd .
  ##### cat
  ##### head
  ##### tail
  ##### ps aux | grep node
#### Jak wypisać 10 ostatnich linijek z pliku testowego?
#### Jak wypisać pierwszych 10 linijek z pliku?
#### Jak wyszukać w pierwszych 100 linijkach pliku xd.dd linii zawierających słowo ```lol``` ?


## BAZY DANYCH
#### Co to jest Primary key
#### Omów Unique index
#### Czym się różnią Clustered Index i Non Clustered index
#### Kiedy używać indeksów w bazie danych a kiedy nie powinno się?
#### Kiedy indeksy przyspieszają działanie bazy, a kiedy spowalniają?
#### Omów SQL: INNER JOIN, OUTER JOIN, HAVING, GROUP BY, ORDER BY
#### Jakie znasz funkcje agregujące? 
#### Omów co to (i po co) jest ACID?
#### Omów poziomy izolacji


## ZASOBY ZEWNĘTRZNE:
http://toolsqa.com - Baza wiedzy o selenium
https://learncodethehardway.org/unix/bash_cheat_sheet.pdf - BASH Cheatsheet

### JAVA 8
https://www.geeksforgeeks.org/functional-interfaces-java/
https://winterbe.com/posts/2014/07/31/java8-stream-tutorial-examples/
https://www.baeldung.com/java-optional

# CLEAN CODE W PIGUŁCE
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

