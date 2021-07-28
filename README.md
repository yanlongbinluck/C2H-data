# C2H-data
We have released our C2H-data and Synthetic-data proposed in paper 'Reconstruction of Hyperspectral Data from RGB Images with Prior Category Information'. 

The 30-channel hyperspectral image data (HSI) is saved as .tiff file, we have provided its corresponding RGB data and given carefully labeled object bounding boxes.  
[Google Drive](https://drive.google.com/file/d/1MlOCe8Ocql5p2OZKQyIuqWLtDXi9iiwW/view?usp=sharing)  
[BaiDu Drive](https://pan.baidu.com/s/1Ma09OEqYYzNGgDjAdFk6hg) password: cy5p  

The 128-channel raw hyperspectral image data can be obtained from：  
[BaiDu Drive](https://pan.baidu.com/s/1HZc7-5bfplHvJCS6OlC8Ng) password: vriu 

.tiff image data can be read as follow python script:
```
import numpy as np
from libtiff import TIFF
def tiff_to_numpy(tiff_image_name): 
    tif = TIFF.open(tiff_image_name, mode = "r")
    idx = 0
    for im in list(tif.iter_images()):
        im=np.expand_dims(im,axis=2)
        if idx==0:
            image=im
        else:
            image=np.concatenate((image,im),axis=2)       
        idx = idx + 1
    return image

```

If you use these datasets in your researches or works, please cite our paper as follow:  
```
@article{yan2020reconstruction,  
  title={Reconstruction of Hyperspectral Data from RGB Images with Prior Category Information},  
  author={Longbin Yan, Xiuheng Wang, Min Zhao, Maboud Farzaneh Kaloorazi, Jie Chen and Susanto Rahardja},  
  journal={IEEE Transactions on Computational Imaging},  
  year={2020},  
  publisher={IEEE}  
}
```
