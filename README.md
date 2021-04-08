
# Hybrid-Image-Encryption
A new image encryption technique 

Steps in our method:
- Generate initial conditions and control parameters.
SHA-256 generates digest of 256 bits regardless the size of the input. If there is one-bit difference between two inputs, their message digest will be completely different. So, this is used to generate digest of the color image to which encryption is to be done. 
This digest is used to generate initial conditions for PWLCM, Lorenz system and Chen’s hyper-chaotic system.
![image](https://user-images.githubusercontent.com/50589688/114006807-643db900-987e-11eb-8a92-87247be859e2.png)
- Encryption process
- Permutation step
	The proposed diffusion of colour image is performed in two ways:
	First each pixel is permuted according a chaotic sequence generated by PWLCM (piece wise linear chaotic map) given as;
𝑎_(𝑖+1)={█(𝑎_𝑖/𝑝_0 ,  0≤𝑎_𝑖<𝑝_0@(𝑎_𝑖−𝑝_0)/(0.5−𝑝_0 ),      𝑝_0≤𝑎_𝑖<0.5  @1−𝑎_𝑖 〖,  𝑎〗_𝑖≥0.5)┤
Then pixels of each channels is permuted separately by using Lorenz system of equations given as;
𝑦 ̇=−𝑓𝑦+𝑓𝑧
     𝑧 ̇=𝑟𝑦−𝑧−𝑦𝑞
𝑞 ̇=−𝑔𝑞+𝑦𝑧
To perform the permutation these sequences are first sorted and then pixels are swapped accordingly.![image](https://user-images.githubusercontent.com/50589688/114006849-6c95f400-987e-11eb-8c35-0d9d0a22c972.png)



![enc_images](https://user-images.githubusercontent.com/50589688/114006530-250f6800-987e-11eb-905c-05d375e59fc3.jpg)
## Above image shows input images along with their encrypted forms

