---
title: 準備目前的網域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: '若要準備網域以主持執行商務用 Skype Server 或商務用 Skype Server 使用者的伺服器, 您必須完成步驟 5: 準備目前的網域, 如使用安裝程式執行網域準備主題中所述。 若要完成此步驟，您必須以目前準備之網域中的 Domain Admins 群組成員身分，或網域所屬之樹系的 Enterprise Admins 群組成員身分登入。 若要準備網域，請執行下列操作：'
ms.openlocfilehash: 16b47a211ebff577844cdc29b6e28acd00952d20
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193530"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="3ce25-105">準備目前的網域</span><span class="sxs-lookup"><span data-stu-id="3ce25-105">Prepare Current Domain</span></span>

<span data-ttu-id="3ce25-106">若要準備網域以主持執行商務用 Skype Server 或商務用 Skype Server 使用者的伺服器, 您必須完成**步驟 5: 準備目前的網域**, 如[使用安裝程式執行網域準備](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)主題中所述。</span><span class="sxs-lookup"><span data-stu-id="3ce25-106">To prepare a domain to host servers running Skype for Business Server or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span></span> <span data-ttu-id="3ce25-107">若要完成此步驟，您必須以目前準備之網域中的 Domain Admins 群組成員身分，或網域所屬之樹系的 Enterprise Admins 群組成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="3ce25-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="3ce25-108">若要準備網域，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="3ce25-108">To prepare the domain:</span></span>

1. <span data-ttu-id="3ce25-109">從商務用 Skype Server 安裝資料夾或媒體, 執行 setup.exe 以啟動商務用 Skype Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="3ce25-109">From the Skype for Business Server installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="3ce25-110">按一下 [準備 Active Directory]\*\*\*\*，然後等候決定部署狀態。</span><span class="sxs-lookup"><span data-stu-id="3ce25-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="3ce25-111">在 [步驟 5：準備目前的網域]\*\*\*\*，按一下 [執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3ce25-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="3ce25-112">在 [執行命令]\*\*\*\* 頁面上，尋找 [工作狀態：完成]\*\*\*\*，然後按一下 [檢視記錄檔]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3ce25-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="3ce25-113">在 [**動作**] 欄底下, 展開 [**網域準備**], 尋找每個工作\*\* \< \> \*\*結尾的成功執行結果, 確認已成功完成 [網域準備], 然後關閉記錄, 然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="3ce25-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="3ce25-114">如果您需要查看由商務用 Skype Server 部署嚮導所建立的記錄檔, 您可以在執行步驟之 Active Directory 網域服務使用者的使用者目錄中, 找到運行 [部署嚮導] 的電腦上的日誌檔。</span><span class="sxs-lookup"><span data-stu-id="3ce25-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="3ce25-115">例如, 如果使用者是以網域 Contoso.net 的網域管理員身分登入, 則記錄檔案位於: C:\Users\Administrator.Contoso\AppData\Local\Temp。</span><span class="sxs-lookup"><span data-stu-id="3ce25-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>


