
# Schrodinger_Docking_and_MD

To use this workflow, download the repo then open it in Knime after Schrodinger has been installed.

There are two input you need to provide, 1st is ```PDB ID``` defines your target, 2nd is ```ligand.smi``` which is a txt or csv file that contains your SMILES string defining the structure of the small molecule to be docked.

Molecular dynamic package integrated with Maestro, as well as Schroindger's Glide docking and Induced a docking, are leading softwares in the molecular simulation area. 
Schrodinger's advantage over other free docking and MD packages is its graphical user interface (GUI). People without coding knowledge can do complex tasks, but every coin has two sides.
By using a GUI to do everything, such as preparing protein structures instead of command line, you slow down the working efficiency. In order to solve this problem, 

An example workflow wrapped by Knime can be found in this repository. It does a docking (either SP mode or IFD mode ) then run a MD to optimise the docked pose to give you a more confident binding mode.

![image](https://user-images.githubusercontent.com/75652473/209523406-065d8cd5-02f8-4554-9083-2590dddb1633.png)

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
Workflow A is too simple, workflow C is too complex, workflow B provides both good time to accuracy value.
As the title of each workflow indicates, there are at least one broken point inside the workflow which is not perfect, you are supposed to mannually connect those broken point by defining the correct output path from prevously finished block. 
