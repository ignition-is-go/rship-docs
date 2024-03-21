# Configs

==In **Configs** view (N.B. Are we keeping this view 3d, or transforming it into 2d? Also, are we setting up automated/default configs?==, you will see the **Machines** and their **Executors** that are registered with Rocketship, and whether they are currently available (connected) or unavailable (disconnected). ==You must connect an available **Executor** to ...  (N.B. Remind me what they get connected to?)== in order for Rocketship to function.

Create a new **Configuration**. Notice that you can now change a session's configuration directly from the footer.

//

The **Configs** view includes four elements: **Machines**, **Instances**, **Services**, and **Clusters**. Each **Machine**, labeled by its unique **Machine ID**, hosts one or many **Instances**. You assign an **Instance** to a **Service**, which tells Rocketship how to route the **Actions** and **Emitters** for that **Service**.

**Instances** can be grouped into **Clusters**. By assigning a **Cluster** to a **Service**, the **Actions** and **Emitters** of that **Service** will be routed to every **Instance** of the **Cluster**. 