# DeepLeptonGrid

Create repo with submodules

```bash
mkdir DeepLeptonGrid
cd DeepLeptonGrid
git remote add origin git@github.com:dietrichliko/DeepLeptonGrid.git

cmsrel CMSSW_10_2_18
cd CMSSW_10_2_18/src

git submodule add -b grid git://github.com/HephyAnalysisSW/DeepLepton
git submodule add -b grid git://github.com/HephyAnalysisSW/RootTools
git submodule add git://github.com/HephyAnalysisSW/Analysis
git submodule add git://github.com/HephyAnalysisSW/Samples
```

Add ```.gitignore```

```bash
.env
CMSSW_10_2_18/*
!CMSSW_10_2_18/src/
```

Create ```.env```

In a clean environment ...
```bash
scram runtime -sh | sed 's/^export \(.*\)\;$/\1/' > ../../.env
```
Workspace settings in Vscode

```json
"python.pythonPath": "/cvmfs/cms.cern.ch/slc7_amd64_gcc700/cms/cmssw/CMSSW_10_2_18/external/slc7_amd64_gcc700/bin/python"
```