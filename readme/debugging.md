# Debugging

To debug your story, first execute it. Then, open the developer tools and navigate to the executed scripts under Source -> Page -> sandbox.worker.main.

{% hint style="info" %}
Before your scripts get executed at runtime, SAP Analytics Cloud transforms them. This is why the JavaScript in the web browser's developer tools doesn't look exactly the same as the scripts you wrote in the script editor during design time.
{% endhint %}

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

Use the search panel to find your scripts: (Ctrl + P)

![](<../.gitbook/assets/image (7).png>)

To pause script execution, open the desired script. On the left, click the line number where you want the pause, marked by a blue indicator. This marker shows where the script will halt during its next run.

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

To enable debug mode in SAP Analytics Cloud, you can also use the `debugger;` statement. This allows your scripts to pause at specific points during runtime, helping you identify and fix errors efficiently.



<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>
