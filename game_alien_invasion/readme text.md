# Alien Invasion

## 1.pygame及命名说明

### 		1.pygame

1. pygame官方地址：https://www.pygame.org/news
2. pygame安装方法（终端运行）：

```终端
$ python -m pip install --user pygame
```

### 		2.命名说明

  1. 辅助方法的名称以单个下划线打头。
  2. 首字母大写的名称指的是类。

## 2.代码文件说明

### 		1.images

​	包含游戏所用的图片。

### 		2.alien_invasion.py

​	包含AlienInvasion类，负责管理游戏资源和行为的类。

​	创建一系列贯穿整个游戏都要用到的属性。

​	要玩游戏，只需运行该文件。

### 		3.bullet.py

​	包含Bullet类，负责管理飞船所发射的子弹。

### 		4.game_stats.py

​	包含GameStats类，负责跟踪游戏的统计信息。

### 		5.settings.py

​	包含Setting类，负责存储游戏中所有的设置。

### 6.ship.py

​	包含Ship类，负责管理飞船。

### 7.scoreboard.py

​	包含Scoreboard类，负责显示得分信息。

### 		8.button.py

​	包含Button类，负责游戏按钮属性。

### 9.alien.py

​	包含Alien类，负责表示单个外星人。

## 3.游戏功能

### 		1.设置

### 		2.开始界面

### 		3.单人游戏

### 		4.双人游戏

#### 				1.双人合作

#### 				2.双人竞争

### 	5.帮助

## 4.游戏打包exe文件

### 		1.安装pyinstaller（终端）

```终端
$ pip install pyinstaller
```

### 		2.进入程序所在目录（终端）

​		如果是在Anaconda环境下直接打包，可能会将其中大部分扩展都打包进去了，造成打包后的exe文件过大，为此有以下解决方案。		1.建立虚拟环境 ：pipenv install

​			当前文件夹出现Pipfile和Pipfile.lock

​		2.进入虚拟环境：pipenv shell
​		3.安装所需模块 pip install pygame
​		4.打包的模块也要安装 pip install pyinstaller

​		可能需要先安装pipenv

```终端
$ pip install --user --upgrade pipenv
```

​		将 pipenv 所在的路径添加到 Path 环境变量

### 		3.用pyinstaller来打包所有的py文件

​		文件之间用 -p 连接

​		常用参数

​		-F： 表示生成单个可执行文件

​		-D：表示打包多个文件，在dist中生成很多依赖文件，
​		-w：指定生成 GUI 软件，表示去掉控制台窗口
​		-i <icon file>: 指定打包后可执行文件的图标

​		例：

```终端
$ pyinstaller -F alien_invasion.py alien.py bullet.py button.py game_stats.py scoreboard.py settings.py ship.py
```

​		打包之后新增build和dist两个文件夹

### 		4.exe文件在dist文件中