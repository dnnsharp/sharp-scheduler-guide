# Getting Started

This page guides you through setting up Sharp Scheduler to run the most simple job to be executed when certain event occur. Let's say you want to send an e-mail once at specified date and time.

1. Before you proceed make sure you have Sharp Scheduler installed on your portal. You can download it from Sharp Scheduler Download Page and install it from Host > Extensions screen.

2. Create a page and add Sharp Scheduler module on it as you normally would with any other module.

3. Locate and click the New Job button in order to create a new job

![](New Job.png)

4. Provide a unique name to your job 

![](Name your job.png)


5. Locate Add New Trigger drop-down button and choose One Time option from the Time category. (Notice that there is no limit on how many triggers a job can have).

![](Triggers.png)

6. So far, we told Sharp Scheduler what triggers should activate. Next, we'll tell it what action to execute when our trigger fires. In our scenario, we want to send an email to a specific email address. So in the Actions section, click Add Action button then select from the dropdown that activates below Notifications > Send Email.

![](Add action.png)