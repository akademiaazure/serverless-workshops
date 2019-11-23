# Zadania

**1.Stwórz funkcję, która będzie co 30 sekund logowała datę/czas. Zmiana formatu daty powinna być możliwa bez zmian w kodzie \(format daty pobierany z ustawień aplikacji\).**

**2.Nie podobają Ci się narzędzia, takie jak Microsoft ToDo - są zbyt skomplikowane. Twoim zadaniem jest stworzenie własnej, prostej listy ToDo za pomocą Azure Functions. Aplikacja powinna zawierać poniższe funkcjonalności:** 

* Dodawanie zadań
* Zwracanie listy zadań
* Odznaczanie zadań
* Usuwanie zadań
* Wydzielenie listy zadań do Table Storage**\***

W podstawowej formie zadania zaimplementuj rozwiązanie na statycznej liście obiektów ToDo. Plik, który zawiera statyczną stronę do obsługi listy znajduje się w repozytorium [ToDos/index](https://raw.githubusercontent.com/akademia-azure/AzureServerlessWorkshops/master/ToDos/index.html).

**3.Twoja firma zatrudnia wielu pracowników. Coraz większym problemem staje się proces onboardingu. Zapadła decyzja, żeby spróbować zautomatyzować ten proces jak najmniejszym nakładem pracy. Wykorzystaj Azure Functions, żeby zaprojektować i zaimplementować takie rozwiązanie. Wymagania, jakie powinien spełniać projekt zostały wypisane poniżej.**

* Odebranie danych z formularza 
* Zapisanie danych do poszczególnych kolejek 
* Odebranie danych z kolejki i wyslanie maila - SendGrid \(wymagane wygenerowanie klucza API\) 
* Odebranie danych z kolejki i zapisanie danych do table storage 
* Hosting statycznej strony html w Storage Blob oraz stworzenie proxy**\***
  * Stworzenie Blob Storage i ustawienie go na static website 
  * Wrzucenie na static website plików z formularzem 
  * Dodanie proxy do Azure Functions 



