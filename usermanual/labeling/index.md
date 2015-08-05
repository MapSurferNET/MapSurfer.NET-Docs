# Labeling 

This section presents the capabilities and functionalities of a labeling engine implemented in MapSurfer.NET.

[Automated label placement](https://en.wikipedia.org/wiki/Automatic_label_placement) is known as one of the most difficult and complex problems in [computer cartography](https://en.wikipedia.org/wiki/Digital_mapping). Therefore, it is normally split up into smaller and simple independent sub-problems, or sub-tasks. These sub-tasks (see figure below) are defined as:

- **Candidate-position generation**: A method that generates a set of label candidates
for each map feature, using its spatial characteristics and taking into account its
type (e.g., point, line or area). The generated label positions (candidates) are considered as the *search space* for the *position selection* procedure.

- **Position evaluation**: A process of scoring each label candidate using a quality function, which measures how well a label is positioned with respect to the geographic object it tags as well as to other labels and features on the map. In general, the quality function should consider and reflect formal cartographic guidelines (see works by [Imhof, 1975](http://www.mapgraphics.net/downloads/Positioning_Names_on_Maps.pdf) and [Wood, 2000](http://www.maneyonline.com/doi/abs/10.1179/caj.2000.37.1.5)) applied to a certain type of designation.

- **Position selection**: A process of choosing only one label position from each set of candidates so that the total sum of labels scores is globally maximized. The higher the score, the more superior level of cartographic quality of the resulting labeling.

<center>![](/media/images/32-labeling-subtasks.png)</center>


## Candidate-position generation <div id="candidate-position">

In cartography, geographic features are labeled using three classes of label  placement (or designations). They are position (e.g., settlements, peaks, etc.), linear (e.g., rivers, streams, mountain ranges, paths, etc.) and areal (e.g., countries, islands, lakes, valleys, etc.) designations. Each type of designation has its own principles and requirements.Furthermore, every type of designation can have different forms of presentations, for example, an island can be labeled using either a horizontally aligned text or a curve text. For more information, we refer to a fundamental work by [Eduard Imhof (1975)](http://www.mapgraphics.net/downloads/Positioning_Names_on_Maps.pdf). 

In MapSurfer.NET framework, the type of designation (or label placement type) is specified in *LabelPlacement* property of a corresponding symbolizer. LabelPlacement property can take one of the following values:     

- [PointPlacement](/usermanual/labeling/label-placement-types#pointplacement)
- [PeakPointPlacement](/usermanual/labeling/label-placement-types#peakpointplacement)
- [MultiPointPlacement](/usermanual/labeling/label-placement-types#multipointplacement)
- [CurvedPointPlacement](/usermanual/labeling/label-placement-types#curvedpointplacement)
- [LinePlacement](/usermanual/labeling/label-placement-types#lineplacement)
- [LinePatternPlacement](/usermanual/labeling/label-placement-types#linepatternplacement)
- [LinePointPatternPlacement](/usermanual/labeling/label-placement-types#linepointpatternplacement)
- [DoubleSidedLinePlacement](/usermanual/labeling/label-placement-types#doublesidedlineplacement)
- [TrapezoidAreaWeightedCenterPolygonPlacement](/usermanual/labeling/label-placement-types#trapezoidareaweightedcenterpolygonplacement)
- [BBoxCentroidPolygonPlacement](/usermanual/labeling/label-placement-types#bboxcentroidpolygonplacement)
- [RandomPointPolygonPlacement](/usermanual/labeling/label-placement-types#randompointpolygonplacement)
- [BoxesInsdiePolygonPlacement](/usermanual/labeling/label-placement-types#boxesinsdiepolygonplacement)
- [GridPatternPolygonPlacement](/usermanual/labeling/label-placement-types#gridpatternpolygonplacement)
- [HorizontalInsidePolygonPlacement](/usermanual/labeling/label-placement-types#horizontalinsidepolygonplacement)
- [HorizontalOutsidePolygonPlacement](/usermanual/labeling/label-placement-types#horizontaloutsidepolygonplacement)
- [StraightInsidePolygonPlacement](/usermanual/labeling/label-placement-types#straightinsidepolygonplacement)

A diagram of label placement types available in MapSurfer.NET is presented in the following figure.

<center>![](/media/images/33-labeling-placement-types.png)</center> 

## Quality evaluation <div id="quality-evaluation"> 

The quality function computes a single numerical score by using a function that is normally expressed through a weighted sum of single metrics [van Dijk et al., 2002](10.1080/13658810210138742). These metrics reflect, in one way or another, the formalized cartographic precepts (Imhof, 1975; Wood, 2000). According to van Dijk et al. (2002), this function can be expressed as:.

<center>![](/media/images/34-labeling-quality-function.png)</center>

where *L* is a set of labels on the map, *F* is a set of non-textual map features, *w<sub>i</sub>*,
*i = 1,2, . . . ,5* are the weights that define the contribution of each metric to the overall quality value. The functions *q*<sub>*</sub>, or metrics, correspond to cartographic criteria summarized by the cartographers in various textbooks and scientific articles. 

MapSurfer.NET's labeling engine has partial implementation of [quality metrics](/usermanual/labeling/quality-metrics) given in the above-mentioned equation. The list of supported quality metrics is:
 
- [Cluttering](/usermanual/labeling/quality-metrics#Cluttering)
- [Coastal Point](/usermanual/labeling/quality-metrics#CoastalPoint)
- [Feature Overlapping](/usermanual/labeling/quality-metrics#FeatureOverlapping)
- [Max Distance](/usermanual/labeling/quality-metrics#MaxDistance)
- [Positioning](/usermanual/labeling/quality-metrics#Positioning)
- [Priority](/usermanual/labeling/quality-metrics#Priority)
- [Unambiguity](/usermanual/labeling/quality-metrics#Unambiguity)
- [Water](/usermanual/labeling/quality-metrics#Water)
- [Water Coverage](/usermanual/labeling/quality-metrics#WaterCoverage)

## Position selection <div id="position-selection">

Position selection task is treated as a mathematical optimization (or mathematical programming) problem which can be solved using one of the existing algorithms, for example, [*greedy*](http://www.maneyonline.com/doi/abs/10.1179/caj.1972.9.2.99) algorithm, [*discrete gradient descent*](http://www.tandfonline.com/doi/abs/10.1559/152304082783948367#.VbjLufkqdUE) method, [*simulated annealing*](http://dl.acm.org/citation.cfm?id=212334) algorithm,[*genetic*](http://pubsonline.informs.org/doi/abs/10.1287/ijoc.9.3.266) algorithm or [*tabu search*](http://link.springer.com/article/10.1023%2FA%3A1013720231747) heuristic. Note that the selection is an NP-hard problem in general. Therefore, all listed algorithms, often called solvers, try to find a feasible near-optimal solution for label placement.

At the moment, the following solvers are implemented and available in MapSurfer.NET: 

- [Greedy](/usermanual/labeling/solvers#Greedy)
- [Local Search](/usermanual/labeling/solvers#LocalSearch)
- [Simulated Annealing](/usermanual/labeling/solvers#SimulatedAnnealing)
- [Hybrid Simulated Annealing](/usermanual/labeling/solvers#HybridSimulatedAnnealing)

You can find more details about solvers and their parameterization in Section [Solvers](/usermanual/labeling/solvers).
