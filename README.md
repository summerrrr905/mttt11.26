# mttt11.26
test
使用前请先download全部文件，并用cat指令整合全部文件：
1.cat mttt_part_aa mttt_part_ab mttt_part_ac ... > mttt.tar.gz

2.并解压tar -xvzf mttt.tar.gz
注：文件中包含tiny imagenet数据集
使用时，请先配置环境：CUDA 11.8 CUDNN 8.6 python3.8
其他包已经打包到environment.yml中 可一键下载，
使用前先安装conda，conda env create -f environment.yml
然后，conda activate 《环境名称》

需要手动下载的有：tensorflow==2.10.0（或更高版本）
torch==2.3.1+cu118   
torchaudio==2.3.1+cu118
torchvision==0.18.1+cu118
jax==0.4.13
jaxlib==0.4.13+cuda11.cudnn86
部分环境包可能存在冲突项，保留核心环境不变即可
![165a0e014721433eed3382e31571617](https://github.com/user-attachments/assets/274b8cc2-f381-4a25-826f-7c383c6ba68d)
![8a08b89cc4762878dcbe2deb1437b6d](https://github.com/user-attachments/assets/0a51bbe0-5084-4f8e-bba3-2356e863eaa6)

3.安装完成后，请测试torch tensorflow jax的使用情况：python -c "import torch; print('PyTorch version:', torch.__version__); print('CUDA available:', torch.cuda.is_available()); print('CUDA version:', torch.version.cuda); print('Number of GPUs:', torch.cuda.device_count())"
python -c "import jax; print('JAX version:', jax.__version__); print('GPU devices:', jax.devices())"
除此之外可能还有其余环境需要手动下载。

4.运行前，请切换到./.../mttt（包含train2.py）的目录中，以脚本指令运行，例：python train2.py --config=/root/PycharmProjects/TTT/mttt/config_patch2.py --workdir=/root/PycharmProjects/TTT/resultparaments
在其余机器运行时，记得更改config和workdir前面的目录路径。以及config_patch2 和train2中的数据集路径。
