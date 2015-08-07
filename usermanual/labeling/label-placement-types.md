# Label Placement Types

This section provides the details about label placement types, which are used to specify the rules of positioning labels in text-related symbolizers (see *LabelPlacement* property). Note that placement parameters are considered in [candidate-position generation](/usermanual/labeling/index#candidate-position) procedure which defines the *search space* of a labeling problem. 

## Point Placements

### PointPlacement

**PointPlacement** is used to label not only point-like features, but also areal objects, whose extents are small enough to apply any other placement type such as, for example, [HorizontalInsidePolygonPlacement](#HorizontalInsidePolygonPlacement) or [StraightInsidePolygonPlacement](StraightInsidePolygonPlacement). The following figure illustrates an example of a model for positional prioritization of point-feature labeling (see Alignments parameter).

![](/media/images/39-labeling-point-positional-prioritization.png)

**Example**

![](/media/images/36-labeling-pointplacement.png)

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Alignments | Alignment[] | Specifies a relative position of a label to the corresponding point feature. Possible values are: TopLeft, TopCenter, TopRight, MiddleLeft, MiddleCenter, MiddleRight, BottomLeft, BottomCenter, BottomRight, Around. | Yes
AngleExpression | Single | Specifies the angle of rotation (in degrees) at which the text will be drawn. | No
Displacement | Point | Specifies the displacement of a label from the original position. | No
HorizOffsetStep | Single | Specifies the step (in pixels) used to generate label placements that touches the point.  | No
MaxiumHorizOffset | Single | Specifies the maximum horizontal offset (in percents) from the MiddleCenter position. | No
PointOnSurface | Boolean | Specifies whether to check if a point lies within an areal feature it tags. Default value is True. | No
PointTextOffset | Single | Specifies the additional distance between symbol and text. Default value is 0. | No
PositionInCenter | Boolean | Specifies whether to compute a centroid point for areal feature or not. Default value is True. | No
PositionTolerance | Single | Specifies the maximum allowed deviation in pixels from the original point where label can be placed. | No
PositionToleranceStep | Single | Determines the step of PositionTolerance increment. Default value is 1. | No
PositionToleranceStepFactor | Single | Determines the factor which is applied to a subsequent PositionToleranceStep. | No
RandomAlignment | Boolean | Specifies whether elements of Alignments list are taken randomly. Default value is False. | No.


### PeakPointPlacement

**PeakPointPlacement** is used to label a specific type of geographic features such as mountain peaks. This type of placement is very similar to **PointPlacement**, but have some noticeable distinctions. First, it allows to output text in curved manner (German style). Second, it allows splitting text into two blocks, where the first block is the name of a peak and the second block is its height, drawn above and below the symbol respectively. The figures below illustrate a resulting labeling produced by using **PeakPointPlacement** with different parameterization.

**Example**

![](/media/images/35-labeling-peakpointplacement.png)

![](/media/images/37-labeling-peakpointplacement.png)

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Alignments | Alignment[] | Specifies a relative position of a label to the corresponding point feature. Possible values are: TopLeft, TopCenter, TopRight, MiddleLeft, MiddleRight, BottomLeft, BottomCenter, BottomRight. | Yes
Displacement | Point | Specifies the displacement of a label from the original position. | No
Curved | Boolean | Determines whether the text is curved or not. | No
AngleStep | Single | Specifies the increment of the angle which varies in the range [MinimumAngle, MaximumAngle]. The less the value, the greater number of candidates are generated. Default value is 5. | Yes
MaximumAngle | Single | Specifies the maximum possible angle in degrees that defines the curvature of the text. Default value is 135. | Yes
MinimumAngle | Single | Specifies the minimum possible angle in degrees that defines the curvature of the text. Default value is 135. | Yes


### MultiPointPlacement

**MultiPointPlacement** allows to label a series of points (e.g., nodes of a polyline) using an array of text values of the same size.

**Example**

![](/media/images/50-labeling-multipointplacement.png)

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Displacement | Point | Specifies the displacement of a label from the original position. | No
Integrated | Boolean | Specifies whether text of the nodes are considered as a single label or not | No

### CurvedPointPlacement

**CurvedPointPlacement** allows to apply a well-known cartographic technique described in [Imhof (1975, see Figure 32 and 33, p. 133)](http://www.mapgraphics.net/downloads/Positioning_Names_on_Maps.pdf) of placing the names of coastal places in curved manner.

**Example**

![](/media/images/49-labeling-curvedpointplacement.png)

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Displacement | Point | Specifies the displacement of a label from the original position. | No
Alignments | Alignment[] | Specifies a relative position of a label to the corresponding point feature. Possible values are: TopLeft, TopRight, MiddleLeft, MiddleRight, BottomLeft, BottomRight. Default values are MiddleLeft and MiddleRight. | Yes
PointTextOffset | Single | Specifies the additional distance between symbol and text. Default value is 0. | No
AngleStep | Single | Specifies the increment of the angle which varies in the range [10, 40] degrees. The less the value, the greater number of candidates are generated. Default value is 5. | Yes
CurvatureRadius | Single | Specifies the curvature of the text in label. Default value is 45 degrees. | No

## Line Placements

### LinePlacement

**LinePlacement** is designed to set and control label placement along linear features such as rivers, mountain ranges, roads, etc.  

**Example**

![](/media/images/38-labeling-lineplacement.png)

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
AllowVerticalLayout | Boolean | Determines whether to perform vertical layout of characters that belong to East Asian languages such as Chines, Japanese, etc. Default value is False. | No 
IsRepeated | Boolean | Specifies whether labels are repeated along a line. Default value is True. | No
MaxAngleDelta | Single | Specifies the maximum allowed angle, in degrees, between adjacent characters in a curved label. Default value is True. | No
MinimumFeatureSize | Single | Specifies the minimum feature size in pixels. If the size of a feature is less than the given threshold, the feature is not labeled. | No
MinimumUpsideDownFactor | Single | Specifies the percentage of characters in the label that should not be upside down. The higher the value, fewer upside down characters are allowed. Default value is 50%. | No
PathLengthExceeding | Single | Specifies the distance on which a label can exceed the length of a linear feature. Default value is 0. | No
PerpendicularOffset | Single | Specifies the perpendicular offset of a label from the line it tags. The sign of a value defines whether a label will be drawn on the left or on the right side of the line respectively. | No
PositionTolerance | Single | Specifies the maximum allowed deviation of label in pixels from a position which is computed using Spacing parameter. | No
PositionToleranceStep | Single | Determines the step of PositionTolerance increment. Default value is 1. | No
PositionToleranceStepFactor | Single | Determines the factor which is applied to a subsequent PositionToleranceStep. Default value is 1. | No
Spacing | Single | Specifies the distance between repeated labels. Default value is 0. | No
TextOrientation | Single | Specifies the orientation of the text. Possible values are: Any, LeftToRight, RightToLeft. Default value is Any. | No
UpsideDownFactorThreshold | Single | Specifies the threshold for the number of characters drawn upside down. If the threshold is crossed, a label with different orientation will be tried. Value given in percents. Default value is 70%. | No

### LinePointPatternPlacement

**LinePointPatternPlacement** allows to place a series of graphic symbols along a linear feature according to a predefined pattern. 

**Example**

![](/media/images/51-labeling-linepointpatternplacement.png)

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
AngleExpression | Single | Specifies the angle of rotation (in degrees) at which the graphic symbol will be drawn. | No
Displacement | Point | Specifies the displacement of a symbol from its preferable position on a line. | No
Pattern | Single[] | Specifies the pattern for placing labels. This pattern is an array of real number that specifies the spaces between symbols. | Yes
PatternInterval | Single | Specifies the scale of the pattern. Default value is 1. | No 

### DoubleSidedLinePlacement

**DoubleSidedLinePlacement** is used to perform pairwise labeling of linear features that present geographic boundaries. This kind of placement helps to easily distinguish boundaries from other linear objects and amplifies the precise graphic relation between the toponyms their features. Furthermore, two names are considered as a unit or a single label. An algorithm for this placement method was taken from the work by [Rylov and Reimer (2015)](http://www.cartographicperspectives.org/index.php/journal/article/view/cp79-rylov-reimer/1375).

**Example**

![](/media/images/40-labeling-doublesidedlineplacement.png)

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
IsRepeated | Boolean | Specifies whether labels are repeated along a line. Default value is True. | No
MinimumFeatureSize | Single | Specifies the minimum feature size in pixels. If the size of a feature is less than the given threshold, the feature is not labeled. | No
MinimumLinesGap | Single | Specifies the minimum allowed distance in pixels between two toponyms. Default value is 2. | No
MaximumLinesGap | Single | Specifies the maximum allowed distance in pixels between two toponyms. Default value is 4. | No
OptimalPlacement | Boolean | Specifies whether to perform an internal optimization to find the best location within label candidates. Default value is True. | No
PathLengthExceeding | Single | Specifies the distance on which a label can exceed the length of a linear feature. Default value is 0. | No
PositionTolerance | Single | Specifies the maximum allowed deviation of label in pixels from a position which is computed using Spacing parameter. | No
PositionToleranceStep | Single | Determines the step of PositionTolerance increment. Default value is 1. | No
PositionToleranceStepFactor | Single | Determines the factor which is applied to a subsequent PositionToleranceStep. Default value is 1. | No
QualityThreshold | Single | Specifies the quality threshold to control and eliminate candidate label positions that corresponded to poor and sloppy label placement. Values belong to the range [0,1], where 1 means that only labels with the highest quality are allowed. Default value is 0.7. | No
Spacing | Single | Specifies the distance between repeated labels. Default value is 0. | No
SuppressPartialLabels | Boolean | Specifies whether partial labels (only one toponym is given) are suppressed. Default value is False. | No 


## Polygon Placements

### BBoxCentroidPolygonPlacement 

**BBoxCentroidPolygonPlacement** defines a simplest method to label a polygon. Label position is a center of a bounding box calculated for a given polygon. 

**Example**

![](/media/images/45-labeling-bboxcentroidpolygonplacement.png)

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
AvoidHoles | Boolean | Specifies whether to avoid placing labels in holes. Default value is True. | No
LargestFeatureOnly | Boolean | Specifies whether to label only largest part of a polygon. Default value is True. | No
MinimumFeatureSize | Single | Specifies the minimum feature area in pixels. If the area of a feature is less than the given threshold, the feature is not labeled. | No
PointOnSurface | Boolean | Specifies whether to check if a point lies within an areal feature it tags. Default value is True. | No
PositionTolerance | Single | Specifies the maximum allowed deviation of label in pixels from the center of bounding box. | No
PositionToleranceStep | Single | Determines the step of PositionTolerance increment. Default value is 1. | No
PositionToleranceStepFactor | Single | Determines the factor which is applied to a subsequent PositionToleranceStep. Default value is 1. | No

### TrapezoidAreaWeightedCenterPolygonPlacement

**TrapezoidAreaWeightedCenterPolygonPlacement** is an advanced technique to label areal features. The original algorithm for this placement type is taken from the work by [Carstensen (1987)](http://www.utpjournals.press/doi/abs/10.3138/GH04-24H7-63T8-167V). It calculates the center of gravity for the polygon by weighting the center point of each edge segment by the area of the trapezoid that that segment forms with the X or Y axis. This algorithm produces better results in comparison to **BBoxCentroidPolygonPlacement** placement type.   

**Example**

![](/media/images/46-labeling-trapezoidareaweightedcenterpolygonplacement.png)

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
AvoidHoles | Boolean | Specifies whether to avoid placing labels in holes. Default value is True. | No
LargestFeatureOnly | Boolean | Specifies whether to label only largest part of a polygon. Default value is True. | No
MinimumFeatureSize | Single | Specifies the minimum feature area in pixels. If the area of a feature is less than the given threshold, the feature is not labeled. | No
PointOnSurface | Boolean | Specifies whether to check if a point lies within an areal feature it tags. Default value is True. | No
PositionTolerance | Single | Specifies the maximum allowed deviation of label in pixels from the center of bounding box. | No
PositionToleranceStep | Single | Determines the step of PositionTolerance increment. Default value is 1. | No
PositionToleranceStepFactor | Single | Determines the factor which is applied to a subsequent PositionToleranceStep. Default value is 1. | No


### BoxesInsdiePolygonPlacement

**BoxesInsdiePolygonPlacement** is used to place labels entirely inside of a polygon. The original algorithm for this placement type is taken from the work by [van Roessel (1989)](http://www.tandfonline.com/doi/abs/10.1559/152304089783814034?journalCode=tcag18#.VcMoEvkqdUE). The algorithm computes a number of horizontally aligned rectangles (boxes) within a polygon. Next, the location and extents of these rectangles are used for generating label candidates.

**Example**

![](/media/images/43-labeling-boxesinsdiepolygonplacement.png)

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
AvoidHoles | Boolean | Specifies whether to avoid placing labels in holes. Default value is True. | No
LargestFeatureOnly | Boolean | Specifies whether to label only largest part of a polygon. Default value is True. | No
MinimumFeatureSize | Single | Specifies the minimum feature area in pixels. If the area of a feature is less than the given threshold, the feature is not labeled. | No
FitRatio | Single | Specifies the threshold of how good the label should fit into a polygon. Values belong to the range [0,1], where 1 means that only labels with the highest quality are allowed. Default value is 0. | No
MaximumCandidates | Integer | Specifies the maximum number of label placements that will be considered as candidates in [position selection](/usermanual/labeling/#candidate-position-generation). Default value is 0, which means that all candidates will be taken into account. | No
PrioritizeCandidates | Boolean | Specifies whether to generate all candidates and only then sort them by placement quality. Default value is False. | No

### HorizontalInsidePolygonPlacement

**HorizontalInsidePolygonPlacement** is a modified version of **BoxesInsdiePolygonPlacement**. 

**Example**

![](/media/images/44-labeling-horizontalinsidepolygonplacement.png)

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
AvoidHoles | Boolean | Specifies whether to avoid placing labels in holes. Default value is True. | No
LargestFeatureOnly | Boolean | Specifies whether to label only largest part of a polygon. Default value is True. | No
MinimumFeatureSize | Single | Specifies the minimum feature area in pixels. If the area of a feature is less than the given threshold, the feature is not labeled. | No
FitRatio | Single | Specifies the threshold of how good the label should fit into a polygon. Values belong to the range [0,1], where 1 means that only labels with the highest quality are allowed. Default value is 0. | No
MaximumCandidates | Integer | Specifies the maximum number of label placements that will be considered as candidates in [position selection](/usermanual/labeling/#candidate-position-generation). Default value is 0, which means that all candidates will be taken into account. | No
PrioritizeCandidates | Boolean | Specifies whether to generate all candidates and only then sort them by placement quality. Default value is False. | No

### StraightInsidePolygonPlacement

**StraightInsidePolygonPlacement** is an advanced method for placing straight labels inside a polygon. The corresponding algorithm tries to detect internal regions where the label entirely fits and has an orientation that coincides with the orientation of a polygon.  

**Example**

![](/media/images/41-labeling-straightinsidepolygonplacement.png)

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
AvoidHoles | Boolean | Specifies whether to avoid placing labels in holes. Default value is True. | No
DominantAngleOnly | Boolean | Specifies whether to only allow labels along the dominant angle of a polygon. Default value is False. | No 
LargestFeatureOnly | Boolean | Specifies whether to label only largest part of a polygon. Default value is True. | No
MinimumFeatureSize | Single | Specifies the minimum feature area in pixels. If the area of a feature is less than the given threshold, the feature is not labeled. | No
FitRatio | Single | Specifies the threshold of how good the label should fit into a polygon. Values belong to the range [0,1], where 1 means that only labels with the highest quality are allowed. Default value is 0. | No
MaximumCandidates | Integer | Specifies the maximum number of label placements that will be considered as candidates in [position selection](/usermanual/labeling/#candidate-position-generation). Default value is 0, which means that all candidates will be taken into account. | No
PrioritizeCandidates | Boolean | Specifies whether to generate all candidates and only then sort them by placement quality. Default value is False. | No


### HorizontalOutsidePolygonPlacement 

**HorizontalOutsidePolygonPlacement** method is designed for efficient labeling of area features externally, i.e. outside their polygonal boundary. This algorithm tries to locate labels in a way of achieving a balance between the feature and its name that helps to emphasize their relationship. 

**Example**

![](/media/images/42-labeling-horizontaloutsidepolygonplacement.png)

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
LargestFeatureOnly | Boolean | Specifies whether to label only largest part of a polygon. Default value is True. | No
MinimumFeatureSize | Single | Specifies the minimum feature area in pixels. If the area of a feature is less than the given threshold, the feature is not labeled. | No
MaximumCandidates | Integer | Specifies the maximum number of label placements that will be considered as candidates in [position selection](/usermanual/labeling/#candidate-position-generation). Default value is 0, which means that all candidates will be taken into account. | No
Offset | Single | Specifies the offset of the label from a polygon it tags. The value is measured in pixels. Default value is 6. | No
Spacing | Single | Specifies the spacing, in pixels, between label candidates. The smaller the value, the greater the number of candidates. Default value is 2. | No

### GridPatternPolygonPlacement

**GridPatternPolygonPlacement** allows to label areas on a large-scale map when the scale becomes too large to place the label inside the area. The algorithm tries to locate labels according to a given grid pattern.


**Example**

![](/media/images/47-labeling-gridpatternpolygonplacement.png)

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
AvoidHoles | Boolean | Specifies whether to avoid placing labels in holes. Default value is True. | No
LargestFeatureOnly | Boolean | Specifies whether to label only largest part of a polygon. Default value is True. | No
MinimumFeatureSize | Single | Specifies the minimum feature area in pixels. If the area of a feature is less than the given threshold, the feature is not labeled. | No
Chessboard | Boolean | Specifies whether the labels should be placed in chessboard-like manner or not. Default value is False. | No
Spacing | Point | Specifies the allowed spacing between labels both in X and Y direction respectively. Default value is 0,0. | Yes

### RandomPointPolygonPlacement 

**RandomPointPolygonPlacement** allows to label areas on a large-scale map when the scale becomes too large to place the label inside the area. The algorithm tries to locate labels randomly, but by considering a minimum allowed distance between candidates. This placement method has a very similar principle of operation as **GridPatternPolygonPlacement**.

**Example**

![](/media/images/48-labeling-randompointpolygonplacement.png)

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
AvoidHoles | Boolean | Specifies whether to avoid placing labels in holes. Default value is True. | No
LargestFeatureOnly | Boolean | Specifies whether to label only largest part of a polygon. Default value is True. | No
MinimumFeatureSize | Single | Specifies the minimum feature area in pixels. If the area of a feature is less than the given threshold, the feature is not labeled. | No
Spacing | Single | Specifies the allowed spacing between adjacent labels. Default value is 0. | Yes