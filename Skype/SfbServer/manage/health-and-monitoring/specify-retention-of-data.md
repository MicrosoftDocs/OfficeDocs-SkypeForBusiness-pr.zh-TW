---
title: 在商務用 Skype Server 中指定保留 CDR 資料
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 摘要：瞭解如何管理商務用 Skype Server (CDR) 資料的詳細通話記錄。
ms.openlocfilehash: abf6461a76ced9d3ba07e4c5157dd4d14bab60a3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104389"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a><span data-ttu-id="1ac65-103">在商務用 Skype Server 中指定保留 CDR 資料</span><span class="sxs-lookup"><span data-stu-id="1ac65-103">Specify retention of CDR data in Skype for Business Server</span></span>
 
<span data-ttu-id="1ac65-104">**摘要：** 瞭解如何管理商務用 Skype Server (CDR) 資料的詳細通話記錄。</span><span class="sxs-lookup"><span data-stu-id="1ac65-104">**Summary:** Learn how to manage call detail recording (CDR) data for Skype for Business Server.</span></span>
  
<span data-ttu-id="1ac65-105">根據預設，[詳細通話記錄] (CDR) 資料會在60天之後清除。</span><span class="sxs-lookup"><span data-stu-id="1ac65-105">By default, call detail recording (CDR) data is purged after 60 days.</span></span> <span data-ttu-id="1ac65-106">您可以使用 [ **詳細通話記錄** ] 頁面上的設定，將資料保留較長或更短的時間週期。</span><span class="sxs-lookup"><span data-stu-id="1ac65-106">You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time.</span></span> <span data-ttu-id="1ac65-107">如果您停用 CDR，啟用 CDR 之前所捕獲的資料也會受到清除。</span><span class="sxs-lookup"><span data-stu-id="1ac65-107">If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1ac65-108">您應設定 CDR 和經驗品質 (QoE) 保留相同天數的資料。</span><span class="sxs-lookup"><span data-stu-id="1ac65-108">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days.</span></span> <span data-ttu-id="1ac65-109">「監控伺服器報告」頁面提供的 [通話詳細資料包告] 中的每個通話 (Cdr) ，包含 CDR 和 QoE 資訊。</span><span class="sxs-lookup"><span data-stu-id="1ac65-109">Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information.</span></span> <span data-ttu-id="1ac65-110">如果 CDR 和 QoE 的清除持續時間不同，有些呼叫可能只會包含 CDR 資料，另有可能只包含 QoE 資料。</span><span class="sxs-lookup"><span data-stu-id="1ac65-110">If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span> 
  
<span data-ttu-id="1ac65-111">使用下列程式可設定 CDR 資料的清除設定。</span><span class="sxs-lookup"><span data-stu-id="1ac65-111">Use the following procedures to configure purge settings for CDR data.</span></span> 
  
### <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="1ac65-112">指定保留 CDR 資料</span><span class="sxs-lookup"><span data-stu-id="1ac65-112">To specify retention of CDR data</span></span>

1. <span data-ttu-id="1ac65-113">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="1ac65-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="1ac65-114">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="1ac65-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="1ac65-115">在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[詳細通話記錄]**。</span><span class="sxs-lookup"><span data-stu-id="1ac65-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>
    
4. <span data-ttu-id="1ac65-116">在 [ **詳細通話記錄** ] 頁面上，按一下表格中的適當網站，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細** 資料]。</span><span class="sxs-lookup"><span data-stu-id="1ac65-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>
    
5. <span data-ttu-id="1ac65-117">若要開啟清除，請選取 [ **啟用清除 cdr**]。</span><span class="sxs-lookup"><span data-stu-id="1ac65-117">To turn on purging, select **Enable purging of CDRs**.</span></span>
    
6. <span data-ttu-id="1ac65-118">在 [ **保持 cdr 的最大持續期間 (天數) ：** 選取應該保留詳細通話記錄的最大天數。</span><span class="sxs-lookup"><span data-stu-id="1ac65-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>
    
7. <span data-ttu-id="1ac65-119">在 [ **將錯誤報表的最大持續時間 (天數]) 中：** 選取應該保留錯誤報表的最大天數。</span><span class="sxs-lookup"><span data-stu-id="1ac65-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>
    
8. <span data-ttu-id="1ac65-120">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="1ac65-120">Click **Commit**.</span></span>
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1ac65-121">使用 Windows PowerShell Cmdlet 指定 CDR 保留</span><span class="sxs-lookup"><span data-stu-id="1ac65-121">Specifying CDR retention by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="1ac65-122">您可以使用 Windows PowerShell 和 Set-CsCdrConfiguration Cmdlet 來建立 CDR 保留設定。</span><span class="sxs-lookup"><span data-stu-id="1ac65-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="1ac65-123">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1ac65-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1ac65-124">如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="1ac65-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="1ac65-125">商務用 Skype Server 中的程式相同。</span><span class="sxs-lookup"><span data-stu-id="1ac65-125">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="1ac65-126">指定特定位置的 CDR 保留</span><span class="sxs-lookup"><span data-stu-id="1ac65-126">To specify CDR retention for a specific location</span></span>

- <span data-ttu-id="1ac65-127">此命令可讓您清除 Redmond 網站的 CDR 資料，並將網站設定為維護 CDR 資料和錯誤報表資料的20天。</span><span class="sxs-lookup"><span data-stu-id="1ac65-127">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="1ac65-128">指定多個位置的 CDR 保留</span><span class="sxs-lookup"><span data-stu-id="1ac65-128">To specify CDR retention for multiple locations</span></span>

- <span data-ttu-id="1ac65-129">此命令會針對組織中使用的所有 CDR 設定設定，設定 CDR 保留。</span><span class="sxs-lookup"><span data-stu-id="1ac65-129">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

<span data-ttu-id="1ac65-130">如需詳細資訊，請參閱 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="1ac65-130">For more information, see the help topic for the [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1ac65-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1ac65-131">See also</span></span>

[<span data-ttu-id="1ac65-132">商務用 Skype Server 中的詳細通話記錄 (CDR) </span><span class="sxs-lookup"><span data-stu-id="1ac65-132">Call detail recording (CDR) in Skype for Business Server</span></span>](call-detail-recording-cdr.md)