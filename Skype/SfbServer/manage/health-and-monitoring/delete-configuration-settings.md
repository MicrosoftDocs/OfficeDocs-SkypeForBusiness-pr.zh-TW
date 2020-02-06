---
title: 在商務用 Skype Server 中刪除現有的 CDR 配置設定集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 摘要：瞭解如何在商務用 Skype Server 中移除 CDR 配置設定。
ms.openlocfilehash: d9e990018d97f8e631f3a95718a76aa83d7d619e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818023"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="1f71b-103">在商務用 Skype Server 中刪除現有的 CDR 配置設定集合</span><span class="sxs-lookup"><span data-stu-id="1f71b-103">Delete an existing collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="1f71b-104">**摘要：** 瞭解如何在商務用 Skype Server 中移除 CDR 配置設定。</span><span class="sxs-lookup"><span data-stu-id="1f71b-104">**Summary:** Learn how to remove CDR configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="1f71b-105">通話詳細資料錄製（CDR）可讓您追蹤諸如對等立即訊息會話、透過網際網路通訊協定（VoIP）電話撥打電話及會議呼叫等專案的使用方式。</span><span class="sxs-lookup"><span data-stu-id="1f71b-105">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls.</span></span> <span data-ttu-id="1f71b-106">此使用量資料包括呼叫者、呼叫者及交談時間的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1f71b-106">This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="1f71b-107">當您安裝商務用 Skype Server 時，系統會為您建立單一、全域的 CDR 配置設定。</span><span class="sxs-lookup"><span data-stu-id="1f71b-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="1f71b-108">系統管理員也可以選擇建立可套用至個別網站的自訂設定集合。</span><span class="sxs-lookup"><span data-stu-id="1f71b-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="1f71b-109">根據設計，在網站範圍設定的設定會優先于在全域範圍中設定的設定。</span><span class="sxs-lookup"><span data-stu-id="1f71b-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="1f71b-110">如果您刪除網站範圍的設定，則會使用全域設定在該網站中管理 CDR。</span><span class="sxs-lookup"><span data-stu-id="1f71b-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="1f71b-111">請注意，您也可以 [刪除] 全域設定。</span><span class="sxs-lookup"><span data-stu-id="1f71b-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="1f71b-112">不過，全域設定將不會實際移除。</span><span class="sxs-lookup"><span data-stu-id="1f71b-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="1f71b-113">相反地，該集合中的所有屬性都會重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="1f71b-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="1f71b-114">例如，在 CDR 配置設定的集合中啟用 [清除]。</span><span class="sxs-lookup"><span data-stu-id="1f71b-114">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="1f71b-115">假設您修改全域集合，以便停用清除功能。</span><span class="sxs-lookup"><span data-stu-id="1f71b-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="1f71b-116">如果您稍後刪除全域設定，所有屬性都將會重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="1f71b-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="1f71b-117">在這種情況下，這表示清除會再次啟用。</span><span class="sxs-lookup"><span data-stu-id="1f71b-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="1f71b-118">您可以使用商務用 Skype Server 的 [控制台] 或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) Cmdlet 來移除 CDR 配置設定。</span><span class="sxs-lookup"><span data-stu-id="1f71b-118">You can remove CDR configuration settings by using the Skype for Business Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="1f71b-119">在商務用 Skype Server [控制台] 中移除 CDR 配置設定</span><span class="sxs-lookup"><span data-stu-id="1f71b-119">To remove CDR configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1f71b-120">在商務用 Skype Server 的 [控制台] 中，按一下 [**監視及**封存]。</span><span class="sxs-lookup"><span data-stu-id="1f71b-120">In Skype for Business Server Control Panel, click **Monitoring and Archiving**.</span></span> 
    
2. <span data-ttu-id="1f71b-121">在 [**通話詳細資料記錄**] 索引標籤上，選取要移除的 CDR 設定的集合（或 [收藏]）。</span><span class="sxs-lookup"><span data-stu-id="1f71b-121">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed.</span></span> <span data-ttu-id="1f71b-122">若要選取多個收藏，請按一下第一個收藏，按住 Ctrl 鍵，然後按一下 [其他集合]。</span><span class="sxs-lookup"><span data-stu-id="1f71b-122">To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>
    
3. <span data-ttu-id="1f71b-123">按一下 [**編輯**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="1f71b-123">Click **Edit**, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="1f71b-124">在商務用 Skype Server [控制台] 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1f71b-124">In the Skype for Business Server Control Panel dialog box, click **OK**.</span></span>
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1f71b-125">使用 Windows PowerShell Cmdlet 移除 CDR 配置設定</span><span class="sxs-lookup"><span data-stu-id="1f71b-125">Removing CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1f71b-126">您可以使用 Windows PowerShell 和**CsCdrConfiguration** Cmdlet 來刪除通話詳細資料錄製設定設定。</span><span class="sxs-lookup"><span data-stu-id="1f71b-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="1f71b-127">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1f71b-127">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1f71b-128">如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="1f71b-128">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="1f71b-129">在商務用 Skype 伺服器中，程式是一樣的。</span><span class="sxs-lookup"><span data-stu-id="1f71b-129">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="1f71b-130">移除指定的 CDR 配置設定集合</span><span class="sxs-lookup"><span data-stu-id="1f71b-130">To remove a specified collection of CDR configuration settings</span></span>

 <span data-ttu-id="1f71b-131">這個命令會移除套用至雷德蒙網站的 CDR 設定設定：</span><span class="sxs-lookup"><span data-stu-id="1f71b-131">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="1f71b-132">移除套用至網站範圍的所有 CDR 設定設定</span><span class="sxs-lookup"><span data-stu-id="1f71b-132">To remove all the CDR configuration settings applied to the site scope</span></span>

 <span data-ttu-id="1f71b-133">這個命令會移除所有適用于網站範圍的 CDR 設定設定：</span><span class="sxs-lookup"><span data-stu-id="1f71b-133">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

<span data-ttu-id="1f71b-134">如需詳細資訊，請參閱[Remove CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="1f71b-134">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1f71b-135">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1f71b-135">See also</span></span>

[<span data-ttu-id="1f71b-136">在商務用 Skype Server 中手動清除通話詳細資料錄製和體驗資料庫品質</span><span class="sxs-lookup"><span data-stu-id="1f71b-136">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

