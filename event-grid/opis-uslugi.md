# Opis usługi

Azure Event Grid to zarządzana platforma oparta o zdarzenia, która umożliwia reagowanie w czasie rzeczywistym na zmiany zachodzące w aplikacjach hostowanych na platformie Azure lub dowolnych posiadanych zasobach platformy Azure.

Aby otrzymać powiadomienie o zmianie stanu, \(na przykład nowy rekord w bazie danych\) zwykle myślisz o zaplanowanym lub ciągłym odpytywaniu. Oznacza to, że stale zużywasz moc obliczeniową do monitorowania wszystkich zmian.

Dzięki usłudze Azure Event Grid możesz o tym zapomnieć. Umożliwia ona wysyłanie zdarzeń, podczas nastąpienia zmiany stanu. Każdy komponent, który subskrybuje zdarzenia, może otrzymywać powiadomienia bez odpytywania, co zmniejsza poprzednie wymagane zasoby sprzętowe. Event Grid, obsługuje wbudowane zdarzenia platformy Azure, a także zdarzenia niestandardowe z aplikacji i publikuje je w czasie rzeczywistym. Może dynamicznie skalować i obsługiwać miliony zdarzeń na sekundę.

Pojęcia przydatne przy pracy z Azure Event Grid:

* **Event** — zdarzenie, które wystąpiło.
* **Event sources**  — źródło zdarzenia.
* **Topics** — endpoint, do którego wysyłane są zdarzenia.
* **Event Subscription** — endpoint lub wbudowany mechanizm przekierowywania zdarzeń, czasami do więcej niż jednego handlera. Subskrypcje są również używane przez handlery w celu inteligentnego filtrowania przychodzących zdarzeń.
* **Event Handlers** — aplikacje lub usługi reagujące na zdarzenia

![](../.gitbook/assets/image%20%2851%29.png)

