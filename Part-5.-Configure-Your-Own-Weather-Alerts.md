![Alert Setup](https://github.com/InitialState/wunderground-sensehat/wiki/img/AlertSetup.jpg)

Let's create a SMS alert whenever temperature drops below freezing.  

> _*Trigger notifications are currently in Alpha. Email contact@initialstate.com for an invitation to be a part of the Trigger development experience._

We are going to follow the Trigger notification setup process outlined at http://support.initialstate.com/knowledgebase/articles/834354-triggers-adding-a-trigger.  

1. Make sure your weather data bucket is loaded.
2. Click on the bucket's settings in the data shelf (under its name).
3. Click on the Triggers tab.
4. Select the data stream to trigger on (you can use the drop-down list to select from existing streams once a data bucket has loaded or you can type in the stream name/key manually; *note Safari does not support HTML5 dropdown lists). In my example screenshot above, I selected Temperature(F).
5. Select the conditional operator, in this case '<'.
6. Select the Trigger value that will trigger an action (manually type in the desired value). In this case, type in 32 as shown above.
7. Click the '+' button to add the Trigger condition.
8. Select the action (current actions available are notify by SMS or email).
9. Click the '+' button to add the action.
10. Input any verification code if adding a new phone number or email to complete setup.

Your trigger is now live and will fire when the condition is met. Click done to return to the main screen.

![PIR SMS](https://github.com/InitialState/wunderground-sensehat/wiki/img/AlertSMS.jpg)

Whenever temperature drops below 32, you will get a text message. You set alerts on anything in your weather data bucket (*note that you need to use emoji tokens, not the actual emojis).  For example, whenever it is raining 
```
:cloud: Weather Conditions = :umbrella:
```
Whenever it is windy 
```
:dash: Wind Speed(MPH) > 20)
``` 
etc.

[<< Part 4: (Bonus) Add a Map to Your Dashboard](Part-4.-Add-a-Map-to-Your-Dashboard)