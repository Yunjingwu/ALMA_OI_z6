# Containing details of data reduction

1. move 'member.*.casa_piperestorescript.py' out to the 'script/' folder 
2. remove commends used to substract the continuum from '*casa_pipescript.py' (e.g. )
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
3. Find emission-line channels:
  * ***Tentatively*** subtract continuum from both expected/unexpected emission-line channels.
  * Finding emission-line channels (Expect location and random interlopers).

4. Generate continuum image (copy .ms files into contsub/ & cont_unsub/)
  * Generate continuum images from line-free region (tclean) in the cont_unsub.ms
  * Run sources-finder code and do photometry
  
5. Generate mom0 map (copy .ms files into contsub/ & cont_unsub/)
  * Subtract continuum from both expected/unexpected emission-line channels.
  * Generate mom0 maps from emission-line region (tclean) in the ***cont_sub.ms***.

6. Tclean can be performed in parallel mode.
```
  mpicasa -n 40 /opt/casa-pipeline-release-5.6.1-8.el7/bin/casa
```
