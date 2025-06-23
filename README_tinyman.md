The following changes have been made to make this run:
- Numpy has been downgraded to 1.26.4 to fix a Torch error where it said Numpy was not available.  
- cudatoolkit upgraded to 11.7 to mach pytorch-cuda=11.7
- ssm_utils.py
	- Added config.platform.thermompnn_dir = current_location = os.path.dirname(os.path.dirname(os.path.realpath(\_\_file\_\_))) after config = OmegaConf.merge(OmegaConf.load(local), OmegaConf.load(aux))

The following has been changed to get CPU support
- copy v2_ssm.py to v2_ssm_cpu.py
- v2_ssm_cpu.py
	- Change all mentions of device = 'cuda' to device = 'cpu'
	- Remove the model.cuda() calls
	- Added parser.add_argument("--threads", type=int, default=1, help="Set number of threads to run") to if \_\_name\_\_ == "\_\_main\_\_"
	- Added torch.set_num_threads(args.threads) into first line in main(args)
