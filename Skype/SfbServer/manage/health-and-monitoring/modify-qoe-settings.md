---
title: 修改商務用 Skype Server 中的經驗品質設定
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
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 摘要：瞭解如何在商務用 Skype Server 中指定 QoE 資料的保留。
ms.openlocfilehash: cba8b2b98aa809c0583ad7323ff846e654ca9ace
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118612"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a><span data-ttu-id="041aa-103">修改商務用 Skype Server 中的經驗品質設定</span><span class="sxs-lookup"><span data-stu-id="041aa-103">Modify Quality of Experience settings in Skype for Business Server</span></span>

<span data-ttu-id="041aa-104">**摘要：** 瞭解如何在商務用 Skype Server 中指定 QoE 資料的保留。</span><span class="sxs-lookup"><span data-stu-id="041aa-104">**Summary:** Learn how to specify retention of QoE data in Skype for Business Server.</span></span>

<span data-ttu-id="041aa-105">根據預設，在60天后會清除 (QoE) 資料的經驗品質。</span><span class="sxs-lookup"><span data-stu-id="041aa-105">By default, Quality of Experience (QoE) data is purged after 60 days.</span></span> <span data-ttu-id="041aa-106">您可以使用 [ **經驗品質資料** ] 頁面上的設定，將資料保留較長或更短的時間週期。</span><span class="sxs-lookup"><span data-stu-id="041aa-106">You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time.</span></span> <span data-ttu-id="041aa-107">如果您停用 QoE，啟用 QoE 之前所捕獲的資料也會加以清除。</span><span class="sxs-lookup"><span data-stu-id="041aa-107">If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

> [!NOTE]
> <span data-ttu-id="041aa-108">您應設定詳細通話記錄 (CDR) 和 QoE 保留相同天數的資料。</span><span class="sxs-lookup"><span data-stu-id="041aa-108">You should configure call detail recording (CDR) and QoE to retain data for the same number of days.</span></span> <span data-ttu-id="041aa-109">[通話詳細資料包告] 中的每個通話 (Cdr) ，可從監控報告首頁取得，包含 CDR 和 QoE 資訊。</span><span class="sxs-lookup"><span data-stu-id="041aa-109">Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information.</span></span> <span data-ttu-id="041aa-110">如果 CDR 和 QoE 的清除持續時間不同，有些呼叫可能只會包含 CDR 資料，另有可能只包含 QoE 資料。</span><span class="sxs-lookup"><span data-stu-id="041aa-110">If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>

<span data-ttu-id="041aa-111">下列程式說明如何設定 QoE 資料的清除設定。</span><span class="sxs-lookup"><span data-stu-id="041aa-111">The following procedure describes how to configure purge settings for QoE data.</span></span>

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="041aa-112">使用商務用 Skype Server 控制台指定 QoE 資料的保留</span><span class="sxs-lookup"><span data-stu-id="041aa-112">To specify retention of QoE data by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="041aa-113">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="041aa-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="041aa-114">如需詳細資訊，請參閱＜**Delegate Setup Permissions**＞。</span><span class="sxs-lookup"><span data-stu-id="041aa-114">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="041aa-115">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="041aa-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="041aa-116">在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[經驗品質資料]**。</span><span class="sxs-lookup"><span data-stu-id="041aa-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="041aa-117">在 [ **經驗品質資料** ] 頁面上，按一下表格中的適當網站，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細** 資料]。</span><span class="sxs-lookup"><span data-stu-id="041aa-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5. <span data-ttu-id="041aa-118">若要開啟清除，請選取 [ **啟用 QoE 的清除**]。</span><span class="sxs-lookup"><span data-stu-id="041aa-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6. <span data-ttu-id="041aa-119">在 [ **保持 QoE 的最大持續時間 (天數])** 選取應該保留 QoE 資料的最大天數。</span><span class="sxs-lookup"><span data-stu-id="041aa-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7. <span data-ttu-id="041aa-120">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="041aa-120">Click **Commit**.</span></span>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="041aa-121">使用 Windows PowerShell Cmdlet 指定 QoE 保留</span><span class="sxs-lookup"><span data-stu-id="041aa-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="041aa-122">您可以使用 Windows PowerShell 及 **Set CsQoEConfiguration** Cmdlet 來建立 QoE 保留設定。</span><span class="sxs-lookup"><span data-stu-id="041aa-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="041aa-123">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="041aa-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="041aa-124">如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="041aa-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="041aa-125">商務用 Skype Server 中的程式相同。</span><span class="sxs-lookup"><span data-stu-id="041aa-125">The process is the same in Skype for Business Server.</span></span>

### <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="041aa-126">指定特定位置的 QoE 保留</span><span class="sxs-lookup"><span data-stu-id="041aa-126">To specify QoE retention for a specific location</span></span>

- <span data-ttu-id="041aa-127">這個命令可讓 Redmond 網站的 QoE 資料得以清除，並設定網站以維護20天的 QoE 資料。</span><span class="sxs-lookup"><span data-stu-id="041aa-127">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>

  ```PowerShell
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="041aa-128">若要指定多個位置的 QoE 保留</span><span class="sxs-lookup"><span data-stu-id="041aa-128">To specify QoE retention for multiple locations</span></span>

- <span data-ttu-id="041aa-129">這個命令會針對組織中使用的所有 QoE 設定設定，設定 QoE 保留。</span><span class="sxs-lookup"><span data-stu-id="041aa-129">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

<span data-ttu-id="041aa-130">如需詳細資訊，請參閱 [Set CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="041aa-130">For more information, see the help topic for the [Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="041aa-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="041aa-131">See also</span></span>

[<span data-ttu-id="041aa-132">部署監控</span><span class="sxs-lookup"><span data-stu-id="041aa-132">Deploying Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)