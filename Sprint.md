# Plan 1 sprintu

## System Zarządzania Cyklem Życia Pracownika: Strategie Rekrutacji i Rozwoju

**Autorzy:** Jan Piaskowy, Piotr Gębalski, Mateusz Cholewa, Rafał Bogacz, Joanna Gniadek, Serhii Cherepiuk

## Spis treści

1. EPIC dla MVP
2. Proof of Concept
3. Cel i zadania sprintu
4. Story points
5. Definition of Done
6. Analiza Pre-Mortem

## 3. EPIC wymagane dla MVP

### 1.1 Lista zdefiniowanych EPICów

- [Backlog zadań](https://zpi-recruitment.atlassian.net/jira/software/projects/ELP/boards/1/backlog)

- **EPIC** [ELP-1](https://zpi-recruitment.atlassian.net/browse/ELP-1) Employer Branding Automation - Scope limited to MVP [34]

  - **STORY** [ELP-6](https://zpi-recruitment.atlassian.net/browse/ELP-6) Auto-generate Social Post Drafts from Job Offers [13]
    - [ELP-7](https://zpi-recruitment.atlassian.net/browse/ELP-7) Define job offer data model and validation rules
    - [ELP-8](https://zpi-recruitment.atlassian.net/browse/ELP-8) Implement draft generation service (template + AI stub)
    - [ELP-9](https://zpi-recruitment.atlassian.net/browse/ELP-9) Save draft & status workflow (Draft -> Ready for Edit)
    - [ELP-10](https://zpi-recruitment.atlassian.net/browse/ELP-10) HR dashboard list view for generated drafts

  - **STORY** [ELP-11](https://zpi-recruitment.atlassian.net/browse/ELP-11) Schedule and Publish a Post to Multiple Platforms [13]
    - [ELP-12](https://zpi-recruitment.atlassian.net/browse/ELP-12) Define publishing workflow statuses and transitions
    - [ELP-13](https://zpi-recruitment.atlassian.net/browse/ELP-13) Implement scheduler (run at time T → enqueue publish job)
    - [ELP-14](https://zpi-recruitment.atlassian.net/browse/ELP-14) Implement LinkedIn publish connector (PoC) + mock FB/IG

  - **STORY** [ELP-15](https://zpi-recruitment.atlassian.net/browse/ELP-15) Content Calendar UI with Drag & Drop Rescheduling [8]
    - [ELP-16](https://zpi-recruitment.atlassian.net/browse/ELP-16) Implement calendar list API (range query)
    - [ELP-17](https://zpi-recruitment.atlassian.net/browse/ELP-17) Implement update schedule API with validation
    - [ELP-18](https://zpi-recruitment.atlassian.net/browse/ELP-18) Implement calendar UI (week view minimum) + Drag&drop

![EPIC ELP-3](path/to/image)

- **EPIC** [ELP-3](https://zpi-recruitment.atlassian.net/browse/ELP-3) Gamified Onboarding & Development (MVP) [39]

  - **STORY** [ELP-19](https://zpi-recruitment.atlassian.net/browse/ELP-19) Quest Path View for New Employees [8]
    - [ELP-20](https://zpi-recruitment.atlassian.net/browse/ELP-20) Define data model for quest paths and assignments
    - [ELP-21](https://zpi-recruitment.atlassian.net/browse/ELP-21) Implement API: fetch assigned path + progress
    - [ELP-22](https://zpi-recruitment.atlassian.net/browse/ELP-22) Implement employee dashboard UI (quest list + progress)

  - **STORY** [ELP-23](https://zpi-recruitment.atlassian.net/browse/ELP-23) GitHub Webhook Integration & Automated Completion (“Smart Check”) [8]
    - [ELP-24](https://zpi-recruitment.atlassian.net/browse/ELP-24) Implement webhook endpoint + request validation
    - [ELP-25](https://zpi-recruitment.atlassian.net/browse/ELP-25) Implement parser for quest IDs + branch rules
    - [ELP-26](https://zpi-recruitment.atlassian.net/browse/ELP-26) Implement quest completion + XP awarding transaction

  - **STORY** [ELP-55](https://zpi-recruitment.atlassian.net/browse/ELP-55) GitHub Branch Validation & User Feedback Loop (“Smart Check") [5]
    - [ELP-27](https://zpi-recruitment.atlassian.net/browse/ELP-56) Implement branch rules in parser for quest IDs

  - **STORY** [ELP-28](https://zpi-recruitment.atlassian.net/browse/ELP-28) Leader Dashboard to Monitor Onboarding Progress (TtP Risk Flags) [13]
    - [ELP-29](https://zpi-recruitment.atlassian.net/browse/ELP-29) Implement team assignment model (leader <-> employees)
    - [ELP-30](https://zpi-recruitment.atlassian.net/browse/ELP-30) Implement progress aggregation query
    - [ELP-31](https://zpi-recruitment.atlassian.net/browse/ELP-31) Implement dashboard UI table view
    - [ELP-32](https://zpi-recruitment.atlassian.net/browse/ELP-32) Implement inactivity detection job + alert trigger

  - **STORY** [ELP-33](https://zpi-recruitment.atlassian.net/browse/ELP-33) Employee Feedback Survey After Completing Onboarding [5]
    - [ELP-34](https://zpi-recruitment.atlassian.net/browse/ELP-34) Implement completion detection + trigger survey
    - [ELP-35](https://zpi-recruitment.atlassian.net/browse/ELP-35) Implement survey UI + validation
    - [ELP-36](https://zpi-recruitment.atlassian.net/browse/ELP-36) Store responses + anonymization step

![EPIC ELP-3](path/to/image)

- **EPIC** [ELP-4](https://zpi-recruitment.atlassian.net/browse/ELP-4) Security, Reliability & MVP Reporting [16]

  - **STORY** [ELP-48](https://zpi-recruitment.atlassian.net/browse/ELP-48) SSO Login via Azure AD (No Local Passwords)
    - [ELP-49](https://zpi-recruitment.atlassian.net/browse/ELP-49) Configure Azure AD app registration (dev env)
    - [ELP-50](https://zpi-recruitment.atlassian.net/browse/ELP-50) Implement OIDC login callback + session
    - [ELP-51](https://zpi-recruitment.atlassian.net/browse/ELP-51) Protect routes/API endpoints with auth middleware

  - **STORY** [ELP-52](https://zpi-recruitment.atlassian.net/browse/ELP-52) GDPR: Consent + "Right to be Forgotten" Hard Delete [8]
    - [ELP-53](https://zpi-recruitment.atlassian.net/browse/ELP-53) Implement consent UI + persistence
    - [ELP-54](https://zpi-recruitment.atlassian.net/browse/ELP-54) Implement hard-delete endpoint + cascade rules

![EPIC ELP-3](path/to/image)

- **EPIC** [ELP-5](https://zpi-recruitment.atlassian.net/browse/ELP-5) External Integrations (MVP/PoC) [21]

  - **STORY** [ELP-37](https://zpi-recruitment.atlassian.net/browse/ELP-37) GitHub Account Linking (OAuth/Token) [5]
    - [ELP-38](https://zpi-recruitment.atlassian.net/browse/ELP-38) Implement "Connect GitHub" UI flow (token-based MVP)
    - [ELP-39](https://zpi-recruitment.atlassian.net/browse/ELP-39) Store token encrypted + user mapping
    - [ELP-40](https://zpi-recruitment.atlassian.net/browse/ELP-40) Implement disconnect/revoke functionality

  - **STORY** [ELP-41](https://zpi-recruitment.atlassian.net/browse/ELP-41) LinkedIn Publishing Connector (PoC) [8]
    - [ELP-42](https://zpi-recruitment.atlassian.net/browse/ELP-42) Implement OAuth token storage + refresh logic
    - [ELP-43](https://zpi-recruitment.atlassian.net/browse/ELP-43) Implement LinkedIn publish API client

  - **STORY** [ELP-44](https://zpi-recruitment.atlassian.net/browse/ELP-44) Notifications via Slack/Teams (Event-Based) [8]
    - [ELP-45](https://zpi-recruitment.atlassian.net/browse/ELP-45) Define event triggers + notification payload format
    - [ELP-46](https://zpi-recruitment.atlassian.net/browse/ELP-46) Implement notification dispatcher (in-app first)
    - [ELP-47](https://zpi-recruitment.atlassian.net/browse/ELP-47) Implement Slack/Teams webhook connector (optional)

![EPIC ELP-3](path/to/image)

### 1.2 Roadmapa dla EPICów

- Roadmapa w Jirze zaplanowana na 3 miesiące : [Employee Lifecycle Platform Roadmap](https://zpi-recruitment.atlassian.net/jira/software/projects/ELP/boards/1/timeline)

![Roadmap](path/to/image)

## 2. Proof of concept

PoC zajmie się głównie przetestowaniem głównych integracji między usługami Azure AD (Entra ID) - GitHub - LinkedIn.

- **Ścieżka 1 (Onboarding):** Weryfikacja mechanizmu **Smart Check**. System odbiera sygnał z Webhooka GitHub, parsuje ID zadania z wiadomości commita i automatycznie aktualizuje status postępu w bazie danych, przypisując go do zidentyfikowanego przez Azure AD pracownika.

- **Ścieżka 2 (Employer Branding):** System przesyła przygotowaną treść testową do zewnętrznego API LinkedIn, sprawdzając poprawność procesów OAuth (odświeżanie tokenów) oraz uprawnień do publikacji na stronie firmowej.

W obu ścieżkach sukcesem jest poprawna zmiana stanu w bazie danych lub na platformie zewnętrznej, potwierdzona powiadomieniem systemowym wysłanym do użytkownika.

## 3. Cel i zadania sprintu

### 3.1 Cel sprintu

Weryfikacja technicznej wykonalności integracji głównych elementów systemu poprzez wdrożenie : uwierzytelniania SSO Azure AD (Entra ID), powiązania konta GitHub oraz wykonania próbnej publikacji na LinkedIn w środowisku deweloperskim

### 3.2 Weryfikacja powodzenia sprintu

1. Wdrożona autoryzacja z użyciem SSO Azure AD (Entra ID)
2. Działające połączenie z testowym kontem na LinkedIn i możliwość publikacji treści na koncie developerskim
3. Możliwość połączenia konta użytkownika systemu z istniejącym kontem Github
4. System odznacza zadania jako wykonane w zależności od działania użytkownika na GitHubie

### 3.3 Zadania w sprincie

- Plan w Jira : [Sprint ELP-1](https://zpi-recruitment.atlassian.net/jira/software/projects/ELP/boards/1/backlog)

![Sprint](path/to/image)

- [ELP-48](https://zpi-recruitment.atlassian.net/browse/ELP-48) SSO Login via Azure AD (No Local Passwords)
- [ELP-41](https://zpi-recruitment.atlassian.net/browse/ELP-41) LinkedIn Publishing Connector (PoC)
- [ELP-23](https://zpi-recruitment.atlassian.net/browse/ELP-23) GitHub Webhook Integration & Automated Completion (“Smart Check”)
- [ELP-37](https://zpi-recruitment.atlassian.net/browse/ELP-37) GitHub Account Linking (OAuth/Token)
- [ELP-19](https://zpi-recruitment.atlassian.net/browse/ELP-19) Quest Path View for New Employees
- [ELP-44](https://zpi-recruitment.atlassian.net/browse/ELP-44) Notifications via Slack/Teams (Event-Based)
- [ELP-55](https://zpi-recruitment.atlassian.net/browse/ELP-55) GitHub Branch Validation & User Feedback Loop (“Smart Check")

## 5. Definition of Done

### Kod i Review

- Przeprowadzono **Code Review** przez przynajmniej jednego innego członka zespołu.
- Kod został zmergowany do odpowiedniego brancha
- Kod przeszedł pozytywnie skanowanie narzędziami do analizy statycznej wykrywającymi podatności security

### Testy i jakość

- Zadanie przechodzi testy jednostkowe (Unit Tests) dla kluczowej logiki.
- Manualna weryfikacja na środowisku lokalnym potwierdziła działanie funkcji.
- Brak błędów typu „Blocker” i „Critical” powiązanych z tym zadaniem.

### Dokumentacja

- Zaktualizowano dokumentacje odnośnie endpointów (jeśli uległy zmianie).
- Zaktualizowano schemat bazy danych (jeśli uległ zmianie).

## 6. Analiza Pre-Mortem

### 1. Problemy z SSO Azure AD (Entra ID)

- **Możliwe scenariusze**
  - Brak odpowiednich uprawnień Azure do rejestracji aplikacji
  - Błędna konfiguracja Redirect URI (powrót z Azure do aplikacji kończy się błędem 404/500)
- **Zadanie zależne**: ELP-48
- **Plan zapobiegawczy**
  - Weryfikacja dostępów do portalu Entra ID w pierwszym dniu sprintu
  - Przygotowanie lokalnego serwera Mock-OIDC do testów.

### 2. Brak możliwości publikacji na LinkedIn

- **Możliwe scenariusze**
  - Brak dostępu do Markieting Developer Platform
  - Wygaśnięcie tokena dostępu (Access Token) bez działającego mechanizmu odświeżania (Refresh Token)
- **Zadanie zależne**: ELP-41
- **Plan zapobiegawczy**
  - Złożenie wniosku o rozszerzone uprawnienia do API natychmiast po starcie Sprintu 1
  - Stworzenie developerskiego konta LinkedIn do testów
  - Implementacja logowania błędów API LinkedIn do bazy, aby od razu widzieć powód odrzucenia postu.

### 3. Wyciek kluczy dostępu GitHub do sieci

- **Możliwe scenariusze**
  - Przechowywanie tokenów GitHub w bazie danych w formacie plain text (czysty tekst)
  - Niezamierzone wypchnięcie sekretów aplikacji do publicznego repozytorium kodu.
- **Zadanie zależne**: ELP-37
- **Plan zapobiegawczy**
  - Obowiązkowe szyfrowanie AES-256 dla tabeli tokenów
  - Konfiguracja skanów security w celu wykrywania obecnych w nich kluczy API

### 4. Problemy z poprawną weryfikacją zadań

- **Możliwe scenariusze**
  - GitHub nie może połączyć się z aplikacją (aplikacja działa na localhost, a GitHub "nie widzi" jej z internetu)
  - Błędny parser wiadomości commita
- **Zadanie zależne**: ELP-23
- **Plan zapobiegawczy**
  - Upewnienie się, że endpointy są poprawnie widziane z poziomu sieci
  - Implementacja elastycznego parsera (Regex) oraz mechanizmu powiadomień
