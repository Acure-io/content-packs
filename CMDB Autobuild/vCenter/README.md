## vCenter Topology

The script works with the events "vim.event.TopologyEvent" obtained with the Data Stream monq of type vCenter.
This scenario processes "vim.event.TopologyEvent" events received from the Data Stream using vCenter template.

In order to run scenario, do the following:
1. Create, configure, and run the vCenter Data Stream.
2. Create a new scenario for automation and import its content in the `base64` format.
    > In the form of creating scenario, select the same Workgroup as the Data Stream belongs to.
3. Open the scenario, in the "FilterByStreamId" block *(usually the third one)*, replace the "StreamId" value with the Stream Id. You can get it on the Data Stream page.
4. Compile and activate scenario, wait for the data to be received into the stream. The scenario will intercept the data from the stream and automatically create a SM Map using the received topology.

### Features of the scenario execution

* During the creation of new CIs, this scenario adds them `"source": "vCenter"` label. When updating and archiving CIs, scenario filters objects by this label within its Workgroup. **For this reason**, CIs, which do not have the `"source": "vCenter"` label or do not belong to the Scenario's Workgroup, will not be processed. 
* At the last stage of topology event processing, the scenario archives all the CIs that have not been created or updated in the current scenario run. **For this reason**, it is not possible to add CIs from two different topology events simultaneously within a **single** Workgroup.
* The name of the SM Map's CI must be unique not only within the Workgroup, but also within the whole Userspace. If the same SM Map is configured for two Workgroups from vCenter, of one of the CIs' names will contain indexes *(e.g., vm-app-01 `(2)`)*.
