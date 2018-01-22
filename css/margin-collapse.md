## What is margin collapsing?

When two elements are touching each other in a vertical way, margin collapsing occurs.

let's assume there are two box elements vertically aligned.
Box A - margin bottom : 20px 
Box B - margin top : 60px

![margin-collapse](images/margin-collapse.png "margin collapse explain")

It’s easy to think that the outcome would be 80px but that’s not correct. The resulting margin would be 60px.
**The largest margin remains the same and smallest margin collapses to 0.**
**Max(top margin, bottom margin)**

Margin collapsing only occurs when two(or more) top and bottom margins are touching, and it doesn’t happen at all with left and right margins.