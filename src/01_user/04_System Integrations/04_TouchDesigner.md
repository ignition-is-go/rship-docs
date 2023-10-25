# Touch Designer

1. Download the RshipTouchdesignerExec.tox from GitHub Releases
2.  Import the .tox into your TouchDesigner project.
3. Add an 'rship' label to every BaseCOMP you wish to appear in Rocketship as a Target. Verify the BaseCOMP appears as a Target in the Rocketship GUI.
4. The custom parameters of labeled BaseCOMPs will appear in Rocketship as Targets. Create a custom parameter and verify it appears in the Rocketship GUI.
5. Bind another parameter to the custom parameter
	1. Right-click on an 'rship'-labeled BaseCOMP and choose 'Customize Component'.
	2. Enter a 'Par Name' and choose the parameter's data type and number of values.
	3. Identify the parameter in your TouchDesigner patch you wish to expose to Rocketship. 
		1. Right-click on the parameter and click 'Copy Parameter'
		2. Navigate back to the 'rship'-labeled BaseCOMP, right-click on the custom parameter you just created, and choose 'Paste Bind'
6. Save the file :)
7. Verify that the custom parameter appears in the Rocketship GUI as a SubTarget. 
8. To export the output of a node to a custom parameter, activate the node, drag it to the parameter name, and choose 'Export'.

**NOTE: If Targets/SubTargets are not appearing in Rocketship, navigate to the 'rship' BaseCOMP and pulse Reconnect.**