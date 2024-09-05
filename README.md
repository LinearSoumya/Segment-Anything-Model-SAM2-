Problem statements

1. Using the first image of each object in data 2d folder and its corresponding mask

("can_chowder_000001.jpg", "can chowder 000001_1 gt.png")

("can_soymilk_000001.jpg", "can soymilk_000001_1_g1.png")

("can_tomatosoup_000001.jpg", "can_tomatosoup 000001_1 gt.png")

("carton_oj_000001.jpg", "carton_oj 000001_1_gt.png")

("carton soymilk_000001.jpg","carton_soymilk 000001_1_gt.png")

("diet_coke_000001.jpg" "diet_coke_000001_1 gt.png") ("hc.potroastsoup 000001.jpg"

"hc_potroastsoup 000001_1_gt.png") ("juicebox 000001.jpg"

"juicebox_000001_1_gt.png") ("rice_tuscan_000001 jpg" "rice_tuscan 000001_1_gt.png")

["ricepilaf_000001.jpg" "ricepilaf 000001_1_gt.png") detect the objects in all other images of the object. That is ("can chowder_000001.jpg". "can_chowder_000001_1_gt.png") should be used to setup SAM2 to locate can_chowder in all other images of can chowder. Similarly first image/mask pair of juicebox to locate juicebox in all other images of type juicebox (number).jpg.

2. You get masks as output, use a closely fitting bounding box as the final output corresponding to output mask you receive

3. Install pycocotools and use the boxes you get in step 2 from the mask like output of SAM2 as prediction and boxes you have as mask for each image (so groound truth for can_chowder_000002.jpg is box around mask in can chowder_000002_1_gt.png while prediction is box around the mask relevant_mask calculated by SAM2 above) as ground truth and calculate object detection preformance for each product individually.

As promised, the code for the function track_item boxes which detects objects zero shot using SAM2 is provided below, you are allowed to use this, but the rest of the code should
