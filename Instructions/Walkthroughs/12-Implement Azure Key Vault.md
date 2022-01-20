---
wts:
    title: '12 - 实现 Azure 密钥保管库（5 分钟）'
    module: '模块 04：介绍常见安全性和网络安全功能'
---
# 12 - 实现 Azure 密钥保管库（5 分钟）

在本演练中，我们将创建一个 Azure 密钥保管库，然后在该密钥保管库中创建一个密码机密，从而提供安全存储且集中管理的密码，以用于应用程序。

# 任务 1：创建 Azure 密钥保管库 

1. 登录到 [Azure 门户](https://portal.azure.com)。

2. 在“**所有服务**”边栏选项卡中，搜索并选择“**密钥保管库**”，然后选择“**+ 添加**”、“**+ 创建**”、“**+ 新建**”。

3. 配置密钥保管库（将密钥保管库名称中的 **“xxxx”** 替换为字母和数字，使该名称在全局范围内唯一）。其他设置均保留默认值。

    | 设置 | 值 | 
    | --- | --- |
    | 订阅 | **使用提供的默认值** |
    | 资源组 | **创建新的资源组** |
    | 密钥保管库名称 | **keyvaulttestxxx** |
    | 位置 | **美国东部** |
    | 定价层 | **标准** |
    
    **备注**：请替换“**xxxx**”以找到唯一的名称。
4. 单击“**查看 + 创建**”，然后单击“**创建**”。 

5. 预配新密钥保管库后，单击 **“转到资源”**。或者，你可以通过搜索找到新密钥保管库。 

6. 单击密钥保管库“**概述**选项卡并记下“**保管库 URI**”。通过 REST API 使用保管库的应用程序将需要此 URI。

7. 花一点时间浏览一些其他密钥保管库选项。在 **“设置”** 下，查看 **“密钥”**、 **“机密”**、 **“证书”**、 **“访问策略”**、 **“防火墙和虚拟网络”**。

    **备注**： 你的 Azure 帐户是可在此新保管库上执行操作的唯一授权帐户。你可以根据需要在 **“设置”** 中的 **“访问策略”** 部分修改此设置。

# 任务 2：向 Key Vault 添加机密
        
在此任务中，我们将向密钥保管库添加密码。 

1. 在 **“设置”** 下，单击 **“机密”**，然后单击 **“+ 生成/导入”**。

2. 配置机密。将其他值保留为默认值。注意，你可以设置激活和到期日期。注意，你还可以禁用机密。

    | 设置 | 值 | 
    | --- | --- |
    | 上传选项 | **手动** |
    | 名称 | **ExamplePassword** |
    | 值 | **hVFkk96** |

3. 单击 **“创建”**。

4. 成功创建机密后，单击 **“ExamplePassword”**，请注意其状态为 **“已启用”**

5. 选择刚刚创建的机密，注意“**机密标识符**”。这是你现在可用于应用程序的 URL 值。它提供了集中管理且安全存储的密码。 

6. 单击按钮 **“显示机密值”**，显示你先前指定的密码。


恭喜！你已创建 Azure 密钥保管库，然后在该密钥保管库中创建了密码机密，从而提供了安全存储且集中管理的密码，以用于应用程序。

**备注**：为避免产生额外费用，你可以根据需要删除此资源组。搜索资源组，单击你的资源组，然后单击“**删除资源组**”。验证资源组的名称，然后单击“**删除**”。关注“**通知**”，了解删除操作的进度。