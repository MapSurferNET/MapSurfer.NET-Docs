# Labeling Solvers

This section presents detailed information about solvers and their parameterization.

## Greedy <div id="Greedy">

A greedy algorithm is an algorithm that makes a decision on basis of information available at the current stage. The lack of backtracking strategy reduces the quality of the solutions that it finds. In many cases, especially with great number of label candidates, a greedy strategy may not provide the globally optimal or even near-optimal solution. However, this type of algorithm can produce a plausible labeling in a reasonable time.

This simple algorithm does not have any parameters.

## Local Search <div id="LocalSearch">

Local search algorithm, also called a discrete gradient descent method, is an improved version of a greedy algorithm. This algorithm allows labels repositioning that yields the most immediate improvement. In practice it produces much better quality of labeling. Note that as a greedy algorithm, local search belongs to the family of simple and straightforward algorithms that are not able to escape from local minima of the quality function.

This algorithm has the following list of parameters:  

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
AnchorPlacementsOnEdges | Boolean | Specifies whether to anchor label placements (exclude from repositioning) that intersect edges of the map. Default value is False. | No
InterruptWhenNoCollisions | Boolean | Specifies whether to interrupt the iterative process if all labels were placed and there are no more collisions between labels. | No
MaxExecutionTime | Integer | The maximum execution time expressed in seconds. | No
    
## Simulated Annealing <div id="SimulatedAnnealing">

[Simulated annealing](https://en.wikipedia.org/wiki/Simulated_annealing) is a stochastic gradient-descent method proposed for finding the global minimum of a scoring function that is able get out from local minima. This algorithm is very efficient for solving a problem with a large search space (great number of labels). Simulated annealing solver is recommended to obtain cartographically plausible labeling. However, it is important to note that this algorithm should be parameterized carefully as its wrong configuration can lead to a noticeable performance degradation of the map rendering process as a whole.   

This algorithm has the following list of parameters:  

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
AnchorPlacementsOnEdges | Boolean | Specifies whether to anchor label placements (exclude from repositioning) that intersect edges of the map. Default value is False. | No 
InterruptWhenNoCollisions | Boolean | Specifies whether to interrupt the iterative process if all labels were placed and there are no more collisions between labels. | No
MaxRejectionsCount | Integer | Specifies the maximum number of consecutive rejections after which the iterative process is interrupted. | No
CoolingSchedule | String | Specifies annealing, or cooling, schedule. Possible values are Linear, Exponential and AartsLaarhoven. Default value is Exponential. | No
MaxTemperature | Integer | The maximum temperature. Default value is 10. | No
MinTemperature | Integer | The minimum temperature. Default value is 0.01. | No
MaxExecutionTime | Integer | The maximum execution time expressed in seconds. | No
StepsCount | Integer | The maximum number of iterations. | No
StepIterationsCount | Integer | The number of label repositions at each temperature. 
TransitOnlyLabelsWithCollisions | Boolean | Specifies whether transitions are allowed only for labels with collisions. | No 


## Hybrid Simulated Annealing <div id="HybridSimulatedAnnealing">

This algorithm is a modified version of Simulated Annealing solver. In contrast to Simulated Annealing, this algorithm anchors none point-like placements and disallows their further repositioning. 