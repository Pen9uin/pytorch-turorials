###程序结构

- 模型定义
- 数据加载
- 训练和测试
- 可视化

其中：

- `checkpoints/`：用于保存训练好的模型，可使程序在异常退出后仍能重新载入模型，恢复训练
- `data/`：存储训练数据，这里有爬好的头像数据（275M，约5万多张图片）：<https://pan.baidu.com/s/1eSifHcA> 提取码：g5qa。 请把所有的图片保存于data/face/目录下
- `imgs/`：用于保存生成图片
- `main.py`：主文件，训练和测试程序的入口，可通过不同的命令来指定不同的操作和参数
- `model.py`：模型定义
- `visualize.py`：可能用到的工具函数，在本次实验中主要是封装了可视化工具

### 用法

- visdom 可视化

  ```
  python -m visdom.server
  ```

- 基本用法

  ```
  Usage： python main.py FUNCTION --key=value,--key2=value2 ..
  ```

- 训练，默认用 gpu+vis

  ```
  python main.py train  
  ```

- 生成图片

  ```
  python main.py generate --nogpu --vis=False \
              --netd-path=checkpoints/netd_200.pth \
              --netg-path=checkpoints/netg_200.pth \
              --gen-img=result.png \
              --gen-num=64
  ```

### 版本

- pytorch 0.4
- python 3.6
