Srinivas Rao K.V, EVA, M6 batch

Edge detectors code/google colab link : https://colab.research.google.com/drive/1XBmzSORmolTpKweofLCQdkK50XnBx71C

Edge detectors when observed more intuitively we can easily understand their impact on the image. For example, what is horizontal edge, it is horizontal line some where in the image where its horizontal neighbors are lesser brighter on one side and opposite side horizontal neighbors are of almost of equal brightness, in other words horizontally if we are scanning image on horizontal edge there is brightness difference starts from horizontal edge. So lets look at how convolving with kernal can detect the above brightness change and resulting image highlights horizontal edges. 

Lets take example of horizontal edge detector/kernal,[[-1,-1,-1],[0,0,0],[1,1,1]], only on the line horizontal line brightness will be highlighted. Imagine we have same/similar brightness horizontally in the image then convolving with horizontal edge detector make pixel value as zero, first line in 3x3 kernal are -1 and third row are 1 and second line are 0. 

Similarly vertical edge detector/kernal [-1,0,1],[-1,0,1],[-1,0,1]], detects vertical brightness changes in the image. When we combine both kernal we can get both horizontal and vertical edges.

Lets review same way blur kernal, simple way to achieve blur is by doing simple average with all other 8 neighboring pixels, here is couple of examples, [0.111,0.111,0.111],[0.111,0.111,0.111],[0.111,0.111,0.111] and [[0.0625,0.125,0.0625],[0.125,0.25,0.125],[0.0625,0.125,0.0625]].
There has been lot of research done on edge detectors, one can find better performing kernals like laplacian and Gaussian. 
In similar lines sharpen filter [0,-1,0],[-1,5,-1],[0,-1,0]] works by sharpening the image comparing its local neighbors.</n>
Identity kernal does not transform the input image, in other input and out put images are same. Lets take a look at kernal, it nullifies the impact of neighbors when convolve and keeps the value of the pix as is at the center. [[0,0,0],[0,1,0],[0,0,0]], this is same as mathematical identity function, f(x) = x. Similarly 45 degrees lines are highlighted by [[1,-1,-1],[0,1,-1],[0,0,1]] and [[-1,-1,1],[-1,1,0],[1,0,0]].

In Neural network usually these kernals are assigned randomly and network adjusts the kernals with each input training and back-propagation. It is quite fascinating to know that in NN initial layers find edges and later layers combine the edges to form part/whole image.
