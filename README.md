# EventHubs - Get started

## Create EventHubs resources

- Create a resource group 
```bash
az group create --name EventHubsGetStarted --location eastus
```

- Create an Event Hubs namespace
```bash
az eventhubs namespace create --name EventHubsGetStartedNamespace --resource-group EventHubsGetStarted --location eastus
```

- Create an event hub
```bash
az eventhubs eventhub create --name MyEventHub --resource-group EventHubsGetStarted --namespace-name EventHubsGetStartedNamespace --message-retention 1 --partition-count 2
```

- Get the connection string from EventHubsGetStartedNamespace -> Shared access policies -> RootManageSharedAccessKey -> Connection string-primary key