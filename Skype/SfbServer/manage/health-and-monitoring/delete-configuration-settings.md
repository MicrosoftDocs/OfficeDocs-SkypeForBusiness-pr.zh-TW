---
title: 在商務用 Skype Server 中刪除現有 CDR 設定設定集合
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
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 摘要：瞭解如何在商務用 Skype Server 中移除 CDR 設定設定。
ms.openlocfilehash: ca6691d6a1a19e0d9219a256986b683b719da885
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816963"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="ceb64-103">在商務用 Skype Server 中刪除現有 CDR 設定設定集合</span><span class="sxs-lookup"><span data-stu-id="ceb64-103">Delete an existing collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="ceb64-104">**摘要：** 瞭解如何在商務用 Skype Server 中移除 CDR 設定設定。</span><span class="sxs-lookup"><span data-stu-id="ceb64-104">**Summary:** Learn how to remove CDR configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="ceb64-p101">詳細通話記錄 (CDR) 讓您能夠追蹤點對點即時訊息工作階段、Voice over Internet Protocol (VoIP) 電話通話，以及會議通話之類的使用狀況。這個使用狀況資料包含有關通話者雙方身分、通話時間以及通話時間長度的資訊。</span><span class="sxs-lookup"><span data-stu-id="ceb64-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="ceb64-107">當您安裝商務用 Skype Server 時，系統會為您建立單一、全域的 CDR 配置設定集合。</span><span class="sxs-lookup"><span data-stu-id="ceb64-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="ceb64-108">系統管理員也可以選擇建立自訂的設定集合，以套用於個別網站。</span><span class="sxs-lookup"><span data-stu-id="ceb64-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="ceb64-109">根據設計，在網站範圍設定的設定會優先于在全域範圍設定的設定。</span><span class="sxs-lookup"><span data-stu-id="ceb64-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="ceb64-110">如果您刪除網站範圍的設定，則會使用通用設定在該網站中管理 CDR。</span><span class="sxs-lookup"><span data-stu-id="ceb64-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="ceb64-111">請注意，您也可以「刪除」全域設定。</span><span class="sxs-lookup"><span data-stu-id="ceb64-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="ceb64-112">不過，全域設定實際上不會被移除。</span><span class="sxs-lookup"><span data-stu-id="ceb64-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="ceb64-113">相反地，該集合中的所有屬性都會重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="ceb64-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="ceb64-114">例如，預設會在 CDR 設定設定的集合中啟用清除。</span><span class="sxs-lookup"><span data-stu-id="ceb64-114">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="ceb64-115">假設您修改全域集合以停用清除。</span><span class="sxs-lookup"><span data-stu-id="ceb64-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="ceb64-116">如果您稍後刪除全域設定，所有屬性都會重設為其預設值。</span><span class="sxs-lookup"><span data-stu-id="ceb64-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="ceb64-117">在此情況下，這表示會再次啟用清除。</span><span class="sxs-lookup"><span data-stu-id="ceb64-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="ceb64-118">您可以使用商務用 Skype Server 控制台或 [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) Cmdlet 來移除 CDR 設定設定。</span><span class="sxs-lookup"><span data-stu-id="ceb64-118">You can remove CDR configuration settings by using the Skype for Business Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="ceb64-119">使用商務用 Skype Server 控制台移除 CDR 設定設定</span><span class="sxs-lookup"><span data-stu-id="ceb64-119">To remove CDR configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ceb64-120">在商務用 Skype Server 控制台中，按一下 [ **監控和** 封存]。</span><span class="sxs-lookup"><span data-stu-id="ceb64-120">In Skype for Business Server Control Panel, click **Monitoring and Archiving**.</span></span> 
    
2. <span data-ttu-id="ceb64-121">在 [ **詳細通話記錄** ] 索引標籤上，選取要移除之 CDR 設定的集合 (或集合) 。</span><span class="sxs-lookup"><span data-stu-id="ceb64-121">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed.</span></span> <span data-ttu-id="ceb64-122">若要選取多個集合，請按一下第一個集合，按住 Ctrl 鍵，然後按一下 [其他集合]。</span><span class="sxs-lookup"><span data-stu-id="ceb64-122">To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>
    
3. <span data-ttu-id="ceb64-123">按一下 [ **編輯**]，然後按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="ceb64-123">Click **Edit**, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="ceb64-124">在 [商務用 Skype Server 控制台] 對話方塊中，按一下 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="ceb64-124">In the Skype for Business Server Control Panel dialog box, click **OK**.</span></span>
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ceb64-125">使用 Windows PowerShell Cmdlet 移除 CDR 設定設定</span><span class="sxs-lookup"><span data-stu-id="ceb64-125">Removing CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ceb64-126">您可以使用 Windows PowerShell 和 **Remove-CsCdrConfiguration** Cmdlet 來刪除詳細通話記錄設定設定。</span><span class="sxs-lookup"><span data-stu-id="ceb64-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="ceb64-127">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ceb64-127">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ceb64-128">如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="ceb64-128">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="ceb64-129">商務用 Skype Server 中的程式相同。</span><span class="sxs-lookup"><span data-stu-id="ceb64-129">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="ceb64-130">移除指定的 CDR 配置設定集合</span><span class="sxs-lookup"><span data-stu-id="ceb64-130">To remove a specified collection of CDR configuration settings</span></span>

 <span data-ttu-id="ceb64-131">此命令會移除套用至 Redmond 網站的 CDR 設定設定：</span><span class="sxs-lookup"><span data-stu-id="ceb64-131">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="ceb64-132">移除所有套用至網站範圍的 CDR 設定設定</span><span class="sxs-lookup"><span data-stu-id="ceb64-132">To remove all the CDR configuration settings applied to the site scope</span></span>

 <span data-ttu-id="ceb64-133">此命令會移除所有套用至網站範圍的 CDR 設定設定：</span><span class="sxs-lookup"><span data-stu-id="ceb64-133">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

<span data-ttu-id="ceb64-134">如需詳細資訊，請參閱 [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="ceb64-134">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ceb64-135">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ceb64-135">See also</span></span>

[<span data-ttu-id="ceb64-136">在商務用 Skype Server 中手動清除詳細通話記錄與經驗品質資料庫</span><span class="sxs-lookup"><span data-stu-id="ceb64-136">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

