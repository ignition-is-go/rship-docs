# Unreal

Rocketship's Unreal Engine integration is facilitated by the Rship-Unreal plugin.

**Installing and Configuring the Plugin**

1. Download and unzip the Rship-Unreal plugin.
2. Create a 'Plugins' folder in your Unreal project directory, next to the .uproject file (it may already exist), and place the extracted Rship-Unreal folder in the Plugins folder.
3. Open an Unreal project and verify the Rship-Unreal plugin is active in the Plugins Manager (you may need to restart Unreal).
4. Open Project Settings and change the Project Game Instance Class to RshipGameInstance.
5. Find the 'Rship Exec' item in the left sidebar of Project Settings.
6. Change the Rocketship Host field to the address of the Rocketship server you wish to connect with.
7. Optionally, set the Service Color.

**Registering a Target**

1. Open the Event Graph of an Actor Blueprint and add the RshipTarget component. Rename the component, which will be the name of the **Target** that appears in Rocketship for that Actor.
2. Add an Rship Bind Action node to the Event Graph and connect the **Target** component.
3. Name the Action ID of the node.
4. Drag off the Float Callback inlet and create a Custom Event node.
6. Connect the Execution Line and Data outlets.

**Using the Target in Rocketship**

1. In a browser, navigate to the Rocketship server address.
2. Create a project.
3. Connect the Config.
4. Create a **Bundle**.
5. Drag an **Action** from the Actor **Target** into the **Bundle**.
6. Set the value of the **Action**.
7. Send the **Bundle**.
8. Verify that the value changes in Unreal Engine.

