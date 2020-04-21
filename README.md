# MRI_Knee_acl
#
#使用框架:Pytorch
#
# 輸入3種不同切片(Coronal, Axial, Sagittal)的膝蓋MRI突來預判是否膝蓋前十字韌帶撕裂(ACL tear)
# 資料集: 使用Standford大學公開的MRNet-v1.0資料集
# 訓練架構: 個別對3種不同的切片(Coronal, Axial, Sagittal)用CNN去訓練,再把3個模型的輸出結合起來用logistic regression 做分類預測
![image](https://github.com/funpi89/MRI_Knee_acl/blob/master/images/mriall.png)
#
#

# 每個切片的CNN模型架構:這裡使用AlexNet預訓練模型
![image](https://github.com/funpi89/MRI_Knee_acl/blob/master/images/mri.png)
# 輸入圖片size為(1, slice, 3, 256, 256)因為每位患者的MRI切片數(slice)不一樣,所以batch size必須取1做訓練
#
# 3種切片的CNN最後測試集roc_auc為80%左右,結合起來用logistic regression的測試集roc_auc為87.8%, accuracy為75%
