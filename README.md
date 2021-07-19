[![ISPRS](https://www.isprs.org/documents/samples/logos/animated_logo0_small.gif)](https://doi.org/10.5194/isprs-annals-V-2-2021-121-2021)

# TESSERAE3D: A BENCHMARK FOR TESSERAE SEMANTIC SEGMENTATION IN 3D POINT CLOUDS

This is the official repository of the **Tesserae3D** dataset. For technical details, please refer to:

**Tesserae3d: a benchmark for tesserae semantic segmentation in 3d point clouds** <br />
[Kharroubi Abderrazzaq](https://orbi.uliege.be/simple-search?query=abderrazzaq+kharroubi), [Line Van Wersch](https://orbi.uliege.be/simple-search?query=line+van+wersch), [Roland Billen](https://orbi.uliege.be/simple-search?query=roland+billen), 
[Florent Poux](https://orbi.uliege.be/simple-search?query=florent+poux) <br />
**[[Paper](https://doi.org/10.5194/isprs-annals-V-2-2021-121-2021)] [[Video](https://youtu.be/Hbb-tnWeEf4)] [[Download](https://forms.gle/661vB1KqSRzJ4NPX8)]** <br />

### Abstract 

3D point cloud of mosaic tesserae is used by heritage researchers, restorers and archaeologists for digital investigations. Information extraction, pattern analysis and semantic assignment are necessary to complement the geometric information. Automated processes that can speed up the task are highly sought after, especially new supervised approaches. However, the availability of labelled data necessary for training supervised learning models is a significant constraint. This paper introduces Tesserae3D, a 3D point cloud benchmark dataset for training and evaluating machine learning models, applied to mosaic tesserae segmentation. It is a publicly available, very high density and coloured dataset, accompanied by a standard multi-class semantic segmentation baseline. It consists of about 502 million points and contains 11 semantic classes covering a wide range of tesserae types. We propose a semantic segmentation baseline building on radiometric and covariance features fed to ensemble learning methods. The results delineate an achievable 89% F1-score and are made available here, providing a simple interface to improve the score based on feedback from the research community.

### (1) Dataset

#### 1.1 Overview

Tesserae3D is a mosaic tesserae 3D point cloud dataset acquired by a phase-based calibrated terrestrial laser scanner merged with dense image matching. We used scan data from a Leica P30 scanner, acquired from one position high enough using an extended mounted tribrach, the scan point cloud was composed of 87.5 million points (scan only). Indeed, data fusion which consists to“combines data from multiple sources to improve the potential values and interpretation performances of the source data, and to produce a high-quality visible representation of the data” (Zhang, 2010) prove to be essentials in this case to enhance the density of point cloud. Pictures were taken with a camera, type Canon EOS 5D Mark III with a full-frame sensor and a 35 mm camera lens. For implementing the so-called Multi-View Stereo method, an amount of  2.058 shots was captured, with 5760 * 3840 pixels in RAW. They were used to obtain a more dense 3D point cloud of all tesserae. This dataset covers approximately 9.3 m² (F. Poux et al., 2017a) and consists of approximately 502 million points (fusion results between scan and dense 3d reconstruction from images) which represents an average density of 54 million pts/m².

The point cloud is classified in 10 labelled tessera type (plus one for mortar, and one for unclassified parts) and contains 7 attributes which are:
-	(X, Y, Z): Position of each point recorded in local coordinates (in meters).
-	(R, G, B): Natural colour reflectance of red, green, blue of each point as an integer from 0 to 255.
-	Label: class of each point, recorded as an integer [0,11]

The dataset is divided into 10 sections, and each section is saved separately in .txt and .laz files. 

#### 1.2	Data annotation

Ground truth annotation is performed at the point level, where each point is manually assigned a corresponding class of tesserae (to not bias annotation by any algorithm use).  An unclassified label is used to only focus the evaluation on the portion of the point cloud that has been classified only, which represent until now 30% of the total mosaic. The manual annotation is performed using the segment tool within the open-source software Cloud Compare (CloudCompare, v2.11, 2020). After manual segmentation, a class index is associated with every category of the point clouds.

### (2) Demo

<p align="center"> <a href="https://youtu.be/Hbb-tnWeEf4"><img src="http://img.youtube.com/vi/Hbb-tnWeEf4/0.jpg" alt="TESSERAE3D: A BENCHMARK FOR TESSERAE SEMANTIC SEGMENTATION IN 3D POINT CLOUDS" width="90%" ></a> </p>

### (3) Training and Evaluation

#### 3.1 Download the dataset 

Download the files [here](https://forms.gle/661vB1KqSRzJ4NPX8). 

#### 3.2 Data processing
Here we provide the training and evaluation script of :
- Random forest [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/13iajqwycs3nNfAnGhiV9iXazOZ05BD6A?usp=sharing) 
- Gradient boosting [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1kF2dOoTKMf8spmLPVR1sVCiFLKCbOQ7X?usp=sharing) 

### Acknowledgements
The authors are acknowledged for the municipality of Germigny-des-Prés and the DRAC Centre Val-de-Loire that allowed access to the church and its mosaic. The research was financed thanks to an FSR-FNRS research project called “Pro-mone” that is directed by Pr. D. Strivay (ULiège) and Pr. L. Verslype (UCL).


### Citation
If you find our work useful in your research, please consider citing:

	@inproceedings{NICE2020,
	  title={TESSERAE3D: A BENCHMARK FOR TESSERAE SEMANTIC SEGMENTATION IN 3D POINT CLOUDS},
	  author={Kharroubi, A., Van Wersch, L., Billen, R., and Poux, F.},
      booktitle={ISPRS Ann. Photogramm. Remote Sens. Spatial Inf. Sci., V-2-2021, 121–128},
	  year={2021}
	}
  
### Updates
* 20/07/2021: The dataset is available for download!
* 07/04/2021: Initial release!

## Related Repos
1. [Random Forest 4 Point Cloud Classification - RF4PCC](https://github.com/3DOM-FBK/RF4PCC) ![GitHub stars](https://img.shields.io/github/stars/3DOM-FBK/RF4PCC.svg?style=flat&label=Star)


