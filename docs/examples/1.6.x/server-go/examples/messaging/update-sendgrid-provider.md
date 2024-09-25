package main

import (
    "fmt"
    "github.com/appwrite/sdk-for-go/client"
    "github.com/appwrite/sdk-for-go/messaging"
)

func main() {
    client := client.NewClient()

    client.SetEndpoint("https://cloud.appwrite.io/v1") // Your API Endpoint
    client.SetProject("<YOUR_PROJECT_ID>") // Your project ID
    client.SetKey("<YOUR_API_KEY>") // Your secret API key

    service := messaging.NewMessaging(client)
    response, error := service.UpdateSendgridProvider(
        "<PROVIDER_ID>",
        messaging.WithUpdateSendgridProviderName("<NAME>"),
        messaging.WithUpdateSendgridProviderEnabled(false),
        messaging.WithUpdateSendgridProviderApiKey("<API_KEY>"),
        messaging.WithUpdateSendgridProviderFromName("<FROM_NAME>"),
        messaging.WithUpdateSendgridProviderFromEmail("email@example.com"),
        messaging.WithUpdateSendgridProviderReplyToName("<REPLY_TO_NAME>"),
        messaging.WithUpdateSendgridProviderReplyToEmail("<REPLY_TO_EMAIL>"),
    )

    if error != nil {
        panic(error)
    }

    fmt.Println(response)
}