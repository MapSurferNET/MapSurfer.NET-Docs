# TextSymbolizer

**TextSymbolizer** specifies how to style text features.

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Clip | Boolean | Specifies whether geometry is clipped to map bounds before rendering or not. Default value is False. | No
GeometryExpression | String | Specifies the [expression](/usermanual/expressions/geometrytransformations) to compute a geometry to be used in rendering. This parameter is optional. If it is not specified, a default geometry field of a data source is used. | No
Graphic | [Graphic](#graphic) | Specifies the graphic object to be rendered. | Yes
GridAlignment | Boolean | Specifies whether to align symbol to a pixel grid. Default value is True. | Yes
LabelBehaviour | [LabelBehaviour](#labelbehaviour) | Specifies the role and behaviour of a label. | Yes
LabelPlacement | [LabelPlacement](usermanual/labeling/label-placement-types)| Specifies the type of a label placement (e.g. point-like, linear or areal labeling style) | No
PriorityExpression | [Expression](usermanual/expressions/index) | Specifies the priority of a label. Being an expression, this parameter allows to take values from a data source. For example, the value can be [field_priority], where field_priority is an attribute in the data source. Note, an expression must always return a numerical value. | No
TextAbbreviation | [TextAbbreviation](#textabbreviation) | Specifies the parameters for text abbreviation. | No
TextLayout | [TextLayout](#textlayout) | Specifies the parameters that define layout of the text. | No


## LabelBehaviour

**LabelBehaviour** element specifies the role and behavior of a label placement during [candidate-position generation](/usermanual/labeling/index#candidate-position). 

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
AllowOverlap | Boolean | Specifies whether the label is allowed to overlap other labels. | No
AvoidEdges | Boolean | Specifies whether the label is allowed to intersect boundaries of the map. | No
CollisionDetectable | Boolean | Specifies whether the label is considered as a candidate for a labeling algorithm. If not, the label will be simply rendered. Default value is True. | No
CollisionMeasures  | [CollisionMeasure](usermanual/labeling/collision-measures)[] | Specifies a list of collision measures. | No
DropOnCollision | Boolean | Specifies whether to drop the label if any collision with other labels exists. | No
IgnorePadding | Boolean | Specifies whether to ignore padding parameter of the map object or not. | No
QualityFilter | [Expression](usermanual/expressions/index) | Specifies the expression to filter labels by using [quality functions](/usermanual/labeling/label-placement-types). | No


## TextAbbreviation

**TextAbbreviation** element specifies how words in labels are abbreviated. 

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
DictionaryName | String | Specifies the name of a dictionary to be used. The name should correspond to the name of one of the entries in [TextAbbreviationDictionaries](/usermanual/map/index#textabbreviationdictionaries). | Yes
Enabled  | Boolean | Specifies whether abbreviation is enabled or not. | No
SkipOriginalText | Boolean | Specifies whether original text is skipped. If the value is False then original not-abbreviated text is tried out first for labeling. Default value is False. | No
StringComparison | [StringComparison](https://msdn.microsoft.com/en-us/library/system.stringcomparison%28v=vs.110%29.aspx) | Specifies the rules to use in the string comparison. Default value is OrdinalIgnoreCase. | No
WholeWordsOnly | Boolean | Specifies whether to apply abbreviation on whole words only. Default value is False. | No

At the moment MapSurfer.NET supports the following dictionary file formats:

- [Maplex](http://webhelp.esri.com/arcgisdesktop/9.1/body.cfm?tocVisable=1&ID=2705&TopicName=Abbreviating%20words%20to%20place%20more%20labels) 

```cs
   * Maplex Extension Dictionary File - v1.0
   * Format: TEXT ABBREVIATION(S) TYPE
   * where TYPE=[Translation|Keyword|Ending]

   "Street" Str St Ending
   "Road" Rd Ending
   ""Post Office"" "Post Off." PO Keyword
  
   * [end]
```

## TextLayout

**TextLayout** element specifies graphical representation of labels such as font, size, color, character spacing, etc. 

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Alignment | [Alignment](#alignment) | Specifies whether the text in the label is left-aligned, right-aligned or centered. Default value is Center.| No
Leading | Single | Determines the space between adjacent [TextBlocks](#textblock). Default value is 0. | No
Blocks | [TextBlock](#textblock)[] | Determines a list of text blocks. By default this list is empty. | Yes
FontReduction | [FontReduction](#fontreduction)[] | Specifies the set of parameters to control the reduction of the font size. | No
CombinedBlocks | Boolean | Specifies whether text blocks are combined, in other words whether one of the text blocks can be skipped from rendering if it does not fit into the current label placement. Default value is True. Note, this parameter is only combined with [LinePlacement](/usermanual/labeling/label-placement-types#lineplacement). | No

### Alignment

**Alignment** specifies the alignment of the text contents of the label.

Member Name | Description
------------ | ------------- 
Center | Text is centered.
CenterAligned | Text is centered with regard to the feature. At the same time text is aligned to the right or left margin of label's bounding box.
Left | Text is aligned to the left.
Right | Text is aligned to the right.

### FontReduction

**FontReduction** element specifies how to reduce the size and the width of the label text. This parameter allows controlling the reduction of both the width and the size of the font independently from each other.

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Enabled | Boolean | Specifies whether the reduction is enabled or not. | No
SizeInterval | Single | Determines a step interval between different font size variants to be tried out. Default value is 0.25. | No
SizeLowerLimit | Single | Specifies the lower limit of the font size. Default value is 8. | No
WidthInterval | Single | Determines an interval which will be used in compressing the width of the font. This parameter is specified in terms of a percentage of the original font width of the label. Default value is 5. The parameter can take values in the range between 1 and 20 percent. | No
WidthLowerLimit | Single | Specifies the lower limit of the font width specified in terms of a percentage of the original font width of the label. Default value is 100. The parameter can take values in the range between 1 and 100 percent. | No

### TextBlock

**TextBlock** element is responsible for displaying small amounts of text that has its own characteristics such as size, color, spacing, etc. 

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
FontSetName | String | The name of a [FontSet](/usermanual/map/index#fontsets). | No
SuppressInCombining | Boolean | Specifies whether the text block can be skipped or not if its label elements can not be located. | No
TextExpression | [Expression](/usermanual/expressions/index) | The content of the label. | No
TextFormat | [TextFormat](#textformat) | Specifies the character formatting information. | No


## TextFormat

**TextFormat** element specifies character formatting information.

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
BidiMode | Boolean | Specifies whether bi-directional mode is enabled or not. Default value is True. | No
CharPadding | [Point](https://msdn.microsoft.com/en-us/library/system.drawing.point%28v=vs.110%29.aspx) | Specifies the size of the padding around label characters. This feature helps to control the density of labels. Default value is 0,0. | No
TextSpacing | [TextSpacing](#textspacing) | Specifies the set of parameters that control leading, kerning, spacing between characters and lines, as well as spreading of the text along the tagged feature. | No
TextStyle | [TextStyle](#textstyle) | Specifies the style of the text including font size, color, decoration effects, etc. | No
TextWrapping | [TextWrapping](#textwrapping) | Determines whether and how text is wrapped when it reaches the specified limits. | No


### TextSpacing

**TextSpacing** element specifies a set of parameters that control leading, kerning, spacing between characters and lines, as well as spreading of the text along the tagged feature.

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
CharacterSpacing | Single | Specifies the spacing between characters in words. Default value is 0. | No
CollisionDetectable | Boolean | Specifies whether spacing is considered in detecting collisions between labels. Default value is True. | No
Kerning | Boolean | Specifies whether kerning is enabled or not. Default value is False. | No
Leading | Single | Determines the space between adjacent lines. Default value is 0. | No
MaximumCharactersSpacing | Single | Specifies the maximum spacing between characters allowed. Default value is 0. | No
SpreadCharacters | Boolean | Specifies whether characters are spread along the line/through polygon or not. Default value is False. | No
WordSpacing | Single | Specifies the spacing between words. Default value is 0. | No


### TextWrapping

**TextWrapping** element determines whether and how text is wrapped when it reaches the specified limits.

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
BeingLineWithCapitalLetter | Boolean | Specifies whether the first letter in the line is capitalized or not. Default value is False. | No
Characters | [WrapCharacter](#wrapcharacter) | Specifies the characters at which line wrapping is performed. Default value is 0. | No
MaxLines | Integer | Specifies the maximum allowed number of lines in the text block. Default value is 0. | No
MaxWidth | Single | Specifies the length of a line. Default value is 0. | No
Mode | [WrapMode](#wrapmode) | Specifies the mode of text wrapping. Default value is NoWrap. | No


#### WrapCharacter

**WrapCharacter** element 

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Character | Boolean | Specifies the character, or even a string, at which the wrapping needs to be performed. Default value is ''. | No
WrapType | WrapType | Determines where the wrapping is performed, i.e. either Before or After the character. Default value is After. | No


#### WrapMode

**TextWrapping** element determines whether and how text is wrapped when it reaches the specified limits.

Member Name | Description 
------------ | ------------- 
NoWrap | Line wrapping is not performed.
Wrap | Line-breaking occurs if the line has mandatory breaking symbols (see Characters).
WrapByCharacters | Line-breaking occurs if the line contains specified characters.  
WrapByMaxWidthChars | Line-breaking occurs if the line exceeds MaxWidth given in chars.
WrapByMaxWidthPixels | Line-breaking occurs if the line exceeds MaxWidth given in pixels


## TextStyle

**TextStyle** element the style of the text characteristics such as font size, color, decoration effects, etc.

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Color | Color | Specifies the text color. Default value is Black. | No
Decoration | [TextDecoration](#textdecoration) | Specifies the decoration added to text. | No
Font | [Font](#font) | Specifies the font of the text. | Yes
Halo | [Halo](#halo) | Specifies the halo of the text. | No
Opacity | Single | Specifies the opacity of the text fill. Default value is 1 (fully opaque). | No


### TextDecoration

**TextDecoration** element specifies the decoration added to text.

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Color | Color | Specifies the color of the decoration. Default value is Black. | No
Opacity | Single | Specifies the opacity of the decoration. Default value is 1 (fully opaque). | No
Scale | Single | Specifies the opacity of the text fill. Default value is 1. Possible values lie in the range [0.1, 5]. | No
Type | [TextDecorationType](#textdecorationtype) | Specifies the type of the decoration. Default value is None.| No

  
#### TextDecorationType 

Member Name | Description
------------ | ------------- 
None | Defines a normal text. This is default.
Underline | Defines a line below the text.
Overline | Defines a line above the text.
Strikethrough | Defines a line through the text.
DoubleStrikethrough | Defines a double line through the text.


### Font

**Font** element specifies the font properties.

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Name | Sting | Name of the font. Default value is platform dependent. | Yes
Size | Single | Size of the font measured in pixels. Default value is 10. | No
Stretch | Single | Specifies the font stretch parameter which allows making text wider or narrower. Default value is 1. | No
Style | FontStyle | Defines font style. Default value is Normal. Possible values are Normal, Oblique, Italic. | No
Weight | FontWeight | Defines font weight. The FontWeight enumeration describes common values for degree of blackness or thickness of strokes of characters in a font. Possible values are Thin, ExtraLight, UltraLight, Light, Normal, Regular, Medium, DemiBold, SemiBold, Bold, ExtraBold, UltraBold, Black, Heavy, ExtraBlack, UltraBlack. Default value is Regular. | No


### Halo

**Halo** element specifies the representation of the halo outline around the text.

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
BlurFactor | Single | Specifies the radius of a Gaussian Blur effect. | No
CollisionDetectable | Boolean | Specifies whether the label is considered as a candidate for a labeling algorithm. If not, the label will be simply rendered. Default value is True. | No
Color | Color | Specifies the halo color. Default value is white. | No
ColorLuminosity | [HaloColorLuminosity](#halocolorluminosity) | Specifies the text luminosity. Default is None. | No
ColorSource | [HaloColorSource](#halocolorsource) | Specifies the source of the color. | No
Displacement | [Point](https://msdn.microsoft.com/en-us/library/system.drawing.point%28v=vs.110%29.aspx) | Specifies the displacement of a texture or a hatch pattern. Default value is (0,0) | No
Mode | [HaloMode](#halomode) | Specifies the halo mode, i.e. solid or blurred. | No
Opacity | Single | Specifies the halo opacity. Default value is 1 (fully opaque). | No
PercOfLuminosity | Single | Specifies the percentage value of the luminosity. Default value is 0.5 | No
Radius | Single | Specifies the halo width. Default value is 0. | No
Sharpness | Single | Specifies the threshold for alpha channel when Smooth mode is applied. Default value is 0. | No

#### HaloColorLuminosity 

Member Name | Description
------------ | ------------- 
None | No color luminosity changes. This is default.
Lighter | Changes the color to a lighter one.
Darker  | Changes the color to a darker one.

#### HaloColorSource

Member Name | Description
------------ | ------------- 
Default | Applies color of the text. This is default.
Background | Applies color of the background image.
Text  | Applies color of the text. This is the same as Default.

#### HaloMode 

Member Name | Description
------------ | ------------- 
Solid | Defines a halo type with solid outline. This is default value.
Blurred | Defines a blurred halo.
SolidAndBlurred | Applies both Solid and Blurred modes simultaneously.

