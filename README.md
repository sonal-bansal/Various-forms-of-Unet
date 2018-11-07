# Various-forms-of-Unet

# UNET

The  typical  use  of  convolutional  networks  is  on  classification  tasks,  where
the output to an image is a single class label. However, in many visual tasks,
especially  in  biomedical  image  processing,  the  desired  output  should  include
localization, i.e., a class label is supposed to be assigned to each pixel.More-
over, thousands of training images are usually beyond reach in biomedical tasks.

We build upon a more elegant architecture, the so-called “fully
convolutional network” .


# VARIOUS FORMS OF U-NET

# 1. Original Unet
The main idea is to supplement a usual contracting network by
successive layers, where pooling operators are replaced by upsampling operators.
Hence, these layers increase the resolution of the output.
One  important  modification  in  our  architecture  is  that  in  the  upsampling
part we have also a large number of feature channels, which allow the network
to propagate context information to higher resolution layers. As a consequence,
the expansive path is more or less symmetric to the contracting path, and yields
a u-shaped architecture.This strategy allows the seamless segmentation of arbitrarily large images by an
overlap-tile strategy.

# 2.All-Dropout
Adding a dropout layer has become
a common practice in modern deep network architectures. We
therefore propose and evaluate an architecture with a dropout
layer placed after every convolutional layer after the activation.

# 3.All-Convolution
This  modification  introduces  new  parameters
into the network that can be considered as learning of pooling
for  each  part  of  the  network  rather  than  just  fixing  pooling
parameters  to  constant  values.  They  showed  that  replacing
pooling  layers  with  convolutional  layers  with  a  higher  stride or  removing  pooling  layers  completely  can  improve  final
results.

# 4.Inverted Net
Another way of dealing with model overfitting is to reduce
the  expressivity  of  the  function.
We propose altering the All-Dropout architecture by introducing the delayed subsampling of the pooling layers.
In contrast to All-Dropout , we propose starting with a large  number  of  feature  maps  and  dividing  this  by  a  factor
of  two  after  every  pooling  layer  in  the  contraction  part  of the  network,  while  increasing  by  a  factor  of  two  after  every upsampling   layer   in   the   expansion   part.   Intuitively,   such architecture seems more reasonable for more rigid anatomical organs such as clavicles, because their topologies do not vary much, meaning there is no need to learn many low resolution
high  level  abstract  features.  In  the  following  evaluation  we will  call  this  architecture InvertedNet, due  to  the  way  the
numbers  of  feature  maps  are  changed  with  respect  to  the All-Dropout architecture.


