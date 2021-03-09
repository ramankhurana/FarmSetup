## How to extract the run:lumi:event for high energy events. 

Since we have the files located in private eos area and not accessible via crab it becomes a bit tedious to get this information. Following are the series of steps to get this information. 

Run the ETTAnalyzer on each of the file. Since we need the name of the .root file untill very end so this association has to be made at each step. Run the ETTAnalyzer, one file per condor job or run it interactively. 

To run interactively use: 

```python runall.py``` 

You can change the output file path in the config file and also the config file if needed. 

Once all the root files are present [note the name of rootfile is same as the input file] we can extract the run,lumi,event. In order to avoid writing a c++ macro and running it on all the files we do it in three steps:
 
1. extraction of raw information using tree->Scan 
2. convert it into the information which is understood to the edm tools. 
3. direct this into a shell script to be executed later. 

this can be done by 

source printEventList.sh

there will be three shell scripts produced as an output of this file, simply source them and you will get the .root files in the respective directories. 




