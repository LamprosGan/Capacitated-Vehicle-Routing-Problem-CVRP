# Capacitated Vehicle Routing Problem (CVRP)
"Repository for files related to the Capacitated Vehicle Routing Problem (CVRP)."

## Mathematical Modeling according to the Miller - Tucker - Zemlin Approach
Constraints related to the elimination of subtours have undergone modifications over time, such as those proposed by Kulkarni-Bhave, Desrochers, and Laporte. Today, the formula for the CVRP problem based on the theory of Miller - Tucker - Zemlin is defined on a graph G = (V, A), where V = {0, 1, …, n}, representing the set of nodes. {0} is the depot, and the rest are customers. A = {(i, j): i, j ∈ V, i ≠ j} is the set of arcs between customers, with the traveled distance denoting the transportation cost 𝑐𝑖𝑗, where 𝑐𝑖𝑗 = 𝑐𝑗𝑖 for each (i, j) ∈ A. Finally, there are m vehicles available at the depot, and the triangular inequality holds in this problem.

The objective function according to Miller - Tucker - Zemlin is:

![image](https://github.com/LamprosGan/Capacitated-Vehicle-Routing-Problem-CVRP/assets/101817382/8e793604-c06c-4260-b1cd-2eca86ec3a4a)


∑𝑛
𝑖=1 𝑥0𝑖 <= 𝑚 (2)
∑𝑛
𝑖=1 𝑥𝑖0 <= 𝑚 (3)
∑𝑛
𝑖=0 𝑥𝑖𝑗 = 1 𝑗 = 1,2, … . . 𝑛 (4)
∑𝑛
𝑗=0 𝑥𝑖𝑗 = 1 𝑖 = 1,2, … . . 𝑛 (5)
𝑢𝑖− ∑𝑛
𝑗=1 ,𝑗≠𝑖 𝑞𝑗𝑥𝑗𝑖 ≥ 𝑞𝑖 𝑖 = 1,2, … . . 𝑛 (6)
𝑢𝑖 + (𝑄 − 𝑚𝑎𝑥𝑗≠𝑖{𝑞𝑗} − 𝑞𝑖)𝑥0𝑖 + ∑𝑛
𝑗=1,𝑗≠𝑖 𝑞𝑖𝑥𝑖𝑗 ≤ 𝑄 , 𝑖 = 1,2, … . . 𝑛 (7)
𝑢𝑖 − 𝑢𝑗 + 𝑄𝑥𝑖𝑗 + (𝑄 − 𝑞𝑖− 𝑞𝑗)𝑥𝑖𝑗 ≤ 𝑄 − 𝑞𝑗 , 𝑖 ≠ 𝑗 , 𝑖, 𝑗 = 1,2, … . . 𝑛 (8)
𝑥𝑖𝑗 ∈ {0,1} 𝑖, 𝑗 ∈ 𝐴 (9)

Where 𝑥𝑖𝑗 = 0 when 𝑞𝑖 + 𝑞𝑗 > Q for all i, j, and 𝑢𝑖, 𝑢𝑗 𝛾𝜄𝛼 ∀𝑖, 𝑗 ∈ 𝑉 \ {0} represent the vehicle's capacity at each location. Objective function (1) aims to minimize the total transportation cost, which depends on the total distance traveled by all vehicles. Constraints (2) and (3) ensure that the vehicles enter and exit the depot equal to their quantity. Constraints (4) and (5) express that each customer-node is visited only once. Then, constraints (6) and (7) determine the upper and lower bounds of 𝑢𝑖 and satisfy 𝑞𝑖 ≤ 𝑢𝑖 ≤ Q, called capacity bounding constraints. Finally, constraint (8) ensures the continuity of the route without subtours according to the demand of the customers on the vehicle's route.
