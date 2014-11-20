The description of our algrithm is in Algorithm.Description.pptx

0. Since it's very time-consuming to load the DCNN model, I recommand you to run step 2 to extract 
   deep learning features of all images before step 3. But it's OK to run step 3 individually, and our
   DCNN_Aesth.exe will automatically extract deep learning features before quality assessment. 

1. First please download the imagenet DCNN model caffe_reference_imagenet_model file here: http://dl.caffe.berkeleyvision.org/ and 
   put it into the same folder with the ExtractDeepFeat.exe

2. Run ExtractDeepFeat.exe to get DCNN features of your images:

   -- Open cmd window in the same folder with ExtractDeepFeat.exe

   -- Execute one of the following 2 commands: 
      1. ExtractDeepFeat.exe "your index file of images, one line per image" "the layer name of DCNN, we use fc7 here."
      2. ExtractDeepFeat.exe "the path of your image folder" "the layer name of DCNN, we use fc7 here."

   -- Sample commands: 
      1. ExtractDeepFeat.exe E:\\imageIndex.txt fc7
      2. ExtractDeepFeat.exe E:\\myimages fc7
 
   -- The deep learning features of every image will be saved into a binary file with 
      the same path as the image and named by "the image name" + ".feat"


3. You can evaluate the quality of images by:

   -- Open cmd window in the same folder with DCNN_Aesth.exe

   -- Excute one of the 3 following commands: 
      1. DCNN_Aesth.exe "the index file of your images, one line per image" "the file to save the scores"
      2. DCNN_Aesth.exe "the path of your image folder" "the file to save the scores"
      3. DCNN_Aesth.exe "the path of your single image" "the file to save the score of this image"

   -- Sample commands:
      1. DCNN_Aesth.exe E:\\imageIndex.txt E:\\imageScores.txt
      2. DCNN_Aesth.exe E:\\yourImageFolder E:\\Scores.txt
      3. DCNN_Aesth.exe E:\\yourImage E:\\yourimage.txt