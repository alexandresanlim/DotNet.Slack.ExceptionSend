# Ex.SendToSlack() (Slack.Exception.Send)

## <a name="very_simple"/> Very Simple
```csharp
try
{
    throw new DivideByZeroException();
}
catch (System.Exception ex)
{
    ex.SendToSlack();
}
```
## <a name="result"/>It's the Awesome Result:

![alt text](https://i.imgur.com/Pc0MXIj.png)


