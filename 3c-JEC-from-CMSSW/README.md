# 3c. JEC from CMSSW

This demonstration requires CMSSW environment, so it won't be accessible from SWAN. There are two options to setup the notebook: either in browser or in Visual Studio Code.

## Setting up CMSSW

Regardless of where you want to use the notebook, you will need an active CMSSW environment. Here we'll be using CMSSW_14_0_8 for no specific reason, but you should check that you have the required Python version and packages in that CMSSW version.

Start by running the following commands in this directory (`3c-JEC-from-CMSSW`):

```
cmsrel CMSSW_14_0_8
cd CMSSW_14_0_8/src
cmsenv
cd -
```

and you are done setting up everything that's required for this demonstration!

In the future you can active the same environment just by running

```
cd CMSSW_14_0_8/src
cmsenv
cd -
```

## Running a notebook on Lxplus via browser

To run a notebook through an ssh connection you need to open a port for it. At this point you can disconnect from lxplus and reconnect to it with the following command:

`ssh -L 8080:localhost:8080 USERNAME@lxplus.cern.ch`

You have now opened a tunnel, which you can access in port 8080 on both your local machine and the lxplus node.

Next start the CMSSW environment as above. Then, let's start a notebook that runs in the correct environment and that you can access through the port:

`jupyter notebook --no-browser --port=8080`

If you now open your browser, you can access the notebook session at http://localhost:8080/. You will need a token, which you can find from the terminal where you started the jupyter notebook.

## Running a notebook on Lxplus via Visual Studio Code

If you would like to run the notebook through VSCode you can start by opening the notebook while connected to Lxplus. In the terminal where you have the CMSSW environment loaded start a notebook session as in the example above, but without the port:

`jupyter notebook --no-browser`

Going back to VSCode, in the upper right hand corner of the notebook you should see a "Select kernel" button. You need to install the Jupyter notebook plugin that might be recommended if you already don't have it. After installing the plugin you can give the localhost address that reads in the terminal as a kernel, and you should be able to run the notebook cells without issues.
