# Specyfikacja Wymagań Oprogramowania (SRS)
## System Zarządzania Cyklem Życia Pracownika: Strategie Rekrutacji i Rozwoju
**Autorzy:** Jan Piaskowy, Piotr Gębalski, Mateusz Cholewa

---

## Spis Treści
1.  [Wstęp](#1-wstęp)
2.  [Opis Ogólny](#2-opis-ogólny)
3.  [Wymagania Dotyczące Interfejsów Zewnętrznych](#3-wymagania-dotyczące-interfejsów-zewnętrznych)
4.  [Wymagania Funkcjonalne](#4-wymagania-funkcjonalne)
5.  [Atrybuty Jakościowe (Wymagania Niefunkcjonalne)](#5-atrybuty-jakościowe-wymagania-niefunkcjonalne)
6.  [Odkrywanie i Analiza Wymagań](#6-odkrywanie-i-analiza-wymagań)
7.  [Dodatki](#7-dodatki)

---

<div style="page-break-after: always;"></div>

## 1. Wstęp

### 1.1. Cel Dokumentu
Celem niniejszego dokumentu Specyfikacji Wymagań Oprogramowania (SRS) jest szczegółowe zdefiniowanie wymagań funkcjonalnych i niefunkcjonalnych dla zintegrowanej platformy informatycznej wspierającej zarządzanie cyklem życia pracownika (Employee Lifecycle Management). System ten, roboczo nazwany "WorkLife Cycle Platform", ma na celu zintegrowanie procesów przyciągania talentów (Employer Branding) z ich efektywnym wdrożeniem i rozwojem (Onboarding).

Dokument ten jest przeznaczony dla:
*   **Zespołu Deweloperskiego:** Jako techniczna mapa drogowa implementacji, definiująca zachowanie systemu, interfejsy i ograniczenia.
*   **Interesariuszy Biznesowych (Zarząd, HR):** W celu weryfikacji, czy zaproponowane rozwiązanie realizuje cele biznesowe organizacji i rozwiązuje zidentyfikowane problemy.
*   **Testerów:** Jako podstawa do tworzenia planów testów, scenariuszy testowych i kryteriów akceptacji.

Dokument stanowi formalny kontrakt między zespołem realizującym a zlecającym, precyzując zakres prac (Scope of Work).

### 1.2. Wizja, Zakres i Cele Produktu

#### 1.2.1. Kontekst Biznesowy i Problem
Współczesne średnie i duże organizacje technologiczne borykają się z dwoma fundamentalnymi problemami, które są ze sobą ściśle powiązane:
1.  **Niespójny Employer Branding:** Działy HR mają trudności z regularnym publikowaniem treści w mediach społecznościowych. Publikacje są chaotyczne (2-3 posty/miesiąc), tworzenie contentu jest czasochłonne (45-90 min/post), a potencjał tkwiący w historiach sukcesu pracowników jest marnowany. Skutkuje to niskim zasięgiem organicznym i wysokim kosztem pozyskania kandydata.
2.  **Nieefektywny Onboarding:** Po zatrudnieniu kandydata, proces wdrożenia jest często niesformalizowany. Materiały są rozproszone (wiki, maile, ustne przekazy), mentorzy tracą czas na powtarzalne czynności, a firma nie posiada danych o rzeczywistym czasie osiągnięcia produktywności (Time-to-Productivity). Prowadzi to do frustracji nowych pracowników i ich szybszej rotacji.

#### 1.2.2. Wizja Produktu
Naszą wizją jest stworzenie **"WorkLife Cycle Platform"** – spójnego ekosystemu, który:
*   **Automatyzuje Employer Branding:** "Czyni każdą firmę ekspertem w employer brandingu", zamieniając zapomniane sukcesy zespołów i oferty pracy w angażujący content w social media przy minimalnym udziale człowieka.
*   **Grywalizuje Onboarding:** Zapewnia nowym pracownikom interaktywną, mierzalną ścieżkę wdrożenia (w formie "Guestów"), która integruje się bezpośrednio z ich środowiskiem pracy (repozytoria kodu), skracając czas do pełnej produktywności.

#### 1.2.3. Zakres Systemu
System będzie aplikacją webową składającą się z dwóch zintegrowanych modułów:
1.  **Moduł Employer Branding:**
    *   Automatyczne generowanie treści postów na podstawie ofert pracy i wsadów od pracowników.
    *   Inteligentny harmonogram publikacji (Scheduler) na platformy LinkedIn, Facebook, Instagram.
    *   Centralny dashboard analityczny zasięgów i konwersji.
2.  **Moduł Onboarding & Development:**
    *   Kreator ścieżek onboardingowych dla różnych ról (np. Backend Dev, Frontend Dev).
    *   System "Questów" (zadań) z postępem wizualnym (Pasek postępu, Odznaki).
    *   Integracja z systemami kontroli wersji (GitHub/GitLab) w celu automatycznej weryfikacji zadań technicznych.
    *   Panel raportowy dla HR i Liderów (metryki TtP, satysfakcja).

#### 1.2.4. Poza Zakresem (Out of Scope)
*   System nie będzie zastępował pełnego systemu ATS (Applicant Tracking System) do zarządzania procesem rekrutacji kandydatów.
*   W wersji MVP nie przewiduje się natywnej aplikacji mobilnej (tylko RWD Web).
*   System nie będzie obsługiwał naliczania płac ani formalnych aspektów kadrowych (umowy).

#### 1.2.5. Główne Cele Biznesowe (SMART)
Zidentyfikowano następujące kluczowe wskaźniki efektywności (KPIs), które system musi zrealizować:

*   **KPI-01 (Zasięg):** Wzrost organicznego zasięgu treści employer brandingowych o **50%** (z bazowego 8,000 do 12,000+ wyświetleń miesięcznie) w ciągu 6 miesięcy od wdrożenia, poprzez zwiększenie wolumenu publikacji do 15-20 postów/miesiąc.
*   **KPI-02 (Efektywność HR):** Redukcja czasu pracy zespołu HR poświęcanego na tworzenie contentu social media z **4 godzin do 30 minut miesięcznie**.
*   **KPI-03 (Time-to-Productivity):** Skrócenie średniego czasu wdrożenia nowego pracownika IT (osiągnięcie pełnej samodzielności) z **90 dni do 21 dni (3 tygodni)** dla 80% zatrudnionych.
*   **KPI-04 (Retencja):** Wzrost wskaźnika ukończenia procesu onboardingu w terminie do **85%**.

### 1.3. Definicje, Akronimy i Skróty
Aby zapewnić jednoznaczne zrozumienie dokumentu, wprowadza się następujące definicje:

*   **TtP (Time-to-Productivity):** Metryka określająca czas od pierwszego dnia pracy pracownika do momentu, w którym osiąga on oczekiwany poziom wydajności (np. samodzielnie realizuje zadania z backlogu).
*   **EB (Employer Branding):** Zespół działań mających na celu budowanie wizerunku pracodawcy jako "pracodawcy z wyboru".
*   **Quest:** Pojedyncze zadanie w procesie onboardingu, sformatowane w języku grywalizacji, posiadające cel, opis i nagrodę (XP).
*   **XP (Experience Points):** Punkty doświadczenia przyznawane pracownikowi za realizację zadań w systemie.
*   **MVP (Minimum Viable Product):** Wersja produktu z minimalnym zestawem cech wystarczającym do zadowolenia wczesnych klientów i zebrania informacji zwrotnych.
*   **ATS (Applicant Tracking System):** System do śledzenia aplikacji kandydatów.
*   **SaaS (Software as a Service):** Model udostępniania oprogramowania w chmurze.

### 1.4. Przegląd Dokumentu
*   **Rozdział 2** opisuje ogólną charakterystykę systemu, w tym jego funkcje, użytkowników i ograniczenia.
*   **Rozdział 3** definiuje interfejsy zewnętrzne, w tym UI oraz API.
*   **Rozdział 4** zawiera szczegółowe wymagania funkcjonalne w formie Historyjek Użytkownika (User Stories).
*   **Rozdział 5** określa wymagania niefunkcjonalne (Atrybuty Jakościowe).
*   **Rozdział 6** przedstawia analizę rynku i konkurencji.

