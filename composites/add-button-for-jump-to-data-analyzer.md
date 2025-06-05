# Add Button for Jump-To Data Analyzer

Go to Insert, to the + sign and add a Button.

<figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

<div align="left"><figure><img src="../.gitbook/assets/image (23).png" alt="" width="142"><figcaption></figcaption></figure></div>

Then click on the Button and with the Styling panel on the Right-Side Panel you set the Properties. Don‘t forget to add an ID.

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

To use the icons, displayed as a little barchart, you can go to the following address:

{% embed url="https://sapui5.hana.ondemand.com/sdk/test-resources/sap/m/demokit/iconExplorer/webapp/index.html#/overview/SAP-icons/?tab=grid&icon=bar-chart&search=chart" %}

Here you need to click on the following symbol and paste it  to the text box of your Button:

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

Now we add scripting for onClick in order to tell the button when clicked it should fire the event

```
Composite.fireEvent(„JumpDA“);
```

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

Add an Event with the a name – best use the same as the button

<div align="left"><figure><img src="../.gitbook/assets/image (28).png" alt="" width="351"><figcaption></figcaption></figure></div>

Now after adding the Composite to your story and with the available scripting event and add Scripting for jumping to DataAnalyzer with Model data and Story Filter

<div align="left"><figure><img src="../.gitbook/assets/image (29).png" alt="" width="563"><figcaption></figcaption></figure></div>

```javascript
NavigationUtils.openDataAnalyzer(undefined, DP1.getDataSource().getInfo().modelId, UrlParameter.create('systemType', 'MODEL'));

```

In View Mode it is now possible to click on the button and DataAnalyzer opens in a new page.

<figure><img src="../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>
