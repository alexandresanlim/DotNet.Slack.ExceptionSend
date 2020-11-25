# Slack Exception Send
[![Nuget](https://img.shields.io/nuget/dt/Slack.Exception.Send)](https://www.nuget.org/packages/Slack.Exception.Send)
[![Nuget](https://img.shields.io/nuget/v/Slack.Exception.Send)](https://www.nuget.org/packages/Slack.Exception.Send)

With this .net package you will be able to create a bug report with Slack application, inspect and track any issues your users run into while running your app.


# How to use?
It's really simple, send an error to be tracked as a handled exception using the function SendToSlack:
```csharp
try
{
    //your code here
}
catch (System.Exception ex)
{
    ex.SendToSlack();
}
```
Results in:

![alt text](https://i.imgur.com/Pc0MXIj.png)

# Getting Start

### Prepare your slack channel to receive the exceptions

1 - Install this [Nuget Package](https://www.nuget.org/packages/Slack.Exception.Send)

2 - Install and add a new configuration Incoming WebHooks Slack App:

![image](https://user-images.githubusercontent.com/5353685/94029386-21f5d400-fd93-11ea-9148-e29bee9993aa.png)

3 - Create a new configuration of Slack.Exception.Send
```csharp
public TestSendException()
{
    SendException.CreateConfig(new SendToSlackConfig
    {
        WebHookUrl = "YOUR WEBHOOK URL"
    });
}
```
4 - Finish! Now your aplication will be solid!

## <a name="many_field"/> Support for extra fields
```csharp
try
{
    throw new DivideByZeroException();
}
catch (System.Exception e)
{
    await e.SendToSlackAsync(new List<Webhooks.SlackField>
    {
         new Webhooks.SlackField
         {
             Title = "Username",
             Value = "Alexandre Sanlim",
             Short = true
         },
         new Webhooks.SlackField
         {
             Title = "S.O",
             Value = "Windows 10",
             Short = true
         },
         new Webhooks.SlackField
         {
             Title = "New Field 3",
             Value = "Hi, I'am a new long field to show in GitHub sample 😎",
         }
    });
}
```
Results in:

![alt text](https://i.imgur.com/sjXiF91.png)


[![forthebadge](https://forthebadge.com/images/badges/built-with-love.svg)](https://forthebadge.com)



