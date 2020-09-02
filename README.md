# PhotonPrescaleTest

To perform event preselection run EventPreselection.C:
```
root -l
.x EventPreselection.C+("*TYPE*")
```
Here `*TYPE*` can be `SinglePhoton_B`, `SinglePhoton_C` and so on up until `SinglePhoton_H`, corresponding to ntuples made from SinglePhoton dataset (miniAOD) of 2016 runs B-H.
You can run a couple of different runs with the same macro if you type e.g. `SinglePhoton_BtoD`, `SinglePhoton_full` or similar.

Please note that ntuples are accessed via xrootd so you might need to initiate proxy
```
voms-proxy-init -voms cms
```
Files `SelectedForFR_E_SinglePhoton_X.root` will be created.

You can run the prescale demo script on the preselected events with PrescaleDemo.C:
```
root -l
.x PrescaleDemo.C+
```
It will draw a combined HLT object p_T historgram of all runs but it will also save separate root files `FR_Hist_TEST_E_SinglePhoton_X.root` with histograms for each run.
You can check those with root TBrowser.
