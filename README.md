# Github-Image-Hosting
测试一下Github当作图床的效果怎么样。

以下为具体步骤：
# 一、新建仓库

# 二、克隆仓库
1.点击Code-Local-Clone-SSH，将地址复制下来。<br>
2.在本地建立一个文件夹，右键Git Bash Here，终端输入以下代码：
```bash
git clone {SSH}
```
其中{SSH}为自己复制的地址（形如`git clone git@github.com:XXX/YYY.git`，XXX为Github名称，YYY为仓库名称）

# 三、创建图床文件夹
在克隆文件夹内创建一个文件夹，名称可以随意，进入该文件夹，我们可以把需要用到的图片复制进此文件夹内。

# 四、上传图片
1.在克隆文件夹内Git Bash Here，输入以下代码：
```bash
git add .
```
（注意有一个小点）
这步的目的是将文件加入到暂存区。<br>
2.输入以下代码：
```bash
git commit -m "更新图片"
```
这步的目的是将暂存区文件加入到本地仓库。<br>
3.输入以下代码：
```bash
git push
```
这步的目的是将本地仓库上传到远程仓库。<br>
4.如果想要对远程仓库进行修改（如删除），需要在执行前三步前先将远程仓库与本地仓库同步：
```bash
git pull
```

# 五、查看仓库内图片
打开在仓库内的图片，可以发现地址为`https://github.com/{用户名}/{图床仓库名}/blob/main/{图片文件夹}/{图片名称}`
我们将其中的blob改为raw，即为我们需要图片的地址。
也可以选择这个地址`https://raw.githubusercontent.com/{用户名}/{图床仓库名}/main/{图片文件夹}/{图片名称}`

# 六、CDN部署加速
经验证，jsd目前已被墙，5.2方法已失效。

## 5.1 Cloudflare部署
创建项目后会给出一个域，形如`aaa-bbb-ccc.pages.dev`
我们在上述域后面添加内容 /{图片文件夹}/{图片名称}，用浏览器进入，即为我们需要图片的地址。

## 5.2 jsdelivr部署
将仓库内图片的地址改为`https://cdn.jsdelivr.net/gh/{你的github用户名}/{图床仓库名}@{仓库分支}/{图片文件夹}/{图片名称}`
其中仓库分支一般为main
