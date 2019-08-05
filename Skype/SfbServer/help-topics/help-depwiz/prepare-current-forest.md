---
title: 準備目前的樹系
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: 若要準備 Active Directory 網域服務林, 您必須成功地延伸架構, 如執行架構準備的主題中所述, 並確定架構已複製。
ms.openlocfilehash: 3d22b2a2cbe69132d7c84cbcced3090fd4ade266
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189691"
---
# <a name="prepare-current-forest"></a><span data-ttu-id="78879-103">準備目前的樹系</span><span class="sxs-lookup"><span data-stu-id="78879-103">Prepare Current Forest</span></span>

<span data-ttu-id="78879-104">若要準備 Active Directory 網域服務林, 您必須成功地延伸架構, 如執行[架構準備](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)的主題中所述, 並確定架構已複製。</span><span class="sxs-lookup"><span data-stu-id="78879-104">To prepare the Active Directory Domain Services forest, you must successfully extend the schema, as described in the topic [Running Schema Preparation](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx), and make sure that the schema has replicated.</span></span>

<span data-ttu-id="78879-p101">完成這些先決條件之後，您就可以開始 [步驟 3：準備目前的樹系]\*\*\*\*。若要準備樹系，請在樹系根中以 Domain Admins 成員身分 (或是以正在準備之樹系的 Enterprise Admins 成員身分) 登入樹系根裡的電腦。</span><span class="sxs-lookup"><span data-stu-id="78879-p101">After completing these prerequisites, you can begin **Step 3: Prepare Current Forest**. To prepare the forest, log on to a computer in the forest root as a member of Domain Admins in the forest root, or as a member of the Enterprise Admins for the forest that you are preparing.</span></span>

1. <span data-ttu-id="78879-107">在「部署精靈」的 [步驟 3：準備目前的樹系] \*\*\*\* 中，按一下 [執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="78879-107">From the Deployment Wizard at **Step 3: Prepare Current Forest**, click **Run**.</span></span>

2. <span data-ttu-id="78879-108">在 [準備樹系] \*\*\*\* 頁面上，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="78879-108">From the **Prepare Forest** page, click **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="78879-109">您可以在 [林準備] 中, 選擇要放置商務用 Skype Server 2015 通用群組的位置。</span><span class="sxs-lookup"><span data-stu-id="78879-109">Forest Preparation enables you to choose where to place the Universal Groups for Skype for Business Server 2015.</span></span> <span data-ttu-id="78879-110">請選擇和組織需求一致的位置。</span><span class="sxs-lookup"><span data-stu-id="78879-110">Choose a location that is consistent with the requirements of your organization.</span></span>

3. <span data-ttu-id="78879-p103">在 [執行命令] \*\*\*\* 頁面上，尋找 [工作狀態: 已完成]\*\*\*\*，然後按一下 [檢視記錄檔]\*\*\*\*。確定沒有任何錯誤。檢閱相關警告，判斷這些是否為基礎結構預期的典型錯誤。</span><span class="sxs-lookup"><span data-stu-id="78879-p103">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**. Make sure that there are no errors. Review the warnings to determine if they are expected and typical for your infrastructure.</span></span>

4. <span data-ttu-id="78879-114">在記錄中的 [**動作**] 欄底下, 展開 [**目錄林準備**], 尋找每個工作結尾的\*\* \<成功\> \*\*執行結果, 以確認已成功完成目錄林準備、關閉記錄, 然後按一下 **[完成]**.</span><span class="sxs-lookup"><span data-stu-id="78879-114">Under the **Action** column in the log, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

5. <span data-ttu-id="78879-115">在執行網域準備前, 請等候 Active Directory 網域服務複製完成, 或強制複製到林根網網域控制站的**Active Directory 網站和服務**管理單元中所列的所有網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="78879-115">Wait for Active Directory Domain Services replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="78879-116">在所有 Active Directory 網站的網網域控制站之間強制進行複製, 以在幾分鐘內進行複製。</span><span class="sxs-lookup"><span data-stu-id="78879-116">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

    > [!TIP]
    > <span data-ttu-id="78879-117">如果您需要查看由商務用 Skype Server 部署嚮導所建立的記錄檔, 您可以在執行步驟之 Active Directory 網域服務使用者的使用者目錄中, 找到已執行部署嚮導的電腦上的日誌檔。</span><span class="sxs-lookup"><span data-stu-id="78879-117">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="78879-118">例如, 如果使用者是以網域 Contoso.net 的網域管理員身分登入, 則記錄檔案位於: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="78879-118">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span>


