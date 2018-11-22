# Bot Seed template C# Version for DevOps
This bot has been created using [Microsoft Bot Framework](https://dev.botframework.com), [C#](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/) and [GitHub](https://github.com)

This samples shows how to:
Deploy a node Bot as DevOps(CD/CI) to be developed/deployed by a group of developers


# Install Your Bot locally
- Create in Azure Portal a [Basic node Bot, or Web Ap Bot](https://docs.microsoft.com/en-gb/azure/bot-service/bot-service-quickstart?view=azure-bot-service-4.0)
- Install [VSCode](https://code.visualstudio.com/Download) or any other code editor
- [Prepare the Bot to run locally in C#](https://docs.microsoft.com/en-us/azure/cognitive-services/luis/luis-csharp-tutorial-bf-v4)


## Run in Visual Studio
- Open the .sln file with Visual Studio.
- Press F5.
## Run in Visual Studio Code
- Open the bot project folder with Visual Studio Code.
- Bring up a terminal.
- Type 'dotnet run'.
## Testing the bot using Bot Framework Emulator
[Microsoft Bot Framework Emulator](https://aka.ms/botframework-emulator) is a desktop application that allows bot developers to test and debug
their bots on localhost or running remotely through a tunnel.
- Install the Bot Framework Emulator from [here](https://aka.ms/botframework-emulator).
### Connect to bot using Bot Framework Emulator
- Launch the Bot Framework Emulator
- File -> Open bot and navigate to the bot project folder
- Select `<your-bot-name>.bot` file

## Start the bot
Before changing any code or settings, verify the bot works. 
Create an appsettings.json file to hold the bot variables the bot code looks for:
```bash
{
    "botFilePath": "<copy value from App settings>",
    "botFileSecret": "<copy value from App settings>"
}
```
Set the values of the variables to the values you copied from the Azure bot service's Application Settings in Step 1 of the Download the [web app bot](https://docs.microsoft.com/en-us/azure/cognitive-services/luis/luis-csharp-tutorial-bf-v4#download-the-web-app-bot).

In Visual Studio, start the bot. A browser window opens with the web app bot's web site at http://localhost:3978/.

# Setup DevOPs : synchronise your Bot with Git Hub and Azure

Create a repo in Github with the name of your Bot but no documents
Download & Install GitBash](https://git-scm.com/downloads)
Get GitBash to access your GitHub account
Open GitBash on your local Bot Directory


```bash
{
  echo "# Your_Bot" >> README.md
  git init
  git add README.md
  git commit -m "first commit"
  git remote add origin https://github.com/your_repo.git
  git push -u origin master
  git add .
  git commit -m "Second commit to add all the files"
  git push -u origin --all
  code .
}
```

To add, commit and synchronise changes:
```bash
{
//adding changes
  git add .
  git commit -m "my commit description"
  git push //to push changes to git
}
```
You can find the botFilePath and botFileSecret in the Azure App Service application settings.


# Deploy this bot to Azure
## Publish from Visual Studio
- Open the .PublishSettings file you find in the PostDeployScripts folder
- Copy the userPWD value
- Right click on the Project and click on "Publish..."
- Paste the password you just copied and publish

## Publish using the CLI tools
You can use the [MSBot](https://github.com/microsoft/botbuilder-tools) Bot Builder CLI tool to clone and configure any services this sample depends on. 
To install all Bot Builder tools - 

Ensure you have [Node.js](https://nodejs.org/) version 8.5 or higher

```bash
npm i -g msbot chatdown ludown qnamaker luis-apis botdispatch luisgen
```
To clone this bot, run
```
msbot clone services -f deploymentScripts/msbotClone -n <BOT-NAME> -l <Azure-location> --subscriptionId <Azure-subscription-id>
```
# Further reading
- [Bot Framework Documentation](https://docs.botframework.com)
- [Bot basics](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-basics?view=azure-bot-service-4.0)
- [Activity processing](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-concept-activity-processing?view=azure-bot-service-4.0)
- [LUIS](https://luis.ai)
- [Prompt Types](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-prompts?view=azure-bot-service-4.0&tabs=javascript)
- [Azure Bot Service Introduction](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-overview-introduction?view=azure-bot-service-4.0)
- [Channels and Bot Connector Service](https://docs.microsoft.com/en-us/azure/bot-service/bot-concepts?view=azure-bot-service-4.0)
- [QnA Maker](https://qnamaker.ai)


## BotSeed - C# Version
