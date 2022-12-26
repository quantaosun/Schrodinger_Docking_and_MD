
# Schrodinger_Docking_and_MD


### To use this workflow, download the repo then open it in Knime after Schrodinger has been installed.

#### Knime by default is come along with Schrodinger, but you could use a third installed Knime as well.

There are two input you need to provide, 1st is ```PDB ID``` defines your target, 2nd is ```ligand.smi``` which is a txt or csv file that contains your SMILES string defining the structure of the small molecule to be docked.

![image](https://user-images.githubusercontent.com/75652473/209549358-4be51f79-2fb8-452a-bd66-e6ae35029e60.png)

Schrodinger's advantage over other free docking and MD packages is its wonderful graphical user interface (GUI). People without coding knowledge can do complex tasks, but every coin has two sides. 

A fancy GUI could easily distract you attention as well, makng it hard to logically think of your problems due to too much colorful process. What you really need is a plain process or a 
black box process, and to save your energy for the final docked pose analysis at last.

![image](https://user-images.githubusercontent.com/75652473/209549513-321f51c1-447a-40a8-a795-c535554ef4a0.png)


By using a GUI instead of command line,  to do every tiny task, the working efficiency drops significantly. In order to solve this problem, 

### An example workflow wrapped by Knime can be found in this repository. It does a docking (either SP mode or IFD mode ) then run a MD to optimise the docked pose to give you a more confident binding mode.


There are 4 blocks, 

```

                     top left : block 1
                    
                    middle left: block 2
                    
                    middle:      block 3
                    
                    right:       block 4
                    
                    
```
2 docking blocks (1, 3), 2 MD blocks (2,4). Selectively runing some of or all of these blocks give us 3 workflow

![image](https://user-images.githubusercontent.com/75652473/209549655-6b67fa79-a0a4-4e67-9394-8f6298bcf361.png)


If a workflow runs block 1 and block 2, and the two block has a broken point (connectioin has been made succesfully in an update) in between that require special attention, then this workflow is named as ```12_sp_docking_md_broken_at_1_2.knwf```, likewise, the other two obey the same rules.

```
workflow A: SP docking then do a MD. 12_sp_md_broken_at_1_2.knwf
workflow B: SP_IFT docking then a MD. 1_34_sp_ifd_md_broken_at_3_4.knwf
workflow C: SP docking then MD, then IFD, then MD, 1234_sp_md_ifd_md_broken_at_1_2_and_3_4.knwf
```
![image](https://user-images.githubusercontent.com/75652473/209549813-18c1ddca-2436-4f32-9bf7-b9d858b2c8fd.png)



Workflow A is too simple, workflow C is too complex, 

workflow B provides both good time to accuracy value.


#### Benefit of this workflow

##### Save your time by automation

#### Increase repeatibility of simulation even years later
