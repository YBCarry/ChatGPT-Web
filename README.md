# 使用GPT-3.5 API创建的ChatGPT聊天页面，模型回复效果与官网的ChatGPT一致
## Star the [Repository](https://github.com/YBCarry/ChatGPT-Web)  
## 特性
> 极简配置  
> 支持railway云部署  
> 支持多用户使用  
> 多对话管理  
> 公式显示  
> 流式逐字加载显示  
> 代码高亮  
> 查余额  

## 演示动图
![演示](https://user-images.githubusercontent.com/38237931/227176542-c924084c-8ceb-41cd-9e09-1f82e1d14366.gif)
  

## 使用前提
> 1. 因国内IP被封或OpenAI API被墙，因此自己需要有代理，稍后需要配置，（若使用railway部署时不需要有代理)    
> 2. 有openai账号
> 3. 创建好api_key, 进入[OpenAI链接](https://platform.openai.com/),右上角点击，进入页面设置  
![image](https://user-images.githubusercontent.com/38237931/222461544-260ef350-2d05-486d-bf36-d078873b0f7a.png)

## 部署方法
分别介绍下面几种部署方法，选择一种即可，部署完成后直接跳转至后面的使用介绍继续即可
<details>
<summary>1. 本地源代码部署（推荐，方便更新，需要有代理）</summary>

> 前提：python3.7及以上运行环境
> 1. 执行 `pip install -r requirements.txt`安装必要包
> 2. 打开`config.yaml`文件，配置HTTPS_PROXY和OPENAI_API_KEY，相关细节已在配置文件中描述
> 5. 执行`python main.py`运行程序.若程序中未指定apikey也可以在终端执行时添加环境变量，如执行`OPANAI_API_KEY=sk-XXXX python main.py`来运行，其中`sk-XXXX`为你的apikey
> 6. 打开本地浏览器访问`127.0.0.1:5000`,部署完成
> 7. 关于更新，当代码更新时，使用git pull更新重新部署即可  
</details>
<details>
<summary>2. Railway部署（推荐，无需代理，云部署，通过url随时随地访问）</summary>  
  
  > - 关于Railway：Railway是云容器提供商，你能够使用它部署你的应用，并使用url链接随时随地访问你的应用，Railway使用前提是你的GitHub账号满180天，绑定并验证后每月送5美元和500小时的使用时长，大概21天，因此如果使用这种方式需要在某些不使用的时段停止你的容器  
  > 1. 首先将代码fork到你的github中
  > 2. 点击右侧[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/new)，然后选择`Deploy from GitHub repo`，再选择`Configure GitHub App`，将会弹出新的窗口，在该窗口中选择`Only select repositories`，然后到下拉列表中选择刚才fork到你账号的仓库
  ![image](https://user-images.githubusercontent.com/38237931/228179892-340ab8e5-dc20-4365-80bb-8ecc2568a4a8.png)
  > 3. 授权完成后，`Configure GitHub App`下将会出现授权的项目  
  ![image](https://user-images.githubusercontent.com/38237931/228181108-597230a2-49b6-4202-bacf-4dd3f9d3da92.png)
  > 4. 不要点击立即部署，点击添加变量
  ![image](https://user-images.githubusercontent.com/38237931/228181839-c7fd4404-69ca-4800-bd43-ae1926e82650.png)
  > 5. 将会跳转至新页面，依次添加`PORT`,`DEPLOY_ON_RAILWAY`以及`OPENAI_API_KEY`三个环境变量,相应值如下PORT为5000，DEPLOY_ON_RAILWAY为true
  ![image](https://user-images.githubusercontent.com/38237931/228186399-c2a1a802-7394-4c54-8148-057284e047b2.png) 
  > 6. 修改变量后会自动部署，可点击`Deployments`查看，还可以点击查看日志  
  ![image](https://user-images.githubusercontent.com/38237931/228187234-4a2b7003-e747-4a50-80fd-36a6f9c5deff.png)
  > 7. 点击查看日志，成功的一般显示如下  
  ![image](https://user-images.githubusercontent.com/38237931/228150419-47ea9ffd-2f8d-4851-a5bd-ed9c3d49b28d.png)  
  > 8. 查看访问url，未生成可点击Generate Domain生成即可，当然如果你自己有域名，还可以添加你自己的自定义域名    
  ![image](https://user-images.githubusercontent.com/38237931/228151149-ab46e0cf-1936-4e9a-860a-4d82f70185d8.png)  
  > 9. 进入后如图，任何网络环境下只要输入url即可访问
  ![image](https://user-images.githubusercontent.com/38237931/228188680-4a802916-8719-448e-a532-94f275601990.png)
  > 10. 关于更新，当源仓库更新时，只需要将fork下来的仓库同步更新，railway将会自动部署更新的代码

  
  
</details>

<details>
<summary>3. Railway template部署（不推荐，代码迟滞高）</summary>  
  
> 1. 点击右侧按钮进行部署[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/template/oT2ZUt?referralCode=LtUnsq)
> 首次使用railway的用户需要先绑定github账号并登陆，并进行验证，验证后可获得5美元、500小时每月的免费额度，绑定完成后重新点击上方图标，进行部署，如图进入后填写相关信息和api key  
> ![image](https://user-images.githubusercontent.com/38237931/228148818-b928763e-eeed-4a7b-a0b2-263bfc3ee4a5.png)  
> 2. 点击部署后，会自动跳转，等待部署完成即可，如图为部署完成  
![image](https://user-images.githubusercontent.com/38237931/228154517-b0ed2a1a-0b5e-4321-b613-686a07bd424f.png)
> 3. 点击查看日志，成功的一般显示如下  
![image](https://user-images.githubusercontent.com/38237931/228150419-47ea9ffd-2f8d-4851-a5bd-ed9c3d49b28d.png)  
> 4. 查看访问url，使用该url即可访问  
![image](https://user-images.githubusercontent.com/38237931/228151149-ab46e0cf-1936-4e9a-860a-4d82f70185d8.png)  
> 5. 关于更新，点击如下进行更新即可，由Dashboard进入选择如下，但该种方式检查更新的迟滞似乎太高      
![image](https://user-images.githubusercontent.com/38237931/228157242-0614b216-564b-4abf-8c37-130ca6736fbd.png)

</details>

<details>
<summary>4. 可执行文件部署（推荐无python运行环境使用，需要自己有代理）</summary>

待补充

</details>

<details>
<summary>5. Docker部署（需要自己有代理）</summary>

待补充

</details>

## 使用介绍
- 开启程序后进入如下页面  
![image](https://user-images.githubusercontent.com/38237931/226513812-ff05e48f-64f2-465f-a8c2-d6ac41df46c2.png)
- 直接输入已有用户id,或者输入new:xxx创建新id，这个id用于绑定会话，下次不同浏览器打开都可以恢复用户的聊天记录,一个浏览器31天内一般不会要求再次输入用户id，如下为创建一个新id，名为zs，下图为发送完成后自动刷新的用户页面，左侧会有一个默认对话  
![image](https://user-images.githubusercontent.com/38237931/224632635-3639e8bd-a6a6-4c1c-9c49-2c3d04c9ed3b.png)  
- 代码中已经设置了apikey，但如果开放给别人用针对个别用户也可以按照说明设置用户专属apikey，这里就暂不设置专属的
- 默认为普通对话模式，即每次发送都是仅对于该提问回答，可点击切换为连续对话模式，chatgpt将会联系上下文(之前的对话，程序中设置了最大5条记录)回复你，但意味着花费会更多money  
- 用python写一个冒泡算法试试看，回车发送，shift+回车换行，然后问用java呢？会联系上下文回答 
![image](https://user-images.githubusercontent.com/38237931/226513646-fe3cd31d-3597-4c0c-aa54-fdb734916b85.png)
- 还可以按如下添加对话
![image](https://user-images.githubusercontent.com/38237931/224634107-f9c43c94-f044-4323-913f-2141c081fc04.png)
- 对话管理，当不使用该对话时，可以点击删除对话，若当前为默认对话，则只可删除聊天记录


## 重要更新  
> 2023.3.19: 代码高亮显示  
> 2023.3.17: 显示公式  
> 2023.3.17: 类似于chatgpt官网，支持实时流获取，即逐字获取动态加载显示  
> 2023.3.13: 类似于chatgpt官网，支持新建对话，单个用户可以管理多个对话  
> 2323.3.6: 会话与用户id绑定并保存用户信息，同一浏览器下次登陆时自动进入绑定的id，其余设备输入用户id后依然可以重载聊天记录  
> 2323.3.6: 支持保存历史聊天记录，当重新打开会话时自动恢复聊天记录，使用pickle持久化存储，程序重启时依然可加载各用户聊天记录   
> 2023.3.5: 支持markdown内容显示 

## TODO List  
- [x] 在连续对话模式下支持多人同时使用
- [x] 重载历史记录
- [x] 切换聊天模式和重置时提示
- [x] 支持多对话管理
- [x] 公式显示
- [x] 流式拉取，逐字词动态实时显示
- [x] 代码高亮显示
- [x] 查余额
- [ ] 界面优化
- [ ] 代码规范化，请求返回值规范、代码文件划分
