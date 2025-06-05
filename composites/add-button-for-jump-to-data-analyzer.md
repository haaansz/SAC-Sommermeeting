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
