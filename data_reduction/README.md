# Containing details of data reduction

1. move 'member.*.casa_piperestorescript.py' out to the 'script/' folder 
============
## 2. remove commends used to substract the continuum from '*casa_pipescript.py' (e.g. )
```
  #hif_makeimlist(specmode='mfs')
  #hif_findcont(pipelinemode="automatic")
  #hif_uvcontfit(pipelinemode="automatic")
  #hif_uvcontsub(pipelinemode="automatic")
  #hif_makeimages(pipelinemode="automatic")
  #hif_makeimlist(specmode='cont')
  #hif_makeimages(pipelinemode="automatic")
  #hif_makeimlist(specmode='cube')
  #hif_makeimages(pipelinemode="automatic")
  #hif_makeimlist(specmode='repBW')
  #hif_makeimages(pipelinemode="automatic")
```
## 3. Generate continuum image (copy .ms files into contsub/ & cont_unsub)
### 3.1. ***Tentatively*** subtract continuum with excluding expected emission line channels.
### 3.2. Finding emission-line channels (Expect location and found random interlopers).
### 3.3. Generate continuum images from line-free region (tclean) in the cont_unsub.ms
### 3.4. Run sources-finder code and do photometry
  
## 4. Generate mom0 map (copy .ms files into contsub/ & cont_unsub)
### 4.1. Subtract continuum from both expected/unexpected emission-line channels.
### 4.2. Generate mom0 maps from emission-line region (tclean) in the ***cont_sub.ms***.

## 5. Tclean can be performed in parallel mode.
   `mpicasa -n 40 /opt/casa-pipeline-release-5.6.1-8.el7/bin/casa`
