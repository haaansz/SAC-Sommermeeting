# Part 1 - Onclick Filter for Measures



<div align="center" data-full-width="true"><figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure></div>

Within this example we want to create some interactivity between the Tile up top and the Linechart below. When clicking on the Text the measure in the linechart should be replaced with the measure from the Tile calling.



## Lets get started

Please open the following dashboard and go to the edit mode and save the file to your [User Folder](https://zpartner-sac-1.eu10.hcs.cloud.sap/sap/fpa/ui/app.html#/files&/f/myfiles/15ECCD848CDFE846C9C217EBAF748FDD).

{% embed url="https://zpartner-sac-1.eu10.hcs.cloud.sap/sap/fpa/ui/app.html#/story2&/s2/76E0A7B1127EFD5B246E454C135444C6/?mode=edit" %}

After Saving the story, we go again into the Edit Mode -> then check out the outline. ( Remember to slide out the left panel )

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

Then find get the Tile for Gross Margin in the outline and find the scripting possibilities.

{% hint style="info" %}
PAN\_Main\_Content\_Chart1
{% endhint %}

Then for simplicity and later usage we are using two variables for the source and the target chart of this interaction.

```
var SourceChart = PAN_Main_Content_Chart1;
var TargetChart = PAN_MAIN_S1_R2_CHART1;
```

```
// set variable with current measure of the target chart ( needed for Removal in next line )
var current_measure = TargetChart.getMembers(Feed.ValueAxis)[0];
```

```
TargetChart.removeMember(Feed.ValueAxis, current_measure);
TargetChart.addMember(Feed.ValueAxis, SourceChart.getMembers(Feed.ValueAxis)[0]);
```

