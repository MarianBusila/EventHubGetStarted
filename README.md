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

- Create a storage acount with a container for EventHub checkpointing
```bash
az storage account create --name ehgetstartedstorage --resource-group EventHubsGetStarted --location eastus  --sku Standard_LRS
az storage container create -n eventhubcontainer --account-name ehgetstartedstorage --fail-on-exist
```

## Run the sender
 - set the required settings in local.settings.json and run Sender project
 
## Run the receiver
- set the required  settings in local.settings.json and run Receiver project
