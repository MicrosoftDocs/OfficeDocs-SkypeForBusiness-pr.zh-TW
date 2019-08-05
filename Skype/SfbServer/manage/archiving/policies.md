---
title: 在商務用 Skype Server 中管理存檔原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: '摘要: 瞭解如何管理適用于商務用 Skype Server 的存檔的使用者原則。'
ms.openlocfilehash: f6918907f73ffe1b098ed96e1997d8ab8ffe4f9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188212"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="8781b-103">在商務用 Skype Server 中管理存檔原則</span><span class="sxs-lookup"><span data-stu-id="8781b-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="8781b-104">**摘要:** 瞭解如何管理適用于商務用 Skype Server 的存檔的使用者原則。</span><span class="sxs-lookup"><span data-stu-id="8781b-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="8781b-105">您最初是在部署封存時設定封存原則, 但是您可以在部署之後變更、新增及刪除設定。</span><span class="sxs-lookup"><span data-stu-id="8781b-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="8781b-106">存檔原則決定是否要封存:</span><span class="sxs-lookup"><span data-stu-id="8781b-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="8781b-107">內部通訊</span><span class="sxs-lookup"><span data-stu-id="8781b-107">Internal communications</span></span>
    
- <span data-ttu-id="8781b-108">外部通訊</span><span class="sxs-lookup"><span data-stu-id="8781b-108">External communications</span></span>
    
<span data-ttu-id="8781b-109">您可以在全域、網站或使用者層級設定歸檔原則。</span><span class="sxs-lookup"><span data-stu-id="8781b-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8781b-110">如果您已針對您的部署啟用 Microsoft Exchange 整合, Exchange 原則會控制是否針對駐留在 Exchange 的使用者啟用封存, 並將其信箱放在就地保留中。</span><span class="sxs-lookup"><span data-stu-id="8781b-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="8781b-111">如需詳細資訊, 請參閱[在商務用 Skype server 中進行](../../plan-your-deployment/archiving/archiving.md)封存的規劃, 以及[設定與商務用 Skype server 的 Exchange 儲存體整合](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="8781b-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="8781b-112">使用 [控制台] 管理歸檔原則</span><span class="sxs-lookup"><span data-stu-id="8781b-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="8781b-113">您可以使用 [控制台] 管理存檔原則, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="8781b-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="8781b-114">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="8781b-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="8781b-115">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="8781b-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="8781b-116">在左側導覽列中, 按一下 [封存**原則**]</span><span class="sxs-lookup"><span data-stu-id="8781b-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="8781b-117">使用 Windows PowerShell 管理存檔原則</span><span class="sxs-lookup"><span data-stu-id="8781b-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="8781b-118">您也可以使用下表所列的 Windows PowerShell Cmdlet 來設定歸檔原則。</span><span class="sxs-lookup"><span data-stu-id="8781b-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="8781b-119">如需語法的詳細資料 (包括所有可用的參數), 請參閱[商務用 Skype Server 管理命令](../management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="8781b-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="8781b-120">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="8781b-120">**Cmdlet**</span></span>|<span data-ttu-id="8781b-121">**說明**</span><span class="sxs-lookup"><span data-stu-id="8781b-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8781b-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="8781b-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="8781b-123">傳回貴組織的立即訊息 (IM) 會話存檔原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="8781b-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="8781b-124">授與 CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="8781b-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="8781b-125">將立即訊息 (IM) 會話存檔原則指派給使用者或使用者組。</span><span class="sxs-lookup"><span data-stu-id="8781b-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="8781b-126">這些原則可讓您封存在內部使用者之間進行的所有 IM 會話, 以及/或封存在內部使用者與外部合作夥伴之間發生的所有 IM 會話。</span><span class="sxs-lookup"><span data-stu-id="8781b-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="8781b-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="8781b-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="8781b-128">建立新的立即訊息 (IM) 會話存檔原則。</span><span class="sxs-lookup"><span data-stu-id="8781b-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="8781b-129">這些原則可讓您封存在內部使用者之間進行的所有 IM 會話, 以及/或封存在內部使用者與外部合作夥伴之間發生的所有 IM 會話。</span><span class="sxs-lookup"><span data-stu-id="8781b-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="8781b-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="8781b-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="8781b-131">移除指定的立即訊息 (IM) 封存原則, 決定商務用 Skype 伺服器是否會自動儲存所有內部使用者之間發生的 IM 會話, 以及/或內部使用者與同盟合作夥伴之間的所有 IM 會話。</span><span class="sxs-lookup"><span data-stu-id="8781b-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="8781b-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="8781b-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="8781b-133">修改現有的立即訊息 (IM) 封存原則。</span><span class="sxs-lookup"><span data-stu-id="8781b-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="8781b-134">存檔原則可讓您將在內部使用者之間發生的所有 IM 會議與會議封存在一起。您也可以封存在內部使用者和聯盟夥伴之間發生的會話。</span><span class="sxs-lookup"><span data-stu-id="8781b-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

