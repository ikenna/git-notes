---
layout: page
title: "Git Bisect"
description: ""
---
{% include JB/setup %}

You want to run a binary search on a projects commit history to find out which commit introduced a bug.

    git bisect start # Starts the binary search
    git bisect bad  # Marks the current commit as having the bug
    git bisect good <commit sha or tag> # tell git which commit or tag did not have the bug,

Git will count the number of commits between the ones you've marked *good* and *bad*, and checkout out the middle commit. You can run your test on the middle commit and check if the bug is present. 
If it is present, run

    git bisect bad

else

    git bsiect good

Continue this until you isolate the commit that introduced the bug. 

At the end run 

    git bisect reset 

to end the binary search. 




