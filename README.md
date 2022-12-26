
# Schrodinger_Docking_and_MD

![image](https://user-images.githubusercontent.com/75652473/209548904-7484d1bc-5388-48b1-b9c1-af9ff5195b0b.png)


### To use this workflow, download the repo then open it in Knime after Schrodinger has been installed.

#### Knime by default is come along with Schrodinger, but you could use a third installed Knime as well.

There are two input you need to provide, 1st is ```PDB ID``` defines your target, 2nd is ```ligand.smi``` which is a txt or csv file that contains your SMILES string defining the structure of the small molecule to be docked.

![image](https://user-images.githubusercontent.com/75652473/209548765-5afd5e53-98f8-42b9-ada9-c9d0557e2645.png)


Schrodinger's advantage over other free docking and MD packages is its wonderful graphical user interface (GUI). People without coding knowledge can do complex tasks, but every coin has two sides. 

A fancy GUI could easily distract you attention as well, makng it hard to logically think of your problems due to too much colorful process. What you really need is a plain process or a 
black box process, and to save your energy for the final docked pose analysis at last.

By using a GUI instead of command line,  to do every tiny task, the working efficiency drops significantly. In order to solve this problem, 

### An example workflow wrapped by Knime can be found in this repository. It does a docking (either SP mode or IFD mode ) then run a MD to optimise the docked pose to give you a more confident binding mode.

![image](https://user-images.githubusercontent.com/75652473/209548684-0ba535fa-4935-4752-b934-0bd39d3343c4.png)


There are 4 blocks, 

```

                     top left : block 1
                    
                    middle left: block 2
                    
                    middle:      block 3
                    
                    right:       block 4
                    
                    
```
2 docking blocks (1, 3), 2 MD blocks (2,4). Selectively runing some of or all of these blocks give us 3 workflow

If a workflow runs block 1 and block 2, and the two block has a broken point in between that require special attention, then this workflow is named as ```12_sp_docking_md_broken_at_1_2.knwf```, likewise, the other two obey the same rules.

```
workflow A: SP docking then do a MD. 12_sp_md_broken_at_1_2.knwf
workflow B: SP_IFT docking then a MD. 1_34_sp_ifd_md_broken_at_3_4.knwf
workflow C: SP docking then MD, then IFD, then MD, 1234_sp_md_ifd_md_broken_at_1_2_and_3_4.knwf
```
![image](https://user-images.githubusercontent.com/75652473/209548803-db11106d-a704-4da3-99ab-9225017770f8.png)

Workflow A is too simple, workflow C is too complex, 

workflow B provides both good time to accuracy value.


#### Benefit of this workflow

##### Save your time by automation

#### Increase repeatibility of simulation even years later
