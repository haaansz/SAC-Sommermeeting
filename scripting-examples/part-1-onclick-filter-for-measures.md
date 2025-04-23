# Part 1 - On click Filter for Measures



<div align="center" data-full-width="true"><figure><img src="../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure></div>

Within this example we want to create some interactivity between the Tile up top and the Linechart below. When clicking on the Text the measure in the linechart should be replaced with the measure from the Tile calling.



## Lets get started

Please open the following dashboard and go to the edit mode and save the file to your [User Folder](https://zpartner-sac-1.eu10.hcs.cloud.sap/sap/fpa/ui/app.html#/files&/f/myfiles/15ECCD848CDFE846C9C217EBAF748FDD).

{% embed url="https://zpartner-sac-1.eu10.hcs.cloud.sap/sap/fpa/ui/app.html#/story2&/s2/76E0A7B1127EFD5B246E454C135444C6/?mode=edit" %}

After Saving the story, we go again into the Edit Mode -> then check out the outline. ( Remember to slide out the left panel )

<figure><img src="../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

Then find get the Tile for Gross Margin in the outline and find the scripting possibilities.

{% hint style="info" %}
PAN\_Main\_Content\_Chart1
{% endhint %}

Then for simplicity and later usage we are using two variables for the source and the target chart of this interaction.

```typescript
var SourceChart = PAN_Main_Content_Chart1;
var TargetChart = PAN_MAIN_S1_R2_CHART1;
```

Now we are storing the measure which is needed to be replaced in the target chart.

```typescript
var current_measure = TargetChart.getMembers(Feed.ValueAxis)[0];
```

In the final step we remove the measure and add the used measure from the source chart.

```typescript
TargetChart.removeMember(Feed.ValueAxis, current_measure);
TargetChart.addMember(Feed.ValueAxis, SourceChart.getMembers(Feed.ValueAxis)[0]);
```



Please check out the help for scripting functions by Pressing:

{% hint style="info" %}
STRG + SPACE
{% endhint %}

<div align="left"><figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure></div>

Also have a look at the available Functions on the chart object.

[https://help.sap.com/doc/1639cb9ccaa54b2592224df577abe822/release/en-US/index.html#Chart](https://help.sap.com/doc/1639cb9ccaa54b2592224df577abe822/release/en-US/index.html#Chart)

## Try your first script -> View Mode - Click on your Tile.

