# Emitters, Pulses, and Actions

Each **Target** registers its own **Emitters** and **Actions**. An **Emitter** observes the **Target** and sends a **Pulse** *to* Rocketship whenever its state changes. Conversely, an **Action** is a command sent *from* Rocketship that sets the state of the **Target**.