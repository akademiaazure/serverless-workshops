# Zadania

**1.Zaprojektuj rozwiązanie** [**onboardingu z zadania 3 - Azure Functions**](../../azure-functions/zadania/) **za pomocą Event Grid. Poniżej znajdziesz wymagania jakie powinno spełniać Twoje rozwiązanie:**

* Submitter - Azure Function, który wrzuca event do EventGrid
* Subscriber - Logic App, który odbiera zdarzenie z Event Grid, następnie:
  * Dodaje wpis do Azure Storage Table.
  * Wysyła maila z powiadomieniem o przejściu procesu onboardingowego.

\*\*\*\*

