---
title: 在商務用 Skype Server 中建立新的封存原則
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
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 摘要：瞭解如何為商務用 Skype Server 建立新的封存原則。
ms.openlocfilehash: 3e1f538aba26025f5868a09babd3b67df36f9a3f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817643"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="8749e-103">在商務用 Skype Server 中建立新的封存原則</span><span class="sxs-lookup"><span data-stu-id="8749e-103">Create a new archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="8749e-104">**摘要：** 瞭解如何為商務用 Skype Server 建立新的封存原則。</span><span class="sxs-lookup"><span data-stu-id="8749e-104">**Summary:** Learn how to create a new archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="8749e-105">您可以使用 [控制台] 或使用 Windows PowerShell Cmdlet 來建立新的封存原則。</span><span class="sxs-lookup"><span data-stu-id="8749e-105">You can create new archiving policies by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a><span data-ttu-id="8749e-106">使用控制台建立新的封存原則</span><span class="sxs-lookup"><span data-stu-id="8749e-106">Create a new archiving policy by using the Control Panel</span></span>

<span data-ttu-id="8749e-107">若要使用 [控制台] 建立新的封存原則：</span><span class="sxs-lookup"><span data-stu-id="8749e-107">To create a new archiving policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="8749e-108">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="8749e-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="8749e-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="8749e-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="8749e-110">在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。</span><span class="sxs-lookup"><span data-stu-id="8749e-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="8749e-111">按一下 **[新增]**，然後執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="8749e-111">Click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="8749e-112">若要建立網站層級的封存原則，請按一下 [ **網站原則**]，然後在 [ **選取網站**] 中，按一下要套用該原則的網站。</span><span class="sxs-lookup"><span data-stu-id="8749e-112">To create a site-level archiving policy, click **Site policy**, and then, in **Select a site**, click the site to which the policy is to be applied.</span></span>
    
   - <span data-ttu-id="8749e-113">若要建立使用者層級的封存原則，請按一下 **[使用者原則]**。</span><span class="sxs-lookup"><span data-stu-id="8749e-113">To create a user-level archiving policy, click **User policy**.</span></span>
    
5. <span data-ttu-id="8749e-114">在 **[新增封存原則]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8749e-114">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="8749e-115">在 **[名稱]** 中，指定新原則的名稱 (例如，externalContoso)。</span><span class="sxs-lookup"><span data-stu-id="8749e-115">In **Name**, specify a name for the new policy (for example, externalContoso).</span></span>
    
   - <span data-ttu-id="8749e-116">在 **[描述]** 中，提供該原則的相關詳細資料 (例如，Contoso 的外部使用者封存原則)。</span><span class="sxs-lookup"><span data-stu-id="8749e-116">In **Description**, provide details about what the policy is (for example, External user archiving policy for Contoso).</span></span>
    
   - <span data-ttu-id="8749e-117">若要控制對與內部使用者通訊所進行的封存，請選取或清除 **[封存內部通訊]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8749e-117">To control archiving of communications with internal users, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="8749e-118">若要控制對與外部使用者通訊所進行的封存，請選取或清除 **[封存外部通訊]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8749e-118">To control archiving of communications with external users, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="8749e-119">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="8749e-119">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8749e-120">使用者原則的設定僅能套用至您套用該原則的特定使用者和使用者群組。</span><span class="sxs-lookup"><span data-stu-id="8749e-120">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="8749e-121">如需詳細資訊，請參閱 [將封存原則套用至商務用 Skype Server 中的使用者](apply-a-policy-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="8749e-121">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a><span data-ttu-id="8749e-122">使用 Windows PowerShell 建立新的封存原則</span><span class="sxs-lookup"><span data-stu-id="8749e-122">Create a new archiving policy by using Windows PowerShell</span></span>

<span data-ttu-id="8749e-123">您也可以使用 Windows PowerShell **New-CsArchivingPolicy** Cmdlet 來建立新的封存原則。</span><span class="sxs-lookup"><span data-stu-id="8749e-123">You can also create new archiving policies by using the Windows PowerShell **New-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="8749e-124">如需詳細資訊，請參閱 [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="8749e-124">For more information, see the help topic for the [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a><span data-ttu-id="8749e-125">在網站層級建立新的封存原則</span><span class="sxs-lookup"><span data-stu-id="8749e-125">To create a new archiving policy at the site level</span></span>

<span data-ttu-id="8749e-126">此命令可以建立 Redmond 網站的新封存原則：</span><span class="sxs-lookup"><span data-stu-id="8749e-126">This command creates a new archiving policy for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a><span data-ttu-id="8749e-127">在每個使用者層級建立新的封存原則</span><span class="sxs-lookup"><span data-stu-id="8749e-127">To create a new archiving policy at the per-user level</span></span>

<span data-ttu-id="8749e-128">若要在每個使用者層級建立新的封存原則，只需在建立原則時指定唯一的身分識別：</span><span class="sxs-lookup"><span data-stu-id="8749e-128">To create a new archiving policy at the per-user level, simply specify a unique Identity when creating the policy:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a><span data-ttu-id="8749e-129">若要建立新的封存原則以啟用內部通訊會話的封存</span><span class="sxs-lookup"><span data-stu-id="8749e-129">To create a new archiving policy that enables archiving of internal communication sessions</span></span>

<span data-ttu-id="8749e-130">由於未在前述命令中指定任何參數 (除了必要的 Identity  參數以外)，因此新原則將針對它們的所有屬性使用預設值。</span><span class="sxs-lookup"><span data-stu-id="8749e-130">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding commands, the new policies will use the default values for all their properties.</span></span> <span data-ttu-id="8749e-131">若要建立使用不同屬性值的原則，只需包含適當的參數和參數值。</span><span class="sxs-lookup"><span data-stu-id="8749e-131">To create policies that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="8749e-132">例如，下列命令會建立允許封存內部立即訊息會話的封存原則：</span><span class="sxs-lookup"><span data-stu-id="8749e-132">For example, the following command creates an archiving policy that permits archiving of internal instant messaging sessions:</span></span> 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a><span data-ttu-id="8749e-133">若要建立新的封存原則以啟用內部和外部通訊會話的封存</span><span class="sxs-lookup"><span data-stu-id="8749e-133">To create a new archiving policy that enables archiving of both internal and external communication sessions</span></span>

<span data-ttu-id="8749e-134">多項屬性值可透過加入多個參數加以修改。</span><span class="sxs-lookup"><span data-stu-id="8749e-134">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="8749e-135">例如，此命令會設定新原則，以封存內部及外部立即訊息會話：</span><span class="sxs-lookup"><span data-stu-id="8749e-135">For example, this command configures the new policy to archive both internal and external instant messaging sessions:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```
