# 导航页面使用说明

## 如何添加条目
`在修改之前，请务必确保你已经了解git的工作原理或者有git使用经验，避免破坏原有数据。`

请先申请自己的github账号，然后fork这个项目，提交pull requrest或者branch。详细方法请参考git的教程。
---------
 #### 如何修改index.html
1. 下载并安装git
2. 在本地新建一个目录，打开git bash
3. 在新建的目录执行 git clone http://github.com/hitheper/hitheper.github.io
4. 克隆完成后找到index.html，用编辑器打开（推荐atom）。
5. 搜索index.html，确定你要修改的地方，模仿其他条目进行修改
6. 在本地用浏览器打开index.html，预览修改的效果
7. cd 到 hitheper.github.io
8. git add .
9. git commit -m “上传网站源码到github”
10. git push 并输入账号密码（github账号密码）
不发生意外的话，就可以更新index.html。
如果本地已经修改过，且远程目录发生了更新，请先执行git pull更新本地再做修改。
#### 如何添加页面
1.制作html文件，推荐使用[dillinger](http://dillinger.io/)生成html，简单方便不用注册。
2.将页面放到目录`pages`下面
3.在index.html中添加指向页面的链接
4.检查链接并更新网站
#### 注意事项
- 请保持网站风格一致，不要添加新的样式
- 若无必要（链接失效错误等原因）不要随意删除项目。
Welcome to the hitheper.github.io wiki
- 这是一个简单的导航页面，希望大家都来完善它。
- 如果你知道这个github账号的密码，直接在线修改就可以了。
- 如果你要做很多修改，最好在本地操作。
- 你可以随意clone这个网页并加以修改，产生一个更加适合自己的页面。


>   赵荣 @20161209
