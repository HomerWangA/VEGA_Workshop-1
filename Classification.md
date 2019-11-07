## Classification with squeezenet1.1

#### Model Downloader

```
cd /opt/intel/openvino/deployment_tools/tools/model_downloader
sudo python3 downloader.py -h
```
```
usage: downloader.py [-h] [-c CONFIG.YML] [--name PAT[,PAT...]]
                     [--list FILE.LST] [--all] [--print_all]
                     [--precisions PREC[,PREC...]] [-o DIR] [--cache_dir DIR]
                     [--num_attempts N] [--progress_format {text,json}]

optional arguments:
  -h, --help            show this help message and exit
  -c CONFIG.YML, --config CONFIG.YML
                        model configuration file (deprecated)
  --name PAT[,PAT...]   download only models whose names match at least one of
                        the specified patterns
  --list FILE.LST       download only models whose names match at least one of
                        the patterns in the specified file
  --all                 download all available models
  --print_all           print all available models
  --precisions PREC[,PREC...]
                        download only models with the specified precisions
                        (actual for DLDT networks)
  -o DIR, --output_dir DIR
                        path where to save models
  --cache_dir DIR       directory to use as a cache for downloaded files
  --num_attempts N      attempt each download up to N times
  --progress_format {text,json}
                        which format to use for progress reporting

```



#### Moder Optimizer 

#### Inference Engine Sample Compile

#### Result
