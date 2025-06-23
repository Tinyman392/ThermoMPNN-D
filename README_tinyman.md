The following changes have been made to make this run:
- examples/configs/local.yaml
	Changed thermompnn_dir to the github repository root (IE /PATH/TO/THERMOMPNN-D/)
- Numpy has been downgraded to 1.26.4 to fix a Torch error where it said Numpy was not available.  

The following has been changed to get CPU support
- v2_ssm.py
	Change all mentions of device = 'cuda' to device = 'cpu'
	Remove the model.cuda() calls

