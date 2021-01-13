---
title: 將封存原則套用至商務用 Skype Server 中的使用者
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
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 摘要：瞭解如何將封存原則指派給商務用 Skype Server 中的使用者。
ms.openlocfilehash: 8dc74fcc8befe39b424b89c77aebca683fe17586
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817763"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="ba6db-103">將封存原則套用至商務用 Skype Server 中的使用者</span><span class="sxs-lookup"><span data-stu-id="ba6db-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="ba6db-104">**摘要：** 瞭解如何在商務用 Skype Server 中將封存原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="ba6db-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="ba6db-105">如果您已為位於商務用 Skype Server 上的使用者建立一或多個使用者原則，您可以將適當的原則套用至那些使用者或使用者群組，以對特定使用者執行封存支援。</span><span class="sxs-lookup"><span data-stu-id="ba6db-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="ba6db-106">例如，如果您建立支援內部通訊封存的原則，您可以將它套用至至少一個使用者或使用者群組，以支援封存使用者的商務用 Skype 伺服器通訊。</span><span class="sxs-lookup"><span data-stu-id="ba6db-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ba6db-107">如果您已針對您的部署啟用 Microsoft Exchange 整合，Exchange In-Place 保留原則會控制是否為位於 Exchange 上的使用者啟用封存，並將其信箱置於 In-Place 保留狀態。</span><span class="sxs-lookup"><span data-stu-id="ba6db-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="ba6db-108">如需詳細資訊，請參閱 Plan for 封存 [In 商務用 Skype server](../../plan-your-deployment/archiving/archiving.md) 和 [設定與 Exchange storage 的整合（適用于商務用 skype 伺服器](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)）。</span><span class="sxs-lookup"><span data-stu-id="ba6db-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="ba6db-109">使用控制台套用使用者原則</span><span class="sxs-lookup"><span data-stu-id="ba6db-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="ba6db-110">若要使用 [控制台] 套用使用者原則：</span><span class="sxs-lookup"><span data-stu-id="ba6db-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="ba6db-111">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="ba6db-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="ba6db-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="ba6db-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="ba6db-113">在左導覽列中，按一下 **[使用者]**，然後搜尋想要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="ba6db-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="ba6db-114">在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="ba6db-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="ba6db-115">在 [封存 **原則**] 下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的封存使用者原則。</span><span class="sxs-lookup"><span data-stu-id="ba6db-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ba6db-116">**\<Automatic\>** 設定將套用預設伺服器安裝設定。</span><span class="sxs-lookup"><span data-stu-id="ba6db-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="ba6db-117">伺服器會自動套用這些設定。</span><span class="sxs-lookup"><span data-stu-id="ba6db-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="ba6db-118">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="ba6db-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="ba6db-119">使用 Windows PowerShell 套用使用者原則</span><span class="sxs-lookup"><span data-stu-id="ba6db-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="ba6db-120">您也可以使用 Windows PowerShell **Grant-CsArchivingPolicy** Cmdlet 來套用使用者原則。</span><span class="sxs-lookup"><span data-stu-id="ba6db-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="ba6db-121">下列命令將個別使用者封存原則 RedmondArchivingPolicy 指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="ba6db-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="ba6db-122">這個命令會將個別使用者的封存原則 RedmondArchivingPolicy 指派給所有具有位於註冊機構集區 atl-cs-001.contoso.com 之帳戶的使用者。</span><span class="sxs-lookup"><span data-stu-id="ba6db-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="ba6db-123">如需此命令中使用之 Filter 參數的詳細資訊，請參閱 [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) Cmdlet 檔。</span><span class="sxs-lookup"><span data-stu-id="ba6db-123">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="ba6db-124">下列命令會移除先前指派給 Ken Myer 的任何個別使用者封存原則。</span><span class="sxs-lookup"><span data-stu-id="ba6db-124">The following command removes any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="ba6db-125">移除每一使用者原則之後，就會使用全域原則（如果有的話）或其本機網站原則來管理 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="ba6db-125">After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="ba6db-126">網站原則優先順序高於全域原則。</span><span class="sxs-lookup"><span data-stu-id="ba6db-126">A site policy takes precedence over the global policy.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="ba6db-127">如需詳細資訊，請參閱 [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) Cmdlet 檔。</span><span class="sxs-lookup"><span data-stu-id="ba6db-127">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  

