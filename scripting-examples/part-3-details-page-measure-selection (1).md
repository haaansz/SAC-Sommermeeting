# Part 3 Details Page Measure Selection

Now we want to allow the users to switch the measures on the details page:

![](<../.gitbook/assets/image (4) (1).png>)

We are using a Dropdownbox which needs to be filled first.&#x20;

If you want this Dropdown to be populated at the start we will need to use the onInitialization script which is executed on startup.

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

Here we redirect  to the init function UTIL\_Init.init().&#x20;

-> To fill the dropdowns, we have an init function which is used to setup the dropdowns for the dashboard.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

```
UTIL_Init.initDropdowns();
```

<pre class="language-typescript"><code class="lang-typescript"><strong>//Define a variable to hold all measures from the Datasource
</strong>var measures = DP1.getDataSource().getMembers("Account_BestRunJ_sold");

// Check out F12 -> Console log
console.log(measures);

//Loops over all measures and adds id and Description to the Dropdown.
for (var i = 0; i &#x3C; measures.length; i++) {
    DROP_Measure.addItem(measures[i].id,measures[i].description);	
}

//Sets the default Measure as the current selected Key of the Dropdown Box.
DROP_Measure.setSelectedKey(PAN_MAIN_S2_Chart1.getMembers(Feed.ValueAxis)[0]);
</code></pre>

{% hint style="info" %}
Console.log() can be used to display variables without the need for debugging.

Press F12 to open the developer tools of your browser.

Under Console -> you should see the measure variable values.
{% endhint %}

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>











The Dropdown should be filled during startup of the story, now we need to script the interaction with the charts on the detail page.

<figure><img src="../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Currently you wouldn't see the details page, because its hidden in design time. Click on the eye symbol to make it visible.

{% hint style="info" %}
This visibility is only for the design time, the visibility during view time is set in the styling panel of the objects.&#x20;

![](<../.gitbook/assets/image (1) (1) (1) (1).png>)
{% endhint %}

To script the interaction are using the Dropdown:

<figure><img src="../.gitbook/assets/image (2) (1) (1).png" alt=""><figcaption></figcaption></figure>

```typescript
PAN_MAIN_S2_Chart1.removeMember(Feed.ValueAxis,PAN_MAIN_S2_Chart1.getMembers(Feed.ValueAxis)[0]);
PAN_MAIN_S2_Chart1.addMember(Feed.ValueAxis,this.getSelectedKey());
PAN_MAIN_S2_TAB1.getDataSource().setDimensionFilter(Alias.MeasureDimension,this.getSelectedKey());
```
