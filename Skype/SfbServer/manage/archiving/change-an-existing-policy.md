---
title: 在商務用 Skype Server 中變更現有的封存原則
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
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 摘要：瞭解如何變更適用于商務用 Skype Server 的使用者封存原則。
ms.openlocfilehash: 47c9d5938c22b93db48c96265831cbf24ecc24d7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817703"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="5b072-103">在商務用 Skype Server 中變更現有的封存原則</span><span class="sxs-lookup"><span data-stu-id="5b072-103">Change an existing archiving policy in Skype for Business Server</span></span>
 
<span data-ttu-id="5b072-104">**摘要：** 瞭解如何變更使用者封存原則，以供商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="5b072-104">**Summary:** Learn how to change user archiving policies for Skype for Business Server.</span></span>
  
<span data-ttu-id="5b072-105">當您第一次部署商務用 Skype Server 時，您會設定初始封存原則，以決定如何對部署中的使用者執行封存。</span><span class="sxs-lookup"><span data-stu-id="5b072-105">When you first deploy Skype for Business Server, you set up initial archiving policies that determine how archiving is implemented for the users in your deployment.</span></span> <span data-ttu-id="5b072-106">本主題說明如何管理和修正原則。</span><span class="sxs-lookup"><span data-stu-id="5b072-106">This topic describes how to manage and amend policies.</span></span> 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="5b072-107">使用控制台變更封存原則</span><span class="sxs-lookup"><span data-stu-id="5b072-107">Change archiving policies by using the Control Panel</span></span>

1. <span data-ttu-id="5b072-108">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="5b072-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="5b072-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="5b072-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="5b072-110">在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。</span><span class="sxs-lookup"><span data-stu-id="5b072-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="5b072-111">在原則清單中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="5b072-111">In the list of policies, do one of the following:</span></span> 
    
   - <span data-ttu-id="5b072-112">若要變更整個部署的原則，請按一下原則清單中的 [ **全域** ]，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="5b072-112">To change the policy for your entire deployment, click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="5b072-113">若要變更單一網站的原則，請按一下原則清單中的網站名稱，再按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="5b072-113">To change the policy for a single site, click the site name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="5b072-114">若要變更單一使用者或使用者群組的原則，請按一下原則清單中的使用者或使用者群組名稱，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="5b072-114">To change the policy for a single user or user group, click the user or user group name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="5b072-115">在 [ **編輯封存原則** ] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="5b072-115">On the **Edit Archiving Policy** page, do the following:</span></span>
    
   - <span data-ttu-id="5b072-116">若要啟用或停用原則的內部封存，請選取或清除 [封存 **內部通訊** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5b072-116">To enable or disable internal archiving for the policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="5b072-117">若要啟用或停用原則的外部封存，請選取或清除 [封存 **外部通訊** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5b072-117">To enable or disable external archiving for the policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="5b072-118">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="5b072-118">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5b072-119">使用者原則的設定僅能套用至您套用該原則的特定使用者和使用者群組。</span><span class="sxs-lookup"><span data-stu-id="5b072-119">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="5b072-120">如需詳細資訊，請參閱 [將封存原則套用至商務用 Skype Server 中的使用者](apply-a-policy-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="5b072-120">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="5b072-121">使用 Windows PowerShell 變更封存原則</span><span class="sxs-lookup"><span data-stu-id="5b072-121">Change archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="5b072-122">您也可以使用 Windows PowerShell **Set-CsArchivingPolicy** Cmdlet 變更封存原則。</span><span class="sxs-lookup"><span data-stu-id="5b072-122">You can also change archiving policies by using the Windows PowerShell **Set-CsArchivingPolicy** cmdlet.</span></span>
  
### <a name="enable-archiving-policies"></a><span data-ttu-id="5b072-123">啟用封存原則</span><span class="sxs-lookup"><span data-stu-id="5b072-123">Enable archiving policies</span></span>

<span data-ttu-id="5b072-124">若要啟用內部通訊會話的封存，請將 ArchiveInternal 參數的值設為 True ($True) ：</span><span class="sxs-lookup"><span data-stu-id="5b072-124">To enable the archiving of internal communication sessions, set the value of the ArchiveInternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

<span data-ttu-id="5b072-125">若要啟用外部通訊會話的封存，請將 ArchiveExternal 參數的值設為 True ($True) ：</span><span class="sxs-lookup"><span data-stu-id="5b072-125">To enable the archiving of external communication sessions, set the value of the ArchiveExternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

<span data-ttu-id="5b072-126">若要同時啟用內部和外部通訊會話的封存，請將 ArchiveInternal 和 ArchiveExternal 參數的值設為 True：</span><span class="sxs-lookup"><span data-stu-id="5b072-126">To enable the archiving of both internal and external communication sessions, set the value of both the ArchiveInternal and ArchiveExternal parameters to True:</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a><span data-ttu-id="5b072-127">停用封存原則</span><span class="sxs-lookup"><span data-stu-id="5b072-127">Disable archiving policies</span></span>

<span data-ttu-id="5b072-128">若要完全停用封存，請將 ArchiveInternal 和 ArchiveExternal 參數的值設為 False， ($False) ：</span><span class="sxs-lookup"><span data-stu-id="5b072-128">To disable archiving altogether, set the value of both the ArchiveInternal and ArchiveExternal parameters to False ($False):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
