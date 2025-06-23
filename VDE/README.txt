
This code and examples follow the VDE model as described in DOI:____. This estimates heat capacity (Cp) as a function of temperature with a given density of states input and material information. 

Code for the VDE model is provided in the VDE_Model_Code folder. Run in Python environment with numpy, matplotlib, scipy, pymatgen, pandas, collections.  

This code relies on a CSV file with material information titled HeatCapacity_DataEntry_ForVDE.csv (see example file in the VDE_Model_Code folder). This information is gathered from the Materials Project database, but in using this model, one's own inputs could be used. 

This code accepts a DOS input CSV file in meV, where the energy is labeled "meV" and the DOS is labeled "DOS" in the first line. This file must be titled "Material ID".csv (as to match what is in the "Material ID" column of the HeatCapacity_DataEntry_ForVDE.csv file (see examples in the VDE_Model_Code folder).

To run the code, you will need to decide whether you would like to include the electronic term. 
-If including with the API, put your API key in line 140 and uncomment line 199 (comment out 197 and 198). 
-If providing your own, input your own values into the HeatCapacity_DataEntry_ForVDE.csv file, and set the code to read out of the file by uncommenting line 197 (comment out 198 and 199). 
-Alternatively, you can set the electronic term to zero by setting the DOS equal to zero (uncomment line 198 and comment out 197 and 199). 

The desired temperature range can be specified in the "Temps" variable when calling the Cp function in line 212 in the main code.

Examples of materials with inputs from ALIGNN, MACE, and DFT DOS estimates are also provided. There are slight modifications to the VDE model code in each of these examples to account for the following:

-ALIGNN DOS estimates were already converted to J before putting them into the model code, so the code in that folder reads inputs in J. The code also reads in a slightly different naming structure of the csv file inputs.

-MACE inputs were in the form of .yaml files and were in THz.

-DFT inputs were in the form of .dat files and were also in THz. 