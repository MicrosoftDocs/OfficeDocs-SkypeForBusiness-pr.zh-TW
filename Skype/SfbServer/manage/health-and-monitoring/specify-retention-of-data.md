---
title: 在商務用 Skype Server 中指定 CDR 資料的保留
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 摘要：瞭解如何管理商務用 Skype Server 的通話詳細資料錄製（CDR）資料。
ms.openlocfilehash: ec24b5b1901bec053417c3a938c688cd4692f1c9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991718"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a><span data-ttu-id="bcea4-103">在商務用 Skype Server 中指定 CDR 資料的保留</span><span class="sxs-lookup"><span data-stu-id="bcea4-103">Specify retention of CDR data in Skype for Business Server</span></span>
 
<span data-ttu-id="bcea4-104">**摘要：** 瞭解如何管理商務用 Skype Server 的通話詳細資料錄製（CDR）資料。</span><span class="sxs-lookup"><span data-stu-id="bcea4-104">**Summary:** Learn how to manage call detail recording (CDR) data for Skype for Business Server.</span></span>
  
<span data-ttu-id="bcea4-105">根據預設，通話詳細資料錄製（CDR）資料會在60天之後清除。</span><span class="sxs-lookup"><span data-stu-id="bcea4-105">By default, call detail recording (CDR) data is purged after 60 days.</span></span> <span data-ttu-id="bcea4-106">您可以使用 [**通話詳細資料記錄**] 頁面上的設定，將資料保留較長或較短的時間週期。</span><span class="sxs-lookup"><span data-stu-id="bcea4-106">You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time.</span></span> <span data-ttu-id="bcea4-107">如果您停用 CDR，在啟用 CDR 之前捕獲的資料，也會受到清除。</span><span class="sxs-lookup"><span data-stu-id="bcea4-107">If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bcea4-108">您應該設定 CDR 和體驗品質（QoE），以保留相同天數的資料。</span><span class="sxs-lookup"><span data-stu-id="bcea4-108">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days.</span></span> <span data-ttu-id="bcea4-109">[監視伺服器報告] 頁面提供的呼叫詳細資料包告（CDRs）中的每個通話，包括 CDR 和 QoE 資訊。</span><span class="sxs-lookup"><span data-stu-id="bcea4-109">Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information.</span></span> <span data-ttu-id="bcea4-110">如果 CDR 與 QoE 的清除持續時間不一樣，有些通話可能只會包含 CDR 資料，而其他可能只包含 QoE 資料。</span><span class="sxs-lookup"><span data-stu-id="bcea4-110">If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span> 
  
<span data-ttu-id="bcea4-111">使用下列程式來設定 CDR 資料的清除設定。</span><span class="sxs-lookup"><span data-stu-id="bcea4-111">Use the following procedures to configure purge settings for CDR data.</span></span> 
  
### <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="bcea4-112">指定保留 CDR 資料</span><span class="sxs-lookup"><span data-stu-id="bcea4-112">To specify retention of CDR data</span></span>

1. <span data-ttu-id="bcea4-113">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦.</span><span class="sxs-lookup"><span data-stu-id="bcea4-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="bcea4-114">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="bcea4-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="bcea4-115">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**呼叫詳細資料錄製**]。</span><span class="sxs-lookup"><span data-stu-id="bcea4-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>
    
4. <span data-ttu-id="bcea4-116">在 [**通話詳細資料記錄**] 頁面上，按一下表格中的適當網站，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="bcea4-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>
    
5. <span data-ttu-id="bcea4-117">若要開啟清除，請選取 [**啟用清除 CDRs**]。</span><span class="sxs-lookup"><span data-stu-id="bcea4-117">To turn on purging, select **Enable purging of CDRs**.</span></span>
    
6. <span data-ttu-id="bcea4-118">在 **[保留 CDRs 的最大持續時間（天數）** ] 中：選取應保留通話詳細資料錄製的最大天數。</span><span class="sxs-lookup"><span data-stu-id="bcea4-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>
    
7. <span data-ttu-id="bcea4-119">若要在**最大持續時間（天）內保留錯誤報表資料：** 請選取要保留錯誤報表的最大天數。</span><span class="sxs-lookup"><span data-stu-id="bcea4-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>
    
8. <span data-ttu-id="bcea4-120">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bcea4-120">Click **Commit**.</span></span>
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bcea4-121">使用 Windows PowerShell Cmdlet 指定 CDR 保留</span><span class="sxs-lookup"><span data-stu-id="bcea4-121">Specifying CDR retention by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="bcea4-122">您可以使用 Windows PowerShell 和 CsCdrConfiguration Cmdlet 來建立 CDR 保留設定。</span><span class="sxs-lookup"><span data-stu-id="bcea4-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="bcea4-123">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bcea4-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bcea4-124">如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="bcea4-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="bcea4-125">在商務用 Skype 伺服器中，程式是一樣的。</span><span class="sxs-lookup"><span data-stu-id="bcea4-125">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="bcea4-126">針對特定位置指定 CDR 保留</span><span class="sxs-lookup"><span data-stu-id="bcea4-126">To specify CDR retention for a specific location</span></span>

- <span data-ttu-id="bcea4-127">這個命令可讓您清除雷德蒙網站的 CDR 資料，並將網站設定為維持 CDR 資料，以及20天的錯誤報表資料。</span><span class="sxs-lookup"><span data-stu-id="bcea4-127">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="bcea4-128">若要為多個位置指定 CDR 保留</span><span class="sxs-lookup"><span data-stu-id="bcea4-128">To specify CDR retention for multiple locations</span></span>

- <span data-ttu-id="bcea4-129">這個命令會針對組織中使用的所有 CDR 配置設定，設定 CDR 保留。</span><span class="sxs-lookup"><span data-stu-id="bcea4-129">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

<span data-ttu-id="bcea4-130">如需詳細資訊，請參閱[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="bcea4-130">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bcea4-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bcea4-131">See also</span></span>

[<span data-ttu-id="bcea4-132">在商務用 Skype Server 中呼叫詳細資料錄製（CDR）</span><span class="sxs-lookup"><span data-stu-id="bcea4-132">Call detail recording (CDR) in Skype for Business Server</span></span>](call-detail-recording-cdr.md)
