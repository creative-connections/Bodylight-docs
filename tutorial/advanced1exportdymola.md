
# Export Model to FMU in Dymola

In this step we will export a Modelica model into FMU version 2.0 in Co-Simulation mode using Dymola tool. If you use Open Modelica tool, skip to next section.
 
# Start Dymola tool

* Start Dymola (tested in version 2019).

# Check License

You may need at least "Binary Mode Export" or "Source Code Generation" license in order to export FMU with source codes.

* Check appropriate license in `Help -> License -> Detail` as seen in this screenshot:

![Dymola Licence](Dymola_License.png)


# Open Model File

Open a Modelica model you would like to use in web simulator. 
* In this guide, we will open Physiolibrary[^1]

![Dymola Physiolibrary](Dymola_Physiolibrary.png)


* and model of Hemodynamics by Fernandez de Cañete [^2] 

![Dymola_Fernandez](Dymola_CaneteModel.png)

# Setup FMU Export options
* Open `Simulation (tab) -> Simulation -> Setup`
* in `FMI-Export` tab check 
  * Type: `Co-Simulation with CVODE`
  * Version: `2.0`
  * Options: `Include source code`

![Dymola FMU Settings](Dymola_FMUSettings.png)

# Do FMU Export
  * `Simulation -> Translate -> FMU`

![Dymola FMU Export](Dymola_FMUExport.png)

# Use FMU file

Last step created a file with `.fmu` extension in current working directory.
Check it in your file system. 

![cmd FMUFile](cmd_FMUFile.png)


Use this file in following section
