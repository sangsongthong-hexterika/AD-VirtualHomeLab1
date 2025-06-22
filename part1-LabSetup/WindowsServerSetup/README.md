# Windows Server Installation on VMWare

First I started off by installing Windows Server on VMWare. I have skipped the basic setup to until I turn the Windows Server on. I chose the Desktop version to simplified the setup.

After the VM is turned on, you will be greeted with this small size window. To make the VM screen fit correctly to my screen, I navigated to the DVD Drive and double-clicked on the VMWare Tools Setup. Follow all the prompt and let it works its magic. The screenshot below showed which file I am talking about.

![Step_0_ResizeWindows](images/WindowsServer2022-0_InstallVMWareTool1.png)

Then, I restarted the Windows Server. Choose "unplanned" as the reason to reboost the server.

To change The Server's PC's Name, click on the Windows logo at the buttom > View PC Name.

Then, you will see something like the screenshot below.

Take a look at the Device Name. If it isn't the one you like, change it to be something that you can recognize. I chose to name it "THE-SPIDER-DC" from the Phantom Troupe from the Hunter x Hunter as my theme.

To change the PC Name, click on "Rename This PC". A new window will pop-up to let you type the new name. Type in the new name and click "Next" as shown in the screenshot below.

The reason to change the PC Name is so anyone in the system can easily identify which PC is which.

![Step_1_ChangePCName](images/WindowsServer2022_1_ViewPCName.png)

Next, I am moving onto configuring the **Active Directory (AD)**. Open the **Server Manager**, look at the top right corner, click on **Manage**, and select **Add Roles and Features** and follow the guided prompts.

## Install Active Directory (AD)

![Step_2_AddRolesAndFeatures](images/WindowsServer2022_2_Manage-AddRolesAndFeatures.png)

After clicking **Add Roles andFeatures**, choose the **installation type**. Even though I am on a Virtual Machine, the goal is to learn it functionality like I would use ito on a normal machine instead of a VM so I select **Role-based or feature-based installation**.

I can deal with the specific setup for the Server on a VM later if I want to.

Then, click **Next**. The screenshot below shows the step I did.

![Step_3_ChooseRolesBaseInstallation](images/WindowsServer2022_3_ChooseRolesBaseInstallation.png)

On this step, I decide to select the server from the server pool. As you can see, the system is already detected this machine, **THE-SPIDER-DC** (My PC Name). Click **Next**.

The screenshot below shows this step that I have done.

![Step_4_SelectServer](images/WindowsServer2022_4_SelectServer.png)

In this step, I am selecting **Active Directory Domain Services**. When the **Add Roles and Features Wizard** window pop up, I stick with the default and click **Add Features** and click **Next**.

The screenshot below shows what I did with arrows.

![Step_5_AddADService](images/WindowsServer2022_5_AddADService.png)

In this step, I accept the default and click **Next**. To show you which step I am in, look at the screenshot below as the reference.

![Step_6_SelectNextWithoutAddingAnything](images/WindowsServer2022_6_SelectNextWithoutAddingAnything.png)

In this step, there is nothing to do except read and click **Next** as shown in the screenshot below.

![Step_7_SelectNextWithoutAddingAnything](images/WindowsServer2022_7_SelectNextWithoutAddingAnything.png)

Read through to confirm the setting before installing. If it is correct, click **Install**. To keep track pf my step, use the screenshot below as the reference.

![Step_8_ClickInstall](images/WindowsServer2022_8_ClickInstall.png)

After the installation is done, click **Close** and restart the machine as shown in the screenshot below.

![Step_9_ClickClose](images/WindowsServer2022_9_ClickClose.png)

At this point, I have installed the Active Directory on this machine successfully.

## Promote To Domain Controller (DC)

This part of the setup is where I set the Active Directory up after it is already installed in this machine.

To help make my point clear, the previous topic was a blank server without the AD installed so I installed the AD.

However, in this step, the AD is already installed on the machine. I just need to set it up. Think of this step as I am telling it what I want it to do.

The first thing to do in this step is to promote the server to be the Domain Controller (DC). The reason to do that is because the domain controller ...

To do so, looking at the top right corner Server Manager window. You will see a warning flag ⚠️. Click on it and select **Promote this server to a domain controller**.

Please see the screenshot below for reference.

![Step_10_PromoteToDC](images/WindowsServer2022_10_PromoteToDC.png)

After the previous step, the Active Directory Domain Configuration Wizard will pop up. Under **Deployment Configuration**, select **Add a new forest**, and type in the **root domain name** of the forest. Mine is **SPIDER-PT.local**. Yours can be something else. Then, click **Next**.

The screenshot below shows this step that I did.

![Step_11_AddANewForest](images/WindowsServer2022_11_AddANewForest.png)

Under the **Domain Controller Options**, add password of your choosing. As you can see, I am using Windows Server 2022, but the system detection was inaccurate. This isn't a huge problem at the moment so I can ignore it for now. Then, click **Next**.

AS usual, you can see the reference in the screenshot below.

![Step_12_GiveItAPassword](images/WindowsServer2022_12_GiveItAPassword.png)

The next step is configure DNS Options. I just need to accept the default and click **Next**. There is nothing much to do as shown in the screenshot below.

![Step_13_DNSOptionClickNext](images/WindowsServer2022_13_DNSOptionClickNext.png)

Under the **Additional Options**, make sure that the NetBIOS name match the **root domain name** from the **Deployment Configuration** step, but without the *.local* part before clicking **Next**.

Take a look at the screenshot below for reference.

![Step_14_SeeNETBIOSDomainName](images/WindowsServer2022_14_SeeNETBIOSDomainName.png)

Under **Paths**, take a look at the file paths below and familiar myself with them. The Cyber Mentor said they will play important roles later.

Other than familiar myself with the paths, I don't need to do anything except clicking **Next**.

The file paths are visible in the screenshot below.

![Step_15_Path](images/WindowsServer2022_15_Path.png)

Under the **Review Options**, double check that the **domain name** and the **NetBIOS name** are the same with the **domain name** has the *.local* while the **NetBIOS name** doesn't have that part.

If both names match, click **Next**.

The screenshot below highlight that I need to check if the **domain name** and the **NetBIOS name** match before clicking **Next**.

![Step_16_ReviewNext](images/WindowsServer2022_16_ReviewNext.png)

In this step, the **Prerequisites Check**, the system will check for the prerequisites before begining the installation. Once the check is done, click **Install** to begin the installation process.

The screenshot below shows the successful of prerequisites.

![Step_17_PreReqInstall](images/WindowsServer2022_17_PreReqInstall.png)

After the installation is done, restart the machine and try to log in as **SPIDER-PT\Administrator**.

![SPIDER-PT-Admin](images/WindowsServer2022_18_SPIDER-PT-Admin.png)

This is it. The process of setting up the Window Server, setting up the Active Directory, and promote it to the Domain Controller is done.

As you can see, if after rebooting the system, if you can log in as `SPIDER-PT\Administrator`, it means you have set it up correctly.

The important part is instead of logging in as **username**, the system shows the **NetBIOS name** + \ + user.

---

**Author:** Sangsongthong C.
**Publishing Date:** 23 June 2025
