# tiffread

Reads 8,16,32 bits uncompressed grayscale and (some) color tiff files into MATLAB

# Description

 tiffread, version 3.31 - September 20, 2014

 stack = tiffread;
 stack = tiffread(filename);
 stack = tiffread(filename, indices);
 
 Two options can be specified: 'ReadUnknownTags' and 'DistributeMetaData', eg:
 stack = tiffread(filename, [], 'ReadUnknownTags',1);
 stack = tiffread(filename, [], 'DistributeMetaData', 1);

 Reads 8,16,32 bits uncompressed grayscale and (some) color tiff files,
 as well as stacks or multiple tiff images, for example those produced
 by metamorph, Zeiss LSM or NIH-image.

 The function can be called with a file name in the current directory,
 or without argument, in which case it pops up a file opening dialog
 to allow for a manual selection of the file.
 If the stacks contains multiples images, reading can be restricted by
 specifying the indices of the desired images (eg. 1:5), or just one index (eg. 2).

 The returned value 'stack' is a vector struct containing the images 
 and their meta-data. The length of the vector is the number of images.
 The image pixels values are stored in a field .data, which is a simple
 matrix for gray-scale images, or a cell-array of matrices for color images.

 The pixels values are returned in their native (usually integer) format,
 and must be converted to be used in most matlab functions.

 Example:
 im = tiffread('spindle.stk');
 imshow( double(im(5).data) );



 Only a fraction of the TIFF standard is supported, but you may extend support
 by modifying this file. If you do so, please return your modification to us,
 such that the added functionality can be redistributed to everyone.
