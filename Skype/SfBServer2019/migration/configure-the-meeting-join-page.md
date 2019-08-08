---
title: 設定會議加入頁面
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 當使用者按一下會議邀請中的會議連結時, [會議加入] 頁面會偵測使用者電腦上已安裝的用戶端。 如果已安裝用戶端, 該用戶端會開啟並加入會議。 如果沒有安裝用戶端, 則預設會開啟 Web 應用程式。
ms.openlocfilehash: 1bab2dff25db94b36c41e5824401777006760bfc
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239560"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="db556-105">設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="db556-105">Configure the meeting join page</span></span>

<span data-ttu-id="db556-106">當使用者按一下會議邀請中的會議連結時, [會議加入] 頁面會偵測使用者電腦上已安裝的用戶端。</span><span class="sxs-lookup"><span data-stu-id="db556-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="db556-107">如果已安裝用戶端, 該用戶端會開啟並加入會議。</span><span class="sxs-lookup"><span data-stu-id="db556-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="db556-108">如果沒有安裝用戶端, 則預設會開啟 Web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="db556-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="db556-109">如果您想要允許使用者加入會議, 您可以修改會議加入頁面的行為。</span><span class="sxs-lookup"><span data-stu-id="db556-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="db556-110">這些設定選項已從 [控制台] 中移除, 但您可以使用 CsWebServiceConfiguration Cmdlet 加以設定。</span><span class="sxs-lookup"><span data-stu-id="db556-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="db556-111">**會議加入頁面 CsWebServiceConfiguration 參數**</span><span class="sxs-lookup"><span data-stu-id="db556-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="db556-112">**CsWebServiceConfiguration 參數**</span><span class="sxs-lookup"><span data-stu-id="db556-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="db556-113">**說明**</span><span class="sxs-lookup"><span data-stu-id="db556-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="db556-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="db556-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="db556-115">如果設為 True, 則使用者使用 Lync 以外的用戶端應用程式加入會議時, 系統會提供加入會議的機會。</span><span class="sxs-lookup"><span data-stu-id="db556-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="db556-116">預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="db556-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="db556-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="db556-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="db556-118">當設定為 True 時, 加入線上會議的替代選項會自動展開並向使用者顯示。</span><span class="sxs-lookup"><span data-stu-id="db556-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="db556-119">當設定為 False (預設值) 時, 將會提供這些選項, 但使用者將必須針對自己顯示選項清單。</span><span class="sxs-lookup"><span data-stu-id="db556-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="db556-120">使用商務用 Skype Server 2019 管理命令介面設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="db556-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="db556-121">啟動商務用 Skype Server 2019 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [ **Microsoft 商務用 skype server 2019**], 然後按一下 [**商務用 skype server Management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="db556-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="db556-122">執行下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="db556-122">Run the following cmdlet:</span></span> 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="db556-123">這個 Cmdlet 會傳回 web 服務配置設定。</span><span class="sxs-lookup"><span data-stu-id="db556-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="db556-124">根據您的喜好設定 (如需此 Cmdlet 之參數的詳細資料, 請參閱[商務用 Skype Server 管理命令](../../SfbServer/manage/management-shell.md)介面檔), 執行下列命令, 並將參數設定為 True 或 False。</span><span class="sxs-lookup"><span data-stu-id="db556-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


