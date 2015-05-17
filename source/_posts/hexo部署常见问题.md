title: "hexo部署常见问题（Mac）"
date: 2015-05-14 22:45:27
categories: 技术
tags: 
- hexo
- 常见问题
---

其实在很早之前我就有接触自定义博客（Hexo，octopress），看过一些关于自定义博客的文章，那时认为这其实没什么技术含量，所谓的逼格高只是相对于业外人士，业外人士也不会很感兴趣。
直到今天才自己尝试了一下自定义博客——Hexo（直到膝盖中了一箭），发现这个过程还是会遇到一些问题（使用mac，所以这里是mac教程），并没有自己想的那么顺利。所以总结一下在这里po出来，当是提醒自己操作流程，当然如果能帮助其他的人，那就更好了。
<!--more-->
## 开始

### 第一步 nodejs安装

Hexo是基于node.js开发的，所以需要安装node.js
－这个过程其实没什么好说的，可以直接在官网下载pkg，
   安装完成 打开终端 输入 ： node  -v
   log输出：v0.12.1   ps:v0.12.1 只是我当前的版本号，能log出版本号就算成功。
   这就证明你的node环境好了。
至于使用，我就不介绍了。顺便说一下，node.js还是很强大的，有兴趣的同学可以深入研究。

More info: [node.js官网](https://nodejs.org/)

### 第二步 hexo安装

当然是按照官网的步骤操作 相当简单的几行命令
``` bash
	npm install hexo-cli -g    ——下载安装  建议加上sudo
	hexo init blog	           ——初始化博客 建立文件夹 blog 一般在用户目录下
	cd blog     			   ——调到 blog文件夹地下操作
	npm install                ——安装一些模板之类的
	hexo server				   ——启动博客  这时候就可以在本地访问了
```
	还有一些其他的命令和配置，在官网有介绍，官网地址在下面会给出，还有很多主题可以下载 
More info: [hexo.js官网](http://hexo.io/)

### 第三步 将博客部署到git服务器上

    首先，要修改hexo的配置文件
    找到 Deployment部分原代码如下：
   ``` bash
		# Deployment
		## Docs: http://hexo.io/docs/deployment.html
		deploy:
		  type:
   ```
	修改为：
``` bash
		# Deployment
		## Docs: http://hexo.io/docs/deployment.html
		deploy:
		  type: git
		  repository: git@github.com:liaozusheng/liaozusheng.github.io.git
		  branch: master
```
	保存之后 hexo c
	        hexo g  ——养成clear再generate的习惯
	        hexo d  这时候状况就很多，报错按下文第四部解决
    如果成功了就可以通过地址
    https://liaozusheng.github.io来访问了。
    后续有时间的话可能还会po一些优化hexo的文章。  

### 第四步 执行hexo d报错的一些处理

    如果报这个错  ERROR Deployer not found: git
    就执行这段命令 npm install hexo-deployer-git --save
    如果报这个错   Permission denied 
	就说明github没有设置ssh
    github使用SSH链接，需要设置SSH,步骤如下：

####  检查SSH key
``` bash
	     cd ~/.ssh 
``` 
####  生成SSH key
``` bash
	     ssh-keygen -t rsa -C liaozu@qq.com
	     第一个输入文件名字如 ——hexoKey
	     然后一直回车就好。
	     最后会log出下面的一段

		+--[ RSA 2048]----+

		|                 |

		|                 |

		|                 |

		|         .       |

		|      . S ..     |

		|     . oE=o..    |

		|      . +o+..    |

		|       ..+.+..   |

		|         oOB=+o  |

		+-----------------+ 
```
####  添加证书 

	查看刚刚生成的证书 ls ~/.ssh/
	hexoKey  hexoKey.pub   ——我生成的证书名字
	使用命令 ssh-add ~/.ssh/hexoKey  添加证书  

####  将SSH key添加到GitHub

	登录到GitHub页面，Account Settings->SSH Public Keys->Add another key
	将生成的key(id_rsa.pub文件）内容copy到输入框中，save。 

####  测试链接
``` bash
	$ ssh git@github.com
		The authenticity of host 'github.com (207.97.227.239)' can't be established.
		RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
		Are you sure you want to continue connecting (yes/no)? yes
		PTY allocation request failed on channel 0
		Hi Jone Zhang! You've successfully authenticated, but GitHub does not provide shell access.
	         Connection to github.com closed.
	出现上述提示信息说明连接成功（github并不提供shell登陆但已经连接成功）
```
####  设置个人信息
``` bash
	$ git config --global user.name "你的名字"
	$ git config --global user.email 邮箱
```
