# Managing Scenes

**Scenes** are the basic units of design for immersive experiences, and encapsulate sets of reactive event relationships.

Scenes are where you create **Bindings** between the **Emitters** and **Actions** of various **Targets**. Bindings live on the **Scene Graph**, and are made by connecting together different **Nodes**.

Scenes have various states. They can be armed and disarmed, and once armed, activated and deactived. The Bindings within a Scene are only live if the Scene is Active.

> NOTE: The same Scene can be in multiple states at the same time across different Sessions, but not within the same Session - within the same Session, latest takes precedence.

Once a Scene is activated, its Bindings are live - a Scene doesn't need to exist 'in time', it will run asynchronously until the scene is deactivated. 