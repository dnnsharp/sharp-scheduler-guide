# Actions

When a trigger fires, Sharp Scheduler will run the respective job. This basically means that all actions that a job has are executed in the specified order. If any action fails, then execution stops and the job is considered to have failed. This is marked in the job Last Ran section as well in History. An action fails if an exception is thrown. This can be intentionally to indicate a certain state such as a missing or invalid parameter. But they can also be unexpected and sometimes even obscure. Make sure to read the section on Debugging to see how errors can be tracked down. 

Sharp Scheduler comes with a dozen different action types and again, the order in which they are added to the list matters a lot for a few different reasons. First of all, Sharp Scheduler provides a shared context where Actions can store their data. This means that actions at the top can provide data for other actions down the stack to use. Think for example an SQL Action with an INSERT statement saving the ID of the newly created entity, so it can be further used to execute a initialization method using the Execute Method action.

Second, think about the errors handling behavior described in the first paragraph - if an action fails, execution stops and job is marked as failed. This means that some actions will get to execute before the error being thrown. It's therefore a good strategy to place the actions that are easier to undo at the top. So if it fails, it's easier to roll back and recover when needed.

![](All actions.png)

It's also worth mentioning that Sharp Scheduler providers a framework for new types of actions to be plugged in. This is for example how Search Boost provides several jobs for granular indexing of content. Make sure to read Extensions pages for more info.

The rest of this section goes through each of the core actions that ship with Sharp Scheduler.