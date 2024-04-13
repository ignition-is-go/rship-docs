# Managing Scenes

**Scenes** are the basic units of design for immersive experiences, and encapsulate sets of reactive event relationships.

Scenes are where you create **Bindings** between the **Emitters** and **Actions** of various **Targets**. Bindings live on the **Scene Graph**, and are made by connecting together different **Nodes**. Actions and Emitters are Nodes, and Rocketship also provides a set of useful Utility Nodes for creating more complex Bindings and orchestrating reactive event relationships between different Scenes (see [Nodes]). 

Once a Scene is activated, its Bindings are live - a Scene doesn't need to exist 'in time', it will run asynchronously until the scene is deactivated. 