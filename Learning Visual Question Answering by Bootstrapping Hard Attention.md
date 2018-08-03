https://arxiv.org/pdf/1808.00300.pdf


Talks about doing hard attention in images for visual question answering. Soft attention aggregates every element \
but never completely ignores them. Thus all the features are added while hard attention allows to 
deselect ( by giving value of 0 to some regions ) and thus 
only focussing on actually relevant regions. Thus far only problem with hard attention is to use a heavy-side step function
as activation which is not differentiable. 

The authors claim is premised on the assumption that **norm of the visual features correlate with their relevance**. They divide the 
image into grids:

Steps: For Image x and question q,

  1. CNN of x at (i,j) using 1x1D convolution to project it into wxhxd
  2. question feature q projected in d using MLP
  3. Combined both and do element-wise addition so that each feats m(i,j) is  wxhxd
  4. Do L2 norm of m(i,j)
  5. Select top k entries and backpropaget the VQA entwork.While this is good but the model could learn to give 
    importance to every locaitons. So, they allow to compete against some threshold (tau). So they do softmax for m(i,j) from 
    step 4 and select those greater than tau. so tau = softmax( 1/ w.h) i.e importance of each locations. So network has to 
    do better than uniform probailiy mass distribution to win against random network .
    
Pros:

  1. Simple idea 

Cons:
  1. Is the premise strong? Are the norms of conv features only indicator of useful features.
  2. 
  
