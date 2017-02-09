# Steganography
Implementing Steganography
-------------------------------

Steganography is a art or science oh hiding information inside an image with a care that image view is not corrupted.

#Technique
#LSB Method
-------------------------------

It uses the least significant bits of the image pixels to store information i.e. LSB are overwritten.
Change in LSB doesnt reflect i.e. human eye cannot detect the variation from actual data to embeded data.
Say 2 LSB are overwritten so the maximum change will be 4.

#STEPS FOR EMBEDING
1. Load the vessel image.
2. Make it readable band by band per pixel.
3. Design a signature with doc name to be embeded as HEADER.
4. 1 byte of information has to be stored in 1 pixel.
5. Using a password generate a flag.
6. For every pixel
    fetch a byte of information
    split it into 3+3+2 bits form
    flagwise store 3,3 and 2 bits of data into RGB bands of pixel.
 7. Store back the memory image as a file.
     ensure the format is non JPG.
     
 #STEPS FOR EXTRACTION
1. Load the vessel image.
2. Make it readable band by band per pixel.
3. Fetch the signature to ensure embedding and get storage form.
4. Using a password generate a flag.
5. For every pixel
      flagwise fetch 3,3 and 2 bits of data from RGB bands of pixel
      Concatenate the bits to form a byte a data.
6. Store back the data as a file.
