
# Schrodinger_Docking_and_MD


### To use this workflow, download the repo then open it in Knime after Schrodinger has been installed.

#### Knime by default is come along with Schrodinger, but you could use a third installed Knime as well. Knime is an open source data science software that will impress you a lot, no matter what science area you belongs to, https://www.knime.com/ 

There are two input you need to provide, 1st is ```PDB ID``` defines your target, 2nd is ```ligand.smi``` which is a txt or csv file that contains your SMILES string defining the structure of the small molecule to be docked. See the last to know how to do this in detail.

![image](https://user-images.githubusercontent.com/75652473/209549358-4be51f79-2fb8-452a-bd66-e6ae35029e60.png)

Schrodinger's advantage over other free docking and MD packages is its wonderful graphical user interface (GUI). People without coding knowledge can do complex tasks, but every coin has two sides. 

A fancy GUI could easily distract you attention as well, makng it hard to logically think of your problems due to too much colorful process. What you really need is a plain process or a 
black box process, and to save your energy for the final docked pose analysis at last.

![image](https://user-images.githubusercontent.com/75652473/209549513-321f51c1-447a-40a8-a795-c535554ef4a0.png)


By using a GUI instead of command line,  to do every tiny task, the working efficiency drops significantly. In order to solve this problem, 

### An example workflow wrapped by Knime can be found in this repository. It does a docking (either SP mode or IFD mode ) then run a MD to optimise the docked pose to give you a more confident binding mode.

![image](https://user-images.githubusercontent.com/75652473/209549655-6b67fa79-a0a4-4e67-9394-8f6298bcf361.png)


```
workflow A: SP docking then do a MD. sp_md.knwf
workflow B: SP_IFT docking then a MD. sp_ifd_md.knwf
workflow C: SP docking then MD, then IFD, then MD, sp_md_ifd_md.knwf
```
![image](https://user-images.githubusercontent.com/75652473/209549813-18c1ddca-2436-4f32-9bf7-b9d858b2c8fd.png)



Workflow A is too simple, workflow C is too complex, 

workflow B provides both good time to accuracy value.


#### Benefit of this workflow

##### Save your time by automation

#### Increase repeatibility of simulation even years later

## How to modify Knime nodes input
#### Right click ```Get PDB``` node to configure, input the PDB ID with capital letters
![image](https://user-images.githubusercontent.com/75652473/209551022-8b68367a-bbb3-4c1d-b69a-a6ceee0853c5.png)

#### Right click ```Smiles Reader``` node to configure by providing the ligand.smi path which contains your SMILES string

![image](https://user-images.githubusercontent.com/75652473/209551248-d179831b-9dcc-4728-87dc-5419163644ec.png)

### How to excute the whole workflow

#### After you have defined you PDB ID and ligand.smi, you could go to the last node of the workflow, and right click then click ```excute```, all upstream nodes would start excuting one by one without any further modification.

# Reference 
https://hub.knime.com/search?q=schrodigner%20space&type=Workflow&sort=best.
