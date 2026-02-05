## 使用

### 克隆仓库（clone）

选择一个文件夹（最好是项目文件夹或者文件夹的上级目录），并通过如图所示方式打开cmd或powershell

![image-20260204155310823](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260204155310823.png)

从项目此处获取git地址（也可以使用https协议，但是push的时候可能需要额外验证身份，所以建议使用ssh）

![image-20260204155735677](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260204155735677.png)

使用如下命令克隆仓库

```text
git clone <git地址> <创建文件夹名称>
```

其中，创建文件夹名称可以省略，则将当前文件夹做为项目文件夹，如果选择的不是项目文件夹或者不是空文件夹，则不建议省略，会根据所写的文件夹路径创建文件夹

![image-20260204160247866](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260204160247866.png)

红色框选内容为项目路径，可选`相对路径`和`绝对路径`，自行了解。如果当前文件夹就是项目文件夹，则可以省去路径，把当前文件夹做为项目文件夹

![image-20260204160505674](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260204160505674.png)

打开目录能看到.git文件夹一般就表示clone成功了（这个文件夹默认被隐藏，自行搜索如何查看隐藏文件夹，但是请不要取消隐藏，可能会出现未知错误）

![image-20260204160733352](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260204160733352.png)

### 切换和创建分支

打开任意编辑器，这里以pycharm为例，选择`打开->选择克隆下来的文件夹（不是.git文件夹，是克隆下来的那一整个文件夹）`

![image-20260204161509691](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260204161509691.png)

不建议勾选添加到排除列表，添加了排除列表会很乱，然后选择信任项目

![image-20260204161538442](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260204161538442.png)

打开IDE后这里将会出现一个main的标识，如果没有就是打开的文件夹错了。

![image-20260204162359054](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260204162359054.png)

![image-20260204162535949](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260204162535949.png)

默认上面本地是没有develop分支的，选择远程/origin，从`origin/develop`分支创建分支，填入分支名称，并创建

![image-20260204162656995](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260204162656995.png)

### 创建文件并提交

切换分支后在项目目录中创建和修改文件，例如这里创建README.md文件，并写入一些内容

![image-20260205150947273](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260205150947273.png)

如果新建文件将会出现是否将文件添加到git，也就是是否跟踪文件，等同于`git add`命令，除了测试文件、缓存文件等不需要跟踪的文件，或者例如密钥等不能公开的文件，否则其他文件都可以选择添加。如果没有添加，也不用担心，后续也可以在git面板添加。

没有被跟踪的文件名称是红色的，正在跟踪的文件名称是绿色的，被修改的文件名称是蓝色的，排除路径的名称是橙色的

![image-20260205151327838](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260205151327838.png)

![image-20260205151503560](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260205151503560.png)

编辑完成之后，点击左侧git面板，可以看到已经更改了的文件，以及没有进行版本管理的文件

![image-20260205151914608](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260205151914608.png)

![image-20260205152013812](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260205152013812.png)

选择本次要提交的文件，以及填写提交信息，然后选择提交（或者提交并推送，推送即为同步到github，如果只是功能开发过程中的备份，可以不着急推送，如果没有选择推送，也可以在顶部菜单栏选择推送）。<span style="color:red">注意看顶部分支名称，切勿在不属于你的分支上进行开发，以免影响到其他人。</span>

![image-20260205152441511](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260205152441511.png)

提交完成之后，可以看到你的提交信息，以及右侧修改的文件。中间面板与你的分支不同颜色的部分即为你的分支基于其他分支的提交点，比如这里是基于develop分支的名称为`init project`的commit（提交）。每次完成部分完整功能都可以提交内容，<span style="color:red">但是，请不要频繁进行无效提交</span>，比如今天代码写了一半，还没完成某些功能，备份以下进度，就提交一次，<span style="color:red">这是错误的做法，提交应是有意义的，能让其他协作者看出你做了什么功能的，</span>后续将会有提交的模板，请按照模板进行提交

### 提交PR（<span style="color:red">重要</span>)

不同成员在基于develop分支的不同分支上进行开发，开发完成一个功能之后就需要把开发的内容通过提交PR（pull requests）请求合并到develop分支上，PR经过验证，确认没有冲突内容和问题之后将会合并到develop分支，经过一段时间的开发，完成了一些完整的功能，develop分支将会合并至main主分支上，表示完成了一个版本或者阶段性的开发。

提交PR的方式很多，可以在pycharm中完成github或其他平台的身份认证之后提交PR，也可以在github上提交PR，这里以在GitHub上提交PR为例。

#### 提交PR的流程

首先提交PR前请确定自己改分支功能开发完成并经过测试，且没有问题。

如果提交的时候没有进行推送，则需要先手动推送。点击左上角分支名称，选择正在开发的分支名称，点击推送。

![image-20260205153808577](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260205153808577.png)

此时会弹出一个窗口，其中包括首行本地分支与github仓库分支的差异，以及该分支新增的提交内容

![image-20260205154024215](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260205154024215.png)

此时需要确认将要提交的分支与github仓库是分支是否对应，如果仓库不存在该分支将会有提示会新建分支，<span style="color:red">请千万不要把自己创建的分支推送到其他人的分支或者main和develop等其他重要分支上。</span>

![image-20260205154255400](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260205154255400.png)

完成推送后将会在远程仓库中也看到自己的分支和分支的提交信息，下一步回到github中，找到仓库地址，选择Pull requests，点击New pull request。

![image-20260205154540379](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260205154540379.png)

选项的地方则是PR相关的分支，左侧为目标分支，右侧为pr分支（将要被合并的分支） ，右侧分支也是在左侧分支创建出来的。<span style="color:red">再次强调，千万不要PR到其他人的分支或者PR到main分支上，除非是在他人的分支上开发，可以合并至他人的分支上。</span>

完成分支选择后点击Create pull requests，进入下一步。如图，请在标题和描述中填写这次PR的内容，最好可以描述清楚这次PR主要新增的功能，也可以更细致的说明一下通过什么方式实现的。（补充：下面的描述支持markdown格式，可以通过点击Preview按钮预览渲染后内容）

![image-20260205155342899](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260205155342899.png)

同时，在右侧可以看到标签选项，可以为本次PR添加标签，便于后续进行快速索引。完成上述的内容后就可以点击绿色的Create pull requests创建PR，等待PR通过即可，如果PR存在问题（与其他分支内容冲突、存在问题等）则将会被驳回，则需要进一步修改。

已批准：

![image-20260205181207925](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260205181207925.png)

批准之后就可以点击绿色按钮合并分支，此时请认真填写这次PR的内容，比如完成了哪些模块的开发，修复了什么问题等等

![image-20260205181328596](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260205181328596.png)

## 格式模板

### 分支规范

分支名称统一使用`type/scope`(即`类型/范围(功能)`）的格式，例:
```text
dev/auth  		# 开发用户认证功能（一般基于develop分支创建分支）
fix/api  		# 关于API的修复分支（一般基于对应的dev分支创建的分支）

# 也可以在后面加上你的信息，表示这个分支的开发者，但请遵循上述的命名规则
dev/ui_hcy
dev/ui_zhuimeng
```

#### 示例

![image-20260205205024896](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260205205024896.png)

### Commit Message 规范

为了确保团队成员在提交代码时保持一致性，所有的 commit message 应该遵循以下规范。

```text
Type(Scope): Short description

Long description(可选)
```

```text
类型(范围): 简要说明

详细说明（可选，一般在修改设计到很多文件的时候会使用，需要自己换行）
```

> 备注：类型和范围部分建议使用英文标点，且英文冒号后添加一个空格，其余部分正常使用中文标点即可。详细说明部分请先空一行再编写内容。

**示例：**

```text
# 涉及文件内容减少且简单
feat(auth): 添加用户登录UI
fix(api): 修复用户认证API
docs(readme): 添加readme文档

# 涉及文件内容多且文件结构复杂
feat(auth): 新增用户登录功能

新增用户登录功能，包括：
  支持使用账号密码登录，由文件（模块）xxxx实现，调用xxxx
  邮箱验证码登录....
（备注：差不多长度就换行，可以通过不同长度的空格体现层级）
```

- 类型（Type）

| 类型     | 描述                             |
| -------- | -------------------------------- |
| feat     | 新功能 (feature)                 |
| fix      | 修复 bug                         |
| docs     | 文档修改                         |
| style    | 代码格式修改（不影响代码逻辑）   |
| refactor | 重构（不修复 bug，也不添加功能） |
| test     | 添加或修改测试                   |
| chore    | 维护工作（如修改构建工具等）     |
| perf     | 性能优化                         |

范围（Scope）

| 范围     | 描述         |
| -------- | ------------ |
| auth     | 认证模块     |
| ui       | 用户界面     |
| api      | 后端接口     |
| database | 数据库       |
| test     | 测试相关     |
| config   | 配置文件相关 |

#### **示例**

![image-20260205183432211](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260205183432211.png)

### PR 规范

#### 创建PR

创建PR的时候说明功能，能够体现做了什么修改即可。建议是按照commit message规范编写，然后待会也可以直接复制到分支合并的commit message中。

#### 合并PR

通过审核之后的PR可以按下绿色按钮合并分支，此时commit message框保持默认，然后下面的description框按照上述的commit总结这个分支的修改。

![image-20260205184255708](https://github.com/zhuimeng-hstc/test_1/blob/test_1/guide/img/image-20260205184255708.png)

## <span style="color:red">强调</span>

千万不要直接编辑和使用main分支和develop分支，如果直接再main和develop分支上进行修改和编辑，可能会导致其他协作者出现无法提交PR，编辑内容失效等问题。所以，<span style="color:red">切记千万不要直接在main分支和develop分支上进行编辑</span>，我已经添加了一些规则，但是只能防呆不防傻，不要因为一些不小心的操作导致他人的努力付诸东流。
