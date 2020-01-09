---
title: 在商務用 Skype Server 中建立封存配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 摘要：瞭解如何建立商務用 Skype Server 的存檔設定。
ms.openlocfilehash: bd2a139e7321542e3b13259ebc2ec1e4ba731caf
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992740"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="016e1-103">在商務用 Skype Server 中建立封存配置</span><span class="sxs-lookup"><span data-stu-id="016e1-103">Create an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="016e1-104">**摘要：** 瞭解如何建立商務用 Skype Server 的存檔設定。</span><span class="sxs-lookup"><span data-stu-id="016e1-104">**Summary:** Learn how to create an archiving configuration for Skype for Business Server.</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="016e1-105">使用 [控制台] 設定存檔選項</span><span class="sxs-lookup"><span data-stu-id="016e1-105">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="016e1-106">若要設定特定網站或文件庫的存檔選項：</span><span class="sxs-lookup"><span data-stu-id="016e1-106">To configure archiving options for a specific site or pool:</span></span> 
  
1. <span data-ttu-id="016e1-107">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="016e1-107">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="016e1-108">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="016e1-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="016e1-109">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。</span><span class="sxs-lookup"><span data-stu-id="016e1-109">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="016e1-110">在 [**存檔**設定] 頁面上，按一下 [**新增**]，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="016e1-110">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="016e1-111">若要建立網站封存設定，請按一下 [**網站**設定]，然後在 [**選取網站**] 中，選取要設定為要存檔的網站。</span><span class="sxs-lookup"><span data-stu-id="016e1-111">To create a site archiving configuration, click **Site Configuration**, and then in **Select a site**, select the site to be configured for archiving.</span></span>
    
   - <span data-ttu-id="016e1-112">若要建立池存檔設定，請按一下 [**池**設定]，然後在 [**選取池**] 中，選取要設定為要存檔的池。</span><span class="sxs-lookup"><span data-stu-id="016e1-112">To create a pool archiving configuration, click **Pool Configuration**, and then in **Select a pool**, select the pool to be configured for archiving.</span></span>
    
5. <span data-ttu-id="016e1-113">在 [**新增封存設定**] 的 [**存檔設定**] 下拉式清單方塊中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="016e1-113">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="016e1-114">若要只針對立即訊息（IM）會話啟用封存，請按一下 [封存**IM 會話**]。</span><span class="sxs-lookup"><span data-stu-id="016e1-114">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="016e1-115">若要在 IM 會話和網路會議中同時啟用封存功能，請按一下 [封存**im 和網路會議會話**]。</span><span class="sxs-lookup"><span data-stu-id="016e1-115">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="016e1-116">若要停用此設定的封存，請按一下 [**停**用封存]。</span><span class="sxs-lookup"><span data-stu-id="016e1-116">To disable archiving for this configuration, click **Disable archiving**.</span></span>
    
6. <span data-ttu-id="016e1-117">此外，在 [新增封存]**設定**中，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="016e1-117">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="016e1-118">若要在封存無法使用時封鎖活動，請選取 [**如果封存失敗，封鎖立即訊息（IM）或 web 會議會話**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="016e1-118">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="016e1-119">若要使用 Microsoft Exchange Server 儲存存檔資料，請按一下 [ **Microsoft exchange 整合**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="016e1-119">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="016e1-120">若要啟用資料清除，請選取 [**啟用 [清除封存資料**] 核取方塊，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="016e1-120">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
     - <span data-ttu-id="016e1-121">若要指定在特定天數後進行清除，請按一下 **[清除匯出的存檔資料]，並儲存在最長持續時間（天數）之後的儲存封存資料**，然後指定天數。</span><span class="sxs-lookup"><span data-stu-id="016e1-121">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="016e1-122">若要限制清除以封存已匯出的資料，請按一下 [**僅清除匯出的存檔資料**]。</span><span class="sxs-lookup"><span data-stu-id="016e1-122">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="016e1-123">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="016e1-123">Click **Commit**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="016e1-124">使用 Windows PowerShell 設定封存選項</span><span class="sxs-lookup"><span data-stu-id="016e1-124">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="016e1-125">您也可以使用**CsArchivingConfiguration** Cmdlet 來設定特定網站或文檔池的存檔選項。</span><span class="sxs-lookup"><span data-stu-id="016e1-125">You can also configure archiving options for a specific site or pool by using the **New-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="016e1-126">下列命令會建立新的 [雷德蒙] 網站存檔設定的集合：</span><span class="sxs-lookup"><span data-stu-id="016e1-126">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="016e1-127">因為在上述命令中沒有指定任何參數（強制身分識別參數以外），所以新的配置設定集合會將預設值用於其所有屬性。</span><span class="sxs-lookup"><span data-stu-id="016e1-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> 
  
<span data-ttu-id="016e1-128">若要建立使用不同屬性值的設定，只要包含適當的參數和參數值即可。</span><span class="sxs-lookup"><span data-stu-id="016e1-128">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="016e1-129">下列範例會建立一個存檔設定的集合，預設只允許封存立即訊息會話：</span><span class="sxs-lookup"><span data-stu-id="016e1-129">The following example creates a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions only:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

<span data-ttu-id="016e1-130">您可以透過包含多個參數來修改多個屬性值。</span><span class="sxs-lookup"><span data-stu-id="016e1-130">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="016e1-131">例如，這個命令會將新設定設為封存立即訊息會話，並封鎖封存服務的立即訊息無法使用：</span><span class="sxs-lookup"><span data-stu-id="016e1-131">For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

<span data-ttu-id="016e1-132">如需詳細資訊，請參閱[新版-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="016e1-132">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
