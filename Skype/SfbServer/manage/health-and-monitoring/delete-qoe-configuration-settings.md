---
title: 在商務用 Skype Server 中刪除經驗的設定品質設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 摘要：瞭解如何在商務用 Skype Server 中刪除 [經驗品質（QoE）] 設定。
ms.openlocfilehash: 134ebe39f41ca051db4ff79eafb094dcc929b5e8
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992420"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="66bdf-103">在商務用 Skype Server 中刪除經驗的設定品質設定</span><span class="sxs-lookup"><span data-stu-id="66bdf-103">Delete Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="66bdf-104">**摘要：** 瞭解如何在商務用 Skype Server 中刪除體驗品質（QoE）設定。</span><span class="sxs-lookup"><span data-stu-id="66bdf-104">**Summary:** Learn how to delete Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="66bdf-105">經驗品質（QoE）度量單位會追蹤您組織中的音訊和視頻通話品質，包括網路資料包遺失、背景雜色及「抖動」（資料包延遲的差異）的數量。</span><span class="sxs-lookup"><span data-stu-id="66bdf-105">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span> <span data-ttu-id="66bdf-106">這些度量單位會與其他資料（例如通話明細記錄）之外，儲存在資料庫中，讓您可以啟用和停用與其他資料錄製無關的 QoE。</span><span class="sxs-lookup"><span data-stu-id="66bdf-106">These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="66bdf-107">當您安裝商務用 Skype Server 時，系統會為您建立單一、全域的 QoE 配置設定集合。</span><span class="sxs-lookup"><span data-stu-id="66bdf-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="66bdf-108">系統管理員也可以選擇建立可套用至個別網站的自訂設定集合。</span><span class="sxs-lookup"><span data-stu-id="66bdf-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="66bdf-109">根據設計，在網站範圍設定的設定會優先于在全域範圍中設定的設定。</span><span class="sxs-lookup"><span data-stu-id="66bdf-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="66bdf-110">如果您刪除網站範圍的設定，就會使用全域設定在該網站中管理 QoE。</span><span class="sxs-lookup"><span data-stu-id="66bdf-110">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="66bdf-111">請注意，您也可以 [刪除] 全域設定。</span><span class="sxs-lookup"><span data-stu-id="66bdf-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="66bdf-112">不過，全域設定將不會實際移除。</span><span class="sxs-lookup"><span data-stu-id="66bdf-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="66bdf-113">相反地，該集合中的所有屬性都會重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="66bdf-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="66bdf-114">例如，在 QoE 配置設定的集合中啟用 [清除]。</span><span class="sxs-lookup"><span data-stu-id="66bdf-114">For example, by default purging is enabled in a collection of QoE configuration settings.</span></span> <span data-ttu-id="66bdf-115">假設您修改全域集合，以便停用清除功能。</span><span class="sxs-lookup"><span data-stu-id="66bdf-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="66bdf-116">如果您稍後刪除全域設定，所有屬性都將會重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="66bdf-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="66bdf-117">在這種情況下，這表示清除會再次啟用。</span><span class="sxs-lookup"><span data-stu-id="66bdf-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="66bdf-118">您可以使用商務用 Skype Server 的 [控制台] 或 [ [remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) ] Cmdlet 來移除 QoE 設定設定。</span><span class="sxs-lookup"><span data-stu-id="66bdf-118">You can remove QoE configuration settings by using the Skype for Business Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="66bdf-119">使用商務用 Skype Server 的 [控制台] 刪除 QoE 配置設定</span><span class="sxs-lookup"><span data-stu-id="66bdf-119">To delete QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="66bdf-120">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="66bdf-120">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="66bdf-121">如需詳細資訊，請參閱**委派設定許可權**。</span><span class="sxs-lookup"><span data-stu-id="66bdf-121">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="66bdf-122">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="66bdf-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="66bdf-123">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**體驗資料品質**]。</span><span class="sxs-lookup"><span data-stu-id="66bdf-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="66bdf-124">在 [**體驗品質資料**] 頁面上，按一下您要的原則，按一下 [**編輯**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="66bdf-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="66bdf-125">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="66bdf-125">Click **OK**.</span></span>
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="66bdf-126">使用 Windows PowerShell Cmdlet 移除 QoE 配置設定</span><span class="sxs-lookup"><span data-stu-id="66bdf-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="66bdf-127">您可以使用 Windows PowerShell 和**Remove-CsQoEConfiguration** Cmdlet 來刪除 QoE 設定設定。</span><span class="sxs-lookup"><span data-stu-id="66bdf-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="66bdf-128">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="66bdf-128">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="66bdf-129">如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="66bdf-129">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="66bdf-130">在商務用 Skype 伺服器中，程式是一樣的。</span><span class="sxs-lookup"><span data-stu-id="66bdf-130">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="66bdf-131">移除指定的 QoE 配置設定集合</span><span class="sxs-lookup"><span data-stu-id="66bdf-131">To remove a specified collection of QoE configuration settings</span></span>

 <span data-ttu-id="66bdf-132">這個命令會移除套用至雷德蒙網站的 QoE 設定設定：</span><span class="sxs-lookup"><span data-stu-id="66bdf-132">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="66bdf-133">若要移除所有套用至網站範圍的 QoE 設定設定</span><span class="sxs-lookup"><span data-stu-id="66bdf-133">To remove all of the QoE configuration settings applied to the site scope</span></span>

 <span data-ttu-id="66bdf-134">這個命令會移除所有套用至網站範圍的 QoE 設定：</span><span class="sxs-lookup"><span data-stu-id="66bdf-134">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="66bdf-135">若要移除 QoE 監視功能停用的所有 QoE 設定設定</span><span class="sxs-lookup"><span data-stu-id="66bdf-135">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="66bdf-136">這個命令會移除已停用 QoE 監視的所有 QoE 設定設定：</span><span class="sxs-lookup"><span data-stu-id="66bdf-136">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

<span data-ttu-id="66bdf-137">如需詳細資訊，請參閱[移除-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="66bdf-137">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="66bdf-138">另請參閱</span><span class="sxs-lookup"><span data-stu-id="66bdf-138">See also</span></span>

[<span data-ttu-id="66bdf-139">在商務用 Skype Server 中手動清除通話詳細資料錄製和體驗資料庫品質</span><span class="sxs-lookup"><span data-stu-id="66bdf-139">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

