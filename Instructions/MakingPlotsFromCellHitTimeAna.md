# Instructions

I have thee stages of the analysis:
1) CellHitTimeAna_module.cc This is run by art and creates ttrees with one entry per slice (regular slice or microslice)
2) AnalSelector.{h,C}   This scans the previous ttrees and makes histograms of interest variables. It stores THStacks which combine the a Data and a MC histogram of the relevant quantit, for quick comparison and plotting. It produces a root file with histograms and THStacks.
3) plot_thstacks.C This one just takes the previous file and plots the THStacks (it's quite short).
If you'd like to modify the histograms, maybe you can make some moifications on plot_thstacks.C, as most of the histograms are retrieved in the code there. The location of the code is
```/nova/app/users/sfsanche/mytags/dev_cellhittimeana/CellHitTimeAna/small_samples/plot_thstacks.C```
You can copy it and run from anywhere, the path of the histograms file is hardcoded. You can run it with
```$ root -X plot_thstacks.C ````
It might be easier to just use a TBrowser over the histograms file, which is
```/nova/app/users/sfsanche/mytags/dev_cellhittimeana/CellHitTimeAna/small_samples/results.root```
If you'd like to change how the histograms are made, you'd need to modify the AnalSelector. It inherits from TSelector. You can again copy the header and source files anywhere. Then, to run, enter root and run:
```root[1] TChain t("neutronana/TNeutronCandidates","t"); t.Add("/nova/app/users/sfsanche/mytags/dev_cellhittimeana/CellHitTimeAna/medium_samples/data/*.root"); t.Add("/nova/app/users/sfsanche/mytags/dev_cellhittimeana/CellHitTimeAna/medium_samples/mc/*.root");  t.Process("AnalSelector.C")```
This will create the output ttree in a file called `results.root`
With the histograms and THStacks.
