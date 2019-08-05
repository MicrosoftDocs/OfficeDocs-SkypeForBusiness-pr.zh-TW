---
title: 在商務用 Skype Server 中變更現有的存檔原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: '摘要: 瞭解如何變更商務用 Skype Server 的使用者歸檔原則。'
ms.openlocfilehash: 4a3da0bfe403d1a00807865cd07762111b59b540
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189346"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="71679-103">在商務用 Skype Server 中變更現有的存檔原則</span><span class="sxs-lookup"><span data-stu-id="71679-103">Change an existing archiving policy in Skype for Business Server</span></span>
 
<span data-ttu-id="71679-104">**摘要:** 瞭解如何變更商務用 Skype Server 的使用者歸檔原則。</span><span class="sxs-lookup"><span data-stu-id="71679-104">**Summary:** Learn how to change user archiving policies for Skype for Business Server.</span></span>
  
<span data-ttu-id="71679-105">當您第一次部署商務用 Skype Server 時, 您會設定初始的存檔原則, 決定如何針對您的部署中的使用者執行封存。</span><span class="sxs-lookup"><span data-stu-id="71679-105">When you first deploy Skype for Business Server, you set up initial archiving policies that determine how archiving is implemented for the users in your deployment.</span></span> <span data-ttu-id="71679-106">本主題說明如何管理及修正原則。</span><span class="sxs-lookup"><span data-stu-id="71679-106">This topic describes how to manage and amend policies.</span></span> 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="71679-107">使用 [控制台] 變更存檔原則</span><span class="sxs-lookup"><span data-stu-id="71679-107">Change archiving policies by using the Control Panel</span></span>

1. <span data-ttu-id="71679-108">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="71679-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="71679-109">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="71679-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="71679-110">在左側導覽列中, 按一下 [**監視及**封存], 然後按一下 [封存**原則**]。</span><span class="sxs-lookup"><span data-stu-id="71679-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="71679-111">在原則清單中, 執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="71679-111">In the list of policies, do one of the following:</span></span> 
    
   - <span data-ttu-id="71679-112">若要變更整個部署的原則, 請在原則清單中按一下 [**全域**], 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="71679-112">To change the policy for your entire deployment, click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="71679-113">若要變更單一網站的原則, 請在原則清單中按一下該網站的名稱, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="71679-113">To change the policy for a single site, click the site name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="71679-114">若要變更單一使用者或使用者群組的原則, 請在原則清單中按一下 [使用者] 或 [使用者組名], 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="71679-114">To change the policy for a single user or user group, click the user or user group name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="71679-115">在 [**編輯存檔原則**] 頁面上, 執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="71679-115">On the **Edit Archiving Policy** page, do the following:</span></span>
    
   - <span data-ttu-id="71679-116">若要啟用或停用原則的內部存檔, 請選取或清除 [封存**內部通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="71679-116">To enable or disable internal archiving for the policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="71679-117">若要啟用或停用原則的外部封存, 請選取或清除 [封存**外部通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="71679-117">To enable or disable external archiving for the policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="71679-118">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="71679-118">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="71679-119">使用者原則的設定只會套用到您要套用原則的特定使用者和使用者群組。</span><span class="sxs-lookup"><span data-stu-id="71679-119">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="71679-120">如需詳細資訊, 請參閱[將存檔原則套用到商務用 Skype Server 中的使用者](apply-a-policy-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="71679-120">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="71679-121">使用 Windows PowerShell 變更存檔原則</span><span class="sxs-lookup"><span data-stu-id="71679-121">Change archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="71679-122">您也可以使用 Windows PowerShell **CsArchivingPolicy** Cmdlet 變更存檔原則。</span><span class="sxs-lookup"><span data-stu-id="71679-122">You can also change archiving policies by using the Windows PowerShell **Set-CsArchivingPolicy** cmdlet.</span></span>
  
### <a name="enable-archiving-policies"></a><span data-ttu-id="71679-123">啟用存檔原則</span><span class="sxs-lookup"><span data-stu-id="71679-123">Enable archiving policies</span></span>

<span data-ttu-id="71679-124">若要啟用內部通訊會話的歸檔, 請將 ArchiveInternal 參數的值設定為 True ($True):</span><span class="sxs-lookup"><span data-stu-id="71679-124">To enable the archiving of internal communication sessions, set the value of the ArchiveInternal parameter to True ($True):</span></span> 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

<span data-ttu-id="71679-125">若要啟用外部通訊會話的存檔, 請將 ArchiveExternal 參數的值設定為 True ($True):</span><span class="sxs-lookup"><span data-stu-id="71679-125">To enable the archiving of external communication sessions, set the value of the ArchiveExternal parameter to True ($True):</span></span> 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

<span data-ttu-id="71679-126">若要同時啟用內部和外部通訊會話的存檔, 請將 ArchiveInternal 和 ArchiveExternal 參數的值設定為 True:</span><span class="sxs-lookup"><span data-stu-id="71679-126">To enable the archiving of both internal and external communication sessions, set the value of both the ArchiveInternal and ArchiveExternal parameters to True:</span></span> 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a><span data-ttu-id="71679-127">停用封存原則</span><span class="sxs-lookup"><span data-stu-id="71679-127">Disable archiving policies</span></span>

<span data-ttu-id="71679-128">若要完全停用存檔, 請將 ArchiveInternal 和 ArchiveExternal 參數的值設為 False ($False):</span><span class="sxs-lookup"><span data-stu-id="71679-128">To disable archiving altogether, set the value of both the ArchiveInternal and ArchiveExternal parameters to False ($False):</span></span> 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
