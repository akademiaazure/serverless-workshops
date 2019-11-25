# Zadanie 1

**Zaprojektuj proces onboardingu z** [**zadania 3 - Azure Functions** ](../../azure-functions/zadania/)**z wykorzystaniem LogicApps.**

Przechodzimy do Portalu Azure i tworzymy nową usługę Logic App.

![](../../.gitbook/assets/image%20%2872%29.png)

![](../../.gitbook/assets/image%20%2819%29.png)

Przechodzimy do nowo stworzonej usługi i wybieramy Trigger HTTP.

![](../../.gitbook/assets/image%20%2811%29.png)

Po przejściu do Logic App Designer musimy podać JSON Schema, która definiuje format danych odbieranych przez endpoint. Najprościej jest to zrobić poprzez podanie przykładowego pliku JSON. \(dane w formacie JSON możemy pobrać z kolejek w Storage Account\)

![](../../.gitbook/assets/image%20%28103%29.png)

![](../../.gitbook/assets/image%20%2891%29.png)

Następnie dodajemy kolejny krok, wyszukujemy Table Storage i wybieramy akcję Insert Entity.

![](../../.gitbook/assets/image%20%2852%29.png)

Następnie należy połączyć się z odpowiednim Storage Account, stworzonym na potrzeby warsztatów oraz podać nazwę połączenia.

![](../../.gitbook/assets/image%20%2837%29.png)

Po połączeniu z odpowiednim Storage Account należy podać nazwę tabeli oraz dane które zostaną zapisane do Table Storage. 

![](../../.gitbook/assets/image%20%2897%29.png)

PartitionKey ustawiamy domyślnie jako onboardingTable, natomiast do RowKey przypisujemy losowo wygenerowany guid za pomocą expression: guid\(\).

![](../../.gitbook/assets/image%20%281%29.png)

Kolejną akcją będzie wysłanie maila za pomocą SendGrid. 

![](../../.gitbook/assets/image%20%2828%29.png)

Aby połączyć się z usługą SendGrid należy podać nazwę połączenia oraz wygenerowany wcześniej ApiKey.

![](../../.gitbook/assets/image%20%2885%29.png)

Po stworzeniu połączenia przechodzimy do konfiguracji wiadomości jaka będzie wysyłana dla użytkowników po zakończeniu procesu onboardingu.

![](../../.gitbook/assets/image%20%282%29.png)

Po zapisaniu stworzonego przepływu w triggerze zostanie wygenerowany adres URL pod którym Logic App będzie nasłuchiwał na nadchodzące zapytania.

![](../../.gitbook/assets/image%20%2873%29.png)

Aby przetestować poprawne działanie przepływu należy zmodyfikować formularz zmieniając adres URL w pliku /js/main.js.

![](../../.gitbook/assets/image%20%28102%29.png)

W każdej chwili możemy uruchomić podgląd przepływu na żywo za pomocą przycisku Run. Podgląd informuję o tym która z akcji przebiegła pomyślnie, a gdzie wystąpił błąd.

![](../../.gitbook/assets/image%20%2844%29.png)

Po naciśnięciu na konkretną akcję możemy sprawdzić jej szczegóły i dowiedzieć się więcej o występujących błędach.

![](../../.gitbook/assets/image%20%2881%29.png)

