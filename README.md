# PolarVH


Gridpack creation

Instructions here: https://cms-generators.docs.cern.ch/how-to-produce-gridpacks/mg5-amcnlo/

Example of cards are here: https://gitlab.cern.ch/cms-gen/genproductions_cards
    

    cd /afs/cern.ch/user/a/amassiro/Framework/Generation
    cmssw-el7
    
    git clone https://gitlab.cern.ch/cms-gen/genproductions_scripts.git
    cd genproductions_scripts
    git checkout mg265
    cd bin/MadGraph5_aMCatNLO/

    
    cd /afs/cern.ch/user/a/amassiro/Framework/Generation/genproductions_scripts/bin/MadGraph5_aMCatNLO/
    cmssw-el7
    
    
    ./gridpack_generation.sh <name of process card without _proc_card.dat> <folder containing cards relative to current location>

    ./gridpack_generation.sh   VHpolar  cards/VHpolar

    
Problem:
    VERSION 2.6.5
    "generate p p > v{0} h, v > lep antilep" with error:
    InvalidCmd : No particle v{0} in model
    
    
For Run3


    cd /afs/cern.ch/user/a/amassiro/Framework/Generation/Run3/
    cmssw-el8
    
    git clone https://gitlab.cern.ch/cms-gen/genproductions_scripts.git
    cd genproductions_scripts
    cd bin/MadGraph5_aMCatNLO/

    
    cd /afs/cern.ch/user/a/amassiro/Framework/Generation/Run3/genproductions_scripts/bin/MadGraph5_aMCatNLO/
    cmssw-el8
    
    
    ./gridpack_generation.sh <name of process card without _proc_card.dat> <folder containing cards relative to current location>

    ./gridpack_generation.sh   VHpolar  cards/VHpolar

    
    
    VERSION 2.9.18
    
    
Test:


    cd /afs/cern.ch/user/a/amassiro/Framework/Generation/Run2-el7/
    cmssw-el7
    
    git clone https://gitlab.cern.ch/cms-gen/genproductions_scripts.git
    cd genproductions_scripts/bin/MadGraph5_aMCatNLO/

    
    cd /afs/cern.ch/user/a/amassiro/Framework/Generation/Run2-el7/genproductions_scripts/bin/MadGraph5_aMCatNLO/
    cmssw-el7
    
    
    ./gridpack_generation.sh <name of process card without _proc_card.dat> <folder containing cards relative to current location>

    ./gridpack_generation.sh   VHpolar  cards/VHpolar

    
    VERSION 2.9.18
    
    
    
    

Generation

Example from: https://github.com/UniMiBAnalyses/CMSSWGeneration/tree/HHbbtautau/crab_miniaod_production/Era2018UL/ZH_HToGluGlu_ZToLL_powheg_pythia8

    cd /afs/cern.ch/user/a/amassiro/Framework/Generation
    
    cmssw-el7
    
    cmsrel CMSSW_10_6_30;
    cd CMSSW_10_6_30/src;
    cmsenv;
    git-cms-init;
    git clone git@github.com:UniMiBAnalyses/CMSSWGeneration.git;

    scramv1 b -j 20
    
    
    cd CMSSWGeneration/crab_miniaod_production/Era2018UL/ZH_HToWW_ZToLL_MG5_Polar/
    
    cd CMSSWGeneration/crab_miniaod_production/Era2018UL/VH_H_VToLL_VL_MG5_Polar/
    cd CMSSWGeneration/crab_miniaod_production/Era2018UL/VH_H_VToLL_VT_MG5_Polar/
    cd CMSSWGeneration/crab_miniaod_production/Era2018UL/VH_H_VToLL_VLT_MG5_Polar/
    
    
    
    
    
    
Running:

    cmssw-el7
    cd /afs/cern.ch/user/a/amassiro/Framework/Generation/CMSSW_10_6_30/src/CMSSWGeneration/crab_miniaod_production/Era2018UL/ZH_HToWW_ZToLL_MG5_Polar/

    
    cmssw-el8  --> not working :(
    
    cmssw-el7
    cd /afs/cern.ch/user/a/amassiro/Framework/Generation/CMSSW_10_6_30/src/CMSSWGeneration/crab_miniaod_production/Era2018UL/VH_H_VToLL_VL_MG5_Polar/
    cmsenv
    cmsRun gen_step.py      inputGridpack=VHpolar_el8_amd64_gcc10_CMSSW_12_4_8_tarball.tar.xz      nEvents=10

    cmsRun gen_step.py      inputGridpack=VHpolar_slc7_amd64_gcc10_CMSSW_12_4_8_tarball.tar.xz      nEvents=10
    --> it works
    
    
    
    

    
    
    