# Bindings

Creating a **Binding** instantiates the reactive relationship between an **Emitter** and a **Bundle**/**Action**. For **Simple Bindings**, whenever Rocketship receives a **Pulse** from the bound **Emitter**, it immediately triggers the **Bundles**/**Actions** bound to that **Emitter**.

Rocketship supports fine-grained control for creating **Complex Bindings** through **Node Graphs**. A **Node Graph** represents the logic and parameters that determine the nature of an interactive relationship.