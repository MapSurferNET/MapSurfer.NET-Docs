# Quality Metrics 

This section provides the details about the metrics which evaluate the quality of a label placement. Every metric has the weight as the first parameter. This weight defines the contribution of each metric in terms of the total quality value. Note that the metrics can also be used to filter labels according to a certain criterion (see TextSymbolizer - > LabelBehaviour > QualityFilter parameter).


## Positioning 

**Positioning** metric evaluates the position of every label candidate according to the cartographic guidelines related to positional desirability. For example, for point-like objects, an example of positional prioritization looks as follows: 

![](/media/images/39-labeling-point-positional-prioritization.png)

where a label position with smaller number has greater priority.

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Weight | Single | Specifies the weight of the metric. The value should fall into the range [0,1]. Default value 1.0. | No


## Priority 

**Priority** metric measures the importance of a geographic feature. Namely, this metric considers the following cartographic principle: 

- Type arrangement should reflect the classification, importance and hierarchy of
objects.

The value for this metric is obtained from *PriorityExpression* property of a text-related [symbolizer](usermanual/styling/symbolizers/index.md).

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Weight | Single | Specifies the weight of the metric. The value should fall into the range [0,1]. Default value 1.0. | No

## Cluttering

**Cluttering**metric can measure the degree of cluttering of neighbouring labels within a specific radius.


**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Weight | Single | Specifies the weight of the metric. | YesWeight | Single | Specifies the weight of the metric. The value should fall into the range [0,1]. Default value 1.0. | No
DistanceThreshold | Single | Specifies the distance threshold in pixels. Default value is 50. | No

> %!IMPORTANT IMPORTANT:!% Note, at the moment this quality metric supports only labels for point-like objects. 

## CoastalPoint 

**CoastalPoint** metric evaluates the degree of relationship of a place to the shore. This metric considers two cartographic requirements which say:

- Names of coastal settlements should be written on the water.
- Labels should be placed completely on the land or completely on the water surface.

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Weight | Single | Specifies the weight of the metric. The value should fall into the range [0,1]. Default value 1.0. | No
LayerName | String | Specifies the name of a layer which contains data source describing coastal lines.| Yes
BufferSize | Single | Specifies the size of the buffer, in pixels, around a point feature which is used to estimate the belonging of a place to the coast. Default value is 5. | No
Water | Boolean | Specifies whether the Layer contains water surfaces or not. Default value is False. | No 

> %!IMPORTANT IMPORTANT:!% Note, at the moment this quality metric is scale-dependent and supports only labels for point-like objects.

## FeatureOverlapping 

**FeatureOverlapping** metric measures the degree of cartographic disturbance introduced by labels that can overprint, cover, or even completely conceal other important geographic features (e.g., roads, rivers, lakes, etc.) lying in the background. This metric corresponds to the following cartographic rule:

- Labels should not overlap other significant features of the map background or do
this as little as possible.


**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Weight | Single | Specifies the weight of the metric. The value should fall into the range [0,1]. Default value 1.0. | No
TileSource | String | Specifies a link to a tile-based web map which contains important background features. | Yes
MaxColors | Integer | Specifies the number of colors which will be used in image segmentation algorithm to perform further analysis. Default value is 256. | No 
MetricWeights | String | Specifies weights of internal quality functions that measure *background homogeneity*, *spatial distribution* and *visual contrast*. More information about these functions you can find in the article written by [Rylov and Reimer (2014)](http://link.springer.com/article/10.1007%2Fs10707-014-0214-6) entitled "Improving label placement quality by considering basemap detail with a raster-based approach". The weights are presented as semicolon separated array of values, where each value falls into the range [0,1]. Default value is "0.5;0.4;0.1".| No
 

## Unambiguity 

**Unambiguity** metric measures the degree of ambiguous relationships of symbols and their names in the process of map lettering. More details about the model for this metric you can find in the paper entitled *A Comprehensive Multi-criteria Model for High Cartographic Quality Point-Feature Label Placement* written by [Rylov and Reimer (2014)](http://www.utpjournals.press/doi/abs/10.3138/carto.49.1.2137).

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Weight | Single | Specifies the weight of the metric. The value should fall into the range [0,1]. Default value 1.0. | No
MinimumDistance | Single | Specifies the minimum allowed distance, in pixels, between adjacent labels. Default value is 5. | No
MinimumCenterDistance | Single | Specifies the minimum allowed distance between the centers of adjacent labels. Default value is 5. | No
QualityThreshold | Single | Specifies the threshold parameter that controls the degree of allowed ambiguity between adjacent labels. Default value is 0.6. | No

> %!IMPORTANT IMPORTANT:!% Note, at the moment this quality metric supports only labels for point-like objects. 

## MaxDistance

TODO

## Water

TODO
 

## WaterCoverage 

TODO


# Configuration

In order to preset quality metrics, you need to edit one of the parameters in *LabelPlacementSettings* called *QualityEvaluators* (see Map > LabelPlacementSettings > QualityEvaluators). Below you will find some example configurations of the quality metrics

**Sample 1**

```cs 
Priority(0.7)
Positioning(0.3)
```


**Sample 2**
 
```cs
Priority(0.20)
Positioning(0.1)
Unambiguity(0.1, 8)
Cluttering(0.05, 30)
CoastalPoint(0.25, water, 10.0,true)
FeatureOverlapping(0.3, http://129.206.74.245:8012/tms_r14.ashx?x={x}&y={y}&z={z}, 16, 0.8;0.2;0.0)	
```