[Ćwiczenie 1.1.txt](https://github.com/user-attachments/files/33023654/Cwiczenie.1.1.txt)
Ćwiczenie 1.1
Typ	Przykładowe wartości	Dozwolone operacje	Rozmiar w pamięci
bool	true, false             AND, OR, NOT             1 bajt		
int32	-10, 0, 25, 2147483647  +, -, *, /, %            4 bajty		
char	'A', 'b', '7'           przypisanie,porównywanie 1 bajt

Ćwiczenie 1.2
a) typowo       W językach statycznie typowanych zmienna x ma typ int, więc nie można przypisać jej tekstu.
b) używany      W językach dynamicznie typowanych zmienna może zmienić typ podczas działania programu.
c) typowo       auto pozwala kompilatorowi automatycznie określić typ. 3.14 jest typu double.
d) używany      W JavaScripcie let pozwala przypisać zmiennej wartość innego typu, więc kod działa poprawnie.

Ćwiczenie 1.3
Wyrażenie	Pyton	JavaScript
"5" + 3		błąd    53
"5" * 2		55      błąd
"10" - 5	błąd    5	
True + 1	2       2	

Ćwiczenie 1.4
Podaj wynik indywidualny.

a)  (int) 7.99            = ___7___
b)  (int) -7.99           = ___-7___
c)  (double) 5            = ___5.0___
d)  (int) 3.5 + (int) 3.5 = ___6___
e)  (int)(3.5 + 3.5)      = ___7___

"d" i "e" Różnią się, ponieważ w d rzutowanie na int odbywa się przed dodawaniem, a w e dopiero po dodawaniu.

Ćwiczenie 1.5
print(int("42abc")) zwróci wyjątek: ValueError

Oznacza to, że nie można zamienić tekstu "42abc" na liczbę całkowitą, ponieważ zawiera znaki inne niż cyfry.

Ćwiczenie 2.1
Liczba bitów	Liczba wartości	  Zakres bez znaku	Zakres ze znakiem
4		16                0–15                  -8–7	
8		256               0–255                 -128–127	
16              65 536            0–65 535              -32 768–32 767

Ćwiczenie 2.2
a)  0000 1111  = ___15___
b)  1000 0000  = ___128___
c)  1111 1111  = ___255___

a)  0000 1111  = ___15___
b)  1000 0000  = ___-128___
c)  1111 1111  = ___-1___

Ćwiczenie 2.3
120 → __-126____ → __-116____ → __-106____
Wartość staje się ujemna po 1 kroku.

Ćwiczenie 2.4
a)  17 / 5    (liczby całkowite)  = ___3___
b)  17 % 5                        = ___2___
c)  -17 / 5   (liczby całkowite)  = ___-3___
d)  Ile stron po 20 rekordów potrzeba na 143 rekordy?  = ___8 stron___

Ćwiczenie 2.5
Dana	                        Typ	 Dobrze
Wiek człowieka		        int8     Wiek mieści się w zakresie -128–127.
Rok kalendarzowy		int16    Rok mieści się w zakresie -32768–32767.
Liczba mieszkańców Polski	int32    Liczba jest większa niż zakres int16.	
Liczba mieszkańców Ziemi	int64    Potrzebny większy zakres niż int32.	
Liczba bajtów pliku wideo	int64    Rozmiar dużego pliku może przekraczać zakres int32.	
Temperatura w °C (całkowita)	int8     Typowy zakres temperatur mieści się w -128–127.

Ćwiczenie 2.6
Wynik to -128 — następuje przepełnienie typu int8.
Wartość przechodzi z 127 na początek zakresu, czyli -128.

Ćwiczenie 3.1
Zastosowanie	                            float czy double	 Dlaczego
Współrzędne GPS z dodatkową do metra	    float                Taka dokładność nie wymaga dużej precyzji	
Kolor piksela (0.0 – 1.0)		    float                Wystarczająca precyzja i mniejsze zużycie pamięci.
Obliczenia naukowe, całkowanie numeryczne   double               Potrzebna jest większa precyzja obliczeń.		
Saldo konta bankowego                       double               Większa precyzja zmniejsza błędy zaokrągleń.

Ćwiczenie 3.2
0,5, 
0,25 
0,75
0,125
1,5
Reguła: Liczba ma skończone rozwinięcie binarne, jeśli można ją zapisać jako ułamek, którego mianownik jest potęgą liczby 2 (np. 2, 4, 8, 16...).

Ćwiczenie 3.3
Wyniki w Pythonie:

0.30000000000000004
False
0.10000000000000000555
0.7999999999999999

Zaskoczyło ponieważ pierwszy wynik: 0.1 + 0.2 nie daje dokładnie 0.3. I to najbardziej zaskoczyło

Ćwiczenie 3.4
Poprawiony kod:

def czy_zaplacono(kwota_wplacona, kwota_do_zaplaty):
    return abs(kwota_wplacona - kwota_do_zaplaty) < 0.00001

Ćwiczenie 3.5
a)  1.0 / 0.0        = ___błąd___
b)  -1.0 / 0.0       = ___błąd___
c)  0.0 / 0.0        = ___błąd___
d)  1 / 0            = ___błąd___   (liczby całkowite)
e)  float('inf') - float('inf')  = ___nan___
f)  float('nan') == float('nan') = ___false___ 

Ćwiczenie 3.6
a) Zamiast 59,97 może pojawić się np. 59.96999999999999 – przez sposób zapisywania liczb float.
b) 1. Przechowywać ceny w groszach jako liczby całkowite → 1999 * 3 = 5997.
2. Używać typu Decimal, który pozwala dokładniej przechowywać wartości dziesiętne.
c) Decimal
from decimal import Decimal
cena = Decimal("19.99")
