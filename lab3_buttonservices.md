# Lab 3 - Use Services

Use Azure Functions and Azure Logic Apps with messaging from the IoT Hub

Using Visual Studio 2017, add the extension:

* Connected Service for Azure IoT Hub

## Create a Logic App

Create a logic app, starting when a HTTP request is received.
The second action should be a tweet or an email.
Send the text *clicking on a button to send a tweet*.

Remember the URL of the logic app.

## Azure Function

Create a new Azure Function. This function will invoke the logic app by doing a HTTP request.

After creating the Function App, create a new Function that is triggered using *IOT Hub (Event Hub)* using C# code.

Change the implementation to the following code. Add the URL for the Logic App.

```csharp
using System;
using System.Text;

private static HttpClient s_client = new HttpClient();
private const string UrlForLogicApp = "";
public static void Run(string myIoTHubMessage, TraceWriter log)
{
    log.Info($"C# IoT Hub trigger function processed a message: {myIoTHubMessage}");
    var httpContent = new StringContent(myIoTHubMessage, Encoding.UTF8, "application/json");
    s_client.PostAsync(UrlForLogicApp, httpContent);
}
```

## Test it

Click the button