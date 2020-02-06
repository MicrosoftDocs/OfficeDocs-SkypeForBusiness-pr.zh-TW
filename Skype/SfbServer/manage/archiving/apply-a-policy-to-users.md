---
title: 將存檔原則套用到商務用 Skype Server 中的使用者
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
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 摘要：瞭解如何將存檔原則指派給商務用 Skype Server 中的使用者。
ms.openlocfilehash: 7be62aaf5b2b70108cb67a36559b242377d26117
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819005"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="4360d-103">將存檔原則套用到商務用 Skype Server 中的使用者</span><span class="sxs-lookup"><span data-stu-id="4360d-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="4360d-104">**摘要：** 瞭解如何將存檔原則指派給商務用 Skype Server 中的使用者。</span><span class="sxs-lookup"><span data-stu-id="4360d-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="4360d-105">如果您已經針對駐留在商務用 Skype Server 上的使用者建立一或多個使用者原則，您可以將適當的原則套用至這些使用者或使用者群組，以實現特定使用者的歸檔支援。</span><span class="sxs-lookup"><span data-stu-id="4360d-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="4360d-106">例如，如果您建立的原則支援內部通訊的歸檔，您可以將它套用至至少一個使用者或使用者群組，以支援使用者的商務用 Skype 伺服器通訊。</span><span class="sxs-lookup"><span data-stu-id="4360d-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4360d-107">如果您已針對您的部署啟用 Microsoft Exchange 整合，Exchange 就地保留原則會控制是否針對託管于 Exchange 的使用者啟用封存，並將其信箱放在就地保留中。</span><span class="sxs-lookup"><span data-stu-id="4360d-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="4360d-108">如需詳細資訊，請參閱[在商務用 Skype server 中進行](../../plan-your-deployment/archiving/archiving.md)封存的規劃，以及[設定與商務用 Skype server 的 Exchange 儲存體整合](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="4360d-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="4360d-109">使用 [控制台] 套用使用者原則</span><span class="sxs-lookup"><span data-stu-id="4360d-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="4360d-110">若要使用 [控制] 面板來套用使用者原則：</span><span class="sxs-lookup"><span data-stu-id="4360d-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="4360d-111">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="4360d-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="4360d-112">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="4360d-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="4360d-113">在左側導覽列中，按一下 [**使用者**]，然後搜尋您要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="4360d-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="4360d-114">在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]\*\*\*\* 及 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4360d-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="4360d-115">在 [**存檔原則**] 下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的存檔使用者原則。</span><span class="sxs-lookup"><span data-stu-id="4360d-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4360d-116">[ \*\* \<自動\> \*\*設定] 會套用預設伺服器安裝設定。</span><span class="sxs-lookup"><span data-stu-id="4360d-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="4360d-117">伺服器會自動套用這些設定。</span><span class="sxs-lookup"><span data-stu-id="4360d-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="4360d-118">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4360d-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="4360d-119">使用 Windows PowerShell 套用使用者原則</span><span class="sxs-lookup"><span data-stu-id="4360d-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="4360d-120">您也可以使用 Windows PowerShell**授與 CsArchivingPolicy** Cmdlet 來套用使用者原則。</span><span class="sxs-lookup"><span data-stu-id="4360d-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="4360d-121">下列命令會將每個使用者的存檔原則 RedmondArchivingPolicy 指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="4360d-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="4360d-122">這個命令會將每個使用者的存檔原則 RedmondArchivingPolicy 指派給擁有 [註冊機] 池 atl-cs-001.contoso.com 之帳戶的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="4360d-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="4360d-123">如需此命令中使用之篩選參數的詳細資訊，請參閱[move-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) Cmdlet 檔。</span><span class="sxs-lookup"><span data-stu-id="4360d-123">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="4360d-124">下列命令會移除先前指派給 Ken Myer 的任何每使用者存檔原則。</span><span class="sxs-lookup"><span data-stu-id="4360d-124">The following command removes any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="4360d-125">移除每個使用者原則之後，就會使用全域原則（如果有的話）自動管理 Ken Myer，或使用其本機網站原則。</span><span class="sxs-lookup"><span data-stu-id="4360d-125">After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="4360d-126">網站原則的優先順序高於全域原則。</span><span class="sxs-lookup"><span data-stu-id="4360d-126">A site policy takes precedence over the global policy.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="4360d-127">如需詳細資訊，請參閱[Grant CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) Cmdlet 檔。</span><span class="sxs-lookup"><span data-stu-id="4360d-127">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  

