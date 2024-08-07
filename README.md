# dicom2niix-webui

The web UI for dcm2niix (DICOM to NIfTI converter)

## 描述(Description)

- 功能：利用 [dcm2niix](https://github.com/rordenlab/dcm2niix) 将 **dicom** 文件转为 **nii** 文件
- 可视化：使用 [Gradio](https://github.com/gradio-app/gradio) 将该功能可视化，分为本地端使用和通用端使用方式

## 安装(Install)
- 新建一个虚拟环境(Python 3.9.16)，或使用已有的Python环境
  - 例如 `$ conda create -n env_name python=3.9`
- 使用 PIP 方式安装
  - `$ pip install dcm2niix-webui`
- 使用源码方式安装
  - 下载本项目代码
    - 点击[本项目GitHub页面](https://github.com/AlionSSS/dcm2niix-webui)右上角的绿色的按钮`Code`，再点击`Download ZIP`
  - 解压项目，进入到项目根目录
    - 安装，执行 `$ pip install -e ./ -i "https://pypi.doubanio.com/simple/"`
- 注
  - dcm2niix 库的当前版本为 1.0.20220715
  - 卸载命令 `$ pip uninstall dcm2niix-webui`

## 启动服务(Start Service)
### 直接启动
- 由于安装时已经在当前 Python 环境中安装了 script
- 所以可以在任意位置直接执行 `$ dcm2niix-gui`，启动 WebUI

### 使用代码启动
- 进入到本项目的目录下，执行 `$ cd src/dcm2niix_webui`
- 二选一
  - 在本地电脑端启动，直接执行 `$ python main.py`
  - 在服务器端启动，执行 `$ nohup python main.py 1>server_run.log 2>&1 &`

## 操作说明(Operating Instructions)
### 本地端(For Local)
- 在本地电脑端启动时使用（打开浏览器，访问 http://localhost:7860 ）
- 说明：填入 dicom 文件目录路径、nii 文件保存路径，点击【开始转换】即可

![local_capture.jpg](https://raw.githubusercontent.com/AlionSSS/dcm2niix-webui/main/doc-resources/local_capture.jpg)


### 通用端(For Universal)
- 在本地电脑端、服务器端启动时皆可使用。
- 在服务端部署后，可供多人在线使用。（打开浏览器，访问 http://服务器IP:7860）
- 说明：上传 dicom 文件目录的压缩包（必填，例如 'dicom.zip'），点击【开始转换】即可

![universal_captrue.jpg](https://raw.githubusercontent.com/AlionSSS/dcm2niix-webui/main/doc-resources/universal_captrue.jpg)

## 手动构建(Build)
- 更新、安装工具
  - `$ pip install --upgrade setuptools`
  - `$ pip install --upgrade build`
- 进入到项目根目录下，执行 `$ python -m build`
- 构建完成会在项目 dist 目录下，生成 tar.gz 和 whl 文件
- 直接使用 PIP 即可安装，如 `pip install .\dist\dcm2niix_webui-0.1.0-py3-none-any.whl`
