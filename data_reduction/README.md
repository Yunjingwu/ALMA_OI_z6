# Containing details of data reduction

1. move 'member.*.casa_piperestorescript.py' out to the 'script/' folder 
2. remove commends used to substract the continuum (e.g. )
  'hif_makeimlist(specmode=\'mfs\')'
  
  'hif_findcont(pipelinemode="automatic")'
  
  'hif_uvcontfit(pipelinemode="automatic")'
  
  'hif_uvcontsub(pipelinemode="automatic")'
  
  'hif_makeimages(pipelinemode="automatic")'
  
  'hif_makeimlist(specmode='cont')'
  
  'hif_makeimages(pipelinemode="automatic")'
  
  'hif_makeimlist(specmode='cube')'
  
  'hif_makeimages(pipelinemode="automatic")'
  
  'hif_makeimlist(specmode='repBW')'
  
  'hif_makeimages(pipelinemode="automatic")'
