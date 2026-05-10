# Setting Domain Controller User Group Policy

Continuing from the server setup from the previous part, at this point the server has AD installed. From this point onwards, I'm going to setup the AD for the real usage by creating users, groups, and services policies.

At the top right corner of the **Server Manager**, click on **Tools**. Then, choose **Active Directory Users and Computer**. As shown in the screenshot below.

![DC_1_ToolsADUserAndComputer](images/DC_1_ToolsADUserAndComputer.png)

A new window calls **Active Directory Users and Computer** pops-up after that. To see that we are on the same page, the screenshot below shows my current step.

![DC_2_ADUserAndComputer](images/DC_2_ADUserAndComputer.png)

Take a look at the left column. Right click on your domain name. Mine is SPIDER.local. Choose **New** and then **Organizational Unit** or **OU** to create a new OU.

To verify that we are both onboarded, take a look at the screenshot below.

![DC_3_CreateANewOU](images/DC_3_CreateANewOU.png)

After that a new window called **New Object - Organizational Unit** appears. Type the name of the OU and click OK. Mine is **Groups** as shown in the screenshot below.

![DC_4_NameANewOU](images/DC_4_NameANewOU.png)

After hitting the **OK** button, you can see that a new OU called **Groups** appears as a new subfolder on the left column.

The screenshot below highlight that a new OU's name's Groups is successfully created. However, be aware that in this screenshot I was in the **Users** OU, not Groups, so the members shown on the right column belongs to the OU's name's **Users**.

There, you can see that **Administrator** and **Guest** are the two default built-in accounts.

---

Creating Chrollo as a domain admin user

![DC_5_ClearOffUsers](images/DC_5_ClearOffUsers.png)

![DC_6_SeeDomainAdminMemberOf](images/DC_6_SeeDomainAdminMemberOf.png)

![DC_7_CreateChrolloAsDomainAdmin](images/DC_7_CreateChrolloAsDomainAdmin.png)

![DC_8_CreateChrolloAsDomainAdminPassword](images/DC_8_CreateChrolloAsDomainAdminPassword.png)

![DC_9_FinishCreatingChrollo](images/DC_9_FinishCreatingChrollo.png)

---

Creating regular users (Hisoka, Illumi)

![DC_10_CreateARegularUser](images/DC_10_CreateARegularUser.png)

![DC_11_FinishCreatingRegularUserHisoka](images/DC_11_FinishCreatingRegularUserHisoka.png)

![DC_12_FinishCreatingRegularUserIllumi](images/DC_12_FinishCreatingRegularUserIllumi.png)

---

Checking users properties

![DC_13_checkIllumiProperties](images/DC_13_checkIllumiProperties.png)

![DC_14_checkHisokaProperties](images/DC_14_checkHisokaProperties.png)

![DC_15_checkChrolloProperties](images/DC_15_checkChrolloProperties.png)

---

Creating SQL service account with password in the description.

It's intentionally misconfigured as a vulnerability for the pentest phase because this is a common practice that can lead to security vulnerability that worth being shown.

![DC_16_create.SQLServiceAccountAsADomainAdmin](images/DC_16_create.SQLServiceAccountAsADomainAdminpng.png)

![DC_17_FinishCreatingSQLServiceAccount](images/DC_17_FinishCreatingSQLServiceAccount.png)

![DC_18_SQLServiceAccountPasswordInDescription](images/DC_18_SQLServiceAccountPasswordInDescription.png)

---

Setting up file share service via SMB

![DC_19_filesShareService](images/DC_19_filesShareService.png)

![DC_20_filesShareServiceCreateNewShare](images/DC_20_filesShareServiceCreateNewShare.png)

![DC_21_selectSMBShareQuick](images/DC_21_selectSMBShareQuick.png)

![DC_22_selectLocationNext](images/DC_22_selectLocationNext.png)

![DC_23_createShareName](images/DC_23_createShareName.png)

![DC_24_otherSettings](images/DC_24_otherSettings.png)

![DC_25_permissions](images/DC_25_permissions.png)

![DC_26_confirmation](images/DC_26_confirmation.png)

![DC_27_result](images/DC_27_result.png)

---

Opening port 445

![DC_28_setShareFolderToOpenPort445](images/DC_28_setShareFolderToOpenPort445.png)

---

Confirming users

![DC_29_confirmUsers](images/DC_29_confirmUsers.png)

---
