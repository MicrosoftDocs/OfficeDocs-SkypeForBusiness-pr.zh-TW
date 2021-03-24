---
title: 準備目前的樹系
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: 若要準備 Active Directory 網域服務樹系，您必須順利擴充架構（如執行架構準備的主題中所述），並確定架構已複製。
ms.openlocfilehash: 94d41a993b2fe976ef7ede885d277c00417ff7dc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103459"
---
# <a name="prepare-current-forest"></a><span data-ttu-id="47990-103">準備目前的樹系</span><span class="sxs-lookup"><span data-stu-id="47990-103">Prepare Current Forest</span></span>

<span data-ttu-id="47990-104">若要準備 Active Directory 網域服務樹系，您必須順利擴充架構（如執行 [架構準備](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-the-active-directory-schema)的主題中所述），並確定架構已複製。</span><span class="sxs-lookup"><span data-stu-id="47990-104">To prepare the Active Directory Domain Services forest, you must successfully extend the schema, as described in the topic [Running Schema Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-the-active-directory-schema), and make sure that the schema has replicated.</span></span>

<span data-ttu-id="47990-p101">完成這些先決條件之後，您就可以開始「步驟 3：準備目前的樹系」。若要準備樹系，請在樹系根中以 Domain Admins 成員身分 (或是以正在準備之樹系的 Enterprise Admins 成員身分) 登入樹系根裡的電腦。</span><span class="sxs-lookup"><span data-stu-id="47990-p101">After completing these prerequisites, you can begin **Step 3: Prepare Current Forest**. To prepare the forest, log on to a computer in the forest root as a member of Domain Admins in the forest root, or as a member of the Enterprise Admins for the forest that you are preparing.</span></span>

1. <span data-ttu-id="47990-107">在 [部署精靈] 的「步驟 3：準備目前的樹系」中，按一下 [執行]。</span><span class="sxs-lookup"><span data-stu-id="47990-107">From the Deployment Wizard at **Step 3: Prepare Current Forest**, click **Run**.</span></span>

2. <span data-ttu-id="47990-108">在「準備樹系」頁面上，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="47990-108">From the **Prepare Forest** page, click **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="47990-109">樹系準備可讓您選擇放置商務用 Skype Server 2015 通用群組的位置。</span><span class="sxs-lookup"><span data-stu-id="47990-109">Forest Preparation enables you to choose where to place the Universal Groups for Skype for Business Server 2015.</span></span> <span data-ttu-id="47990-110">請選擇和組織需求一致的位置。</span><span class="sxs-lookup"><span data-stu-id="47990-110">Choose a location that is consistent with the requirements of your organization.</span></span>

3. <span data-ttu-id="47990-p103">在「執行命令」頁面上，尋找 [工作狀態: 已完成]，然後按一下 [檢視記錄檔]。確定沒有任何錯誤。檢閱相關警告，判斷這些是否為基礎結構預期的典型錯誤。</span><span class="sxs-lookup"><span data-stu-id="47990-p103">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**. Make sure that there are no errors. Review the warnings to determine if they are expected and typical for your infrastructure.</span></span>

4. <span data-ttu-id="47990-114">在記錄檔的 [ **動作** ] 欄中，依序展開 [ **樹系準備**]，尋找 **\<Success\>** 執行結果以驗證樹系準備順利完成，關閉記錄檔，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="47990-114">Under the **Action** column in the log, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

5. <span data-ttu-id="47990-115">等候 Active Directory 網域服務複寫完成，或是強制複寫到樹系根域控制 **站之 Active Directory 網站和服務** 嵌入式管理單元中列出的所有網域控制站，然後再執行網域準備作業。</span><span class="sxs-lookup"><span data-stu-id="47990-115">Wait for Active Directory Domain Services replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="47990-116">強制在所有 Active Directory 網站的網域控制站之間進行複寫，以在幾分鐘內進行網站的複寫。</span><span class="sxs-lookup"><span data-stu-id="47990-116">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

    > [!TIP]
    > <span data-ttu-id="47990-117">如果您需要複查由商務用 Skype Server 部署嚮導所建立的記錄檔，您可以在執行該步驟之 Active Directory 網域服務使用者的 [使用者] 目錄中，找到其上執行「部署」嚮導的電腦。</span><span class="sxs-lookup"><span data-stu-id="47990-117">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="47990-118">例如，如果使用者登入網域 Contoso.net 中的網域管理員，則記錄檔位於： C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="47990-118">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span>