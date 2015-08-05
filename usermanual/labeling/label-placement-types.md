# Label Placement Types

This section provides the details about label placement types, which are used to specify the rules of positioning labels in text-related symbolizers (see *LabelPlacement* property). Note that placement parameters are considered in [candidate-position generation](/usermanual/labeling/index#candidate-position) procedure which defines the *search space* of a labeling problem. 


## PointPlacement

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



## PeakPointPlacement

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


## MultiPointPlacement


**Example**


## CurvedPointPlacement


**Example**


## LinePlacement

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
PathLengthExceeding | Single | Specifies the distance on which a label can exceed the length of a linear feature. | No
PerpendicularOffset | Single | Specifies the perpendicular offset of a label from the line it tags. The sign of a value defines whether a label will be drawn on the left or on the right side of the line respectively. | No
PositionTolerance | Single | Specifies the maximum allowed deviation of label in pixels from a position which is computed using Spacing parameter. | No
PositionToleranceStep | Single | Determines the step of PositionTolerance increment. Default value is 1. | No
PositionToleranceStepFactor | Single | Determines the factor which is applied to a subsequent PositionToleranceStep. Default value is 1. | No
Spacing | Single | Specifies the distance between repeated labels. Default value is 0. | No
TextOrientation | Single | Specifies the orientation of the text. Possible values are: Any, LeftToRight, RightToLeft. Default value is Any. | No
UpsideDownFactorThreshold | Single | Specifies the threshold for the number of characters drawn upside down. If the threshold is crossed, a label with different orientation will be tried. Value given in percents. Default value is 70%. | No

## LinePatternPlacement


**Example**

## LinePointPatternPlacement


**Example**

## DoubleSidedLinePlacement

![](/media/images/40-labeling-doublesidedlineplacement.png)


**Example**

## TrapezoidAreaWeightedCenterPolygonPlacement


**Example**

## BBoxCentroidPolygonPlacement 


**Example**
## RandomPointPolygonPlacement 

**Example**

## BoxesInsdiePolygonPlacement 


**Example**

## GridPatternPolygonPlacement 

**Example**


## HorizontalInsidePolygonPlacement 

**Example**

## HorizontalOutsidePolygonPlacement 

**Example**

## StraightInsidePolygonPlacement 

![](/media/images/42-labeling-horizontaloutsidepolygonplacement)


**Example**

![](/media/images/41-labeling-straightinsidepolygonplacement.png)