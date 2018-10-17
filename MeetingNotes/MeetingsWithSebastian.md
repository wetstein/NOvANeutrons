# NotePad


### 10.9.2018

We discussed Sebastian's new additions to the CellHitTimeAnalyzer package, where he is now able to extract unpronged Hits from slices. The default plan is to add them onto the Slice-0 hits and regroup them in the mini-slices.

There are several questions we would like to answer in the data and MC:
* What is the E-per-hit spectrum for the un-pronged hits?
* What is the time spectrum (time-elapsed from earliest hit) of the un-pronged hits?
* What is the distribution of N-unpronged-hits per slice?
* What is the distribution of the fraction of unpronged-hits per slice?

These can possibly be compared between data and MC. We can also compare unpronged-hits with unsliced hits and sliced/pronged hits...

Another question is: how often do the unpronged hits end up being a part of a good mini-cluster with slice-0 hits?

The last thread of our discussion was about finalizing the Noise hit time distribution comparison. I would like to see it with:
* the shift-corrected
* the pedestal subtracted
* shape normalized
* for Nhits>1 mini-slices

### 10.17.2018

We looked at the number of unpronged hits distributions in data and MC. We would like to normalized by total number of prongs. Same for the fraction of unpronged and the total cell hits.
