Here we solve the network flows optimization problem propused by AIMMS in https://download.aimms.com/aimms/download/manuals/AIMMS3_OM.pdf using AIMMS software.

In this problem, we have two sources, located in Arnhem and Gouda, and six customers, located in London, Berlin, Maastricht, Amsterdam, Utrecht and The Hague. For reasons of efficiency, deliveries abroad are only made by one source. So that, Arnhem delivers to Berlin and Gouda to London.

We can find the original limits of production/supply for each source, the demand for each customer and transportation costs between each source and customer in network_flows_optimization\data\data_0.xlsx. In this problem, the goal is to satisfy the customers’ demand while minimizing transportation costs.

The main project file is network_flows_optimization\network_flows_optimization.aimms (see Image1.PNG). You can ask for a free developer license with CBC solver (AIMMS Community Edition) to open the project and review the code here: https://www.aimms.com/support/licensing/ (see Image2.PNG).

When you open the project, a dialog message appears asking for an input data file to work with (see Image3.PNG). The optimization model will be run with this data file and the output data will be stored in 'network_flows_optimization\data' folder.

If you want to try the model again, you can close and open the project or run 'MainExecution' procedure (see Image4.PNG and Image5.PNG). 
 
We have four data files in 'network_flows_optimization\data' folder that we can use to try the code:
* data_0.xlsx. This is the base case.
* data_1.xlsx. Shadow price interpretation for source constraints. Using base case, we move one ton of supply capacity from Gouda to Arnhem and the objective function improves in 0.2 euros (shadow price for Arnhem in the base case).
* data_2.xlsx. Shadow price interpretation for customer constraints - case 1. Using the base case, we increase the demand in London in one ton and we increase one ton of supply capacity in Gouda (Gouda is the only source for London). Then the objective function gets worse in 2.5 euros (shadow price for London in the base case).
* data_3.xlsx. Shadow price interpretation for customer constraints - case 2. Using the base case, we increase the demand in Berlin in one ton and we increase one ton of supply capacity in Gouda (Arnhem is the only source for Berlin). Then the objective function gets worse in 2.7 euros (shadow price for Berlin in the base case).
* data_4.xlsx. Reduced cost interpretation for not active routes. Using the base case, we fixed a transportation between Arnhem and Amsterdam equal to 1 ton. Then the objective function gets worse in 0.6 euros (reduced cost for this transportation in the base case).