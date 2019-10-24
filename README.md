# PCA-Image-Compression

Image Compression


To begin image compression using PCA, an image can be represented as a matrix of pixel color values in which the values of X and Y are the coordinates of the pixels in the image and f(x,y) is the corresponding level of grey.

In image compression, the samples are the columns of the image matrix. For example, a 1024 by 1024 image, you can consider it as 1024 samples (vectors) with dimension 1024.  The first step is to standardize the data, or normalize the image, by subtracting the mean of each sample (column) from the original matrix. This is important since PCA is a variance-maximizing method and therefore loses its integrity if the data is not standardized. [Makes them all treated as equally important]. The second step is to calculate the covariance matrix and then find the eigenvectors and eigenvalues. Finally, the last step is to reconstruct the original image in lower dimension. 
 The eigenvector with the largest corresponding eigenvalue is the new basis the image data will be projected onto (this is the direction of greatest variation in the image dataset). Finally, the last step is to transform the image by projecting the image data to the new basis found in the previous step with reduced features. In other words, the image is reconstructed in lower dimension space. 

Here is an example of using PCA for image compression which demonstrates the increase in quality as the number of components increase. The MATLAB code uses PCA to reconstruct an image and we can see the difference in the quality of the reconstructed image when using different numbers of principal components. I had originally thought that when I used 150 PC that the quality matched the original image, but I could still notice some difference when I blew the picture up. I finally used 250 PC and could not tell a difference, I’m not sure if you can tell which image is the original and which is the reconstructed one, but this image on the left is the original, whose dimensions are 1280 x 870  and the image on the right is the reconstructed image using 250 principal components and has dimensions 566 x 384, so we can see that the image is more compact but essentially exhibits the same quality. An example of when this is used is with a projector like this, since there are only 4K projectors available for purchase, although apparently 8K projectors will be on the market soon, in order for a 4K projector to display an 8K video, image compression needs to performed so that the projector can display the video as closest to its original quality as possible. You can try it out for yourself by running the MATLAB code and choosing the number of principal components desired. 

The central advantage of PCA in image compression is the removal of noise and redundancy between neighbouring pixels. This allows for major differences to be focused on so that the image retains its most important features. This allows images to exhibit the same quality but be more compact. This conserves resources making it easier/faster to send picture messages or emails, saves space.


References:
 http://ecammar.blogspot.com/2013/04/image-compression-using-principal-of.html
