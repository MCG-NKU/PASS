# PASS method for LUSS task


## Introduction
![image](https://user-images.githubusercontent.com/20515144/196449430-5ac6a88c-24ea-4a82-8a45-cd244aeb0b3b.png)

We propose a new method for LUSS, namely PASS, containing four steps. 1) A randomly initialized model is trained with self-supervision of pretext tasks (i.e. our proposed Non-contrastive pixel-to-pixel representation alignment and Deep-to-shallow supervision) to learn shape and category representations. After representation learning, we obtain the features set for all training images. 2) We then apply a pixel-attention-based clustering scheme to obtain pseudo categories and assign generated categories to each image pixel. 3) We fine-tune the pre-trained model with the generated pseudo labels to improve the segmentation quality. 4) During inference, the LUSS model assigns generated labels to each pixel of images, same to the supervised model. 

More details about the LUSS task and [ImageNet-S dataset](https://github.com/LUSSeg/ImageNet-S) are in [project page](https://LUSSeg.github.io/) and [paper link](https://arxiv.org/abs/2106.03149).



## Usage
We give the training and inference details in **[USAGE](USAGE.md)**.
## Results
**Fully Unsupervised Evaluation Protocol**
<table><tbody>
<!-- START TABLE -->
<!-- TABLE HEADER -->
<th valign="bottom">Dataset</th>
<th valign="bottom">Arch</th>
<th valign="bottom">Val</th>
<th valign="bottom">Test</th>
<th valign="bottom">Args</th>
<th valign="bottom">Pretrained</th>
<th valign="bottom">Pixelatt</th>
<th valign="bottom">Centroid</th>
<th valign="bottom">Finetuned</th>
<!-- TABLE BODY -->
<tr>
<td align="left">ImageNet-S</td>
<td align="center">ResNet50</td>
<td align="center">11.5</td>
<td align="center">11.0</td>
<td align="center"><a href="scripts/luss919_pass.sh">bash</a></td>
<td align="center"><a href="https://github.com/LUSSeg/PASS/releases/download/pass/pass919_pretrained.pth.tar">model</a></td>
<td align="center"><a href="https://github.com/LUSSeg/PASS/releases/download/pass/pass919_pixelatt.pth.tar">model</a></td>
<td align="center"><a href="https://github.com/LUSSeg/PASS/releases/download/pass/pass919_centroids.npy">centroid</a></td>
<td align="center"><a href="https://github.com/LUSSeg/PASS/releases/download/pass/pass919_finetuning.pth.tar">model</a></td>
</tr>
<td align="left">ImageNet-S 300</td>
<td align="center">ResNet50</td>
<td align="center">18.0</td>
<td align="center">18.1</td>
<td align="center"><a href="scripts/luss300_pass.sh">bash</a></td>
<td align="center"><a href="https://github.com/LUSSeg/PASS/releases/download/pass/pass300_pretrained.pth.tar">model</a></td>
<td align="center"><a href="https://github.com/LUSSeg/PASS/releases/download/pass/pass300_pixelatt.pth.tar">model</a></td>
<td align="center"><a href="https://github.com/LUSSeg/PASS/releases/download/pass/pass300_centroids.npy">centroid</a></td>
<td align="center"><a href="https://github.com/LUSSeg/PASS/releases/download/pass/pass300_finetuning.pth.tar">model</a></td>
</tr>
</tr>
<td align="left">ImageNet-S 50</td>
<td align="center">ResNet18</td>
<td align="center">29.2</td>
<td align="center">29.3</td>
<td align="center"><a href="scripts/luss50_pass.sh">bash</a></td>
<td align="center"><a href="https://github.com/LUSSeg/PASS/releases/download/pass/pass50_pretrained.pth.tar">model</a></td>
<td align="center"><a href="https://github.com/LUSSeg/PASS/releases/download/pass/pass50_pixelatt.pth.tar">model</a></td>
<td align="center"><a href="https://github.com/LUSSeg/PASS/releases/download/pass/pass50_centroids.npy">centroid</a></td>
<td align="center"><a href="https://github.com/LUSSeg/PASS/releases/download/pass/pass50_finetuning.pth.tar">model</a></td>
</tr>
</tbody></table>

**Distance Matching Evaluation Protocol**
<table><tbody>
<!-- START TABLE -->
<!-- TABLE HEADER -->
<th valign="bottom">Dataset</th>
<th valign="bottom">Arch</th>
<th valign="bottom">Val</th>
<th valign="bottom">Test</th>
<th valign="bottom">Pretrained</th>
<!-- TABLE BODY -->
</tr>
<td align="left">ImageNet-S</td>
<td align="center">ResNet50</td>
<td align="center">15.6</td>
<td align="center">15.6</td>
<td align="center"><a href="https://github.com/LUSSeg/PASS/releases/download/pass/pass919_pretrained.pth.tar">model</a></td>
</tr>
</tr>
<td align="left">ImageNet-S 300</td>
<td align="center">ResNet50</td>
<td align="center">25.1</td>
<td align="center">25.2</td>
<td align="center"><a href="https://github.com/LUSSeg/PASS/releases/download/pass/pass300_pretrained.pth.tar">model</a></td>
</tr>
</tr>
<td align="left">ImageNet-S 50</td>
<td align="center">ResNet18</td>
<td align="center">39.6</td>
<td align="center">40.4</td>
<td align="center"><a href="https://github.com/LUSSeg/PASS/releases/download/pass/pass50_pretrained.pth.tar">model</a></td>
</tr>
</tbody></table>

**Semi-supervised Evaluation Protocol**

We provide a new codebase for semi-supervised evaluation in [ImageNetSegModel](https://github.com/LUSSeg/ImageNetSegModel).


## Citation
```
@article{gao2022luss,
  title={Large-scale Unsupervised Semantic Segmentation},
  author={Gao, Shanghua and Li, Zhong-Yu and Yang, Ming-Hsuan and Cheng, Ming-Ming and Han, Junwei and Torr, Philip},
  journal=TPAMI,
  year={2022}
}
```

## Acknowledgement

This codebase is build based on the [SwAV codebase](https://github.com/facebookresearch/swav).

If you have any other question, open an issue or email us via shgao@live.com


