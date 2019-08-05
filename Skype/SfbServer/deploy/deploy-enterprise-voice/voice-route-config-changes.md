---
title: 在商務用 Skype 中發佈 [語音路由設定] 的擱置變更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: '摘要: 瞭解如何使用商務用 Skype Server 控制台, 在商務用 Skype Server 中查看、發佈或取消語音路由設定變更。'
ms.openlocfilehash: 1ff33dee1518581e4a94aac56ecae34d9bfd1159
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193255"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a><span data-ttu-id="cb7f1-103">在商務用 Skype 中發佈 [語音路由設定] 的擱置變更</span><span class="sxs-lookup"><span data-stu-id="cb7f1-103">Publish pending changes to the voice routing configuration in Skype for Business</span></span>
 
<span data-ttu-id="cb7f1-104">**摘要:** 瞭解如何使用商務用 Skype Server 控制台, 在商務用 Skype Server 中查看、發佈或取消語音路由設定變更。</span><span class="sxs-lookup"><span data-stu-id="cb7f1-104">**Summary:** Learn how to review, publish, or cancel voice routing configuration changes in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="cb7f1-105">在您針對 [**語音路由**] 群組中的頁面變更任何設定設定之後, 請執行此程式來審閱、發佈或解除擱置中的變更。</span><span class="sxs-lookup"><span data-stu-id="cb7f1-105">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cb7f1-106">確定一次只有一個使用者會修改 [語音路由設定] 設定。</span><span class="sxs-lookup"><span data-stu-id="cb7f1-106">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cb7f1-107">只要執行 [**全部提交**] 命令, 就必須同時發佈所有擱置中的變更。</span><span class="sxs-lookup"><span data-stu-id="cb7f1-107">All pending changes must be published at the same time by running the **Commit all** command.</span></span> <span data-ttu-id="cb7f1-108">您無法選擇性地發佈擱置中的變更。</span><span class="sxs-lookup"><span data-stu-id="cb7f1-108">You cannot selectively publish pending changes.</span></span> <span data-ttu-id="cb7f1-109">發佈待定變更之前, 請先執行 [**查看未提交的變更**] 命令, 然後取消任何您不想發佈的設定變更。</span><span class="sxs-lookup"><span data-stu-id="cb7f1-109">Before you publish pending changes, run the **Review uncommitted changes** command and cancel any configuration changes that you do not want to publish.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cb7f1-110">如果您在提交掛起的變更前, 移出 [**語音路由**] 群組中的頁面, 所有擱置的變更都會遺失。</span><span class="sxs-lookup"><span data-stu-id="cb7f1-110">If you navigate away from the pages in the **Voice Routing** group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="cb7f1-111">不過, 您可以將目前的設定 (包括任何擱置中的變更) 匯出到語音設定檔案, 然後匯入併發布更新的設定。</span><span class="sxs-lookup"><span data-stu-id="cb7f1-111">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="cb7f1-112">如需詳細資訊, 請參閱[在商務用 Skype 中匯出或匯入語音路由設定檔](voice-route-configuration-import-export.md)。</span><span class="sxs-lookup"><span data-stu-id="cb7f1-112">For details, see [Export or import a voice route configuration file in Skype for Business](voice-route-configuration-import-export.md).</span></span> 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="cb7f1-113">若要查看、發佈或取消語音路由設定變更</span><span class="sxs-lookup"><span data-stu-id="cb7f1-113">To review, publish, or cancel voice routing configuration changes</span></span>

1. <span data-ttu-id="cb7f1-114">以 RTCUniversalServerAdmins 群組的成員或**CsVoiceAdministrator**、 **CsServerAdministrator**或**CsAdministrator**系統管理角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="cb7f1-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="cb7f1-115">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="cb7f1-115">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="cb7f1-116">在左側導覽列中, 按一下 [**語音路由**]。</span><span class="sxs-lookup"><span data-stu-id="cb7f1-116">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="cb7f1-117">針對 [**語音路由**] 群組的每個頁面上的設定變更您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="cb7f1-117">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>
    
5. <span data-ttu-id="cb7f1-118">若要查看待定的變更而不發佈, 請選取 [**確認**] 功能表中的 [**查看未提交的變更**]。</span><span class="sxs-lookup"><span data-stu-id="cb7f1-118">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>
    
6. <span data-ttu-id="cb7f1-119">如果您想要取消任何待定的變更, 請執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="cb7f1-119">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
   - <span data-ttu-id="cb7f1-120">從 [**認可**] 功能表中選取 [**取消所有未提交的變更**]。</span><span class="sxs-lookup"><span data-stu-id="cb7f1-120">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
   - <span data-ttu-id="cb7f1-121">流覽至含有您要取消之待定變更之 [**語音路由**] 頁面的索引標籤, 選取含有待定變更的專案, 按一下 [**認可**], 然後按一下 [**取消選取的變更**]。</span><span class="sxs-lookup"><span data-stu-id="cb7f1-121">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>
    
7. <span data-ttu-id="cb7f1-122">審閱完所有擱置的變更並取消任何不想發佈的變更之後, 請按一下 [**認可**], 然後按一下 [**全部提交**]。</span><span class="sxs-lookup"><span data-stu-id="cb7f1-122">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>
    
8. <span data-ttu-id="cb7f1-123">在 [**未提交的語音設定**] 對話方塊中, 顯示所有待定變更的清單, 按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="cb7f1-123">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span> 
    
    <span data-ttu-id="cb7f1-124">當商務用 Skype Server 控制台提交變更之後, 就會出現 [**成功發佈的語音路由**設定] 訊息。</span><span class="sxs-lookup"><span data-stu-id="cb7f1-124">When Skype for Business Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>
    

