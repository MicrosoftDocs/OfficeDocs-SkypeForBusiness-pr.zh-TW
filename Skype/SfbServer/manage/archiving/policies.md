---
title: 管理商務用 Skype Server 中的封存原則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 摘要：瞭解如何管理用於商務用 Skype Server 封存的使用者原則。
ms.openlocfilehash: 949ac807faea4f563ee078512a3c0a335a517d2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828543"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="20f22-103">管理商務用 Skype Server 中的封存原則</span><span class="sxs-lookup"><span data-stu-id="20f22-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="20f22-104">**摘要：** 瞭解如何管理適用于商務用 Skype Server 之封存的使用者原則。</span><span class="sxs-lookup"><span data-stu-id="20f22-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="20f22-105">您在部署封存時，最初會設定封存原則，但您可以在部署後變更、新增和刪除設定。</span><span class="sxs-lookup"><span data-stu-id="20f22-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="20f22-106">封存原則決定是否要封存：</span><span class="sxs-lookup"><span data-stu-id="20f22-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="20f22-107">內部通訊</span><span class="sxs-lookup"><span data-stu-id="20f22-107">Internal communications</span></span>
    
- <span data-ttu-id="20f22-108">外部通訊</span><span class="sxs-lookup"><span data-stu-id="20f22-108">External communications</span></span>
    
<span data-ttu-id="20f22-109">您可以在全域、網站或使用者層級設定封存原則。</span><span class="sxs-lookup"><span data-stu-id="20f22-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="20f22-110">如果您已針對您的部署啟用 Microsoft Exchange 整合，Exchange 原則會控制是否為位於 Exchange 上的使用者啟用封存，並將其信箱置於 In-Place 保留狀態。</span><span class="sxs-lookup"><span data-stu-id="20f22-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="20f22-111">如需詳細資訊，請參閱 Plan for 封存 [In 商務用 Skype server](../../plan-your-deployment/archiving/archiving.md) 和 [設定與 Exchange storage 的整合（適用于商務用 skype 伺服器](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)）。</span><span class="sxs-lookup"><span data-stu-id="20f22-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="20f22-112">使用控制台管理封存原則</span><span class="sxs-lookup"><span data-stu-id="20f22-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="20f22-113">您可以使用 [控制台] 來管理封存原則，如下所示：</span><span class="sxs-lookup"><span data-stu-id="20f22-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="20f22-114">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="20f22-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="20f22-115">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="20f22-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="20f22-116">在左導覽列中，按一下 [封存 **原則**]</span><span class="sxs-lookup"><span data-stu-id="20f22-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="20f22-117">使用 Windows PowerShell 管理封存原則</span><span class="sxs-lookup"><span data-stu-id="20f22-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="20f22-118">您也可以使用下表所列的 Windows PowerShell Cmdlet 來設定封存原則。</span><span class="sxs-lookup"><span data-stu-id="20f22-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="20f22-119">如需語法的詳細資訊（包括所有可用參數），請參閱 [商務用 Skype Server 管理命令](../management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="20f22-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="20f22-120">**指令程式**</span><span class="sxs-lookup"><span data-stu-id="20f22-120">**Cmdlet**</span></span>|<span data-ttu-id="20f22-121">**描述**</span><span class="sxs-lookup"><span data-stu-id="20f22-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="20f22-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="20f22-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="20f22-123">傳回組織的立即訊息 (IM) 會話封存原則的資訊。</span><span class="sxs-lookup"><span data-stu-id="20f22-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="20f22-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="20f22-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="20f22-125">指派立即訊息 (IM) 會話封存原則指派給使用者或使用者組。</span><span class="sxs-lookup"><span data-stu-id="20f22-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="20f22-126">這些原則可讓您封存內部使用者之間及/或封存內部使用者與外部協力廠商之間所發生的所有 IM 工作階段。</span><span class="sxs-lookup"><span data-stu-id="20f22-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="20f22-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="20f22-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="20f22-128">建立新的立即訊息 (IM) 會話封存原則。</span><span class="sxs-lookup"><span data-stu-id="20f22-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="20f22-129">這些原則可讓您封存內部使用者之間及/或封存內部使用者與外部協力廠商之間所發生的所有 IM 工作階段。</span><span class="sxs-lookup"><span data-stu-id="20f22-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="20f22-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="20f22-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="20f22-131">移除指定的立即訊息 (IM) 封存原則，可判斷商務用 Skype 伺服器是否會自動儲存內部使用者和/或內部使用者與同盟協力廠商之間所有 IM 會話之間所發生的所有 IM 會話。</span><span class="sxs-lookup"><span data-stu-id="20f22-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="20f22-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="20f22-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="20f22-133">修改現有的立即訊息 (IM) 封存原則。</span><span class="sxs-lookup"><span data-stu-id="20f22-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="20f22-134">封存原則讓您能夠封存內部使用者之間所發生的所有 IM 會話和會議。您也可以封存在內部使用者與同盟協力廠商之間進行的會話。</span><span class="sxs-lookup"><span data-stu-id="20f22-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

