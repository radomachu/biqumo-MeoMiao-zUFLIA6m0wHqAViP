[上一期](https://github.com)介绍了为什么要打造自己的 DeepSeek，本期将介绍怎么安装自己的 DeepSeek。

---

这里要使用的工具是 **Ollama**。

> 它是一个免费开源的本地大语言模型运行平台，可以帮我们把 DeepSeek 模型下载到我们自己的电脑上运行，支持 Windows、MacOS 和 Linux 三大主流操作系统（本月 8 日，华为发布了鸿蒙电脑操作系统，相信在不久的将来，Ollama 也会支持）。

具体的部署步骤如下：

# 一、下载 Ollama

1. 访问 Ollama 官网：[www.ollama.com](https://github.com)

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746951694052-c0774eea-ede4-4099-a367-3c51d0eaf1ec.png)

可以看到，除了 DeepSeek R1，它还支持很多其他的开源模型。

> 至于为什么没有大名鼎鼎的 ChatGPT，当然是因为它不开源了（研发它的公司叫做 OpenAI，以 Open 为名，却从不开源，应该叫 “CloseAI” 才是）。

这里以部署 DeepSeek R1 为例，其他开源模型部署的步骤是大同小异的，大家可以自行尝试。

2. 点击“Download”进行下载：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746952141436-0f691bae-2d92-4c20-825a-33c24bf37187.png)

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746952365934-28dcf7b9-96bb-4f97-9551-9ec9fcf9d34b.png)

这里自动识别了电脑的操作系统，我的电脑是 Windows 系统，这里就以 Windows 为例演示了，其他系统步骤大同小异。

# 二、安装 Ollama

Ollama 的安装非常简单。

1. 打开安装程序，点击“Install”即开始安装，没有多余选项。

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746952677979-d5516428-a14a-4adf-ad3a-a6c82a51fb3d.png)

2. 按键盘上的 Win + R 键，在弹窗中输入 `cmd`

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746953000910-377e6337-8402-4577-b208-65b80d0af71c.png)

点击“确定”，打开命令窗口：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746953047209-fa88cf0a-d6cc-4d23-9fbe-4622dbcf1fc8.png)

3. 输入 `ollama`，点击回车，如果出现如下输出，代表 Ollama 安装成功。

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746953133585-05bd9ef4-44fc-4ae0-aec1-c855432f19b3.png)

# 三、下载 DeepSeek R1 模型

1. 回到 [Ollama 官网首页](https://github.com):[西柚加速器](https://xiyojiasu.com)，点击 “DeepSeek R1”：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746953412070-b1aa1929-2e43-488b-8e30-a99ba2a070f4.png)

会进入到 DeepSeek R1 模型的下载主页：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746953491169-380dd780-f453-406e-a1b8-b3aaac99c80c.png)

点击这里可以看到 DeepSeek R1 不同量级模型对应的显存要求列表：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746953582587-f402e87d-e5b0-4df5-b245-319fa46f74ba.png)

数字后面的 b 是 billion 的缩写，代表十亿个参数，参数量越大代表得到的回答的质量也就越高，但相对的对配置的要求也越高。

```
- 如果电脑只有集显，就选择 1.5b 的模型。
- 如果是统一架构的 CPU，一部分内存可以当显存用，根据可以当作显存使用的内存大小选择模型。
- 如果电脑有独立显卡，根据显存大小选择模型。
- 至于 671b，显存要求高达 404GB！它是大家现在使用的公版 DeepSeek 的量级，个人电脑几乎不可能达到，一般都是大公司部署使用。
```

这里我们以配置要求最低的 1.5b 模型进行演示。

2. 下滑找到 1.5b 模型对应的安装命令，“复制”命令：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746954520342-69b9aeb9-79a5-4232-8430-cb0f48565e53.png)

3. 回到刚才打开的命令窗口，“粘贴”命令：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746954614853-271122a3-3dc1-48fd-bd48-fa6286a417b8.png)

点击“回车”运行：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746954679001-075d68c3-e462-46aa-be5a-a989466bccb0.png)

当看到输出“success”，即代表安装成功。

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746954833613-642d6528-8f11-4e83-bb15-ea65cbe18679.png)

这里其实已经可以使用 DeepSeek 了，比如：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746954927121-f147cf8e-cf0b-4694-89c5-92bf661a93fd.png)

但这样的命令行方式显然很不方便，所以还需要使用第三方工具，实现类似于官网那样的使用体验。

# 四、下载 Cherry Studio

1. 访问 Cherry Studio 官网：[www.cherry-ai.com](https://github.com)

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746955131308-b68736d3-65a3-432a-a25d-3b68a1b4460b.png)

2. 点击“下载客户端”进行下载：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746955175021-4eb2f91a-4bdd-45c6-bde8-2c1868aeaaac.png)

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746955717869-b33951f1-8831-4aa2-8b89-6674fba41004.png)

这里根据自己的系统架构进行选择：

```
- 如果是 x86 64 位架构，就选择 “x64”选项。
- 如果是 ARM 64 位架构，就选择“ARM64”选项。
```

> 这里很好判断，个人电脑目前除了苹果的 M 系列芯片电脑以及本月 19 号发布的华为鸿蒙电脑，都是 x86 64 位架构的。

我的电脑是 x86 64 位的：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746955980247-ad6db3d5-860c-4763-afd4-807c635b3a26.png)

# 五、安装 Cherry Studio

1. 打开安装程序：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746956155562-e49e7226-355f-4d14-9267-7e551ab5bccd.png)

指定想要安装的目录，进行安装：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746956219237-52604426-8e5c-4f3b-a4c3-155b099e4d78.png)

出现如下界面代表安装完成：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746956253689-1bfb92c6-b71e-455a-a91b-cbece71b8b0e.png)

# 六、使用 Cherry Studio

1. 打开安装好的 Cherry Studio：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746956362424-90f1bd29-2284-4e8e-8324-26c3cdfb2d77.png)

2. 点击左下角的“设置”按钮：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746956414770-af4a4c0d-7634-4312-acb9-f50a59056094.png)

3. 在模型服务中选择“Ollama：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746956477421-e72c1dae-2329-43e2-9e14-57e34c2b6925.png)

4. 打开顶部的开关：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746956527805-3add89fe-882c-4c77-a385-b0a64957b381.png)

5. 点击“管理”按钮：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746956567944-17ca6c73-f390-4d52-9761-92120ab8a80b.png)

6. 添加刚才下载的 DeepSeek 模型：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746956657165-634dd6c6-9b1b-4b8b-a36d-119b6e548934.png)

关闭对话框：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746956723976-fc586288-27da-425b-ae7e-1daf51c80265.png)

7. 关闭其他模型的开关：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746959071800-f9f9d277-9c98-48c5-8b79-39123944f9d1.png)

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746956865938-5dba7eb9-bb7a-4916-8237-3b6ac12c2610.png)

8. 回到主页的对话界面：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746956780368-25a78c8a-2557-4211-9494-f07f7ed762ce.png)

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746957154159-dec951c3-69c0-4227-ba8a-7aa634cadb30.png)

这样就可以跟平时一样与 DeepSeek 对话了：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746957218142-c8081f6b-9a68-494a-96ce-bac62041fb6b.png)

如果安装了多个 DeepSeek 模型，还可以点击顶部切换：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746957254056-fa9bce5f-7efe-4d40-aba4-a49b19645637.png)

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746957266420-b5e96e22-d2b1-4d03-9ce0-6d3e71780ebf.png)

---

**这样就完成了自己的 DeepSeek 安装。**

电脑重启后会在系统右下角有 Ollama 的图标，代表 Ollama 正在运行：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746957784611-3724300c-92f7-4099-ad07-048b0201937a.png)

如何不想运行，右键点击退出即可：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746957817081-fb95c2d6-8903-47b3-9012-db3f07c60e3a.png)

如果想要再次使用按 Win 键搜索“Ollama”即可打开：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746958037856-cb4e24f1-b8ec-405b-a7f1-585b428a460f.png)

然后打开 Cherry Studio 即可直接使用：

![](https://cdn.nlark.com/yuque/0/2025/png/29483397/1746957864216-4a095bba-a1a8-4a9a-8377-8c7822543c2d.png)
