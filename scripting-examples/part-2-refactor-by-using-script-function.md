# Part 2 - Refactor by using Script Function

Obviously we don't want to paste the script 4 times to add the same functionality to the other tiles.

Therefore we can make use of scripting functions.

1. Create a new Scripting Function „replaceMeasure“ under the Scripting Object UTIL\_Navigation ( in Outline.

<figure><img src="../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

2. Move your current coding from PAN\_Main\_Content\_Chart1 -> OnSelect to the new scripting function „replaceMeasure“

<pre class="language-typescript"><code class="lang-typescript">// getMeasures response is usually an array, in this case the target chart only has one measure, 
// therefore we can access the first and only measure with [0]
TargetChart.removeMember(Feed.ValueAxis,targetChart.getMeasures(Feed.ValueAxis)[0]);
TargetChart.addMeasure(sourceChart.getMeasures(Feed.ValueAxis)[0],Feed.ValueAxis);
<strong>
</strong></code></pre>

<figure><img src="../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

3. Call new scripting function from PAN\_Main\_Content\_Chart1 -> OnSelect

```typescript
// Use Script Function to replace measure in Linechart
UTIL_Navigation.replaceMeasure(PAN_MAIN_S1_R2_CHART1,this);
```

<figure><img src="../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

## Now you can copy and paste this script to all other tiles you want so have interactivity with the line chart.
