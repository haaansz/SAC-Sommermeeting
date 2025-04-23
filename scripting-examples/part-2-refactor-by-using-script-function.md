# Part 2 - Refactor by using Script Function

Obviously we don't want to paste the script 4 times to add the same functionality to the other tiles.

Therefore we can make use of scripting functions.

1. Create a new Scripting Function „replaceMeasure“ under the Scripting Object UTIL\_Navigation ( in Outline.

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

2. Move your current coding from PAN\_Main\_Content\_Chart1 -> OnSelect to the new scripting function „replaceMeasure“

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

3. Call new scripting function from PAN\_Main\_Content\_Chart1 -> OnSelect

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>
