# Formaty plików:

|  Format  |       narzędzia        |  dodatkowo (warto znać co najmniej na poziomie "z czym to się je")   |
|----------|------------------------|----------------------------------------------------------------------|
| CSV      | cut, column, grep, awk | TSV, escape'owanie (\" vs "")                                        |
| JSON     | jq                     | mongodb, bson                                                        |
| XML      | xmllint, xmlstarlet    | DTD, XSD, XSLT, namespaces, SOAP                                     |
| YAML     |                        | dlaczego yaml jest zły: https://stackoverflow.com/a/21699210/7687388 |
| TOML     |                        |                                                                      |
| Markdown |                        |                                                                      |

- dla każdego formatu ogarnąć formatowanie i walidację (pomijając może yaml i toml)

# Podstawy basha

- grep (-r, -l, -e), awk, cut (-d, -f), cat, ls (-l, -h, -s, -Sr, -Tr), find (-name, -mindepth/maxdepth -type, -mtime, -exec, -delete), xargs (-n), df (-h), du (-shc), less (wiele plików, -S (word wrap) -i (case in/sensitive, F (live fetch)), time, watch, htop, ps (aux), kill (sygnały! wystarczy pobieżnie wiedzieć jakie są i wiedzieć co robi -9 (SIGKILL))
- ssh (klucz publiczny / klucz prywatny, agent forwarding)
- git: https://www.gitbook.com/; projekt na githubie, minimum: clone, commit, branch, push, pull, merge, log, wypadałoby rebase

# Architektura:

- wzorce projektowe:
  - builder
  - factory
  - singleton
  - adapter
  - decorator
  - facade
  - chain of responsibility
  - command
  - null object
  - strategy
  - template method

# Randomowe słowa kluczowe które warto rozumieć

- dependency injection
- SOLID
- KISS, YAGNI (te dwie załatwiają moim zdaniem cały solid i całe wzorce projektowe ;])


# Programowanie:
- low level:
  - wskaźnik, referencja, różnica
  - przekazywanie przez wartość, przez wskaźnik/referencję, move
  - const
  - stos vs sterta
  - linkowanie statyczne vs dynamiczne (dll)
  - kompilacja vs interpretacja
  - byte code / virtual machine (c#, java)
  - garbage collector - co to jest jak to działa, jakie ma strategie (wystarczy pobieżnie)
  - jaka jest różnica między tablicą jedno- a dwuwymiarową. Jak może być ułożona w pamięci tablica dwuwymiarowa? Jak efektywnie się iterować po tablicy 2d?
- object oriented:
  - napisz dowolną klasę, bez dziedziczenia, ale z jakimiś polami i metodami. Potem zaimplementuj to w c, czyli języku bez klas. Stwórz kilka instancji (w c)
  - zrozum jak dokładnie działają metody wirtualne
  - różnica pomiędzy typem statycznym a dynamicznym
  - po co w ogóle stosować dziedziczenie? Jaka jest alternatywa i kiedy ta alternatywa nie wystarcza? (słowo-klucz na p)
  - override vs overload
  - klasa abstrakcyjna vs interfejs
  - problem wielokrotnego dziedziczenia
  - dlaczego interfejsy z domyślnymi metodamy (coś pomiędzy klasą abstrakcyjną a interfejsem), czyli praktycznie traity, nie są zbyt problematyczne?
- programowanie funkcyjne
  - spróbuj napisać funkcję która jako argument przyjmuje funkcję
  - używaj lambd (funkcji anonimowych)
  - co to jest monada (uwaga, to jest trudne, chociaż w praktyce wcale nie jest takie straszne)
  - co to jest partial application
- templates:
  - co to jest, czym się różnią templates w c++, c# (generics), rust
- Rust:
  - ownership, borrowing, life time
  - rust book
  - algebraiczne typy danych
  - dlaczego const w c++ jest gówniany w porównaniu do mut w ruście (i nie tylko dlatego, że w ruście jest const by default ;))
- inne:
  - typowanie mocne / słabe, dynamiczne / statyczne. Co ma jakie zalety a jakie wady?

# Algorytmy i struktury danych:
- jak działa hashmapa? Co to jest hash. Do czego służy, jakie musi mieć właściwości?
- co to jest złożoność obliczeniowa? Notacja dużego O

# Testowanie:
- testy jednostkowe, integracyjne, akceptacyjne, wydajnościowe, black box, end-to-end
- mockowanie / stubowanie, po co to (podpowiedź: jak napisać test, gdy twój kod wykonuje zapytanie po http albo np. jak przetestować kod który robi booka)
- CI, CD (wystarczy żebyś wiedział co to)

# Programowanie wielowątkowe / równoległe
- to jest dość zaawansowane. Na początek wystarczy bardzo pobieżna wiedza: co to jest wątek, jakie są główne problemy (np. dwa wątki zapisują jednocześnie do zmiennej), jak uruchomić / zabić wątek
- później: jak sobie radzić z problemami wielowątkowości (mutex, semaphore, interlocked), join, co to jest threadpool
- dlaczego w ruście programanie wielowątkowe jest bajecznie fajne?

# Edycja tekstu:
- polecam sublime lub visual studio code
- ogarniaj skróty jak (windows/linux - na macu są inne): shift + strzałki, ctrl + strzałki, shift + ctrl + strzałki, [ctrl]+[shift]+home, [ctrl]+[shift]+end, delete / insert, ctrl + d (zaznaczanie tego samego słowa), ctrl + f, ctrl + h (znajdź i zamień), regexy, ctrl + [-] \(wróc do poprzedniego miejsca, czasem w niektórych edytorach jest inaczej a ctrl - zmniejsza tekst, polecam zmienić keybindings w tym wypadku)
- terminal - ogarnij terminator (dzielenie okna ctrl + o/e, alt + strzałki), ctrl+k do kasowania słowa, ctrl+r (szukanie w historii), ogarnij kopiowanie i wklejanie w terminalu (skrótami, nie myszką, chociaż zaznaczać i tak trzeba myszką...)
- ogarnij edytor tekstu w konsoli:
  - vim - wystraczy tyle, żebyś wiedział, jak z niego wyjść ;D Ale nic nie zaszkodzi, jeśli przez tydzień będziesz używał wyłącznie vima, a nuż ci przypadnie do gustu?
  - nano - bardzo prosty, bardzo przydatny, wszędzie obecny
  - emacs - wystarczy, żebyś wiedział, że jest

# Zadania:

Wszystkie zadania wykonuj na linuksie, a projekty przechowuj w gicie. To "sztuczna" wiedza, ale w ten sposób napotkasz ogrom "codziennych" problemów i zdobędziesz bardzo dużo wiedzy.

Staraj się nic nie robić ręcznie. Refactor (np. zmienienie nazwy zmiennej której używasz w 20 miejscach) staraj się robić automatycznie, np. używając regexów. Postaraj się dodawać testy unitowe do swoich rozwiązań

- napisz prosty program w assemblerze. To moze byc chocby wyswietlenie hello world albo np. jakas prosta animacja w konsoli (np. pojawiajacy sie tekst literka po literce)
- stworz program ktory bedzie deserializowal kazdy z wymienionych wyżej typów (nie musisz sam pisać deserializera, użyj gotowych libek)
- napisz w haskellu: quicksort, drzewo, inne szkolne programy
- zaimplementuj w dowolnym języku (lub w dowolnym i w haskellu): listę jedno- i dwukierunkową, stos, kolejkę, drzewo (+ algorytmy bfs, dfs), kopiec, kolejkę priorytetową (wystarczy najprostsza); zaimplementuj quicksort, bubblesort, mergesort, selection sort, insertion sort, bucket sort. Zaimplementuj jakiś ciekawy algorytm jak A* (np. napisz program który generuję mapę dwuwymiarową, tworzy na niej kilka przeszkód, potem wybiera sobie punkt startu i końca i szuka drogi, a całość rysuje w konsoli)
- napisz dowolny program (może być któryś z powyższych) z GUI np. w c#/wpf albo czymkolwiek innym
- zainstaluj prologa i napisz choćby najprostszy program w nim (następnie szybko odinstaluj, zapomnij i idź się alkoholizować)
- przekonaj się na własnej skórze jaka jest różncia między iterowaniem się po tablicy 2d kolumnami a wierszami (napisz jakiś banalny proram np. tablica 10000 x 10000 i na każdej komórce zrób jakąś operację typu mnożenie czy podniesienie do potęgi czy cokolwiek i zmierz czasy)
- napisz dowolny program w ruby. Niech ma przynajmniej jedną jakąś zależność (libkę). Alternatywnie możesz użyć pythona
- napisz dowolny frontend w js (np. w angularze, reactcie, vue). Wykorzystaj jakiś framework css, np. twitter bootstrap. Dowiedz się co to npm i dlaczego js to gówno.
- napisz swój własny webservice (możesz to połączyć z zadaniem wyżej, czyli piszesz backend który nasłuchuje i wystawia jakieś metody i frontend, który z tego korzysta)
