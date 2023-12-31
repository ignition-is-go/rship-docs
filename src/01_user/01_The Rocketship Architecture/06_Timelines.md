# Timelines

A **Scene** encapsulates both a **Node Graph** and a **Timeline**, thus introducing a higher level of organizational control over reactive relationships. 

The **Timeline** locally sequences the evolution of a reactive relationship. Each **Node** from the **Node Graph** is represented as a discrete 'lane', and keyframe-like markers placed on each 'lane' indicate at what point the **Node** should execute.

When a **Scene** is activated, its **Timeline** begins immediately, and the **Timeline** of one **Scene** can be configured to activate other **Scenes**.
