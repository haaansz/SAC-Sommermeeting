# Part 3 - Details Page

In this 3 part we want to have the possibility to use a Dropdown for a measure selection in the details page.

The details page can be accessed by clicking on the measure name on top of the tile.

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

The detailed page  consists of one chart and one table with a detailled view for the selected measure.

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

Let's have look at what is happening when we click on the Text "Gross Margin".

First identify the object for the "Gross Margin" Text and then have a look at the Function.

![](<../.gitbook/assets/image (12).png>)

```typescript
UTIL_Navigation.goToMainPAN(2);
```

Check out the Function goToMainPan:

```typescript
switch(ipan){
		case 1:
		PAN_MAIN_S1.setVisible(true);
		PAN_MAIN_S2.setVisible(false);		
		break;	
		case 2:
		PAN_MAIN_S1.setVisible(false);
		PAN_MAIN_S2.setVisible(true);		
		break;	
		case 3:
		PAN_MAIN_S1.setVisible(false);
		PAN_MAIN_S2.setVisible(false);	
		break;	
}
```

In this function the PAN\_MAIN\_S1 will be hidden while currently hidden PAN\_MAIN\_S2 ( contains the details objects ) will be set to visible.





