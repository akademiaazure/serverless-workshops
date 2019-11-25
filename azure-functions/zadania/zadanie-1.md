# Zadanie 1

**Stwórz funkcję, która będzie co 30 sekund logowała datę/czas. Zmiana formatu daty powinna być możliwa bez zmian w kodzie \(format daty pobierany z ustawień aplikacji\).**

Uruchamiamy Visual Studio i wybieramy Azure Functions.

![](../../.gitbook/assets/image%20%285%29.png)

W kolejnym kroku nadajemy jej nazwę, po czym wybieramy odpowiedni trigger - Timer trigger. Będzie się on wyzwalał, co pewien - zdefiniowany w formacie CRON czas. Ustawiamy mu uruchamianie się co 30 sekund i klikamy Create.

![](../../.gitbook/assets/image%20%2867%29.png)

Tworzy nam się podstawowa funkcja, która loguje czas co 30 sekund.

![](../../.gitbook/assets/image%20%2856%29.png)

Należy teraz ją zdefiniować tak, aby dało się ustalić jej format daty, z możliwością edycji - bez ingerencji w kod funkcji. Aby to zrobić należy dodać odpowiedni setting w pliku local.settings.json, na przykład "Format".

![](../../.gitbook/assets/image%20%2846%29.png)

Następnie należy odczytać zdefiniowane ustawienie. Najprościej jest to zrobić za pomocą Environment.GetEnvironmentVariable\("nazwaKlucza"\). Możemy teraz skorzystać z naszej zmiennej przy formacie daty.

![](../../.gitbook/assets/image%20%2833%29.png)

Uruchamiamy funkcję. Powinna ona teraz zwracać czas w zdefiniowanym wcześniej formacie.

![](../../.gitbook/assets/image%20%287%29.png)

