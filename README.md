
# Schrodinger_Docking_and_MD

## This repository does a docking (either SP mode or IFD mode ) then run a MD to optimise the docked pose to give you a more confident binding mode.

Schrodinger's advantage over other free docking and MD packages is its wonderful graphical user interface (GUI). People without coding knowledge can do complex tasks, but every coin has two sides. A fancy GUI could easily distract you attention and slows down the work efficiency as well. A good way to automatition for Schrodinger simulation and hide unnecessary process as backend is to use Knime(https://www.knime.com/ ). It saves great amount of time and make the simulation process highly repeatable.

## To use this workflow, download the repo then open it in Knime  after Schrodinger has been installed.

There are two input you need to provide, 1st is ```PDB ID``` defines your target, 2nd is ```ligand.smi``` which is a txt or csv file that contains your SMILES string defining the structure of the small molecule to be docked.

![image](https://user-images.githubusercontent.com/75652473/209549358-4be51f79-2fb8-452a-bd66-e6ae35029e60.png)


## How to modify Knime nodes input
#### Right click ```Get PDB``` node to configure, input the PDB ID with capital letters
![image](https://user-images.githubusercontent.com/75652473/209551022-8b68367a-bbb3-4c1d-b69a-a6ceee0853c5.png)

#### Right click ```Smiles Reader``` node to configure by providing the ligand.smi path which contains your SMILES string

![image](https://user-images.githubusercontent.com/75652473/209551248-d179831b-9dcc-4728-87dc-5419163644ec.png)

# Reference 
https://hub.knime.com/search?q=schrodigner%20space&type=Workflow&sort=best.
