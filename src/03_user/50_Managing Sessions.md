# Managing Sessions

**Sessions** are where high-level organization of **Machines**, **Services**, **Instances**, and **Clusters** takes place.
A Machine is the physical hardware running a Service, e.g. some software like TouchDesigner or Ableton Live or a lighting control system or even your microwave.

Multiple Instances of a Service can be running at the same time, either on the same Machine or different Machines.
Instances can be treated individually or as part of a Cluster (a group of Instances). We will see how this feature becomes useful when dealing with reactive event relationships that involve lots of Instances of a Service.

All of these organizational abstractions are couched in a particular Session, and you can have multiple Sessions active at once, for example, if you are designing a live show and want different sessions for pre-viz, rehearsal, and performance.  

> ### Window Groups
> In order to better manage multiple Sessions from the same client, they can be assigned to different Window Groups (differentiated by the color of the footer), meaning you can however many different windows of however many different sessions as you'd like.