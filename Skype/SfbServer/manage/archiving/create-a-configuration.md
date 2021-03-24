---
title: 在商務用 Skype Server 中建立封存設定
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
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 摘要：瞭解如何為商務用 Skype 伺服器建立封存設定。
ms.openlocfilehash: f00e5b2b9254b53760351c162ea86cd195473788
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095427"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="0acd6-103">在商務用 Skype Server 中建立封存設定</span><span class="sxs-lookup"><span data-stu-id="0acd6-103">Create an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="0acd6-104">**摘要：** 瞭解如何為商務用 Skype 伺服器建立封存設定。</span><span class="sxs-lookup"><span data-stu-id="0acd6-104">**Summary:** Learn how to create an archiving configuration for Skype for Business Server.</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="0acd6-105">使用控制台設定封存選項</span><span class="sxs-lookup"><span data-stu-id="0acd6-105">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="0acd6-106">若要設定特定網站或集區的封存選項：</span><span class="sxs-lookup"><span data-stu-id="0acd6-106">To configure archiving options for a specific site or pool:</span></span> 
  
1. <span data-ttu-id="0acd6-107">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="0acd6-107">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="0acd6-108">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="0acd6-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="0acd6-109">在左導覽列中 **，按一下 [\*\*\*\*監視與** 封存]，然後按一下 [封存設定]。</span><span class="sxs-lookup"><span data-stu-id="0acd6-109">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="0acd6-110">在 [ **封存** 設定] 頁面上，按一下 [ **新增**]，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="0acd6-110">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="0acd6-111">若要建立網站封存設定，請按一下 [ **網站** 設定]，然後在 [ **選取網站**] 中，選取要設定封存的網站。</span><span class="sxs-lookup"><span data-stu-id="0acd6-111">To create a site archiving configuration, click **Site Configuration**, and then in **Select a site**, select the site to be configured for archiving.</span></span>
    
   - <span data-ttu-id="0acd6-112">若要建立集區封存設定，請按一下 [ **集** 區設定]，然後在 [ **選取集** 區] 中，選取要設定封存的集區。</span><span class="sxs-lookup"><span data-stu-id="0acd6-112">To create a pool archiving configuration, click **Pool Configuration**, and then in **Select a pool**, select the pool to be configured for archiving.</span></span>
    
5. <span data-ttu-id="0acd6-113">在 **[建立新的封存設定]** 的 **[封存設定]** 下拉式清單方塊中，執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="0acd6-113">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="0acd6-114">若只要啟用立即訊息 (IM) 工作階段的封存，請按一下 **[封存 IM 工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="0acd6-114">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="0acd6-115">若要同時啟用 IM 會話和 web 會議的封存，請按一下 [封存 **im 和 web 會議會話**]。</span><span class="sxs-lookup"><span data-stu-id="0acd6-115">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="0acd6-116">若要停用此設定的封存，請按一下 [ **停** 用封存]。</span><span class="sxs-lookup"><span data-stu-id="0acd6-116">To disable archiving for this configuration, click **Disable archiving**.</span></span>
    
6. <span data-ttu-id="0acd6-117">此外，在 **[建立新的封存設定]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="0acd6-117">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="0acd6-118">若要在封存無法使用時封鎖活動，請選取 **[封存失敗時封鎖立即訊息 (IM) 和 Web 會議工作階段]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="0acd6-118">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="0acd6-119">若要使用 Microsoft Exchange Server 儲存封存資料，請按一下 [ **Microsoft exchange 整合** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="0acd6-119">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="0acd6-120">若要啟用資料清除，請選取 **[啟用封存資料的清除]** 核取方塊，然後執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="0acd6-120">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
     - <span data-ttu-id="0acd6-121">若要指定在特定天數後進行清除，請按一下 **[在最大持續期限 (天) 後清除匯出的封存資料和儲存的封存資料]**，然後指定天數。</span><span class="sxs-lookup"><span data-stu-id="0acd6-121">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="0acd6-122">若要限制只清除已匯出的封存資料，請按一下 **[只清除匯出的封存資料]**。</span><span class="sxs-lookup"><span data-stu-id="0acd6-122">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="0acd6-123">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="0acd6-123">Click **Commit**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="0acd6-124">使用 Windows PowerShell 設定封存選項</span><span class="sxs-lookup"><span data-stu-id="0acd6-124">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="0acd6-125">您也可以使用 **New-CsArchivingConfiguration** Cmdlet 來設定特定網站或集區的封存選項。</span><span class="sxs-lookup"><span data-stu-id="0acd6-125">You can also configure archiving options for a specific site or pool by using the **New-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="0acd6-126">下列命令會為 Redmond 網站建立新的封存配置設定集合：</span><span class="sxs-lookup"><span data-stu-id="0acd6-126">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="0acd6-127">因為上述命令未指定參數 (除了必要的 Identity 參數)，新的組態設定集合會將預設值用於其所有屬性。</span><span class="sxs-lookup"><span data-stu-id="0acd6-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> 
  
<span data-ttu-id="0acd6-128">若要使用不同的屬性值來建立設定，只要包含適當的參數及參數值即可。</span><span class="sxs-lookup"><span data-stu-id="0acd6-128">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="0acd6-129">下列範例會建立封存設定的集合，根據預設，只允許封存立即訊息會話：</span><span class="sxs-lookup"><span data-stu-id="0acd6-129">The following example creates a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions only:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

<span data-ttu-id="0acd6-130">多項屬性值可透過加入多個參數加以修改。</span><span class="sxs-lookup"><span data-stu-id="0acd6-130">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="0acd6-131">例如，此命令會將新設定設定為封存立即訊息會話，並封鎖封存服務的立即訊息無法使用：</span><span class="sxs-lookup"><span data-stu-id="0acd6-131">For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

<span data-ttu-id="0acd6-132">如需詳細資訊，請參閱 [New-CsArchivingConfiguration](/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="0acd6-132">For more information, see the help topic for the [New-CsArchivingConfiguration](/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>