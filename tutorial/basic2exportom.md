# 2. Export Model to FMU in OpenModelica

<div class="w3-panel w3-pale-red w3-border w3-display-container">
  <h3>Under construction</h3>
  <p>This section is under construction and instruction may fail as new version of Open Modelica was not tested yet properly with an option to export FMU with CVODE solver.</p>
</div>

In this step we will export a Modelica model into FMU in Co-Simulation mode using OpenModelica tool. If you use Dymola - follow previous section and skip this section.

## Start OpenModelica Editor 

* Start OMEdit.

![OMStart](OM_Start.png)


## Open Model File

Open a Modelica model you would like to use in web simulator. 
* In this guide, we will open Physiolibrary[^1] via `File -> System Libraries -> Physiolibrary`

* and model of Hemodynamics by Fernandez de Cañete [^2] 

![OM_MeursModel](OM_CaneteModel.png)

## Setup FMU Export options
* Open `Tools -> Options -> FMI`
* check these options
  * Version: `2.0`
  * Type: `Co-Simulation`
  * Move FMU: `/vagrant_data` or any other existing directory
  * Model Description Filter: `internal`
  * Include Source Code: checked <input type="checkbox" checked disabled/>

![OM_FMUSettings](OM_FMUSettings.png)

## Do FMU Export
  * right click on the selected model and select `Export -> FMU`

![OM_FMUExport](OM_FMUExport.png)


## Use FMU file

Last step created a file with `.fmu` extension in directory set in step 2.2 
Check it in your file system. 

![bash_FMUFile](bash_FMUFile.png)

And use this file in following section.

