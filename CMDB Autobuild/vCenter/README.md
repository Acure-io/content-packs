## vCenter Topology

The script works with the events "vim.event.TopologyEvent" obtained with the data stream monq of type vCenter.

To run the script, do the following:
1. Create, configure, and run the vCenter data stream.
2. Create a new script for automation and create its content in the `base64` format.
    > When creating, select the same Workgroup as the Stream as the owner of the Scenario.
3. Open the Script and at the very beginning, in the "FilterByStreamId" block *(usually the third one)*, replace the "StreamId" value with the Stream Id *(you can get it from the Data Stream page)*.
4. Compile and activate the script, wait for the data to be received in the stream - the script will intercept the data from the stream and automatically create a DSM using the received topology.

### Features of the script work

* When creating new CIs, the script adds to them the `"source" label: "vCenter"`, and when updating and archiving CIs, the script filters objects by this label within its Workgroup. **So**, CIs that do not have the tag `"source" label: "vCenter"` or that are not in the script's Workgroup will not be processed.
* In the last stage of topology event processing, the script archives all the CIs that have not been created or updated in the current script run. **So**, it is not possible to add CIs from two different topology events simultaneously within a **single** WG.
* The name of a RCM CI must be unique not only within the Workgroup, but also within the whole Userspace. **So** if the same SM are configured for two Workgroups from vCenter, the CI names of one of them will have indexes in the name *(e.g., vm-app-01 `(2)`)*.