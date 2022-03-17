Hi friends, I wanted to tell of PyRoot from ROOT CERN Framework.

What did I do to install it?

I have seen that people with an "Apple M1" have problems installing ROOT or rather PyRoot libraries on this machine.

I work with Particle Detectors and I work with ROOT.
I am an entrepreneur's Technology and futuristic visionary, I m a maker technology.

In this Readme, I talk about how I solved installation of PyRoot libraries.



if you have a version of Conda not for Apple Silicon, please delete all.
(many python version there are)
delete all homebrew installation for delete all file not compatible with new conda for arm64.
use:

where homebrew

and delete

I downloaded the version of CONDA for Apple Silicon M1 directly from here:
https://docs.conda.io/en/latest/miniconda.html 
the file is:
https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-arm64.sh
( for newbie install with sh ./filename.sh)

After that I followed as reported:
in this link

https://root.cern/install/#conda


$ conda config --set channel_priority strict 
$ conda create -c conda-forge --name <my-environment> root 
$ conda activate <my-environment>
  
for example:
  
conda config --set channel_priority strict 
conda create -c conda-forge --name env1 root 
conda activate env1
With enviroment conda actived

in python3 prompt

’’’
import ROOT
’’’
now work fine, without error.
Python 3.10 is installed with conda.

I posted this solution on the CERN ROOT forum, where I was looking for help to install it and finally shared the solution I found myself
https://root-forum.cern.ch/t/how-to-install-root-with-pyroot-in-apple-m1/48459/9

Thanks for support
