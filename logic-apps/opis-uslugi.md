# Opis usługi

Azure Logic Apps to usługa, która pomaga zaplanować, zautomatyzować i organizować zadania lub procesy biznesowe, gdy trzeba zintegrować aplikacje, dane, systemy i usługi między przedsiębiorstwami lub organizacjami. Usługa ułatwia projektowanie i tworzenie skalowalnych rozwiązań na potrzeby integracji aplikacji, danych, systemów, usług oraz komunikacji między firmami \(B2B\), zarówno w chmurze, jak i środowisku lokalnym.

Każdy przepływ rozpoczyna się od wyzwalacza, który jest aktywowany, gdy zajdzie określone zdarzenie.

Po każdym aktywowaniu wyzwalacza usługa uruchamia akcje przepływu pracy. Te akcje mogą również obejmować konwersje danych i kontrole przepływów, na przykład instrukcje warunkowe, instrukcje switch, pętle i rozgałęziania. Przykładem może być plik, który jest wrzucany na Storage Account. Jeśli wyzwalacz wykryje zdarzenie zgodne z tymi kryteriami, aktywuje się i uruchamia akcje przepływu pracy. W tym przypadku akcje obejmują transformacje XML, aktualizacje danych, rozgałęzienia decyzji i powiadomienia e-mail.

Budowa Logic Apps

![](../.gitbook/assets/workflow%20%283%29.png)

Logic Apps można tworzyć wizualnie za pomocą Logic Apps Designer dostępnego w Portalu Azure lub w programie Visual Studio. Każdy Logic App jest tak naprawdę plikiem JSON, zawierającym jego definicję. W bardziej skomplikowanych przypadkach Logic Apps tworzy się za pomocą edycji pliku JSON zawierającego definicję przepływu.

