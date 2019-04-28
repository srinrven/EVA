Srinivas Rao K.V, EVA, M6 batch

- ***What are Channels and Kernels (according to EVA)?****

  Any image, music, food item etc are usually a combination of certain features, some features are strong/bright, some are light/less. Before we define Kernals/filters for images lets take some practical examples of Kernals for food item say veg pulao and music.

  ​		Lets start with veg pulao, it is made of many ingredients like potato, peas, rice, vegetables,  onions etc. Lets say we have a kernal which only looks for potato, so when I apply potato filter on veg pulao, it detects one potato piece at a time. When we put all potatoes together from veg pulao, we call that combination of all potatoes together called potato channel. Same concept can be applied for other ingredients of pulao.

  ​		If we extend the above kernal example to 1 minute music clip, which is composed by different instruments say guitar, violin, drums, saxophone etc. Here we can have different filter/kernal which extracts notes from music specific to particular instrument.  For example guitar filter will find single note where as guitar channel consists of all guitar notes from 1 minute music clip. So in general words, we can say filter/kernal looks for specific feature and when the filter is applied over the component/music clip/image we get a channel. 
  ​		So extending above discussion to images, we can have multiple feature extractors/kernals like vertical edges, horizontal edges, sharpen filters which applied ove the entire image we get a channel. 3x3 edge detector finds edges in 3x3 image of mxn image, when 3x3 applied all ove image mxn we get a channel, in this case channel is also image which clearly shows edges of the image. 

  Filters are matrix operator applied across image to transform the encoded information. Simple filters can blur,outline,sharpen the input image, for example edge detection is done by using filter convolution with input image. Kernals are small matrix which are convolved with input images highlight the regions which are of importance to specific filter in the input.  In CNNs Kernals are used to extract important features across different convoluted layers to detect objects, feature extraction.  Filters are extensively used in image processing and CNNs to emphasize certain features of interest and some times remove features.

  

- **Why should we only (well mostly) use 3x3 Kernels?**

   With 3x3 matrices one can always compute any other odd size filter like 5x5 or 7x7 etc.
    In other words out put of image convoluted with 5x5 is same convolving image twice with 3x3. 
    This led to revolutionizing or improving hard ware efficiency only for 3x3 matrix operator computations, which is one of the major reasons for the rapid growth of research in deep learning.

  3x3 matrices are symmetric, more intuitive for image processing.

    

- **How many times do we need to perform 3x3 convolution operation to reach 1x1 from 199x199 (show calculations)**

  Let '>' represent convolving with 3x3 kernal
  199x199 > = 197x197 > =195x195 > =193x193 > =191x191 > =189x189 > =	187x187 > =185x185 > = 183x183 > =181x181 > =179x179 > =177x177  > = 175x175  >=173x173  > =171x171  > =169x169 >  = 167x167 >=165x165 > =163x163 > =161x161 > = 159x159 > =157x157 > = 155x155 > =153x153 > =151x151 > =149x149 > =147x147 > =145x145 > =143x143 > =141x141 > = 139x139 > =137x137 > =

  135x135 > =133x133 > =131x131 > =129x129 > =127x127 > =125x125 > =123x123 > =121x12 1> =

  119x119 > =117x117 > =115x115 > =113x113 > =111x111 > =109x109 > =107x107 > =105x105 > =103x103 > =101x101 > = 99x99> =97x97 > =95x95 > =93x93 > =91x91 > =89x89 > =87x87 > =

  85x85> =83x83 > =81x81 > =79x79 > =77x77 > =75x75 > =73x73 > =71x71 > = 69x69 > = 67x67 > =65x65 > =63x63 > =61x61 > =59x59> =57x57 > =55x55 > =53x53 > =51x51 > =49x49 > =47x47 > =45x45 > =43x43> =41x41 > =39x39 > =37x37 > =35x35 > =33x33 > =31x31 > =29x29 > =27x27 > =25x25 > =23x23 > =21x21 > = 19x19 > =17x17 > =15x15 > =13x13 > =11x11 > =9x9 > =7x7 > =5x5 > =3x3> =1x1

  It took 99 convolutions with 3x3 kernal, to transform 199x199 image to 1x1, in neural networks we say we need 99 layers. 
