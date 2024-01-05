# MystMS_SP2_20230507
Side reaction analysis and Nanospray results interpretation.

## The background of this project is related to [MystNMR](https://github.com/xueannafang/MystNMR)

This is a Jupyter-based tool for side product prediction for multi-step synthesis. The target reaction follows a SN2 mechanism, whereas ester hydrolysis, transesterification, E2, ester exchange, formation of ionic liquid would also be possible under certain conditions. The effect of solvents, in particular, potential competative behaviour compared to dominant reactants, have been addressed.

# Latest version (20230629):

- [MystMS_organised_20230507.ipynb](https://github.com/xueannafang/MystMS_SP2_20230506/blob/main/MystMS_organised_20230507.ipynb)

This is the main working notebook.

- Database of suspicious solvents: [susp_solv.json](https://github.com/xueannafang/MystMS_SP2_20230506/blob/main/susp_solv.json)

This summarises potential competative reactions led by "suspicious" functional groups contained by individual solvents.

- Example output: [rxn_anls_log_05072023175150.txt](https://github.com/xueannafang/MystMS_SP2_20230506/blob/main/rxn_anls_log_05072023175150.txt)

Results contain different possibilities of the mass of products and how the component was formed.

For example,

```
ms : 338.44700000000006
msg : 1 * OH group(s) on trioxyl methyl-benzoate substituted by dodecyl group(s). 1 * ester group(s) on methyl-benzoate hydrolysised into carboxylic acid. 
name : smOH->OC12H25_1|COOMe->COOH_1
```

this is a compound with ```ms``` equals 338. The compound is formed by 1 step substitution, with 1 ester hydrolysised into acid, as summarised in ```msg```. The ```name``` shows a brief structure evloution process, where ```smOH``` is the starting material with hydroxyl groups, ```->OC12H25``` is the substituent, with ```_1``` standing for only one reaction site was substituted. The rest says the ```COOMe``` group degraded to ```COOH```. This step also only happened once (```_1```).

In another group, the mass corresponds to ionic liquid formed by competitive solvent methylimidazole:

```
ms : 331.34000000000003
msg : Ionic liuqid is formed between N-methylimidazole and 1-bromododecane.
name : NMI_BrAlkane_salt
```

The ```msg``` will describe things going on for this compound.

ANother case shows an aliphatic alochol participated in the transesterification:

```
ms : 366.50200000000007
msg : The methyl ester fraction on the smOH->OC12H25_1 is replaced by ethanol .
name : EtOH_smOH->OC12H25_1_new_ester
```

The compound here corresponds to a mono-substituted product (only one -OH reacted), whose other side (the methyl-ester) has now been replaced by ethyl-ester.

-----------------------------
Note that the log file only suggests all the possibilities of product combinations. No quantum calculation was carried out to simulate the real reaction situation.

-----------------------------
### Associated with other methods or chemical problems:

- [MystMS_NMR_qsp.ipynb](https://github.com/xueannafang/MystMS_SP2_20230506/blob/main/MystMS_NMR_qsp.ipynb)

The prototype of MystNMR. See top as the full introduction of MystNMR project.

- Dimer test output: [dimer_test_output_20230508.txt](https://github.com/xueannafang/MystMS_SP2_20230506/blob/main/dimer_test_output_20230508.txt)

This version addresses potential polymerisation among the reactant itself.


