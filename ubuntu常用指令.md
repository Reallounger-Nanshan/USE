# ubuntu常用指令

## (一) 权限切换

### 1. 普通用户转超级用户

* ```
  sudo -s
  ```

### 2. 超级用户转普通用户

* ```
  su - <usrname>
  ```



## (二) 基础操作

### 1. 创建快捷方式

* ```
  ls -s [目标文件] [目标位置]
  ```

### 2. 光标

* ```
  echo -e "\033[?25l"   #隐藏光标
  ```

* ```
  echo -e "\033[?25h"   #显示光标
  ```

### 3. 查看核心数

* ```
  nproc
  ```

### 4. 查看结点使用情况

* ```
  df -ia
  ```

### 5. 查看目标路径

* ```
  whereis [target]
  ```



## (三) 录屏

### 1. 开始和停止

* ~~~
  Ctrl + Alt + Shift + R
  ~~~



## (四) pip

### 1. 更新

* ~~~
  python3 -m pip install --upgrade pip
  ~~~

### 2. 镜像源

* ~~~
  https://pypi.tuna.tsinghua.edu.cn/simple
  ~~~

* ~~~
  http://pypi.douban.com/simple/ 
  ~~~

* ~~~
  http://mirrors.cloud.tencent.com/pypi/simple 
  ~~~

* ```
  https://mirrors.aliyun.com/pypi/simple/
  ```



## (五) Anaconda

### 1. 查看当前系统环境

* ~~~
  conda env list
  ~~~

### 2. 创建环境

* ~~~
  # 指定python版本为3.x，注意至少需要指定python版本或者要安装的包
  conda create -n env_name python=3.x
  
  # 同时安装必要的包
  conda create -n env_name numpy matplotlib python=3.x
  ~~~


### 3. 激活环境

* ~~~
  conda activate env_name
  ~~~

### 4. 退出环境

* ~~~
  conda deactivate
  ~~~

### 5. 删除不需要的环境

* ~~~
  conda remove -n env_name --all
  ~~~

### 6. 安装包

* ~~~
  # 切换到指定环境下安装
  conda activate env_name
  
  # 安装包
  conda install pkg_name
  # 安装anaconda发行版中所有的包
  conda install anaconda
  ~~~

* ~~~
  # 指定环境安装
  conda install -n env_name pkg_name
  ~~~

### 7. 复制环境

* ~~~
  conda create --name <new_env_name> --clone <copied_env_name>
  ~~~

