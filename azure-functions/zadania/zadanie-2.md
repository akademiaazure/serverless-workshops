# Zadanie 2

**Nie podobają Ci się narzędzia, takie jak Microsoft ToDo - są zbyt skomplikowane. Twoim zadaniem jest stworzenie własnej, prostej listy ToDo za pomocą Azure Functions. Aplikacja powinna zawierać poniższe funkcjonalności:**

* Dodawanie zadań
* Zwracanie listy zadań
* Odznaczanie zadań
* Usuwanie zadań
* Wydzielenie listy zadań do Table Storage**\***

W podstawowej formie zadania zaimplementuj rozwiązanie na statycznej liście obiektów ToDo. Plik, który zawiera statyczną stronę do obsługi listy znajduje się w repozytorium [ToDos/index](https://raw.githubusercontent.com/akademia-azure/AzureServerlessWorkshops/master/ToDos/index.html).

Tak jak w poprzednim zadaniu, tworzymy projekt Azure Functions, jednak w tym przypadku wybieramy Http Trigger.

Tworzymy statyczną - widoczną dla wszystkich funkcji listę Todos, która będzie przetrzymywała dane.

![](../../.gitbook/assets/image%20%2857%29.png)

Klasa ToDo powinna zostać zaimplementowana jak poniżej.

![](../../.gitbook/assets/image%20%2841%29.png)

Implementujemy teraz funkcjonalność. W HttpTrigger definiujemy AutorizationLevel, metodę requesta oraz routing. W tej funkcji zwracamy tylko listę Todos.

![](../../.gitbook/assets/image%20%2828%29.png)

Kolejna funkcja odpowiada za dodawanie danych do listy. Musimy podbrać dane z requesta - tym razem jest to post \(należy pobrać body\), zwalidować je i jeśli są poprawne - dodać nowy rekord do listy zadań.

![](../../.gitbook/assets/image%20%2830%29.png)

Kolejna funkcja odpowiada za usuwanie danych z listy. Tym razem musimy odczytać dane z query, z wysłanym parametrem - id. Sprawdzamy, czy taki obiekt istnieje - jeśli tak, usuwamy.

![](../../.gitbook/assets/image%20%283%29.png)

Ostatnia z funkcji odpowiada za zmianę stanu obiektu. Podobnie jak w przypadku delete - sprawdzamy czy obiekt istnieje - jeżeli tak zmieniamy mu wartość Checked na przeciwną do obecnej.

![](../../.gitbook/assets/image%20%2815%29.png)

Po uruchomieniu projektu oraz statycznej strony HTML możemy sprawdzić działanie funkcji.

![](../../.gitbook/assets/image%20%289%29.png)

**Uwaga!!! Należy się upewnić, że port na którym działają funkcje jest identyczny jak ten zdefiniowany w statycznej stronie HTML.**

![](../../.gitbook/assets/image%20%2836%29.png)

![](../../.gitbook/assets/image%20%2813%29.png)

**Ponadto, jeżeli w przeglądarce będą problemy z pobraniem zawartości a w konsoli będzie błąd związany z CORS, w local.settings.json należy dodać kod, jak na zdjęciu poniżej. Pozwoli on na wykonywanie żądań do funkcji z dowolnego adresu.**

![](../../.gitbook/assets/image%20%2893%29.png)

**Wydzielenie listy zadań do Table Storage\***

Zadanie należy zacząć od dodanie nugeta Microsoft.Azure.WebJobs.Extensions.Storage.

Następnie obiekt ToDo zmieniamy tak, aby dziedziczył z klasy TableEntity - dostarczonej przez zainstalowany uprzednio nuget.

![](../../.gitbook/assets/image%20%2864%29.png)

Dane będą przetrzymywane na lokalnym środowisku, za co odpowiada ustawienie AzureWebJobsStorage.

Zmieniamy pierwszą z funkcji tak, aby zwracała dane z Table Storage. Musimy stworzyć query, które będzie zwracało wszystkie dane ze zdefiniowanej przez nas tabeli. Ponadto dodajemy nowy parametr do funkcji - Table, który "połączy" ją ze zdefiniowaną przez nas tabelą. W połączeniu podajemy wartość z local.settings.json.

![](../../.gitbook/assets/image%20%2895%29.png)

W kolejnych przypadkach należy skorzystać z możliwości dodanego nugeta. Pamiętaj, aby dla każdego rekordu zdefiniować PartitionKey oraz RowKey. Poniżej funkcja dodania nowego rekordu.

![](../../.gitbook/assets/image%20%2831%29.png)

Funkcja usuwania danych.

![](../../.gitbook/assets/image%20%2885%29.png)

Funkcja zmiany stanu obiektu.

![](../../.gitbook/assets/image%20%2881%29.png)

Uruchamiamy projekt - wynik powinien być identyczny jak w pierwszym przypadku.

