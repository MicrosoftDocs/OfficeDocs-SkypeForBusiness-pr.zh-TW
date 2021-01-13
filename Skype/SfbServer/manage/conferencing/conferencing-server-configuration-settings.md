---
title: 在商務用 Skype Server 中管理會議服務器設定設定
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
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 摘要：瞭解如何在商務用 Skype Server 中管理會議服務器設定設定。
ms.openlocfilehash: 7f8714a4098285e955b559b2baf70d74957159a1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828283"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="0f21b-103">在商務用 Skype Server 中管理會議服務器設定設定</span><span class="sxs-lookup"><span data-stu-id="0f21b-103">Manage conferencing server configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="0f21b-104">**摘要：** 瞭解如何在商務用 Skype Server 中管理會議服務器設定設定。</span><span class="sxs-lookup"><span data-stu-id="0f21b-104">**Summary:** Learn how to manage conferencing server configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="0f21b-105">本主題說明如何管理會議配置設定。</span><span class="sxs-lookup"><span data-stu-id="0f21b-105">This topic describes how to manage conferencing configuration settings.</span></span> <span data-ttu-id="0f21b-106">如需如何規劃及部署會議的詳細資訊，請參閱在商務用 skype server 中 [規劃會議](../../plan-your-deployment/conferencing/conferencing.md) ，以及 [在商務用 Skype server 中部署會議](../../deploy/deploy-conferencing/deploy-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="0f21b-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="0f21b-107">會議配置設定會決定會議內容和講義的允許大小上限等專案;應用程式共用會議服務的最大頻寬量;儲存量限制和到期期限;支援之用戶端的內部及外部下載的 URLs;指向內部和外部 URLs 的指標，使用者可以在其中取得會議説明和資源;以及用來進行應用程式共用、用戶端音訊、檔案傳輸和媒體流量的埠。</span><span class="sxs-lookup"><span data-stu-id="0f21b-107">Conferencing configuration settings determine such things as the maximum allowed size for meeting content and handouts; maximum amount of bandwidth for the Application Sharing Conferencing service; storage limits and expiration periods; the URLs for the internal and external downloads of the supported client; pointers to internal and external URLs where users can obtain conferencing help and resources; and the ports used for application sharing, client audio, file transfers, and media traffic.</span></span> <span data-ttu-id="0f21b-108">這些設定可讓您自行管理實際的伺服器。</span><span class="sxs-lookup"><span data-stu-id="0f21b-108">These settings allow you to manage the actual servers themselves.</span></span> <span data-ttu-id="0f21b-109">您可以使用商務用 Skype Server 管理命令介面來設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="0f21b-109">These settings can be set by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="0f21b-110">當您安裝商務用 Skype Server 時，系統會在全域集合) 中，為您提供單一會議配置設定的集合 (。</span><span class="sxs-lookup"><span data-stu-id="0f21b-110">When you install Skype for Business Server, the system provides you with a single collection of conferencing configuration settings (the global collection).</span></span> <span data-ttu-id="0f21b-111">如果您需要為網站或服務建立自訂設定，您可以使用 **New-CsConferencingConfiguration** Cmdlet 來執行。</span><span class="sxs-lookup"><span data-stu-id="0f21b-111">If you need to create custom settings for a site or service, you can do so using the **New-CsConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="0f21b-112">請注意，新設定只能在網站或服務範圍上套用;您無法建立新的會議設定全域集合，但您可以使用 **Set-CsConferencingConfiguration** Cmdlet 修改全域集合。</span><span class="sxs-lookup"><span data-stu-id="0f21b-112">Note that new settings can be applied only at the site or service scope; you cannot create a new global collection of conferencing configuration settings, but you can modify the global collection by using the **Set-CsConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="0f21b-113">此外，任何網站或服務都不能裝載多個設定集合。</span><span class="sxs-lookup"><span data-stu-id="0f21b-113">In addition, no site or service can host more than one collection of settings.</span></span> <span data-ttu-id="0f21b-114">如果您嘗試為 Redmond 網站建立新的設定，而 Redmond 網站已裝載會議設定的集合，則此命令會失敗。</span><span class="sxs-lookup"><span data-stu-id="0f21b-114">If you try to create new settings for the Redmond site and the Redmond site already hosts a collection of conferencing configuration settings, then your command will fail.</span></span>
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0f21b-115">使用商務用 Skype Server 管理命令介面來管理會議配置設定</span><span class="sxs-lookup"><span data-stu-id="0f21b-115">Manage conferencing configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="0f21b-116">若要使用商務用 Skype Server 管理命令介面來管理會議配置設定，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0f21b-116">To manage conferencing configuration settings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="0f21b-117">**會議配置設定**</span><span class="sxs-lookup"><span data-stu-id="0f21b-117">**Conferencing configuration settings**</span></span>

|<span data-ttu-id="0f21b-118">**指令程式**</span><span class="sxs-lookup"><span data-stu-id="0f21b-118">**Cmdlet**</span></span>|<span data-ttu-id="0f21b-119">**描述**</span><span class="sxs-lookup"><span data-stu-id="0f21b-119">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="0f21b-120">Get-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0f21b-120">Get-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="0f21b-121">傳回組織的會議設定設定資訊。</span><span class="sxs-lookup"><span data-stu-id="0f21b-121">Returns information about the conferencing configuration settings for your organization.</span></span>  <br/> |
|[<span data-ttu-id="0f21b-122">New-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0f21b-122">New-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="0f21b-123">會建立新的會議配置設定集合。</span><span class="sxs-lookup"><span data-stu-id="0f21b-123">Creates a new collection of conferencing configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="0f21b-124">Remove-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0f21b-124">Remove-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="0f21b-125">移除指定的會議配置設定集合。</span><span class="sxs-lookup"><span data-stu-id="0f21b-125">Removes the specified collection of conferencing configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="0f21b-126">Set-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0f21b-126">Set-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="0f21b-127">修改現有會議配置設定的集合。</span><span class="sxs-lookup"><span data-stu-id="0f21b-127">Modifies an existing collection of conferencing configuration settings.</span></span>  <br/> |
   
<span data-ttu-id="0f21b-128">下列命令會為 Redmond 網站 (site： Redmond) 建立新的會議配置設定集合。</span><span class="sxs-lookup"><span data-stu-id="0f21b-128">The following command creates a new collection of conferencing configuration settings for the Redmond site (site:Redmond).</span></span> <span data-ttu-id="0f21b-129">在此範例中，會包含另一個參數 (組織) 用以將組織屬性值設定為 Litwareinc：</span><span class="sxs-lookup"><span data-stu-id="0f21b-129">In this example, one additional parameter is included (Organization) which is used to set the value of the Organization property to Litwareinc:</span></span> 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

<span data-ttu-id="0f21b-130">請注意，每個網站只能有一個這類集合，所以如果 Redmond 網站已具備會議設定的集合，則此命令會失敗。</span><span class="sxs-lookup"><span data-stu-id="0f21b-130">Note that you can have only one such collection per site, so this command would fail if the Redmond site already has a collection of conferencing configuration settings.</span></span> 
  
<span data-ttu-id="0f21b-131">下一個範例會定義新的會議設定的集合，這些設定會在最初儲存于記憶體中，然後再套用至 Redmond 網站。</span><span class="sxs-lookup"><span data-stu-id="0f21b-131">The next example defines a new collection of conferencing configuration settings, which are stored in memory initially, and then applied to the Redmond site at a later time.</span></span> 
  
<span data-ttu-id="0f21b-132">第一個命令會使用 **New-CsConferencingConfiguration** 指令程式，來建立新的記憶體集合，這些設定會儲存在變數 $x 中。</span><span class="sxs-lookup"><span data-stu-id="0f21b-132">The first command uses the **New-CsConferencingConfiguration** cmdlet to create a new, in-memory collection of settings stored in the variable $x.</span></span> <span data-ttu-id="0f21b-133">InMemory 參數會指定應該在記憶體中建立集合，而不會立即套用至 Redmond 網站。</span><span class="sxs-lookup"><span data-stu-id="0f21b-133">The InMemory parameter specifies that the collection should be created in memory rather than immediately applied to the Redmond site.</span></span>
  
<span data-ttu-id="0f21b-134">建立集合之後，第二個命令會將組織關係屬性的值設定為 Litwareinc。</span><span class="sxs-lookup"><span data-stu-id="0f21b-134">After the collection has been created, the second command sets the value of the Organization property to Litwareinc.</span></span> 
  
<span data-ttu-id="0f21b-135">最後，第三個命令會使用 **Set-CsConferencingConfiguration** Cmdlet，以實際將新設定套用至 Redmond 網站：</span><span class="sxs-lookup"><span data-stu-id="0f21b-135">Finally, the third command uses the **Set-CsConferencingConfiguration** cmdlet to actually apply the new settings to the Redmond site:</span></span>
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

<span data-ttu-id="0f21b-136">如果您未呼叫 **Set-CsConferencingConfiguration** Cmdlet，新設定永遠不會生效。</span><span class="sxs-lookup"><span data-stu-id="0f21b-136">If you do not call the **Set-CsConferencingConfiguration** cmdlet, the new settings will never take effect.</span></span> <span data-ttu-id="0f21b-137">相反地，當您結束 Windows PowerShell 會話或刪除變數 $x 時，它們會立即消失。</span><span class="sxs-lookup"><span data-stu-id="0f21b-137">Instead, they will disappear as soon as you end your Windows PowerShell session or delete the variable $x.</span></span>
  

