# Opis usługi

Azure Functions umożliwia uruchamianie małych frogmentów kodu - funkcji w chmurze. Z ich pomocą możesz napisać kod rozwiązujący dany problem, bez potrzeby stawiania całej infrastruktury aplikacji. Ponadto usługa ta pozwala pisać kod w wielu językach programowania, takich jak:

* C\#
* Java
* Javascript
* PowerShell
* Python

Azure Functions daje sporo możliwości tworzenia oprogramowania. Pierwszą zaletą korzystania z tej usługi jest model płatności, w którym płacisz za ilość wywołań oraz czas pracy funkcji. Ponadto możliwe jest korzystanie z bibliotek - obsługiwane są rozwiązania NuGet oraz npm. Ważną zaletą tej usługi są również zintegrowane zabezpieczenia, które dostajemy out of the box. Za pomocą protokołu HTTP - za pośrednictwem dostawców uwierzytelniania OAuth, takich jak Azure Active Directory, Facebook, Google, Twitter i Microsoft Account.

Warto też wspomnieć, że Azure Functions jest Open Source, a cały kod dostępny jest w serwisie [GitHub](https://github.com/Azure/azure-functions-host).

Azure Functions oparte są o tzw. wiązania \(ang. bindings\). Dostępne mamy 3 typy wiązań:

* Trigger - wyzwalacz, który definiuje akcję po której dana funkcja się uruchomi
* Input - dane wejściowe, które przekazujemy do funkcji podczas jej wywołania
* Output - dane wyjściowe, które są zwracane przez funkcję

Przykłady wyzwalaczy:

* HttpTrigger - kod jest wyzwalany po otrzymaniu żądania HTTP
* TimerTrigger - kod jest wyzwalany w zadanych odstępach czasowych
* BlobTrigger, CosmosDBTrigger, QueueTrigger, EventGridTrigger, EventHubTrigger ServiceBusQueueTrigger,  ServiceBusTopicTrigger - kod jest wyzwalany po otrzymaniu nowych danych z danych usług lub ich aktualizacji

[Pełna lista wiązań i wsparcie dla poszczególnych typów.](https://docs.microsoft.com/en-in/azure/azure-functions/functions-triggers-bindings#supported-bindings)

![](../.gitbook/assets/image%20%2857%29.png)

