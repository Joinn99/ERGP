# ERGP
This is the official implementation of our paper:
> Tianjun Wei, Tommy W. S. Chow, and Jianghong Ma. Efficient and Scalable Recommendation via Item-Item Graph Partitioning.

## Requirements
The model implementation ensures compatibility with the Recommendation Toolbox [RecBole](https://recbole.io/) (Github: [Recbole](https://github.com/RUCAIBox/RecBole)), and uses [CuPy](https://cupy.dev/) to accrelate the model training on GPU. The requirements of the running environement:
- Python: 3.8+
- RecBole: 1.0.1
- CuPy: 0.10.5+

## Dataset
Here we only put *pinterest* dataset in the respository due to the storage limits. Other datasets are available at
[Google Drive](https://drive.google.com/file/d/1-2NZ27EYH1i9r7mWjy-J0D05qJLGeles/view?usp=sharing) or can be directly fetched by runing 
```bash
wget 'https://drive.google.com/uc?export=download&id=1-2NZ27EYH1i9r7mWjy-J0D05qJLGeles' -O Data.zip
unzip -o Data.zip && rm Data.zip
```

## Run
The script `run.py` is used to reproduced the results presented in paper. Train and avaluate ERGP on a specific dataset, run
```bash
python run.py --dataset DATASET_NAME
```
For public datasets *Amazon-cds*, *Douban*, and *Pinterest*, the experiments are repeated 7 times and the reported results are the average of all 7 experiments. To produce all results, change the `seed` parameter in `Params/Overall.yaml` to any element in [2020, 2022, 2024, 2026, 2028, 2030, 2032] to produce all results.

For convenience, we have saved the model training information and results on three benchmarking datasets of [BARS](https://openbenchmark.github.io/BARS/) in `BARS.ipynb`.
