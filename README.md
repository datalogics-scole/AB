# README

This repository demonstrates that there *can*, in fact, be two commits that share two common ancestors such that neither common ancestor is an ancestor of the other.  However, such a situation only arises when there are multiple commits with no ancestors (i.e., more than one "initial" commit).  

## Explanation

Consider commits <a href="https://github.com/datalogics-scole/AB/commit/9804ad52d1aec2833d955bf91e991fa19fc8986e"><i>a</i></a> and <a href="https://github.com/datalogics-scole/AB/commit/0d6785fccffde802f3266886017a813672df93b2"><i>b</i></a> (referenced by branches <a href="https://github.com/datalogics-scole/AB/tree/master-a">master-a</a> and <a href="https://github.com/datalogics-scole/AB/tree/master-a">master-b</a>, respectively).  *a* and *b* were both created by merging <a href="https://github.com/datalogics-scole/AB/commit/c80806cc2fdc357947d2858ccd6b4e2beab0de25"><i>a</i>'</a> and <a href="https://github.com/datalogics-scole/AB/commit/320dbe70f16564992365b79eab7d58cdce50e99b"><i>b</i>'</a>.  Thus, *a*' and *b*' are *both* common ancestors of *a* and *b*, yet they each have 0 parents, so neither is an ancestor of the other.  

Note that this is only possible because there are two "initial" commits (i.e., commits with 0 parents).  This repository was concocted by creating two separate repositories *A* and *B*, adding *B* as a remote to *A*, and merging a branch from *B* into a branch from *A*.  *a*' and *b*' are the initial commits from *A* and *B*, and *a* and *b* are merge commits.  