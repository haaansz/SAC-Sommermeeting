# Part 3 Details Page Measure Selection

Now we want to allow the users to switch the measures on the details page:

![](<../.gitbook/assets/image (4).png>)

We are using a Dropdownbox which needs to be filled first.&#x20;

If you want this Dropdown to be populated at the start we will need to use the onInitialization

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

Here we redirect to a init function in a script object to fill the Dropdown:

```
UTIL_Init.initDropdowns();
```

Function initDropdowns():

```typescript
var measures = DP1.getDataSource().getMembers("Account_BestRunJ_sold");

// Check out F12 -> Console 
console.log(measures);

for (var i = 0; i < measures.length; i++) {
    DROP_Measure.addItem(measures[i].id,measures[i].description);
	DROP_Measure.setSelectedKey(PAN_MAIN_S2_Chart1.getMembers(Feed.ValueAxis)[0]);
}
```

In a first step we define a variable to hold all measures from the Datasource.&#x20;

{% hint style="info" %}
After entering getMembers( you can also use the shortcut Strg + Space to help you with the account dimension.
{% endhint %}

The Dropdown should be filled during startup of the story, now we need to script the interaction with the charts on the detail page.

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

Currently you wouldn't see the details page, because its hidden in design time. Click on the eye symbol to make it visible.

{% hint style="info" %}
This visibility is only for the design time, the visibility during view time is set in the styling panel of the objects.&#x20;

![](<../.gitbook/assets/image (1) (1) (1).png>)
{% endhint %}

To script the interaction are using the Dropdown:

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

```typescript
PAN_MAIN_S2_Chart1.removeMember(Feed.ValueAxis,PAN_MAIN_S2_Chart1.getMembers(Feed.ValueAxis)[0]);
PAN_MAIN_S2_Chart1.addMember(Feed.ValueAxis,this.getSelectedKey());
PAN_MAIN_S2_TAB1.getDataSource().setDimensionFilter(Alias.MeasureDimension,this.getSelectedKey());
```
