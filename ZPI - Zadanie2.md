# Zadanie Projektowe: Przygotowanie Specyfikacji Wymagań Oprogramowania (SRS)

## Cel zadania:

Głównym celem tego zadania jest zapoznanie studentów w zakresie pozyskiwania, analizowania, dokumentowania i walidacji wymagań dla systemu informatycznego. Dokument specyfikacji wymagań oprogramowania (SRS) jest jednym z artefaktów w procesie tworzenia oprogramowania, stanowiąc fundament dla dalszych prac projektowych, implementacyjnych i testowych. Działa on jak kontrakt pomiędzy klientem a zespołem deweloperskim.

Studenci, pracując w grupach, mają za zadanie stworzyć kompletny i jednoznaczny dokument SRS dla tworzonego przez siebie systemu, stosując najlepsze praktyki branżowe.

## Organizacja pracy:

- **Praca w grupach:** 4-7 osobowych.
- **Narzędzia:** System kontroli wersji (np. Git z platformą GitHub).
- **Forma oddania:** Dokument w formacie PDF oraz link do repozytorium z historią pracy nad dokumentem.

### Sugerowana Struktura Dokumentu SRS

Wasz dokument powinien posiadać następującą strukturę:

#### 1. Wstęp

* **1.1. Cel:** Zidentyfikuj produkt, którego dotyczą wymagania, wraz z numerem wersji. Opisz cel tego dokumentu – dla kogo jest przeznaczony i jak powinien być używany
* **1.2. Wizja, Zakres i Cele Produktu:**
    * **Wizja:** Stwórzcie krótką, inspirującą projektu.
    * **Zakres:** Zdefiniujcie, co system będzie robił. Wymieńcie główne **cele biznesowe** i **cele użytkowników** wraz z mierzalnymi **kryteriami akceptacji** (KPIs).
    * **Poza Zakresem:** Jasno określcie, czego system nie będzie robił, aby uniknąć nieporozumień.
* **1.3. Definicje, Akronimy i Skróty:** Stwórzcie słowniczek pojęć, aby zapewnić spójne rozumienie terminologii.
* **1.4. Przegląd Dokumentu:** Krótko opiszcie, co zawierają kolejne rozdziały.

#### 2. Opis Ogólny

* **2.1. Główne Funkcje Produktu:** Przedstawcie w formie listy lub diagramu główne moduły systemu. Ma to być ogólny zarys tego, co zostanie uszczegółowione w Rozdziale 4.
* **2.2. Klasy Użytkowników:** Szczegółowo opiszcie każdą z ról. Dla kluczowych ról stwórzcie persony (patrz Dodatek B).
* **2.3. Ograniczenia Projektowe i Implementacyjne:** Wymieńcie wszelkie ograniczenia, kategoryzując je:
    * **Technologiczne:** Np. wymóg użycia konkretnego języka programowania, frameworka, bazy danych, ograniczenia sprzętowe serwera.
    * **Organizacyjne:** Np. budżet, termin oddania projektu, dostępność członków zespołu, narzucone metodyki pracy.
    * **Prawne i Środowiskowe:** Np. zgodność z RODO (GDPR), regulacje uczelniane.
* **2.4. Założenia Projektow:** Określcie założenia projektowe.

#### 3. Wymagania Dotyczące Interfejsów Zewnętrznych

* **3.1. Interfejsy Użytkownika (UI):** Ogólny opis wyglądu i stylu. Dołączcie tu makiety. Rekomenduję wykorzystanie narzędzi typu Figma lub Miro. Proszę zamodelować tylko główny przypadek użycia systemu.
* **3.2. Interfejsy Programowe (API):** Opis integracji z innymi systemami (np. z systemem płatności, USOS).

#### 4. Wymagania Funkcjonalne

To najważniejsza część dokumentu. Zastosujcie strukturę zorientowaną na funkcjonalność, która łączy perspektywę użytkownika (User Story) z precyzyjnymi kryteriami akceptacji. Dla każdej głównej funkcjonalności stwórzcie osobną sekcję, stosując poniższy szablon. W ramach jednego wymagania może pojawić się kilka historyjek użytkownika.

**Przykład:**
* **Tytuł:** Aplikowanie na ofertę praktyk
* **Opis:** Umożliwia studentom składanie aplikacji na opublikowane oferty praktyk.
* **Historyjka Użytkownika:**
    * Jako student,
    * chcę móc aplikować na wybraną ofertę praktyki,
    * abym mógł wziąć udział w procesie rekrutacyjnym.
* **Cel Biznesowy:** Usprawnienie procesu aplikacyjnego dla studentów i zwiększenie liczby jakościowych aplikacji dla firm.
* **Warunki Wstępne:** Użytkownik jest zalogowany w systemie jako student.
* **Warunki Końcowe:** Aplikacja studenta zostaje zarejestrowana w systemie i jest widoczna dla firmy.
* **Kryteria Akceptacji:**

    * **WF-APLIK-01: Pomyślne złożenie aplikacji (Scenariusz Główny)**
        * *Opis:* Student z kompletnym profilem aplikuje na dostępną praktykę.
        * *Kryteria Akceptacji:*
            * **Given:** Jestem zalogowanym studentem z kompletnym profilem i wymaganymi dokumentami w systemie.
            * **And:** Znalazłem interesującą, aktywną ofertę praktyk, na którą jeszcze nie aplikowałem.
            * **When:** Kliknę przycisk "Aplikuj" i potwierdzę wysłanie.
            * **Then:** Moja aplikacja otrzymuje status "Wysłana".
            * **And:** Przedstawiciel firmy otrzymuje powiadomienie o nowej aplikacji.
            * **And:** Oferta na liście ofert jest dla mnie oznaczona jako "Aplikowano".

    * **WF-APLIK-02: Aplikowanie bez wymaganego dokumentu (Scenariusz Alternatywny)**
        * *Opis:* System uniemożliwia aplikowanie bez kompletu wymaganych dokumentów.
        * *Kryteria Akceptacji:*
            * **Given:** Jestem zalogowanym studentem, który nie załączył jeszcze CV do swojego profilu.
            * **And:** Znalazłem ofertę praktyk, która wymaga CV.
            * **When:** Kliknę przycisk "Aplikuj".
            * **Then:** System powinien wyświetlić komunikat informujący o konieczności załączenia CV.
            * **And:** Powinien przekierować mnie do strony edycji profilu w celu dodania pliku.
            * **And:** Aplikacja nie zostanie wysłana.

    * **WF-APLIK-03: Aplikowanie na nieaktywną ofertę (Scenariusz Wyjątkowy)**
        * *Opis:* System blokuje możliwość aplikowania na oferty, które wygasły.
        * *Kryteria Akceptacji:*
            * **Given:** Jestem zalogowanym studentem i trafiłem na stronę oferty, której termin składania aplikacji już minął.
            * **When:** Próbuję znaleźć i kliknąć przycisk "Aplikuj".
            * **Then:** Przycisk "Aplikuj" powinien być nieaktywny lub niewidoczny.
            * **And:** Na stronie oferty powinien znajdować się wyraźny komunikat "Rekrutacja na to stanowisko została zakończona".

##### 4.1. Priorytetyzacja Wymagań

Zgodnie ze wzorem z poprzedniego zadania, studenci powinni stworzyć priorytetyzację wymagań.

#### 5. Atrybuty Jakościowe

Opisują one, jak system ma działać. Muszą być mierzalne i weryfikowalne.

*   **Jakość wykonania**
    *   **Wydajność (Performance):**
        *   **WNF-WYD-01:** Czas odpowiedzi serwera na zapytanie o listę dostępnych pokoi nie może przekroczyć 1.5 sekundy przy 200 jednoczesnych użytkownikach.
    *   **Dostępność (Availability):**
        *   **WNF-NIEZ-01:** Dostępność systemu musi wynosić 99.8% w skali roku, z wyłączeniem planowanych okien serwisowych.
    *   **Bezpieczeństwo (Security):**
        *   **WNF-BEZ-01:** Hasła użytkowników muszą być hashowane z użyciem bcrypt.
        *   **WNF-BEZ-02:** Sesja użytkownika wygasa automatycznie po 30 minutach bezczynności.
    *   **Skalowalność (Scalability):**
        *   **WNF-SKAL-01:** Architektura systemu musi pozwalać na horyzontalne skalowanie w celu obsłużenia 5000 jednoczesnych sesji użytkowników.

*   **Jakość projektu**
    *   **Modyfikowalność (Modifiability):**
        *   **WNF-ROZ-01:** System musi umożliwiać dodanie nowego typu integracji z systemem płatności bez modyfikacji istniejącego kodu.
    *   **Przenośność (Portability):**
        *   **WNF-PRZEN-01:** Aplikacja musi być w pełni uruchamialna za pomocą jednego polecenia `docker-compose up` na maszynie deweloperskiej.

##### 5.1. Priorytetyzacja Wymagań

Zgodnie ze wzorem z poprzedniego zadania, studenci powinni stworzyć priorytetyzację atrybutów jakościowych.

### 6. Odkrywanie i Analiza Wymagań

#### 6.1. Analiza Porównawcza
Systematyczny proces porównywania własnego projektu z najlepszymi praktykami rynkowymi w celu identyfikacji mocnych i słabych stron oraz znalezienia inspiracji do ulepszeń.

* **Krok 1: Identyfikacja Konkurencji/Wzorców:** Zidentyfikujcie podmioty rozwiązujące podobny problem. Mogą to być:
    * *Konkurencja bezpośrednia:* Istniejące portale dedykowane praktykom i stażom.
    * *Konkurencja pośrednia:* Biura Karier uczelni, duże portale pracy.
    * *Wzorce funkcjonalne:* Systemy rekrutacyjne pod kątem procesu aplikacyjnego.
* **Krok 2: Zdefiniowanie Kryteriów Oceny:** Stwórzcie tabelę z kryteriami obejmującymi kluczowe aspekty, takie jak funkcjonalność, user experience (UX), model biznesowy i wsparcie.
* **Krok 3: Synteza Wyników:** Porównajcie zebrane dane, aby odpowiedzieć na pytania: Co konkurencja robi dobrze? Gdzie są ich słabe punkty? Jakie unikalne funkcje oferują? Wyniki analizy powinny bezpośrednio wpłynąć na treść dokumentu SRS.

## Dodatki

* **Dodatek A: Modele Analityczne:**
    * **Diagram Przypadków Użycia:** Pokażcie interakcje między aktorami a grupami funkcjonalności systemu.
* **Dodatek B: Persony Użytkowników:** Stwórzcie 2 fikcyjne postacie dla każdej z głównych ról.
* **Dodatek C: Kwestie do Rozwiązania:** Lista pytań i niejasności, które pojawiły się w trakcie analizy.

### Kryteria Oceny Projektu

| Sekcja | Elementy podlegające ocenie | Maks. punkty | Opis kryterium |
| :--- | :--- | :---: | :--- |
| **1. Wstęp** | 1.1. Cel<br>1.2. Wizja, Zakres i Cele (KPIs)<br>1.3. Słownik<br>1.4. Przegląd | 5 | Kompletność sekcji wstępnych, poprawność definicji celu i zakresu, czytelność słownika. |
| **2. Opis Ogólny** | 2.1. Funkcje produktu<br>2.2. Klasy użytkowników i Persony<br>2.3. Ograniczenia<br>2.4. Założenia | 6 | Trafność identyfikacji funkcji i klas użytkowników. Jakość i realizm person. Poprawne rozróżnienie i kategoryzacja ograniczeń oraz założeń. |
| **3. Interfejsy Zewnętrzne** | 3.1. Interfejsy Użytkownika<br>3.2. Interfejsy Programowe  | 4 | Estetyka i użyteczność makiet. Poprawność definicji punktów styku z innymi systemami. |
| **4. Funkcjonalności Systemu** | 4.1. Opis i Priorytet<br>4.2. Historyjki Użytkownika<br>4.3. Kryteria Akceptacji <br>4.4. Priorytetyzacja | 14 | Najważniejsza sekcja. Poprawność składni User Stories. Precyzja i testowalność kryteriów akceptacji w formacie Given-When-Then (scenariusze główne, alternatywne i wyjątkowe). Logika priorytetyzacji. |
| **5. Atrybuty Jakościowe** | 5.1. Jakość wykonania<br>5.2. Jakość projektu | 6 | Mierzalność wymagań niefunkcjonalnych (konkretne wartości liczbowe). Pokrycie kluczowych atrybutów. |
| **6. Analiza Wymagań** | 6.1. Analiza Porównawcza | 5 | Głębia analizy konkurencji, trafność wniosków i ich wpływ na kształt wymagań. |
| **7. Współpraca i Jakość** | 7.1. Historia Git<br>7.2. Struktura i format dokumentu<br>7.3. Spójność i styl | 10 | Regularność commitów, jakość opisów PR, współpraca w zespole. Profesjonalny wygląd dokumentu, poprawność językowa, brak błędów formatowania. |
| **SUMA** | | **50** | |