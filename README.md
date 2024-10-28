# Zadanie domowe #2 - JavaScript

Dobra robota! 💪


Czas podsumować i zastanowić się nad tym, co już zostało zrobione w module 2.

Sprawdź siebie — teraz wiesz:

* jak działają rozgałęzienia: instrukcje `if`, operator `switch`, operator trójskładnikowy
* operatory logiczne `&&`, `||`, `!`
* metody ciągów znaków: `slice()`, `toLowerCase()`, `toUpperCase()`, `includes()`, `startsWith()`, `endsWith()`, `indexOf()`, `trim()`
* pętle `while`, `do…while`, `for`

Nadszedł czas, aby praktycznie utrwalić te wiadomości i powtórzyć poprzedni materiał.



* Utwórz repozytorium `goit-js-hw-02`.
* Utwórz oddzielny plik z rozszerzeniem `.js` dla każdego z zadań 1-4.
* Przeczytaj każde zadanie i wykonaj je w edytorze kodu.
* Upewnij się, że kod jest sformatowany za pomocą `Prettiera`, a w konsoli nie ma błędów ani ostrzeżeń podczas otwierania strony zadania na żywo.
* Prześlij zadanie domowe do sprawdzenia.


**Format złożenia**: Zadanie domowe zawiera dwa linki: do plików źródłowych i do strony roboczej na `GitHub Pages`.



### Zadanie 1. Zamówienie droidów

Stacja sprzedaży droidów naprawczych jest gotowa do uruchomienia, pozostało napisać oprogramowanie dla działu sprzedaży. Zadeklaruj funkcję `makeTransaction(quantity, pricePerDroid, customerCredits)`, która komponuje i zwraca komunikat o zakupie droidów naprawczych.



Deklaruje ona trzy parametry, których wartości będą ustalane podczas jej wywołania:

* `quantity` — ilość zamówionych droidów
* `pricePerDroid` — cena jednego droida
* `customerCredits` — suma środków na koncie klienta


Uzupełnij funkcję w następujący sposób:

* Zadeklaruj zmienną do przechowywania całkowitej sumy zamówienia (łączna wartość wszystkich zamówionych droidów) i przypisz jej wyrażenie obliczające tę sumę.
* Dodaj sprawdzenie, czy klient może zapłacić za zamówienie:
* jeśli suma do zapłaty przekracza ilość kredytów na koncie klienta, funkcja powinna zwracać ciąg znaków `"Insufficient funds!"`
* w przeciwnym przypadku funkcja powinna zwracać ciąg znaków `"You ordered <quantity> droids worth <totalPrice> credits!"`, gdzie `<quantity>` to ilość zamówionych droidów, a `<totalPrice>` to ich łączna wartość.


Weź poniższy kod i wstaw go po deklaracji swojej funkcji, aby sprawdzić poprawność jej działania. W konsoli zostaną wyświetlone wyniki jej działania.


```
console.log(makeTransaction(5, 3000, 23000)); // "You ordered 5 droids worth 15000 credits!"
console.log(makeTransaction(3, 1000, 15000)); // "You ordered 3 droids worth 3000 credits!"
console.log(makeTransaction(10, 5000, 8000)); // "Insufficient funds!"
console.log(makeTransaction(8, 2000, 10000)); // "Insufficient funds!"
console.log(makeTransaction(10, 500, 5000)); // "You ordered 10 droids worth 5000 credits!"
```


Zostaw ten kod do sprawdzenia przez mentora.



**Na co będzie zwracał uwagę mentor przy sprawdzaniu:**

* Zadeklarowana funkcja `makeTransaction(quantity, pricePerDroid, customerCredits)`
* Wywołanie` makeTransaction(5, 3000, 23000)` zwraca `"You ordered 5 droids worth 15000 credits!"`
* Wywołanie `makeTransaction(3, 1000, 15000)` zwraca `"You ordered 3 droids worth 3000 credits!"`
* Wywołanie `makeTransaction(10, 5000, 8000)` zwraca `"Insufficient funds!"`
* Wywołanie `makeTransaction(8, 2000, 10000)` zwraca `"Insufficient funds!"`
* Wywołanie `makeTransaction(10, 500, 5000)` zwraca `"You ordered 10 droids worth 5000 credits!"`


### Zadanie 2. Formatowanie wiadomości

Zadeklaruj funkcję `formatMessage(message, maxLength)`, która przyjmuje ciąg znaków (parametr `message`) i sprawdza jego długość w stosunku do określonej maksymalnej długości (parametr `maxLength`).

Uzupełnij kod funkcji w taki sposób, że:

* Jeśli długość ciągu znaków jest równa lub mniejsza niż `maxLength`, funkcja zwraca początkowy ciąg znaków bez zmian.
* Jeśli długość przekracza `maxLength`, funkcja skraca ciąg znaków do `maxLength` znaków, dodaje trzy kropki `"..."` na końcu i zwraca skróconą wersję.


Weź poniższy kod i wstaw go po deklaracji swojej funkcji, aby sprawdzić poprawność jej działania. W konsoli zostaną wyświetlone wyniki jej działania.


```
console.log(formatMessage("Curabitur ligula sapien", 16)); // "Curabitur ligula..."
console.log(formatMessage("Curabitur ligula sapien", 23)); // "Curabitur ligula sapien"
console.log(formatMessage("Vestibulum facilisis purus nec", 20)); // "Vestibulum facilisis..."
console.log(formatMessage("Vestibulum facilisis purus nec", 30)); // "Vestibulum facilisis purus nec"
console.log(formatMessage("Nunc sed turpis a felis in nunc fringilla", 15)); // "Nunc sed turpis..."
console.log(formatMessage("Nunc sed turpis a felis in nunc fringilla", 41)); // "Nunc sed turpis a felis in nunc fringilla"
```


Zostaw ten kod do sprawdzenia przez mentora.

**Na co będzie zwracał uwagę mentor przy sprawdzaniu:**

* Zadeklarowana funkcja `formatMessage(message, maxLength)`
* Wywołanie funkcji `formatMessage("Curabitur ligula sapien", 16)` zwraca `"Curabitur ligula..."`
* Wywołanie funkcji `formatMessage("Curabitur ligula sapien", 23)` zwraca `"Curabitur ligula sapien"`
* Wywołanie funkcji `formatMessage("Vestibulum facilisis purus nec", 20)` zwraca `"Vestibulum facilisis..."`
* Wywołanie funkcji `formatMessage("Vestibulum facilisis purus nec", 30)` zwraca `"Vestibulum facilisis purus nec"`
* Wywołanie funkcji `formatMessage("Nunc sed turpis a felis in nunc fringilla", 15)` zwraca `"Nunc sed turpis..."`
* Wywołanie funkcji `formatMessage("Nunc sed turpis a felis in nunc fringilla", 41)` zwraca `"Nunc sed turpis a felis in nunc fringilla"`


### Zadanie 3. Sprawdzanie spamu

Funkcja `checkForSpam(message)` przyjmuje ciąg znaków (parametr `message`), sprawdza go pod kątem zawartości zabronionych słów `spam` i `sale`, i zwraca wynik sprawdzenia. Słowa w ciągu znaków parametru message mogą być w dowolnym przypadku, na przykład `SPAM` lub `sAlE`.

Uzupełnij kod funkcji tak, aby:

* Jeśli zostanie znalezione zabronione słowo (`spam` lub `sale`), funkcja zwraca wartość logiczną `true`
* Jeśli w ciągu znaków nie ma zabronionych słów, funkcja zwraca wartość logiczną `false`

Weź poniższy kod i wstaw go po deklaracji swojej funkcji, aby sprawdzić poprawność jej działania. W konsoli zostaną wyświetlone wyniki jej działania.


```
console.log(checkForSpam("Latest technology news")); // false
console.log(checkForSpam("JavaScript weekly newsletter")); // false
console.log(checkForSpam("Get best sale offers now!")); // true
console.log(checkForSpam("Amazing SalE, only tonight!")); // true
console.log(checkForSpam("Trust me, this is not a spam message")); // true
console.log(checkForSpam("Get rid of sPaM emails. Our book in on sale!")); // true
console.log(checkForSpam("[SPAM] How to earn fast money?")); // true
```


Zostaw ten kod do sprawdzenia przez mentora.

**Na co będzie zwracał uwagę mentor przy sprawdzaniu:**

* Zadeklarowana funkcja `checkForSpam(message)`.
* Wywołanie funkcji `checkForSpam("Latest technology news")` zwraca `false`
* Wywołanie funkcji `checkForSpam("JavaScript weekly newsletter")` zwraca `false`
* Wywołanie funkcji `checkForSpam("Get best sale offers now!")` zwraca `true`
* Wywołanie funkcji `checkForSpam("Amazing SalE, only tonight!")` zwraca `true`
* Wywołanie funkcji `checkForSpam("Trust me, this is not a spam message")` zwraca `true`
* Wywołanie funkcji `checkForSpam("Get rid of sPaM emails. Our book in on sale!")` zwraca `true`
* Wywołanie funkcji `checkForSpam("[SPAM] How to earn fast money?")` zwraca `true`


### Zadanie 4. Dostawa towaru

Zadeklaruj funkcję `getShippingCost(country)`, która powinna sprawdzać możliwość dostawy towaru do kraju użytkownika (parametr `country`) i zwracać komunikat o wyniku. Obowiązkowo użyj instrukcji `switch`.

Format zwracanego ciągu znaków `"Shipping to <country> will cost <price> credits"`, gdzie zamiast `<country>` i `<price>` należy podstawić odpowiednie wartości.



Lista krajów i koszt dostawy:

`China` — 100 kredytów
`Chile` — 250 kredytów
`Australia` — 170 kredytów
`Jamaica` — 120 kredytów


Z listy widać, że dostawa jest możliwa nie wszędzie. Jeśli podany kraj nie znajduje się na liście, funkcja powinna zwrócić ciąg znaków `"Sorry, there is no delivery to your country"`.



Weź poniższy kod i wstaw go po deklaracji swojej funkcji, aby sprawdzić poprawność jej działania. W konsoli zostaną wyświetlone wyniki jej działania.


```
console.log(getShippingCost("Australia")); // "Shipping to Australia will cost 170 credits"
console.log(getShippingCost("Germany")); // "Sorry, there is no delivery to your country"
console.log(getShippingCost("China")); // "Shipping to China will cost 100 credits"
console.log(getShippingCost("Chile")); // "Shipping to Chile will cost 250 credits"
console.log(getShippingCost("Jamaica")); // "Shipping to Jamaica will cost 120 credits"
console.log(getShippingCost("Sweden")); // "Sorry, there is no delivery to your country"
```


Zostaw ten kod do sprawdzenia przez mentora.

**Na co będzie zwracał uwagę mentor przy sprawdzaniu:**

* Zadeklarowana funkcja `getShippingCost(country)`
* W ciele funkcji użyta instrukcja `switch`
* Wywołanie `getShippingCost("Australia")` zwraca `"Shipping to Australia will cost 170 credits"`
* Wywołanie` getShippingCost("Germany")` zwraca `"Sorry, there is no delivery to your country"`
* Wywołanie `getShippingCost("China")` zwraca `"Shipping to China will cost 100 credits"`
* Wywołanie `getShippingCost("Chile")` zwraca `"Shipping to Chile will cost 250 credits"`
* Wywołanie `getShippingCost("Jamaica")` zwraca `"Shipping to Jamaica will cost 120 credits"`
* Wywołanie `getShippingCost("Sweden")` zwraca `"Sorry, there is no delivery to your country"`
