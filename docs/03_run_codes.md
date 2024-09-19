# Reproducibility


<br>

## 1. Usage


<br>

### 1.1 In terminal

```
# Run the main file (at the root of the project)
python main_TSP_edge_classification.py --dataset TSP --config 'configs/TSP_edge_classification_GatedGCN_100k.json  # for CPU
python main_TSP_edge_classification.py --dataset TSP --gpu_id 0 --config 'configs/TSP_edge_classification_GatedGCN_100k.json'  # for GPU
```

The training and network parameters for each dataset and network is stored in a json file in the [`configs/`](../configs) directory.












<br>

### 1.2 In jupyter notebook
```
# Run the notebook file (at the root of the project)
conda activate benchmark_gnn 
jupyter notebook
```
Use [`main_TSP_edge_classification.ipynb`](../main_TSP_edge_classification.ipynb) notebook to explore the code and do the training interactively.




<br>

## 2. Output, checkpoints and visualizations

Output results are located in the folder defined by the variable out_dir in the corresponding config file (e.g., configs/TSP_edge_classification_GatedGCN_100k.json file).  

If `out_dir = 'out/TSP_edge_classification/'`, then 

#### 2.1 To see checkpoints and results
1. Go to`out/TSP_edge_classification/results` to view all result text files.
2. Directory `out/TSP_edge_classification/checkpoints` contains model checkpoints.

#### 2.2 To see the training logs in Tensorboard on local machine
1. Go to the logs directory, i.e. `out/TSP_edge_classification/logs/`.
2. Run the commands
```
source activate benchmark_gnn
tensorboard --logdir='./' --port 6006
```
3. Open `http://localhost:6006` in your browser. Note that the port information (here 6006 but it may change) appears on the terminal immediately after starting tensorboard.


#### 2.3 To see the training logs in Tensorboard on remote machine
1. Move this [script](../scripts/TensorBoard/script_tensorboard.sh) to the root of the repository, i.e. benchmarking-gnns/.
2. Run the script `bash script_tensorboard.sh`.
3. On your local machine, run the command `ssh -N -f -L localhost:6006:localhost:6006 user@xx.xx.xx.xx`.
4. Open `http://localhost:6006` in your browser. Note that `user@xx.xx.xx.xx` corresponds to your user login and the IP of the remote machine.



<br>

## 3. Reproduce results (4 runs on all, except CSL and TUs)


```
# At the root of the project 
bash scripts/TSP/script_main_TSP_edge_classification_100k.sh # run TSP dataset for 100k params
bash scripts/TSP/script_main_TSP_edge_classification_edge_feature_analysis.sh # run TSP dataset for edge feature analysis
```
For GPU, add the --gpu_id argument to the scripts or modify them to include the GPU flag.
Scripts are [located](../scripts/) at the `scripts/` directory of the repository.

 

 <br>

## 4. Generate statistics obtained over mulitple runs (except CSL and TUs)
After running a script, statistics (mean and standard variation) can be generated from a notebook. For example, after running the script `scripts/TSP/script_main_TSP_edge_classification_100k.sh`, go to the results folder `out/TSP_edge_classification/results/`, and run the [notebook](../scripts/StatisticalResults/generate_statistics_TSP_edge_classification.ipynb) `scripts/StatisticalResults/generate_statistics_TSP_edge_classification.ipynb` to generate the statistics.


















<br><br><br>