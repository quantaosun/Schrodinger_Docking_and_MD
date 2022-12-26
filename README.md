# Schrodinger_Docking_and_MD

### To use this workflow, download this repo then open the workflow with Knime after Schrodinger has been intalled.

Schroindger's Glide docking and Induced fit docking are leading softwares in molecular docking area, so is the molecular dynamic package integrated with Maestro. 
Compared to other free docking and MD packages, the advantage of Schrodinger is its graphical user interface(GUI). It allows people without coding basis to do complex jobs, but every coin has a second side.
It slows down the working efficiency if you do everything in a GUI like prepare a protein structure.  To address this problem, 

### this repository shows a workflow wrapped by Knime. It does a docking (either SP mode or IFD mode ) then run a MD to optimise the docked pose to give you a more confident binding mode.

![image](https://user-images.githubusercontent.com/75652473/209523406-065d8cd5-02f8-4554-9083-2590dddb1633.png)

There are 4 blocks, 2 docking blocks (1, 3), 2 MD blocks (2,4). Selectively runing some of or all of these blocks give us 3 workflow


```
workflow A: SP docking then do a MD. 12_sp_md_broken_at_1_2.knwf
workflow B: SP_IFT docking then a MD. 1_34_sp_ifd_md_broken_at_3_4.knwf
workflow C: SP docking then MD, then IFD, then MD, 1234_sp_md_ifd_md_broken_at_1_2_and_3_4.knwf
```
Workflow A is too simple, workflow C is too complex, workflow B provides both good time to accuracy value.
