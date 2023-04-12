# NatCompAssignment6

This is a repository containing the code for Natural Computing Assignment 6. 

## Running the code:
-) Download the files
-) Open wrapper.html in the browser of your choice

## In-depth explanation

For this project, the no-install version of the artistoo framework was used, therefore the
”installation” was just downloading the artistoo.js and fpsmeter.min.js from their
webpage and setting up a basic HTML template for the control simulation as well as the
simulation with the obstacles. For a better comparison a third file, a wrapper, was created
to have both of the simulations displayed next to each other. This wrapper file basically
just loads each of the simulation in an HTML iframe, so the simulations do not interfere
with each other, but start at the same time.

### CellMigrationWithObstacles.html
The most important file is the CellMigrationWithObstacles.html which runs the sim-
ulation for the experiment with the obstacles. The first part of the script section defines
the parameters for the simulation.
Some general parameters, such as the dimension of the grid (ndim), the size of the grid
(field size) and a seed for reproducibility are set. Furthermore, the parameters for the
cell behaviour itself are set, such as the temperature (T), the volume constraint parameter,
the perimeter constraint parameters and the activity constraint parameters. Each of those
constraint parameters consist of two values, the importance parameter (called lambda) and
the target parameter. The activity constraint has an additional parameter, that decides
whether the neighbourhood activity is computed using the geometric or the arithmetic
mean. The last cell behaviour parameter that needed to be set, was the adhesion parame-
ters, which are saved in a matrix, where each row contains the adhesion behaviour for one
cell type towards itself and the other two cell types.
The last part of the configuration contains the simulation settings, where the initial
number of non-background cells can be set using the NRCELLS parameter, as well as the
colour for each cell and the borders of the cells. Some general parameters like the zoom of
the simulation, the RUNTIME and the FRAMERATE are also set here.
After the configuration several functions are defined, the initialize, step, initial-
izeGrid and the drawCanvas functions. The first one is used to define custom functions as
well as adding the PersistenceConstraint as an additional constraint. This was needed
to draw lines indicating the direction, the cell is moving towards. As this would impact
the simulation the weight of the peristence constraint was set to zero for all simulations,
so it has no impact on the behaviour of the cells, but gives visual information to the user.
The step function was used to let the simulation run. For the initializeGrid function
an example from the github repository of artistoo2 was used to seed obstacle cells as well
as moving cells in a equidistant manner. Both cells were seeded at the same location for all
the simulations to guarantee comparability. Last but not least, the drawCanvas function
was taken from an example from artistoo.net3. This function is used to draw the visual
indication of the direction a cell is moving in.
### CellMigrationBaseline.html
This file was used as a control for the simulations with obstacles. It is an exact copy of
the CellMigrationWithObstacles.html file, therefore all the parameters being the same,
with the sole exception that no obstacle cells are seeded.
