# Dokument wymagań produktu (PRD) - WebDevAI

## 1. Przegląd produktu

WebDevAI to innowacyjna aplikacja wspierająca web-developera, która automatyzuje proces budowy stron internetowych. Aplikacja analizuje przesłany projekt graficzny, a następnie:

- Generuje strukturę ACF w WordPressie,
- Tworzy odpowiadające komponenty w React/Gatsby,
- Integruje wygenerowane elementy z systemem CI/CD (GitHub, Netlify),
- Działa w architekturze multiagentowej, w której każdy agent odpowiada za określone zadania, takie jak analiza projektu, generowanie struktur ACF, tworzenie komponentów oraz triggerowanie builda.

Stack technologiczny obejmuje WordPress, ACF, React/Gatsby oraz Node.js, co umożliwia płynną i autonomiczną produkcję stron internetowych.

## 2. Problem użytkownika

Web-developerzy często spędzają dużo czasu na ręcznym tworzeniu struktury backendu (ACF) oraz frontendowych komponentów. Problemy te obejmują:

- Ręczne definiowanie pól ACF i konfiguracji strony,
- Brak spójności między backendem a frontendem,
- Długi czas wdrożenia wynikający z konieczności ręcznych interwencji,
- Powtarzalne zadania związane z tworzeniem komponentów UI na podstawie projektu graficznego,
- Konieczność ręcznego wdrażania zmian i uruchamiania procesów buildów.

WebDevAI rozwiązuje te problemy poprzez automatyzację procesu interpretacji projektu graficznego, co znacząco skraca czas produkcji i redukuje ryzyko błędów.

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
7. Panel administracyjny do zarządzania projektami i monitorowania statusu prac.
8. Mechanizmy obsługi błędów, logowania oraz raportowania, które umożliwiają szybkie reagowanie na niepowodzenia procesu.
9. Uwierzytelnianie i autoryzacja użytkowników, gwarantujące bezpieczny dostęp do aplikacji i generowanych projektów.
10. API umożliwiające integrację z istniejącymi systemami i workflow developerów.

## 4. Granice produktu

- Aplikacja skupia się wyłącznie na automatyzacji procesów związanych z budową stron za pomocą WordPressa (ACF) i React/Gatsby.
- Nie obejmuje pełnego hostingu ani zarządzania infrastrukturą serwerową WordPressa – integruje się z istniejącymi instalacjami.
- Interpretacja projektu graficznego opiera się na określonych formatach (PNG, JPG, WEBP).
- Automatyzacja dotyczy standardowych projektów graficznych; nietypowe rozwiązania mogą wymagać manualnych poprawek.
- Produkt nie stanowi kompleksowego systemu CMS, a jedynie automatyzuje kluczowe elementy budowy strony.
- System nie generuje treści strony, a jedynie strukturę i komponenty na podstawie projektu graficznego.
- Aplikacja nie zastępuje kompletnie pracy web-developera, lecz wspiera go w najbardziej czasochłonnych i powtarzalnych zadaniach.

## 5. Historyjki użytkowników

US-001
Tytuł: Rejestracja i logowanie użytkownika
Opis: Jako nowy użytkownik chcę zarejestrować się w systemie i utworzyć konto, aby móc korzystać z funkcji aplikacji.
Kryteria akceptacji:

- Użytkownik może utworzyć konto podając email, hasło i podstawowe dane.
- System weryfikuje unikalność adresu email w bazie danych.
- Użytkownik otrzymuje email z linkiem aktywacyjnym.
- Użytkownik może zalogować się po aktywacji konta.
- System oferuje również logowanie za pomocą OAuth (GitHub, Google).

US-002
Tytuł: Przesłanie projektu graficznego
Opis: Jako web-developer chcę przesłać projekt graficzny do systemu, aby rozpocząć automatyczną analizę oraz generowanie struktury ACF i komponentów React/Gatsby.
Kryteria akceptacji:

- Użytkownik może przesłać plik projektu w obsługiwanym formacie (PNG, JPG, WEBP).
- System potwierdza otrzymanie projektu i wyświetla podsumowanie analizy.
- Użytkownik może dodać opis projektu i określić podstawowe parametry.
- System informuje o szacowanym czasie analizy projektu.

US-003
Tytuł: Konfiguracja parametrów projektu
Opis: Jako web-developer chcę skonfigurować podstawowe parametry projektu przed rozpoczęciem analizy, aby zapewnić poprawne generowanie struktury ACF i komponentów.
Kryteria akceptacji:

- Użytkownik może określić nazwę projektu i jego opis.
- Użytkownik może zdefiniować docelowy serwer WordPress i dane dostępowe.
- Użytkownik może określić preferowany styl komponentów i biblioteki UI.
- System zapisuje konfigurację i stosuje ją w procesie generowania.

US-004
Tytuł: Automatyczne generowanie struktury ACF
Opis: Jako web-developer chcę, aby system automatycznie wygenerował strukturę ACF w WordPressie na podstawie przesłanego projektu, aby zaoszczędzić czas na ręcznej konfiguracji.
Kryteria akceptacji:

- Wygenerowana struktura ACF odpowiada elementom projektu graficznego.
- Struktura ACF jest testowalna przy użyciu testów integracyjnych.
- Użytkownik otrzymuje podsumowanie wygenerowanej struktury przed wdrożeniem.
- System umożliwia korektę i dostosowanie struktur ACF przed ich finalnym wdrożeniem.

US-005
Tytuł: Automatyczne tworzenie komponentów React/Gatsby
Opis: Jako web-developer chcę otrzymać gotowe komponenty React/Gatsby, które odpowiadają poszczególnym sekcjom projektu graficznego, aby przyśpieszyć proces tworzenia frontendu.
Kryteria akceptacji:

- System generuje komponenty zgodne z wymaganiami projektu.
- Użytkownik ma możliwość podglądu generowanych komponentów przed ich wdrożeniem.
- Komponenty są spójne z wygenerowaną strukturą ACF.
- System generuje również odpowiednie style dla komponentów (CSS/SCSS).

US-006
Tytuł: Integracja backendu z frontendem
Opis: Jako web-developer chcę, aby system zintegrował wygenerowaną strukturę ACF z komponentami React/Gatsby, zapewniając poprawne działanie strony.
Kryteria akceptacji:

- Po generowaniu struktury ACF, komponenty frontendowe są automatycznie powiązane z danymi.
- Proces integracji jest monitorowany, a ewentualne błędy są raportowane.
- System umożliwia walidację integracji poprzez testy symulujące działanie strony.
- Użytkownik otrzymuje dokumentację dotyczącą integracji i ewentualnych wymaganych dostosowań.

US-007
Tytuł: Triggerowanie procesu budowania strony
Opis: Jako web-developer chcę, aby system automatycznie triggerował proces budowania strony poprzez integrację z GitHub i Netlify, umożliwiając szybkie wdrożenie gotowej witryny.
Kryteria akceptacji:

- System wysyła sygnał do GitHub/Netlify po zakończeniu generacji elementów strony.
- Proces budowania jest logowany i monitorowany.
- Użytkownik otrzymuje powiadomienie o sukcesie lub niepowodzeniu builda.
- System udostępnia link do podglądu wdrożonej strony po zakończeniu procesu.

US-008
Tytuł: Podgląd i testowanie wygenerowanej strony
Opis: Jako web-developer chcę mieć możliwość podglądu i testowania wygenerowanej strony przed jej finalnym wdrożeniem, aby upewnić się, że spełnia wymagania projektu.
Kryteria akceptacji:

- System udostępnia środowisko testowe z podglądem wygenerowanej strony.
- Użytkownik może testować responsywność strony na różnych urządzeniach.
- System oferuje narzędzia do walidacji dostępności i wydajności strony.
- Użytkownik może zgłaszać problemy bezpośrednio z poziomu podglądu.

US-009
Tytuł: Zarządzanie projektami
Opis: Jako web-developer chcę mieć możliwość zarządzania swoimi projektami, aby śledzić ich status i historię zmian.
Kryteria akceptacji:

- Użytkownik widzi listę swoich projektów wraz z ich statusem.
- Użytkownik może edytować, usuwać i archiwizować projekty.
- System przechowuje historię zmian i wdrożeń dla każdego projektu.
- Użytkownik może eksportować dane projektu do formatu JSON/YAML.

US-010
Tytuł: Manualna korekta wygenerowanych elementów
Opis: Jako web-developer chcę mieć możliwość ręcznej korekty wygenerowanych elementów (ACF, komponenty), aby dopasować je do specyficznych wymagań projektu.
Kryteria akceptacji:

- System oferuje edytor do modyfikacji wygenerowanych struktur ACF.
- Użytkownik może edytować kod komponentów React/Gatsby.
- System waliduje wprowadzone zmiany pod kątem poprawności i spójności.
- Zmiany ręczne są uwzględniane w procesie budowania i wdrażania.

US-011
Tytuł: Eksport i import konfiguracji
Opis: Jako web-developer chcę mieć możliwość eksportu i importu konfiguracji projektu, aby móc wykorzystać ją w przyszłych projektach.
Kryteria akceptacji:

- Użytkownik może wyeksportować konfigurację projektu do pliku.
- Użytkownik może zaimportować konfigurację z pliku do nowego projektu.
- System dostosowuje zaimportowaną konfigurację do bieżącego projektu.
- Użytkownik może selektywnie wybierać elementy konfiguracji do importu.

US-012
Tytuł: Uwierzytelnianie i autoryzacja użytkownika
Opis: Jako użytkownik aplikacji chcę mieć możliwość bezpiecznego logowania się do systemu, aby chronić moje projekty i dane przed nieautoryzowanym dostępem.
Kryteria akceptacji:

- System obsługuje logowanie za pomocą email/hasła lub OAuth.
- Tylko uwierzytelnieni użytkownicy mają dostęp do generowanych danych.
- System definiuje role użytkowników oraz przypisane uprawnienia w celu ograniczenia dostępu do poszczególnych modułów.
- System umożliwia reset hasła i dwuskładnikowe uwierzytelnianie.

US-013
Tytuł: Raportowanie błędów i analityka
Opis: Jako web-developer chcę mieć dostęp do raportów błędów i analityki procesu, aby móc optymalizować workflow i identyfikować problematyczne obszary.
Kryteria akceptacji:

- System generuje szczegółowe logi i raporty dla każdego etapu procesu.
- Użytkownik ma dostęp do dashboardu z kluczowymi metrykami.
- System automatycznie wykrywa i sugeruje rozwiązania dla typowych problemów.
- Użytkownik może eksportować raporty do formatu CSV/PDF.

US-014
Tytuł: Integracja z istniejącymi systemami
Opis: Jako web-developer chcę mieć możliwość integracji WebDevAI z istniejącymi systemami i narzędziami, aby zachować spójność workflow.
Kryteria akceptacji:

- System udostępnia API do integracji z zewnętrznymi narzędziami.
- Użytkownik może skonfigurować webhooks dla kluczowych wydarzeń.
- System integruje się z popularnymi narzędziami CI/CD (GitHub Actions, GitLab CI).
- Dostępne są gotowe integracje z systemami zarządzania projektami (Jira, Trello).

US-015
Tytuł: Tworzenie i zarządzanie wersjami strony
Opis: Jako web-developer chcę mieć możliwość tworzenia i zarządzania wersjami strony, aby testować różne warianty i zachować historię zmian.
Kryteria akceptacji:

- Użytkownik może tworzyć nowe wersje projektu na podstawie istniejących.
- System umożliwia porównywanie różnych wersji projektu.
- Użytkownik może przywracać wcześniejsze wersje projektu.
- System umożliwia równoległe testowanie różnych wersji projektu.

## 6. Metryki sukcesu

1. Poprawność generowanej struktury ACF, potwierdzona testami integracyjnymi (cel: 95% zgodności z oczekiwaniami).
2. Spójność wyglądu i funkcjonalności wygenerowanych komponentów React/Gatsby z przesłanym projektem graficznym (cel: 90% zgodności wizualnej).
3. Redukcja czasu produkcji strony, mierzona statystykami buildów (cel: skrócenie czasu o 60% w porównaniu do tradycyjnego procesu).
4. Monitorowanie liczby błędów zgłaszanych podczas automatycznego procesu oraz szybkości ich naprawy (cel: automatyczne rozwiązanie 70% typowych błędów).
5. Poziom satysfakcji użytkowników, mierzony ankietami oraz opiniami zwrotnymi (cel: średnia ocena 4.5/5).
6. Procent procesów zautomatyzowanych w stosunku do ręcznych interwencji (cel: 80% automatyzacji).
7. Liczba aktywnych użytkowników i retencja (cel: 70% użytkowników powraca do aplikacji w ciągu miesiąca).
8. Czas potrzebny na wdrożenie wygenerowanej strony (cel: 90% projektów wdrożonych w ciągu 24 godzin od przesłania projektu graficznego).
9. Liczba udanych integracji z zewnętrznymi systemami (cel: bezproblemowa integracja z 95% popularnych narzędzi CI/CD).
10. Stabilność działania aplikacji mierzona czasem bezawaryjnej pracy (cel: 99.9% dostępności).
