# Capacitated Vehicle Routing Problem (CVRP)
"Repository for files related to the Capacitated Vehicle Routing Problem (CVRP)."

## Mathematical Modeling according to the Miller - Tucker - Zemlin Approach
Constraints related to the elimination of subtours have undergone modifications over time, such as those proposed by Kulkarni-Bhave, Desrochers, and Laporte. Today, the formula for the CVRP problem based on the theory of Miller - Tucker - Zemlin is defined on a graph G = (V, A), where V = {0, 1, …, n}, representing the set of nodes. {0} is the depot, and the rest are customers. A = {(i, j): i, j ∈ V, i ≠ j} is the set of arcs between customers, with the traveled distance denoting the transportation cost 𝑐𝑖𝑗, where 𝑐𝑖𝑗 = 𝑐𝑗𝑖 for each (i, j) ∈ A. Finally, there are m vehicles available at the depot, and the triangular inequality holds in this problem.

The objective function according to Miller - Tucker - Zemlin is:

![image](https://github.com/LamprosGan/Capacitated-Vehicle-Routing-Problem-CVRP/assets/101817382/8e793604-c06c-4260-b1cd-2eca86ec3a4a)


![image](https://github.com/LamprosGan/Capacitated-Vehicle-Routing-Problem-CVRP/assets/101817382/b9c0cde4-438d-4c14-aaba-b071c721008c)


Where 𝑥𝑖𝑗 = 0 when 𝑞𝑖 + 𝑞𝑗 > Q for all i, j, and 𝑢𝑖, 𝑢𝑗 𝛾𝜄𝛼 ∀𝑖, 𝑗 ∈ 𝑉 \ {0} represent the vehicle's capacity at each location. Objective function (1) aims to minimize the total transportation cost, which depends on the total distance traveled by all vehicles. Constraints (2) and (3) ensure that the vehicles enter and exit the depot equal to their quantity. Constraints (4) and (5) express that each customer-node is visited only once. Then, constraints (6) and (7) determine the upper and lower bounds of 𝑢𝑖 and satisfy 𝑞𝑖 ≤ 𝑢𝑖 ≤ Q, called capacity bounding constraints. Finally, constraint (8) ensures the continuity of the route without subtours according to the demand of the customers on the vehicle's route.

## Results
In our case, the experiment was implemented on the dataset E-n22-k4, which is one of the instances from the Elion and Christoforides' Capacitated Vehicle Routing Problem Library. This experiment pertains to the business process of reducing distribution costs for products. As mentioned earlier, it is an experiment with 21 customers, each with specific product demands, and the deliveries are made using at least 4 vehicles, each with a capacity of 6,000 units.

In this experiment, two different scenarios were considered. In the first scenario, we assumed that there are 4 vehicles performing the distribution, while in the second scenario, there are 5 vehicles. Therefore, in constraints (2) and (3) for the first scenario, only equality holds true, not less than or equal to, as in the second scenario.

In both scenarios, the algorithm completed the computation process, finding the optimal solution, which according to the dataset, was 375, and all customers/nodes were served. The optimal routes for both scenarios are as follows:

For 4 vehicles:
1st vehicle: (0, 9), (9, 7), (7, 5), (5, 2), (2, 1), (1, 6), (6, 0)
2nd vehicle: (0, 13), (13, 11), (11, 4), (4, 3), (3, 8), (8, 10), (10, 0)
3rd vehicle: (0, 16), (16, 19), (19, 21), (21, 14), (14, 0)
4th vehicle: (0, 17), (17, 20), (20, 18), (18, 15), (15, 12), (12, 0)

Notably, in the first scenario where the number of vehicles was 4, and the number of vehicles performing the routes was known, the algorithm completed the computation in approximately 2 minutes. In contrast, in the second scenario with 5 available vehicles, the total computation duration significantly increased, taking approximately 2 hours. This observation can be attributed to the fact that the constraints in the second scenario made the problem more challenging.

It's important to note that the computation time in the second scenario should not be misleading. Both scenarios successfully achieved the correct prediction, confirming the effectiveness of the algorithm in solving for the optimal solution.
