Listy, tuple i funkcje
########################

.. contents::
    :depth: 1
    :local:

Pobierz *n* liczb
*******************

    **ZADANIE**: Pobierz od użytkownika *n* liczb i zapisz je w liście.
    Wydrukuj: elementy listy i ich indeksy, elementy w odwrotnej kolejności,
    posortowane elementy. Usuń z listy pierwsze wystąpienie elementu podanego
    przez użytkownika. Usuń z listy element o podanym indeksie.
    Podaj ilość wystąpień oraz indeks pierwszego wystąpienia podanego elementu.
    Wybierz z listy elementy od indeksu *i* do *j*.

    **POJĘCIA**: *tupla, lista, metoda*.

Wszystkie poniższe przykłady warto wykonać w konsoli Pythona.
Treść komunikatów w funkcjach ``print`` można skrócić.
Można również wpisywać kolejne polecenia do pliku i sukcesywanie go uruchomiać.

.. raw:: html

    <div class="code_no">Kod nr <script>var code_no = code_no || 1; document.write(code_no++);</script></div>

.. literalinclude:: 04_listy_01.py
    :linenos:

Jak to działa
===================

Funkcja ``input()`` pobiera dane wprowadzone przez użytkownika podobnie jak
jak ``raw_input()``, ale próbuje zinterpretować je jako kod Pythona.
Podane na wejściu liczby oddzielone przecinkami zostają spakowane jako
:term:`tupla` (krotka). Jest to uporządkowana sekwencja poindeksowanych danych,
przypominająca tablicę, której wartości nie można zmieniać. Zainicjowanie
tupli wartościami od razu w kodzie jest proste: ``tupla = (4, 3, 5)``.

Lista to również uporządkowane sekwencje indeksowanych danych, zazwyczaj
tego samego typu, które jednak możemy zmieniać.

.. note::

    W definicji tupli nawiasy są opcjonalne, można więc pisać tak: ``tupla = 3, 2, 5, 8.``

Dostęp do elementów tupli lub listy uzyskujemy podając nazwę i indeks, np. ``lista[0]``.
Elementy indeksowane są od 0 (zera!). Funkcja ``len()`` zwraca ilość elementów w tupli/liście.
Funkcja ``enumerate()`` zwraca obiekt zawierający indeksy i elementy sekwencji
(np. tupli lub listy) podanej jako atrybut. Funkcja ``reversed()`` zwraca
odwróconą sekwencję.

Lista ma wiele użytecznych metod: ``.append(x)`` – dodaje x do listy;
``.remove(x)`` – usuwa pierwszy x z listy;
``.insert(i, x)`` – wstawia x przed indeksem i;
``.count(x)`` – zwraca ilość wystąpień x;
``.index(x)`` – zwraca indeks pierwszego wystąpienia x;
``.pop()`` – usuwa i zwraca ostatni element listy.

Funkcja ``reversed(lista)`` zwraca kopię listy w odwróconym porządku,
natomiast ``sorted(lista)`` zwraca kopię listy posortowanej rosnąco.
Jeżeli chcemy trwale odwrócić lub posortować elementy listy stosujemy metody:
``.reverse()`` i ``.sort()``.

Z każdej sekwencji (napisu, tupli czy listy) możemy wydobywać fragmenty
dzięki notacji *slice* (wycinek). W najprostszym przypadku polega ona
na podaniu początkowego i końcowego (wyłącznie) indeksu elementów, które chcemy
wydobyć, np. ``lista[1:4]``.

Zadania dodatkowe
===================

    Utwórz w konsoli Pythona dowolną listę i przećwicz notację *slice*. Sprawdź działanie indeksów pustych
    i ujemnych, np. ``lista[2:], lista[:4], lista[-2], lista[-2:]``.
    Posortuj dowolną listę malejąco. Wskazówka: wykorzystaj metodę ``.sort(reverse=True)``.

Ciąg Fibonacciego
*********************

    **ZADANIE**: Wypisz ciąg Fibonacciego aż do *n*-tego wyrazu podanego przez użytkownika.
    Ciąg Fibonacciego to ciąg liczb naturalnych, którego każdy wyraz poza dwoma
    pierwszymi jest sumą dwóch wyrazów poprzednich. Początkowe wyrazy tego ciągu to: 0 1 1 2 3 5 8 13 21.

    **POJĘCIA**: *funkcja, zwracanie wartości, tupla, rozpakowanie tupli, przypisanie wielokrotne*.

.. raw:: html

    <div class="code_no">Kod nr <script>var code_no = code_no || 1; document.write(code_no++);</script></div>

.. literalinclude:: 04_funkcja_02.py
    :linenos:

Jak to działa
===================

Definicja funkcji w Pythonie polega na użyciu słowa kluczowego ``def``,
podaniu nazwy funkcji i w nawiasach okrągłych ewentualnej listy parametrów.
Definicję kończymy znakiem dwukropka, po którym wpisujemy w następnych liniach,
pamiętając o wcięciach, ciało funkcji. Funkcja może, ale nie musi zwracać wartości.
Jeżeli chcemy zwrócić jakąś wartość używamy polecenia return wartość.

Zapis ``a, b = pwyrazy`` jest przykładem rozpakowania tupli, tzn. zmienne *a* i *b*
przyjmują wartości kolejnych elementów tupli ``pwyrazy``. Zapis równoważny, w którym nie
definiujemy tupli tylko wprost podajemy wartości, to ``a, b = 0, 1``; ten sposób
przypisania wielokrotnego stosujemy w kodzie ``a, b = b, b+a``. Jak widać, ilość
zmiennych z lewej strony musi odpowiadać liczbie wartości rozpakowywanych z tupli
lub liczbie wartości podawanych wprost z prawej strony.

Zadania dodatkowe
===================

    Zmień funkcję ``fibonnacci()`` tak, aby zwracała wartość *n*-tego wyrazu. Wydrukuj tylko tę wartość w programie.
