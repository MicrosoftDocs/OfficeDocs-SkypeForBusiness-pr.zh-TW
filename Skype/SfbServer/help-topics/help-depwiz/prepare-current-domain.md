---
title: 準備目前網域
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
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 若要準備網域以主控執行商務用 Skype Server 2015 或商務用 Skype 伺服器使用者的伺服器，您必須完成步驟5：準備目前的網域，如使用安裝程式執行網域準備主題的主題所述。 若要完成此步驟，您必須以您準備的網域中的 Domain Admins 群組成員身分登入，或以網域所屬樹系的 Enterprise Admins 群組成員身分登入。 若要準備網域：
ms.openlocfilehash: c9c33e466b7b0fcc7c2711603c284e5f419960a1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096869"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="5326f-105">準備目前網域</span><span class="sxs-lookup"><span data-stu-id="5326f-105">Prepare Current Domain</span></span>

<span data-ttu-id="5326f-106">若要準備網域以主控執行商務用 Skype Server 2015 或商務用 Skype 伺服器使用者的伺服器，您必須完成 **步驟5：準備目前的網域**，如 [使用安裝程式執行網域準備](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation)主題的主題所述。</span><span class="sxs-lookup"><span data-stu-id="5326f-106">To prepare a domain to host servers running Skype for Business Server 2015 or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation).</span></span> <span data-ttu-id="5326f-107">若要完成此步驟，您必須以您準備的網域中的 Domain Admins 群組成員身分登入，或以網域所屬樹系的 Enterprise Admins 群組成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="5326f-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="5326f-108">若要準備網域：</span><span class="sxs-lookup"><span data-stu-id="5326f-108">To prepare the domain:</span></span>

1. <span data-ttu-id="5326f-109">從商務用 Skype Server 2015 安裝資料夾或媒體，執行 Setup.exe 以啟動商務用 Skype Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="5326f-109">From the Skype for Business Server 2015 installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="5326f-110">按一下 **[準備 Active Directory]**，然後等候決定部署狀態。</span><span class="sxs-lookup"><span data-stu-id="5326f-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="5326f-111">在 **[步驟 5：準備目前的網域]**，按一下 **[執行]**。</span><span class="sxs-lookup"><span data-stu-id="5326f-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="5326f-112">在 **[執行命令]** 頁面上，尋找 **[工作狀態：完成]**，然後按一下 **[檢視記錄檔]**。</span><span class="sxs-lookup"><span data-stu-id="5326f-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="5326f-113">在 [ **動作** ] 欄下，依序展開 [ **網域準備**]、[尋找 **\<Success\>** 執行結果]，以驗證網域準備順利完成，請關閉記錄檔，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="5326f-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="5326f-114">如果您需要複查由商務用 Skype Server 部署嚮導所建立的記錄檔，您可以在執行該步驟之 Active Directory 網域服務使用者的使用者目錄中，找到執行「部署」嚮導的電腦。</span><span class="sxs-lookup"><span data-stu-id="5326f-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="5326f-115">例如，如果使用者登入網域 Contoso.net 中的網域管理員，則記錄檔位於： C:\Users\Administrator.Contoso\AppData\Local\Temp。</span><span class="sxs-lookup"><span data-stu-id="5326f-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>