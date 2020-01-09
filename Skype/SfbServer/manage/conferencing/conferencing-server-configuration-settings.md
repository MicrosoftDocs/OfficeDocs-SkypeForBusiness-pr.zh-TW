---
title: 在商務用 Skype Server 中管理會議服務器配置設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 摘要：瞭解如何在商務用 Skype Server 中管理會議服務器配置設定。
ms.openlocfilehash: be6ccb094cc19a29534d1ca78eb2cae1457d6512
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991898"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="3e013-103">在商務用 Skype Server 中管理會議服務器配置設定</span><span class="sxs-lookup"><span data-stu-id="3e013-103">Manage conferencing server configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="3e013-104">**摘要：** 瞭解如何在商務用 Skype Server 中管理會議服務器配置設定。</span><span class="sxs-lookup"><span data-stu-id="3e013-104">**Summary:** Learn how to manage conferencing server configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="3e013-105">本主題說明如何管理會議配置設定。</span><span class="sxs-lookup"><span data-stu-id="3e013-105">This topic describes how to manage conferencing configuration settings.</span></span> <span data-ttu-id="3e013-106">如需如何規劃及部署會議的詳細資訊，請參閱[在商務用 Skype server 中規劃會議](../../plan-your-deployment/conferencing/conferencing.md)，以及[在商務用 Skype 伺服器中部署會議](../../deploy/deploy-conferencing/deploy-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="3e013-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="3e013-107">會議設定設定會決定會議內容和講義的允許大小上限等專案，應用程式共用會議服務的頻寬最大使用量;儲存空間限制與到期期;受支援之用戶端內部和外部下載的 Url;使用者可取得會議說明和資源之內部和外部 Url 的指標;以及用於應用程式共用、用戶端音訊、檔案傳輸及媒體流量的埠。</span><span class="sxs-lookup"><span data-stu-id="3e013-107">Conferencing configuration settings determine such things as the maximum allowed size for meeting content and handouts; maximum amount of bandwidth for the Application Sharing Conferencing service; storage limits and expiration periods; the URLs for the internal and external downloads of the supported client; pointers to internal and external URLs where users can obtain conferencing help and resources; and the ports used for application sharing, client audio, file transfers, and media traffic.</span></span> <span data-ttu-id="3e013-108">這些設定可讓您管理實際的伺服器本身。</span><span class="sxs-lookup"><span data-stu-id="3e013-108">These settings allow you to manage the actual servers themselves.</span></span> <span data-ttu-id="3e013-109">您可以使用商務用 Skype Server Management Shell 來設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="3e013-109">These settings can be set by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="3e013-110">當您安裝商務用 Skype Server 時，系統會為您提供單一的會議配置設定集合（全域集合）。</span><span class="sxs-lookup"><span data-stu-id="3e013-110">When you install Skype for Business Server, the system provides you with a single collection of conferencing configuration settings (the global collection).</span></span> <span data-ttu-id="3e013-111">如果您需要建立網站或服務的自訂設定，您可以使用**CsConferencingConfiguration** Cmdlet 來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="3e013-111">If you need to create custom settings for a site or service, you can do so using the **New-CsConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="3e013-112">請注意，新設定只能在網站或服務範圍內套用;您無法建立新的會議設定全域集合，但您可以使用**CsConferencingConfiguration** Cmdlet 來修改全域集合。</span><span class="sxs-lookup"><span data-stu-id="3e013-112">Note that new settings can be applied only at the site or service scope; you cannot create a new global collection of conferencing configuration settings, but you can modify the global collection by using the **Set-CsConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="3e013-113">此外，任何網站或服務都不能裝載一個以上的設定集合。</span><span class="sxs-lookup"><span data-stu-id="3e013-113">In addition, no site or service can host more than one collection of settings.</span></span> <span data-ttu-id="3e013-114">如果您嘗試為雷德蒙的網站建立新的設定，而雷德蒙的網站已經託管會議設定的集合，則您的命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="3e013-114">If you try to create new settings for the Redmond site and the Redmond site already hosts a collection of conferencing configuration settings, then your command will fail.</span></span>
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="3e013-115">使用商務用 Skype Server Management Shell 管理會議配置設定</span><span class="sxs-lookup"><span data-stu-id="3e013-115">Manage conferencing configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="3e013-116">若要使用商務用 Skype Server Management Shell 管理會議配置設定，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3e013-116">To manage conferencing configuration settings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="3e013-117">**會議配置設定**</span><span class="sxs-lookup"><span data-stu-id="3e013-117">**Conferencing configuration settings**</span></span>

|<span data-ttu-id="3e013-118">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="3e013-118">**Cmdlet**</span></span>|<span data-ttu-id="3e013-119">**描述**</span><span class="sxs-lookup"><span data-stu-id="3e013-119">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="3e013-120">CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3e013-120">Get-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="3e013-121">傳回貴組織會議配置設定的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="3e013-121">Returns information about the conferencing configuration settings for your organization.</span></span>  <br/> |
|[<span data-ttu-id="3e013-122">New-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3e013-122">New-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="3e013-123">建立新的會議配置設定集合。</span><span class="sxs-lookup"><span data-stu-id="3e013-123">Creates a new collection of conferencing configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="3e013-124">移除-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3e013-124">Remove-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="3e013-125">移除指定的會議配置設定集合。</span><span class="sxs-lookup"><span data-stu-id="3e013-125">Removes the specified collection of conferencing configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="3e013-126">Set-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3e013-126">Set-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="3e013-127">修改現有的會議配置設定集合。</span><span class="sxs-lookup"><span data-stu-id="3e013-127">Modifies an existing collection of conferencing configuration settings.</span></span>  <br/> |
   
<span data-ttu-id="3e013-128">下列命令會針對雷德蒙網站（網站：雷蒙德）建立新的會議配置設定集合。</span><span class="sxs-lookup"><span data-stu-id="3e013-128">The following command creates a new collection of conferencing configuration settings for the Redmond site (site:Redmond).</span></span> <span data-ttu-id="3e013-129">在這個範例中，包含一個額外的參數（組織），用來將組織屬性的值設定為 Litwareinc：</span><span class="sxs-lookup"><span data-stu-id="3e013-129">In this example, one additional parameter is included (Organization) which is used to set the value of the Organization property to Litwareinc:</span></span> 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

<span data-ttu-id="3e013-130">請注意，每個網站只能有一個此類集合，所以如果雷德蒙者網站已有會議設定的集合，此命令就會失敗。</span><span class="sxs-lookup"><span data-stu-id="3e013-130">Note that you can have only one such collection per site, so this command would fail if the Redmond site already has a collection of conferencing configuration settings.</span></span> 
  
<span data-ttu-id="3e013-131">下一個範例定義了新的會議配置設定集合，這些設定會先儲存在記憶體中，然後再套用到雷德蒙網站。</span><span class="sxs-lookup"><span data-stu-id="3e013-131">The next example defines a new collection of conferencing configuration settings, which are stored in memory initially, and then applied to the Redmond site at a later time.</span></span> 
  
<span data-ttu-id="3e013-132">第一個命令使用**CsConferencingConfiguration** Cmdlet 來建立一個新的記憶體內集合，這些設定會儲存在變數 $x 中。</span><span class="sxs-lookup"><span data-stu-id="3e013-132">The first command uses the **New-CsConferencingConfiguration** cmdlet to create a new, in-memory collection of settings stored in the variable $x.</span></span> <span data-ttu-id="3e013-133">InMemory 參數指定應該在記憶體中建立集合，而不會立即套用到雷德蒙的網站。</span><span class="sxs-lookup"><span data-stu-id="3e013-133">The InMemory parameter specifies that the collection should be created in memory rather than immediately applied to the Redmond site.</span></span>
  
<span data-ttu-id="3e013-134">建立集合之後，第二個命令會將 [組織] 屬性的值設定為 [Litwareinc]。</span><span class="sxs-lookup"><span data-stu-id="3e013-134">After the collection has been created, the second command sets the value of the Organization property to Litwareinc.</span></span> 
  
<span data-ttu-id="3e013-135">最後，第三個命令使用**CsConferencingConfiguration** Cmdlet，以實際將新設定套用至雷德蒙網站：</span><span class="sxs-lookup"><span data-stu-id="3e013-135">Finally, the third command uses the **Set-CsConferencingConfiguration** cmdlet to actually apply the new settings to the Redmond site:</span></span>
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

<span data-ttu-id="3e013-136">如果您沒有呼叫**CsConferencingConfiguration** Cmdlet，新設定就不會生效。</span><span class="sxs-lookup"><span data-stu-id="3e013-136">If you do not call the **Set-CsConferencingConfiguration** cmdlet, the new settings will never take effect.</span></span> <span data-ttu-id="3e013-137">相反地，當您結束 Windows PowerShell 會話或刪除變數 $x，它們就會消失。</span><span class="sxs-lookup"><span data-stu-id="3e013-137">Instead, they will disappear as soon as you end your Windows PowerShell session or delete the variable $x.</span></span>
  

