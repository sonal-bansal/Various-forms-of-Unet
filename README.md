# Various-forms-of-Unet

# UNET

The  typical  use  of  convolutional  networks  is  on  classification  tasks,  where
the output to an image is a single class label. However, in many visual tasks,
especially  in  biomedical  image  processing,  the  desired  output  should  include
localization, i.e., a class label is supposed to be assigned to each pixel.More-
over, thousands of training images are usually beyond reach in biomedical tasks.

We build upon a more elegant architecture, the so-called “fully
convolutional network” .
The main idea is to supplement a usual contracting network by
successive layers, where pooling operators are replaced by upsampling operators.
Hence, these layers increase the resolution of the output
