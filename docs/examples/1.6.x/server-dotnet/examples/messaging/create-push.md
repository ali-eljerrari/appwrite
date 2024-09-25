using Appwrite;
using Appwrite.Models;
using Appwrite.Services;

Client client = new Client()
    .SetEndPoint("https://cloud.appwrite.io/v1") // Your API Endpoint
    .SetProject("<YOUR_PROJECT_ID>") // Your project ID
    .SetKey("<YOUR_API_KEY>"); // Your secret API key

Messaging messaging = new Messaging(client);

Message result = await messaging.CreatePush(
    messageId: "<MESSAGE_ID>",
    title: "<TITLE>",
    body: "<BODY>",
    topics: new List<string>(), // optional
    users: new List<string>(), // optional
    targets: new List<string>(), // optional
    data: [object], // optional
    action: "<ACTION>", // optional
    image: "[ID1:ID2]", // optional
    icon: "<ICON>", // optional
    sound: "<SOUND>", // optional
    color: "<COLOR>", // optional
    tag: "<TAG>", // optional
    badge: "<BADGE>", // optional
    draft: false, // optional
    scheduledAt: "" // optional
);