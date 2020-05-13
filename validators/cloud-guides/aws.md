---
description: 'To launch your AWS instance, follow the steps below.'
---

# AWS

## Step 1: Launching your AWS Node步骤1：启动您的AWS节点 <a id="step-1-launching-your-aws-node"></a>

**1.** If you don’t already have an AWS account, register one at [https://aws.amazon.com](https://aws.amazon.com/). 如果您还没有AWS账户，请在[https://aws.amazon.com上注册一个。](https://aws.amazon.com上注册一个。)

**2.** Once you have set up and logged into your AWS account, click on the top left bar “Services -&gt; Compute -&gt; EC2". 设置并登录到您的AWS账户后，单击左上方的“服务-&gt;计算-&gt; EC2”。

![](https://blobs.gitbook.com/assets%2F-M-IDt7HenNiPUXWT_3k%2F-M-SpPev7Rx3tI5_8vit%2F-M-SvY1PztdgOcjd96xZ%2Fassets_-LlDqlxK8e45wuh1WH4h_-LlEvL4ccZjjcXwS1WWY_-LlEoh9qALwq7NrZTaQH_assets%252F-LiQYKCcGux_Ib7Gddno%252F-Lj2HFbsGU29d_abCLle%252F-Lj2HGc3Atm_1mokTWXl%252FAWS-step3%20%281%29.png?alt=media&token=2ab52e1b-9c94-4ae3-bf28-738cbeb9a917)

**3.** Click on the blue button “Launch Instance". 单击蓝色按钮“启动instance”。

![](https://blobs.gitbook.com/assets%2F-M-IDt7HenNiPUXWT_3k%2F-M-SpPev7Rx3tI5_8vit%2F-M-Sv_xB0oo1-kzPVcC6%2Fassets_-LlDqlxK8e45wuh1WH4h_-LlEvL4ccZjjcXwS1WWY_-LlEoorXG-dkasj2ahJd_assets%252F-LiQYKCcGux_Ib7Gddno%252F-Lj2HFbsGU29d_abCLle%252F-Lj2HGc5NkR0XElzEk6I%252FAWS-step4.png?alt=media&token=29eea808-5ec5-4a38-b483-8d22c1941c76)

**4.** Select “Amazon Linux 2 AMI \(HVM\), SSD Volume Type”.选择 “Amazon Linux 2 AMI \(HVM\), SSD Volume Type”.

![](https://blobs.gitbook.com/assets%2F-M-IDt7HenNiPUXWT_3k%2F-M18EnlHhxfs4IlN_Xhi%2F-M18Eym_BjlKXaPChBdj%2Fassets_-LlDqlxK8e45wuh1WH4h_-LlEvL4ccZjjcXwS1WWY_-LlEoyu2o6s4Sjkvm34W_assets%252F-LiQYKCcGux_Ib7Gddno%252F-Lj2HFbsGU29d_abCLle%252F-Lj2HGc7aUnyzpkZdHd7%252FAWS-step5.png?alt=media&token=d89a9daf-e89c-4472-97ff-c2890379be82)

**5.** Choose instance type “t3.small”.选择机器类型“ t3.small”。

![](https://blobs.gitbook.com/assets%2F-M-IDt7HenNiPUXWT_3k%2F-M18EnlHhxfs4IlN_Xhi%2F-M18F2JIm4erwMfI-q2t%2FScreen%20Shot%202020-02-12%20at%206.20.12%20PM.png?alt=media&token=6eafd968-4468-4b58-b843-5360050982ce)

**6.** Click “Next: Configure Instance Details” at the bottom right corner of the page.

**7.** Don't change anything. Click “Next: Add Storage” at the bottom right corner of the page.

**8.** Change the “Size \(GiB\)” category to 30.

6. 单击页面右下角的“下一步：配置实例详细信息”。 

7.不要改变任何东西。单击页面右下角的“下一步：添加存储”。 

8.将“大小（GiB）”类别更改为30。

![](https://blobs.gitbook.com/assets%2F-M-IDt7HenNiPUXWT_3k%2F-M18EnlHhxfs4IlN_Xhi%2F-M18F8KuOllmF1Crzz68%2FScreen%20Shot%202020-02-27%20at%204.01.10%20PM.png?alt=media&token=feb59374-66c5-4e85-adb7-e020c172ad92)

**9.** Click “Next: Add Tags".

**10.** Click "Add Tag." Then, in the “Key” input box put “Name” in “Value” put “Pangaea-key”.

9.单击“下一步：添加标签”。 

10.单击“添加标签”。然后，在“键”输入框中，在“值”中输入“名称”，然后输入“ Pangaea键”。

![](https://blobs.gitbook.com/assets%2F-M-IDt7HenNiPUXWT_3k%2F-M-SpPev7Rx3tI5_8vit%2F-M-SvyBAYVDNioAq1d8n%2Fassets_-LlDqlxK8e45wuh1WH4h_-LlEvL4ccZjjcXwS1WWY_-LlEqF6sFapEJt6e_ruU_Capture.png?alt=media&token=c2319a18-312e-447a-814f-9d204183a32e)

**11.** Click “Next: Configure Security Group”.

**12.** On the default SSH with port 22, change the “Source” option to “Anywhere”.

**13.** Click "Add Rule". Under "Type" select "Custom TCP Rule", under "Port Range" put "6000" and under "Source" select "Anywhere".

**14.** Click "Add Rule" again. This time, under "Type" select "Custom TCP Rule", under "Port Range" put "9000" and under "Source" select "Anywhere".

1.单击“下一步：配置安全组”。 

12.在带有端口22的默认SSH上，将“源”选项更改为“任何地方”。 

13.单击“添加规则”。在“类型”下，选择“自定义TCP规则”，在“端口范围”下，放置“ 6000”，在“源”下，选择“任何地方”。 

14.再次单击“添加规则”。这次，在“类型”下选择“自定义TCP规则”，在“端口范围”下放置“ 9000”，在“源”下选择“任何地方”。

![](https://blobs.gitbook.com/assets%2F-M-IDt7HenNiPUXWT_3k%2F-M-SpPev7Rx3tI5_8vit%2F-M-Sw01Yoy6KQN9QE9PX%2Fassets_-LlDqlxK8e45wuh1WH4h_-Lw56FxOeYv0YR4puCg__-Lw56P4Wvhdd5sBaWFho_security_groups_aws.jpg?alt=media&token=f3004e29-8898-4d6f-8654-37de5d847936)

**15.** Click “Review and Launch” and then click "Launch". \(Note: Ignore warnings such as “your security group is open to the world” or “your instance configuration is not eligible for free tier”\)

**16.** In the pop-up window you will need to create a new key pair. Select “Create a new key pair” and then enter a name that you like, for example “Pangaea-key”.

15.单击“查看并启动”，然后单击“启动”。 （注意：忽略诸如“您的安全组向世界开放”或“您的实例配置不符合免费套餐条件”之类的警告） 

16.在弹出窗口中，您将需要创建一个新的密钥对。选择“创建新的密钥对”，然后输入您喜欢的名称，例如“ Pangaea-key”。

![](https://blobs.gitbook.com/assets%2F-M-IDt7HenNiPUXWT_3k%2F-M-SpPev7Rx3tI5_8vit%2F-M-Sw3fLntQmXXvy3JHd%2Fassets_-LlDqlxK8e45wuh1WH4h_-LlEvL4ccZjjcXwS1WWY_-LlEqxD-n79Fd0kkMCF3_Capture.png?alt=media&token=673b6e2c-f70a-4a36-8485-751f3becad99)

**17.** Click “Download Key Pair” and save the key file somewhere you'll remember.

**18.** Click “Launch Instances”.

**19.** Click “View Instances” at the bottom right. Your new instance should be initializing. Wait a few moments for it to get started.

**21.** Congratulations your instance is up and running! Now it's time to connect to your instance.

17.单击“下载密钥对”，然后将密钥文件保存在您会记得的地方。 

18.单击“启动instance”。 19.单击右下角的“查看instance”。此时正在初始化。请稍等片刻，使其开始使用。

21.恭喜您的instance已启动并正在运行！现在是时候连接到您的instance了。

![](https://blobs.gitbook.com/assets%2F-M-IDt7HenNiPUXWT_3k%2F-M18Fj8DCAY2KtBma_zp%2F-M18G50wfliuTSWxfFPs%2Fassets_-LlDqlxK8e45wuh1WH4h_-LlEvL4ccZjjcXwS1WWY_-LlErACMN7pbdPNpbeia_assets%252F-LiQYKCcGux_Ib7Gddno%252F-Lj2HFbsGU29d_abCLle%252F-Lj2HGcJYpniB9O_xpMo%252FAWS-step21.png?alt=media&token=cbd9a6fb-c7dd-43db-83cd-bfc8026058a8)

## Step 2: Connecting to your AWS Instance步骤2：连接到您的AWS instance <a id="step-2-connecting-to-your-aws-instance"></a>

**1.** Open a Terminal window on your computer. 在计算机上打开一个终端窗口。 

**For Mac:** If you can’t find Terminal, use spotlight to search for it. Or go to your "Applications' folder, and it should be inside of “Utilities”.

Mac：如果找不到Terminal，请使用Spotlight进行搜索。或转到“应用程序”文件夹，该文件夹应位于“实用程序”的内部。

![](https://blobs.gitbook.com/assets%2F-M-IDt7HenNiPUXWT_3k%2F-M-SpPev7Rx3tI5_8vit%2F-M-SwDSVomei_wm8RgU8%2Fassets_-LlDqlxK8e45wuh1WH4h_-LlEvL4ccZjjcXwS1WWY_-LlErPyudVu-nb4ZLB4D_assets%252F-LiQYKCcGux_Ib7Gddno%252F-Lj2HFbsGU29d_abCLle%252F-Lj2HGcLt-ekXY8UUO4g%252Fkey-step1.png?alt=media&token=04abdbb4-bec6-4c09-94ae-b9aca707139d)

**For Windows:** Download PuTTY to allow your computer to SSH into the AWS instance. For instructions on connecting to an EC2 instance using Putty follow [these instructions](https://docs.aws.amazon.com/quickstarts/latest/vmlaunch/step-2-connect-to-instance.html) from Amazon.

Windows：下载PuTTY以允许您的计算机通过SSH进入AWSInstance。有关使用Putty连接到EC2的说明，请遵循Amazon的这些说明。

**2.** Once Terminal is open, use the `cd` command to change your directory to where the key pair file \(Pangaea-key.pem\) that you generated is. Hint it may be in your “Downloads” folder.

2.打开终端后，使用cd命令将目录更改为所生成的密钥对文件（Pangaea-key.pem）所在的目录。提示它可能在您的“下载”文件夹中。

![](https://blobs.gitbook.com/assets%2F-M-IDt7HenNiPUXWT_3k%2F-M-SpPev7Rx3tI5_8vit%2F-M-SwIfjL7K3O36MS2Lc%2Fassets_-LlDqlxK8e45wuh1WH4h_-LlYZ1j_-40H7bnDrwxD_-LlYgjVgJIwE8kk2L6wF_AWSCDDOWNLAODS.png?alt=media&token=3d58106e-1758-46e7-835e-45efc1a8f6de)

**3.** Enter the command `chmod 400 Pangaea-key.pem`. This command makes your key not publicly viewable.3输入命令chmod 400 Pangaea-key.pem。此命令使您的密钥不公开可见。 

**Note:** On Mac, your pem file may have been changed to a .txt file so the correct command on Mac would be: `chmod 400 Pangaea-key.pem.txt`

注意：在Mac上，您的pem文件可能已更改为.txt文件，因此在Mac上正确的命令是：chmod 400 Pangaea-key.pem.txt

![](https://blobs.gitbook.com/assets%2F-M-IDt7HenNiPUXWT_3k%2F-M1ZJQFhdhIexbw67x-l%2F-M1ZUv7XgOzmLxxNLMUq%2Fimage.png?alt=media&token=ffbf732d-b408-47ce-9179-9d5ac19a22d2)



**4.** Go back to your AWS window where you are viewing your instances. Select your new "Pangaea-key" instance and click “Connect” on the top bar.

4.返回您正在查看实例的AWS窗口。选择新的“ Pangaea键”，然后单击顶部栏上的“连接”。

**5.** In the pop-up window, under the “Example:” header, copy the sample command to connect to your ec2 instance. The command will look something like:

在弹出窗口的“ Example：”标题下，复制示例命令以连接到您的ec2 Instance。该命令将类似于： ssh -i“ pangaea-key.pem” ec2-user@ec2-13-250-30-215.ap-southeast-1.compute.amazonaws.com

```text
ssh -i "pangaea-key.pem" ec2-user@ec2-13-250-30-215.ap-southeast-1.compute.amazonaws.com
```

Now connect to your instance by running the sample command you copied from the “Connect” page in your terminal window.现在，通过运行从终端窗口“连接”页面复制的示例命令来连接到您的Instance。

![](https://blobs.gitbook.com/assets%2F-M-IDt7HenNiPUXWT_3k%2F-M1ZJQFhdhIexbw67x-l%2F-M1ZVNJoWUwvEOWQ5xFq%2Fimage.png?alt=media&token=b998d9af-6344-48bd-ae7f-1523787b30c4)

It may ask you whether or not you want to continue connecting. Type in “yes” and hit enter.

它可能会询问您是否要继续连接。输入“是”，然后按Enter。

![](https://blobs.gitbook.com/assets%2F-M-IDt7HenNiPUXWT_3k%2F-M-SpPev7Rx3tI5_8vit%2F-M-SwU2UBsT7Dov4WsF6%2Fassets_-LlDqlxK8e45wuh1WH4h_-LlYZ1j_-40H7bnDrwxD_-LlYiEuvvkCZfCrmaujP_AWSpangaeaConnected.png?alt=media&token=0b089e53-81bf-49b0-acc3-7ea47f5e9f55)

Congratulations! You should be logged into your new AWS instance!

## Step 3: Installing Required Packages步骤3：安装所需的软件包 

_\*\*_Run the following command to make sure your instance is properly updated:\*\*运行以下命令以确保机器已正确更新： 

```bash
sudo yum update
```

When prompted whether or not you want to download packages, enter "y" for yes.

当提示您是否要下载软件包时，输入“ y”代表是。 

Now install the following packages that will be needed to run Harmony by typing:

现在，通过键入以下命令来安装运行Harmony所需的以下软件包： 

```bash
sudo yum install tmux
```

You will be asked to confirm if you would like to download and install these packages. Just press Y to confirm.

安装tmux 系统将要求您确认是否要下载并安装这些软件包。只需按Y确认。

