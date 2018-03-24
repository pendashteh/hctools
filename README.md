# hctools
Tools to build, run and test distributed applications using Holochain

# Introduction
`hctools` is a developer toolkit.
It has been designed to help a Holochain developer build, run and test their apps without un-necasseary struggles.
The most important one, **simulating a multi-node environment**.

These tools are either wrapper around the main `hc*` commands or they are helpers.

# Developer Journeies
Let's go through some of the very common *developer journeies* and see how the toolkit helps.

You can also jump to the section where we introduce tools, individually.

## Run your app on two browser tabs that simlulate two users
You've written the code and want to see if the app works for two users!

For that, we need to run two totally seperate instances of the app. Those instances are called a **node** or an **agent**.

To make it clean and simple, we will have two terminal windows open and run commands for every `agent` in its own terminal.

1. Let's create two agents first and call them `a1` and `a2`:
*Terminal 1:* `$ hcagent-init a1`
*Terminal 2:* `$ hcagent-init a2`

2. Now, let's install our app for both of them:
*Both Terminals:* `$ cd ~/dev/dapps/myapp`
*Terminal 1:* `$ hcadmin-agent a1 join . myapp`
*Terminal 2:* `$ hcadmin-agent a2 join . myapp`

3. Ok, ready to run the app?
Before we do so, we need to start the **Bootstrap Server (BS)**.
We need to keep Bootstrap Server running, so let's run it in a separete terminal:
*Terminal 3:* `$ bs --port=5001`

`bs` is a standard Holochain command. `hctools` is using `5001` as the BS port.

4. Finally it's time to run our apps, or better to say to get our agents run their node!
*Terminal 1:* `$ hcd-agent a1 myapp 3141`
*Terminal 2:* `$ hcd-agent a2 myapp 3142`

Cool, had fun? More journeies to come, stay tuned!

*Tip:* Did you know you can **Star** and **Watch** a project on Github at the same time?!

# Installation, Manual, Contribution, etc
They're all in the oven, in the meantime, enjoy dapping with Holochain with the above entrees!
