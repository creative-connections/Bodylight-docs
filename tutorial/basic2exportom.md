# 2. Export Model to FMU in OpenModelica

"Explicit Euler" solver is here mentioned and supported by following compiler tool. OpenModelica since 1.16 can export FMU with "CVODE" solver, but it is not yet supported by the following compiler tool.

In this step we will export a Modelica model into FMU in Co-Simulation mode using OpenModelica tool. If you use Dymola - follow previous section and skip this section.

## Start OpenModelica Editor

* Start OMEdit.

![OMstart](../img/OM\_start.png)

## Open Model File

Open a Modelica model you would like to use in web simulator.

* In this guide, we will open Physiolibrary ^\[https://www.physiolibrary.org free open-source Modelica library designed for modeling human physiology. ] via `File -> System Libraries -> Physiolibrary`
* and implementation of model of Hemodynamics by Fernandez de Cañete ^\[Kulhánek T, Tribula M, Kofránek J, Mateják M: Simple models of the cardiovascular system for educational and research purposes. MEFANET Journal 2014; 2(2); ISSN:1805-9171. Available at WWW: https://mj.mefanet.cz/mj-04140914.]

![OM\_MeursModel](../img/OM\_CaneteModel.png)

## Setup FMU Export options

* Open `Tools -> Options -> FMI`
* check these options
  * Version: `2.0`
  * Type: `Co-Simulation`
  * Move FMU: `/vagrant_data` or any other existing directory
  * Solver for Co-Simulation: `Explicit Euler` ^\[OpenModelica can export FMU in Co-simulation with "explicit Euler" solver or "CVODE" solver since OM version 1.16. Use "explicit Euler" solver for further use in Bodylight.js-FMU-Compiler. "CVODE" solver is not yet supported by the compiler tool, as it needs additional manual steps to do.]
  * Model Description Filter: `internal`
  * Include Source Code: checked&#x20;

![OM\_FMUSettings](../img/OM\_FMUSettings.png)

## Do FMU Export

* right click on the selected model and select `Export -> FMU`

![OM\_FMUExport](../img/OM\_FMUExport.png)

## Use FMU file

Last step created a file with `.fmu` extension in directory set in step 2.2 Check it in your file system.

![bash\_FMUFile](../img/bash\_FMUFile.png)

And use this file in following section.
