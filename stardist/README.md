# StarDist models

Here you can find pre-trained StarDist models as frozen *.pb* files that are compatible with OpenCV's DNN module.

This means they can be used in QuPath with the help of the [QuPath StarDist extension](https://github.com/qupath/qupath-extension-stardist).

**Important!** The original models 
* dsb2018_heavy_augment.pb
* dsb2018_paper.pb
* he_heavy_augment.pb
were trained by the original StarDist developers, Uwe Schmidt and Martin Weigert. 
They are available at [https://github.com/stardist/stardist-imagej](https://github.com/stardist/stardist-imagej/tree/master/src/main/resources/models/2D) and the license file included here is from that repo.

For terms of use and credit, check out:

* [StarDist](https://github.com/stardist/stardist#pretrained-models-for-2d)
* [StarDist-ImageJ](https://github.com/stardist/stardist-imagej)

and also the source training data

* [DataScienceBowl 2018](https://bbbc.broadinstitute.org/BBBC038) ([CC0](https://creativecommons.org/publicdomain/zero/1.0/))
* [MoNuSeg 2018](https://monuseg.grand-challenge.org/Data/) ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode))
* [TNBC dataset from Naylor et al. 2018](https://doi.org/10.5281/zenodo.1174342) ([CC BY 4.0](https://creativecommons.org/licenses/by/4.0/legalcode))

The files included here have been converted with [tf2onnx](https://github.com/onnx/tensorflow-onnx)
```
python -m tf2onnx.convert --opset 10 --saved-model "/path/to/saved/model/" --output_frozen_graph "/path/to/output/model/file.pb"
```
as a convenience so that they can be run in QuPath using OpenCV rather than TensorFlow.
