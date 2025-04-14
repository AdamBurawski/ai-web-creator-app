# Dokument wymagań produktu (PRD) - AutoWebBuilder

## 1. Przegląd produktu

AutoWebBuilder to innowacyjna aplikacja wspierająca web-developera, która automatyzuje proces budowy stron internetowych. Aplikacja analizuje przesłany projekt graficzny, a następnie:

- Generuje strukturę ACF w WordPressie,
- Tworzy odpowiadające komponenty w React/Gatsby,
- Integruje wygenerowane elementy z systemem CI/CD (GitHub, Netlify),
- Działa w architekturze multiagentowej, w której każdy agent odpowiada za określone zadania, takie jak analiza projektu, generowanie struktur ACF, tworzenie komponentów oraz triggerowanie builda.

Stack technologiczny obejmuje WordPress, ACF, React/Gatsby oraz Node.js z React/Vite, co umożliwia płynną i autonomiczną produkcję stron internetowych.

## 2. Problem użytkownika

Web-developerzy często spędzają dużo czasu na ręcznym tworzeniu struktury backendu (ACF) oraz frontendowych komponentów. Problemy te obejmują:

- Ręczne definiowanie pól ACF i konfiguracji strony,
- Brak spójności między backendem a frontendem,
- Długi czas wdrożenia wynikający z konieczności ręcznych interwencji.

AutoWebBuilder rozwiązuje te problemy poprzez automatyzację procesu interpretacji projektu graficznego, co znacząco skraca czas produkcji i redukuje ryzyko błędów.

## 3. Wymagania funkcjonalne

1. Analiza i interpretacja projektu graficznego za pomocą algorytmów AI.
2. Automatyczne generowanie struktury ACF w WordPressie na podstawie przesłanego projektu.
3. Automatyczne tworzenie komponentów w React/Gatsby odpowiadających elementom projektu graficznego.
4. Integracja wygenerowanych elementów backendu (ACF) z frontendem (React/Gatsby) w celu zapewnienia spójności działania strony.
5. Triggerowanie procesu budowania strony poprzez integrację z narzędziami CI/CD (GitHub, Netlify).
6. Architektura multiagentowa, gdzie każdy agent zarządza specyficznym zadaniem:
   - Agent do analizy projektu graficznego,
   - Agent do generowania struktury ACF,
   - Agent do tworzenia komponentów React/Gatsby,
   - Agent do integracji i monitorowania procesu builda.
7. Mechanizmy obsługi błędów, logowania oraz raportowania, które umożliwiają szybkie reagowanie na niepowodzenia procesu.
8. Uwierzytelnianie i autoryzacja użytkowników, gwarantujące bezpieczny dostęp do aplikacji i generowanych projektów.

## 4. Granice produktu

- Aplikacja skupia się wyłącznie na automatyzacji procesów związanych z budową stron za pomocą WordPressa (ACF) i React/Gatsby.
- Nie obejmuje pełnego hostingu ani zarządzania infrastrukturą serwerową WordPressa – integruje się z istniejącymi instalacjami.
- Interpretacja projektu graficznego opiera się na określonych algorytmach, co może ograniczać wsparcie dla niestandardowych lub zaawansowanych układów.
- Automatyzacja dotyczy standardowych projektów graficznych; nietypowe rozwiązania mogą wymagać manualnych poprawek.
- Produkt nie stanowi kompleksowego systemu CMS, a jedynie automatyzuje kluczowe elementy budowy strony.

## 5. Historyjki użytkowników

US-001
Tytuł: Przesłanie projektu graficznego
Opis: Jako web-developer chcę przesłać projekt graficzny do systemu, aby rozpocząć automatyczną analizę oraz generowanie struktury ACF i komponentów React/Gatsby.
Kryteria akceptacji:

- Użytkownik może przesłać plik projektu w obsługiwanym formacie.
- System potwierdza otrzymanie projektu i wyświetla podsumowanie analizy.

US-002
Tytuł: Automatyczne generowanie struktury ACF
Opis: Jako web-developer chcę, aby system automatycznie wygenerował strukturę ACF w WordPressie na podstawie przesłanego projektu, aby zaoszczędzić czas na ręcznej konfiguracji.
Kryteria akceptacji:

- Wygenerowana struktura ACF odpowiada elementom projektu graficznego.
- Struktura ACF jest testowalna przy użyciu testów integracyjnych.
- Użytkownik otrzymuje podsumowanie wygenerowanej struktury przed wdrożeniem.

US-003
Tytuł: Automatyczne tworzenie komponentów React/Gatsby
Opis: Jako web-developer chcę otrzymać gotowe komponenty React/Gatsby, które odpowiadają poszczególnym sekcjom projektu graficznego, aby przyśpieszyć proces tworzenia frontendu.
Kryteria akceptacji:

- System generuje komponenty zgodne z wymaganiami projektu.
- Użytkownik ma możliwość podglądu generowanych komponentów przed ich wdrożeniem.
- Komponenty są spójne z wygenerowaną strukturą ACF.

US-004
Tytuł: Integracja backendu z frontendem
Opis: Jako web-developer chcę, aby system zintegrował wygenerowaną strukturę ACF z komponentami React/Gatsby, zapewniając poprawne działanie strony.
Kryteria akceptacji:

- Po generowaniu struktury ACF, komponenty frontendowe są automatycznie powiązane z danymi.
- Proces integracji jest monitorowany, a ewentualne błędy są raportowane.
- System umożliwia walidację integracji poprzez testy symulujące działanie strony.

US-005
Tytuł: Triggerowanie procesu budowania strony
Opis: Jako web-developer chcę, aby system automatycznie triggerował proces budowania strony poprzez integrację z GitHub i Netlify, umożliwiając szybkie wdrożenie gotowej witryny.
Kryteria akceptacji:

- System wysyła sygnał do GitHub/Netlify po zakończeniu generacji elementów strony.
- Proces budowania jest logowany i monitorowany.
- Użytkownik otrzymuje powiadomienie o sukcesie lub niepowodzeniu builda.

US-006
Tytuł: Uwierzytelnianie i autoryzacja użytkownika
Opis: Jako użytkownik aplikacji chcę mieć możliwość bezpiecznego logowania się do systemu, aby chronić moje projekty i dane przed nieautoryzowanym dostępem.
Kryteria akceptacji:

- System obsługuje logowanie za pomocą email/hasła lub OAuth.
- Tylko uwierzytelnieni użytkownicy mają dostęp do generowanych danych.
- System definiuje role użytkowników oraz przypisane uprawnienia w celu ograniczenia dostępu do poszczególnych modułów.

## 6. Metryki sukcesu

1. Poprawność generowanej struktury ACF, potwierdzona testami integracyjnymi.
2. Spójność wyglądu i funkcjonalności wygenerowanych komponentów React/Gatsby z przesłanym projektem graficznym.
3. Redukcja czasu produkcji strony, mierzona statystykami buildów (np. skrócenie czasu o 50%).
4. Monitorowanie liczby błędów zgłaszanych podczas automatycznego procesu oraz szybkości ich naprawy.
5. Poziom satysfakcji użytkowników, mierzony ankietami oraz opiniami zwrotnymi.
6. Procent procesów zautomatyzowanych w stosunku do ręcznych interwencji.
