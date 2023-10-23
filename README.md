# Explanation for slide 19 (Ref: https://x-c3ll.github.io/)
## Step 0
Define font families with only one characters which have side adjusted to 200% and one with all with normal size.
## Step 1
As height gets auto-adjusted and we want to trigger a vertical scrollbar, we set overflow-y to auto.
## Step 2
We used -wekbkit-scrollbar to style the scollbar with a custom background which is can be a URL to fetch from attacker.com
## Step 3
Set a loop to go through the characters one by one by increasing width of div each time. Note that this is incomplete and we will come back to why later.
## Step 4
Same but showing an example with the normal 100% sized characters
## Step 5
Another loop. Each time we add one character to the width, we test it by changing font family. If it triggers a vertical scrollbar by increasing size to 200%, the styling will try to fetch attacker URL as background and thus we will know.
## Step 6
Even if we increase width bit by bit and the rest of the characters are not visible, it is still considered in the rendering. We set the font-size to 0 and apply work-break. This way anything that does not fit the width gets broken into the next line. Then we use the first-line selector to set only the font-size of the first line to something greater than 0. So only the first line is actually rendered.
## Step 7
Example with 3 characters. It will not work yet because the height is hard coded to something much larger than needed to trigger vertical scrollbar
## Step 8
We fix the height and it works 
