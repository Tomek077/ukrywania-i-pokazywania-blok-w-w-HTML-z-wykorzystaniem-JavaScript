# Ukrywania i pokazywania bloków w HTML z wykorzystaniem JavaScript

---

## Spis treści

1. [Wprowadzenie](#wprowadzenie)  
2. [Podstawy: HTML, CSS, JavaScript](#podstawy-html-css-javascript)  
3. [Tutorial – krok po kroku](#tutorial--krok-po-kroku)  
   - [Krok 1: Tworzymy strukturę HTML](#krok-1-tworzymy-strukturę-html)  
   - [Krok 2: Dodajemy styl (CSS) – opcjonalnie](#krok-2-dodajemy-styl-css--opcjonalnie)  
   - [Krok 3: Wstawiamy przyciski i blok](#krok-3-wstawiamy-przyciski-i-blok)  
   - [Krok 4: Pisanie skryptu JavaScript](#krok-4-pisanie-skryptu-javascript)  
   - [Krok 5: Uruchom i przetestuj](#krok-5-uruchom-i-przetestuj)  
4. [Ćwiczenia](#ćwiczenia)  
   - [Ćwiczenie 1: Rozbudowa układu](#ćwiczenie-1-rozbudowa-układu)  
   - [Ćwiczenie 2: Dodanie przełączania (toggle)](#ćwiczenie-2-dodanie-przełączania-toggle)  
   - [Ćwiczenie 3: Ukrywanie/pokazywanie wielu bloków](#ćwiczenie-3-ukrywaniepokazywanie-wielu-bloków)  
5. [Podsumowanie](#podsumowanie)

---

## 1. Wprowadzenie

Wyobraź sobie, że chcesz zrobić stronę internetową, gdzie pewne informacje mają pojawiać się dopiero po kliknięciu przycisku. Może to być opis produktu w sklepie internetowym albo dodatkowe wskazówki do zadania. Dzięki prostej funkcji w **JavaScripcie** możesz ukrywać lub pokazywać dowolne fragmenty strony.

W tej lekcji dowiesz się:

- Jak przygotować kod HTML tak, aby mieć element (tzw. blok) do ukrywania/pokazywania.  
- Jak używać podstawowych właściwości w CSS, aby kontrolować widoczność.  
- Jak napisać prosty kod w JavaScripcie, który pokaże lub ukryje fragment strony po kliknięciu przycisku.  

---

## 2. Podstawy: HTML, CSS, JavaScript

1. **HTML (HyperText Markup Language)** – to „szkielet” strony internetowej. Określa, jakie elementy będą na stronie (np. nagłówki, przyciski, paragrafy, obrazy).

2. **CSS (Cascading Style Sheets)** – styluje stronę, czyli odpowiada za kolory, rozmiary, układ i inne aspekty wizualne.

3. **JavaScript** – ożywia stronę, pozwalając reagować na kliknięcia i zmieniać elementy w czasie rzeczywistym (np. pokazywać/ukrywać bloki, zmieniać kolory, animacje).

---

## 3. Tutorial – krok po kroku

### Krok 1: Tworzymy strukturę HTML

1. Otwórz edytor kodu (np. Notepad++, Visual Studio Code lub nawet Notatnik).  
2. Utwórz nowy plik i zapisz go jako **index.html**.  
3. Rozpocznij od podstawowego szablonu HTML:

```html
<!DOCTYPE html>
<html lang="pl">
<head>
  <meta charset="UTF-8" />
  <title>Ukrywanie i pokazywanie bloków</title>
</head>
<body>

  <!-- Tutaj będziemy dodawać kolejne elementy -->

</body>
</html>
```

### Krok 2: Dodajemy styl (CSS) – opcjonalnie
Możemy na razie pominąć własny plik CSS i użyć prostego stylu w **style="..."** lub w `<style>`.

Przykład (umieść w sekcji `<head>` lub użyj `style` bezpośrednio w HTML przy elemencie):

```html
<style>
  /* Przykładowe style */
  body {
    font-family: Arial, sans-serif;
    margin: 20px;
  }
  #blok {
    width: 200px;
    height: 100px;
    background-color: lightblue;
    text-align: center;
    line-height: 100px; /* Wyśrodkowanie tekstu w pionie */
    margin-top: 20px;
  }
</style>
```

### Krok 3: Wstawiamy przyciski i blok

W sekcji `<body>` potrzebujemy:

1. **Nagłówek** (np. `<h1>`), który informuje, o czym jest strona.  
2. **Przyciski** – klikając w nie, będziemy wywoływać funkcje JavaScript.  
3. **Blok** (np. `<div>`) z unikalnym `id`, który chcemy ukryć/pokazać.

```html
<h1>Przykład ukrywania i pokazywania bloku</h1>

<!-- Przyciski -->
<button onclick="ukryjBlok()">Ukryj blok</button>
<button onclick="pokazBlok()">Pokaż blok</button>

<!-- Blok, który będziemy ukrywać/pokazywać -->
<div id="blok">
  Jestem blokiem!
</div>
```

### Krok 4: Pisanie skryptu JavaScript

Pod koniec sekcji `<body>` (ale przed `</body>`), wstaw **blok skryptu**:

```html
<script>
  function ukryjBlok() {
    document.getElementById("blok").style.display = "none";
  }

  function pokazBlok() {
    document.getElementById("blok").style.display = "block";
  }
</script>
```

- `document.getElementById("blok")` wyszukuje w dokumencie element o **id="blok"**.  
- `style.display = "none"` ukrywa element (blok znika).  
- `style.display = "block"` ponownie go pokazuje.

### Krok 5: Uruchom i przetestuj

1. Zapisz plik (**index.html**).  
2. Otwórz go w przeglądarce (np. Chrome, Firefox).  
3. Zobaczysz:  
   - Nagłówek „Przykład ukrywania i pokazywania bloku”.  
   - Dwa przyciski: „Ukryj blok” i „Pokaż blok”.  
   - Blok (niebieski prostokąt) z tekstem „Jestem blokiem!”.  

Spróbuj kliknąć **Ukryj blok** – powinien zniknąć.  
Następnie kliknij **Pokaż blok** – powinien się pojawić ponownie.

Gratulacje – masz działającą wersję podstawową!

---

## 4. Ćwiczenia

### Ćwiczenie 1: Rozbudowa układu

- Dodaj jeszcze jeden element HTML (np. `<p>` z krótkim opisem).  
- Zastosuj inny kolor tła w CSS dla nowego elementu.  
- Sprawdź, czy chcesz go także ukrywać/pokazywać (możesz dodać osobne przyciski lub skorzystać z tych samych funkcji).

**Wskazówka**: Pamiętaj, by dodać unikalne `id` (np. `"opis"`) i w JavaScripcie stwórz nowe funkcje `ukryjOpis()`, `pokazOpis()`, albo – jeśli chcesz poćwiczyć – spróbuj jednej funkcji `ukryjPokazOpis()`, która będzie przełączała stan.

---

### Ćwiczenie 2: Dodanie przełączania (toggle)

- Zamiast dwóch przycisków **(„Ukryj blok” i „Pokaż blok”)** stwórz **jeden przycisk** (np. nazwij go „Przełącz”).  
- W JavaScripcie dodaj funkcję, która sprawdza, czy blok ma `style.display = "none"`. Jeśli tak – ustawia „block”, a jeśli nie – ustawia „none”.  

Przykładowy przebieg (logika, **nie gotowy kod**):  
```text
Jeśli display == "none" -> zmień na "block"
Jeśli display == "block" -> zmień na "none"
```
Przykład gotowego rozwiązania
```html
<!DOCTYPE html>
<html lang="pl">
<head>
  <meta charset="UTF-8" />
  <title>Ukrywanie i pokazywanie bloków – wersja z przełączaniem</title>
  <style>
    #blok {
      width: 200px;
      height: 100px;
      background-color: lightblue;
      text-align: center;
      line-height: 100px; /* wyśrodkowanie tekstu w pionie */
      margin-top: 20px;
    }
  </style>
</head>
<body>

  <h1>Przykład funkcji „Przełącz” (toggle)</h1>

  <!-- Jeden przycisk do przełączania widoczności -->
  <button onclick="przelaczBlok()">Przełącz blok</button>

  <!-- Blok do ukrywania/pokazywania -->
  <div id="blok">
    Jestem blokiem!
  </div>

  <!-- JavaScript -->
  <script>
    function przelaczBlok() {
      // Pobierz element
      const blok = document.getElementById("blok");

      // Sprawdź obecny styl display
      if (blok.style.display === "none") {
        // Jeśli jest ukryty (display=none), to go pokaż
        blok.style.display = "block";
      } else {
        // W przeciwnym wypadku (domyślnie "block") - ukryj
        blok.style.display = "none";
      }
    }
  </script>

</body>
</html>

```
---

### Ćwiczenie 3: Ukrywanie/pokazywanie wielu bloków

- Dodaj **dwa** różne bloki na stronie (np. `id="blok1"` i `id="blok2"`).  
- Wstaw **przyciski** (lub jeden przycisk z przełączaniem) do ukrywania/pokazywania każdego z nich osobno.  
- Spróbuj też zrobić przycisk, który **ukrywa/pokazuje oba** bloki jednocześnie.  

**Rozbuduj** w miarę swojego pomysłu – np. różne kolory tła, różne wymiary, a przyciskami steruj, co się wyświetla.

---

## 5. Podsumowanie

1. **HTML** daje nam strukturę elementów na stronie.  
2. **CSS** pomaga zdefiniować wygląd i ewentualnie ukryć/pokazać coś za pomocą `display: none;` lub `display: block;`.  
3. **JavaScript** umożliwia zmianę stylów (np. `style.display`) w momencie kliknięcia przycisku, co w praktyce pozwala ukrywać/pokazywać wybrany element.  

W tej lekcji poznałeś(aś) podstawy, które wystarczą, aby tworzyć proste, interaktywne strony. Zachęcam do eksperymentowania z dodatkowymi stylami, animacjami (np. `transition` czy biblioteki jak jQuery), a nawet z frameworkami (React, Vue, Angular) w przyszłości.  

**Powodzenia!** Ucz się w swoim tempie, zadawaj pytania i ciesz się z pierwszych efektów interakcji na swojej stronie.
