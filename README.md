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
    
    
Example:

    /eos/cms/store/user/amassiro/PrivateMC/RunIISummer20UL18NanoAODv9/VH_H_VToLL_VL_mg_pythia8/RunIISummer20UL18NanoAODv9_106X_upgrade2018_realistic_v11_L1v1-MINIAODSIM/251023_085208/0000/nanoStep_231.root
    
    many files:
    /eos/cms/store/user/amassiro/PrivateMC/RunIISummer20UL18NanoAODv9/VH_H_VToLL_VL_mg_pythia8_v2/RunIISummer20UL18NanoAODv9_106X_upgrade2018_realistic_v11_L1v1-MINIAODSIM/251027_134624/0000/



    
build pileup list

    cmssw-el7
    cd /afs/cern.ch/user/a/amassiro/Framework/Generation/CMSSW_10_6_30/src/CMSSWGeneration/crab_miniaod_production/Era2018UL/VH_H_VToLL_VL_MG5_Polar/
    cmsenv
    
    python3 generateDatasetFileList.py   --dataset  /Neutrino_E-10_gun/RunIISummer20ULPrePremix-UL18_106X_upgrade2018_realistic_v11_L1v1-v2/PREMIX   -o mypileup.py
    
    /Neutrino_E-10_gun/RunIISummer20ULPrePremix-UL18_106X_upgrade2018_realistic_v11_L1v1-v2/PREMIX
    

    
Number of files in the dataset =  49577
Number of bad queries =  1
Number of files on Disk =  15111
Number of files on Disk but in blacklist =  0
Number of Valid files =  15111




Post-processing
====


Step by Step installation


    cd /afs/cern.ch/user/a/amassiro/work/Latinos/Framework/PolarVH/

    git clone git@github.com:latinos/mkShapesRDF.git
    cd mkShapesRDF/
    source install.sh


Install PlotsConfigurationRun3

    cd /afs/cern.ch/user/a/amassiro/work/Latinos/Framework/PolarVH/
    git clone git@github.com:latinos/PlotsConfigurationsRun3.git


Step by Step use


    cd /afs/cern.ch/user/a/amassiro/work/Latinos/Framework/PolarVH/mkShapesRDF/
    source start.sh

    < the development branch>
    cd /afs/cern.ch/user/a/amassiro/work/Latinos/Framework/mkShapesRDF/
    source start.sh


Post-processing private sample

    /VH_H_VToLL_VL_mg_pythia8_v2/amassiro-RunIISummer20UL18NanoAODv9_106X_upgrade2018_realistic_v11_L1v1-MINIAODSIM-00000000000000000000000000000000/USER

    some files here: /eos/user/a/amassiro/HIG/ZHpolar
    and here:
    /eos/cms//store/user/amassiro/PrivateMC/RunIISummer20UL18NanoAODv9/VH_H_VToLL_VL_mg_pythia8_v2/RunIISummer20UL18NanoAODv9_106X_upgrade2018_realistic_v11_L1v1-MINIAODSIM/251027_134624/0000/


    cd /afs/cern.ch/user/a/amassiro/work/Latinos/Framework/PolarVH/mkShapesRDF/
    source start.sh


    store: /eos/user/a/amassiro/HIG/ZHpolarPostProc/


    alias vomsgrid='voms-proxy-init --rfc --voms cms -valid 193:00'

    vomsgrid

    Modify the files:
        samplesCrossSections_UL.py
        Summer20UL18_106x_nAODv9.py

    fish://amassiro@lxplus.cern.ch/afs/cern.ch/user/a/amassiro/work/Latinos/Framework/PolarVH/mkShapesRDF/mkShapesRDF/processor/framework/samples/Summer20UL18_106x_nAODv9.py


    Need more steps ...
    MCl1loose2018v9__MCCorr2018v9NoJERInHorn__l2tightOR2018v9
    At least: MCCorr2018v9, now added in the step "MCFull2018v9"

    mkPostProc -o 0 -p Summer20UL18_106x_nAODv9_Full2018v9 -s MCFull2018v9 -T ZH_H_ZToLL_ZL   -dR 1

    mkPostProc -o 0 -p Summer20UL18_106x_nAODv9_Full2018v9 -s MCFull2018v9 -T ZH_H_ZToLL_ZL

    jobs in: /afs/cern.ch/work/a/amassiro/Latinos/Framework/PolarVH/mkShapesRDF/mkShapesRDF/processor/condor

    interactive mode:
    python /afs/cern.ch/work/a/amassiro/Latinos/Framework/PolarVH/mkShapesRDF/mkShapesRDF/processor/condor/Summer20UL18_106x_nAODv9_Full2018v9/MCFull2018v9/ZH_H_ZToLL_ZL__part39/script.py


    output is here: /eos/cms/store/group/phys_higgs/cmshww/amassiro/HWWNano//Summer20UL18_106x_nAODv9_Full2018v9/MCFull2018v9
    then moved here:
    /eos/user/a/amassiro/HIG/ZHpolarPostProc/
    /eos/user/a/amassiro/HIG/ZHpolarPostProc/Summer20UL18_106x_nAODv9_Full2018v9/MCFull2018v9/


    https://twiki.cern.ch/twiki/bin/view/LHCPhysics/CERNYellowReportPageAt13TeV


    if problems with password (git clone via https):
    git remote set-url origin git@github.com:latinos/mkShapesRDF



mkShapes


Install PlotsConfigurationRun3

    cd /afs/cern.ch/user/a/amassiro/work/Latinos/Framework/PolarVH/
    git clone git@github.com:latinos/PlotsConfigurationsRun3.git


Step by Step use

    cd /afs/cern.ch/user/a/amassiro/work/Latinos/Framework/PolarVH/mkShapesRDF/
    source start.sh

    cd ../PlotsConfigurationsRun3/PolarVH/





