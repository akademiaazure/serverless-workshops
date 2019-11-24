# Zadanie 3

**Twoja firma zatrudnia wielu pracowników. Coraz większym problemem staje się proces onboardingu. Zapadła decyzja, żeby spróbować zautomatyzować ten proces jak najmniejszym nakładem pracy. Wykorzystaj Azure Functions, żeby zaprojektować i zaimplementować takie rozwiązanie. Wymagania, jakie powinien spełniać projekt zostały wypisane poniżej.**

* Odebranie danych z formularza 
* Zapisanie danych do poszczególnych kolejek 
* Odebranie danych z kolejki i wyslanie maila - SendGrid \(wymagane wygenerowanie klucza API\) 
* Odebranie danych z kolejki i zapisanie danych do table storage 
* Hosting statycznej strony html w Storage Blob oraz stworzenie proxy**\***
  * Stworzenie Blob Storage i ustawienie go na static website 
  * Wrzucenie na static website plików z formularzem 
  * Dodanie proxy do Azure Functions

Uruchamiamy Visual Studio i tworzymy nowy projekt - Azure Functions.

![](../../.gitbook/assets/image%20%282%29.png)

### Funkcja 1 - ReceiveDataFromForm.cs

W kolejnym kroku tworzymy pierwszą funkcję do obsługi zapytania i wysłania danych do dwóch kolejek. Nadajemy jej nazwę, po czym wybieramy odpowiedni trigger - HttpRequest. Będzie się on wyzwalał w momencie gdy wyślemy zapytanie na określony adres URL. Dla uproszczenia wybieramy Authorization Level: Anonymous.

![](../../.gitbook/assets/functions-ex3-1.png)

Authorization level pozwala nałożyć autoryzacje na funkcje. Są 3 poziomy autoryzacji:

* Anonymous - funkcja dostępna publicznie
* Function - autoryzacja odbywa się na podstawie klucza przypisanego do poszczególnej funkcji \(Function Key\)
* Admin - autoryzacja odbywa się na podstawie klucza przypisanego do danego Function App \(Master Key\) 

Następnie instalujemy biblioteki potrzebne przekazania wiadomości do kolejek oraz obsługi wysyłki maili.

![](../../.gitbook/assets/image%20%2838%29.png)

Kolejnym krokiem będzie utworzenie modelu, za pomocą którego nastąpi deserializacja danych z Body requestu.

![](../../.gitbook/assets/image%20%2831%29.png)

Mając model możemy już pobrać dane z zapytania, następnie je zwalidować i przesłać do odpowiednich kolejek.

![](../../.gitbook/assets/image%20%2833%29.png)

### Stworzenie kolejek lokalnie

Dla uproszczenia stworzymy kolejki lokalnie za pomocą programu Azure Storage Explorer.

![](../../.gitbook/assets/image%20%2821%29.png)

![](../../.gitbook/assets/image%20%288%29.png)

Aby przetestować stworzoną funkcję należy uruchomić Azure Function App lokalnie. W konsoli dostaniemy informacje o funkcjach oraz ich adresach.

![](../../.gitbook/assets/image%20%2818%29.png)

Do wysłania zapytania możemy skorzystać z programu Postman lub wykorzystując gotowy formularz. W przypadku wykorzystania gotowego formularza należy wstawić adres URL funkcji w pliku /js/main.js.

![](../../.gitbook/assets/image%20%2834%29.png)

### Funkcja 2 - SaveToTableStorage.cs

Kolejnym krokiem będzie dodanie funkcji, która odbiera wiadomości z kolejki tableQueue i zapisuje dane do Table Storage.

