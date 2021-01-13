---
title: 在商務用 Skype 中將擱置的變更發佈至語音路由設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 摘要：瞭解如何使用商務用 Skype Server 控制台複查、發佈或取消商務用 Skype Server 中的語音路由設定變更。
ms.openlocfilehash: 6b75b6a1135cf9abde9551112fc9c29579862a8b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830393"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a><span data-ttu-id="adb6d-103">在商務用 Skype 中將擱置的變更發佈至語音路由設定</span><span class="sxs-lookup"><span data-stu-id="adb6d-103">Publish pending changes to the voice routing configuration in Skype for Business</span></span>
 
<span data-ttu-id="adb6d-104">**摘要：** 瞭解如何使用商務用 Skype Server 控制台，查看、發佈或取消商務用 Skype Server 中的語音路由設定變更。</span><span class="sxs-lookup"><span data-stu-id="adb6d-104">**Summary:** Learn how to review, publish, or cancel voice routing configuration changes in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="adb6d-105">變更 [ **語音路由** ] 群組中的任何設定設定後，請執行此程式以複查、發佈或取消暫止的變更。</span><span class="sxs-lookup"><span data-stu-id="adb6d-105">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="adb6d-106">請確定一次只能有一個使用者修改語音路由設定的設定。</span><span class="sxs-lookup"><span data-stu-id="adb6d-106">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="adb6d-107">所有擱置的變更都必須同時發佈，只要執行 [ **全部認可** ] 命令即可。</span><span class="sxs-lookup"><span data-stu-id="adb6d-107">All pending changes must be published at the same time by running the **Commit all** command.</span></span> <span data-ttu-id="adb6d-108">您無法選擇性發行暫止的變更。</span><span class="sxs-lookup"><span data-stu-id="adb6d-108">You cannot selectively publish pending changes.</span></span> <span data-ttu-id="adb6d-109">在您發佈暫止的變更之前，請執行 [ **檢查未** 認可的變更] 命令，並取消您不想發佈的任何設定變更。</span><span class="sxs-lookup"><span data-stu-id="adb6d-109">Before you publish pending changes, run the **Review uncommitted changes** command and cancel any configuration changes that you do not want to publish.</span></span>
  
> [!NOTE]
> <span data-ttu-id="adb6d-110">如果您在提交暫止的變更之前，移離 **語音路由** 群組中的頁面，所有擱置的變更將會遺失。</span><span class="sxs-lookup"><span data-stu-id="adb6d-110">If you navigate away from the pages in the **Voice Routing** group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="adb6d-111">不過，您可以將目前的設定 (包括任何擱置的變更) 至語音設定檔，然後匯入併發行更新的設定。</span><span class="sxs-lookup"><span data-stu-id="adb6d-111">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="adb6d-112">如需詳細資訊，請參閱 [Export or import voice route configuration file In 商務用 Skype](voice-route-configuration-import-export.md)。</span><span class="sxs-lookup"><span data-stu-id="adb6d-112">For details, see [Export or import a voice route configuration file in Skype for Business](voice-route-configuration-import-export.md).</span></span> 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="adb6d-113">若要檢查、發佈或取消語音路由設定變更</span><span class="sxs-lookup"><span data-stu-id="adb6d-113">To review, publish, or cancel voice routing configuration changes</span></span>

1. <span data-ttu-id="adb6d-114">以 RTCUniversalServerAdmins 群組成員的身分，或是 **CsVoiceAdministrator**、 **CsServerAdministrator** 或 **CsAdministrator** 系統管理角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="adb6d-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="adb6d-115">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="adb6d-115">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="adb6d-116">在左導覽列中，按一下 **[語音路由]**。</span><span class="sxs-lookup"><span data-stu-id="adb6d-116">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="adb6d-117">在 [ **語音路由** ] 群組的每一頁上進行設定的設定變更。</span><span class="sxs-lookup"><span data-stu-id="adb6d-117">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>
    
5. <span data-ttu-id="adb6d-118">若要在未發佈的情況下複查擱置中的變更，請選取 [從 **認可**] 功能表 **查看未** 認可的變更</span><span class="sxs-lookup"><span data-stu-id="adb6d-118">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>
    
6. <span data-ttu-id="adb6d-119">如果您想要取消任何擱置的變更，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="adb6d-119">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
   - <span data-ttu-id="adb6d-120">從 [**認可**] 功能表中，選取 [**取消所有未** 認可的變更]。</span><span class="sxs-lookup"><span data-stu-id="adb6d-120">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
   - <span data-ttu-id="adb6d-121">流覽至 [ **語音路由** ] 頁面上的 [語音路由] 頁面，其中含有您想要取消的待處理變更，選取具有暫止變更的專案，按一下 [ **認可**]，然後按一下 [ **取消選取的變更**]。</span><span class="sxs-lookup"><span data-stu-id="adb6d-121">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>
    
7. <span data-ttu-id="adb6d-122">在您檢查所有擱置的變更並取消任何不想發佈的變更之後，請按一下 [ **認可**]，然後按一下 [ **全部認可**]。</span><span class="sxs-lookup"><span data-stu-id="adb6d-122">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>
    
8. <span data-ttu-id="adb6d-123">在 [ **未認可的語音設定** ] 對話方塊中，顯示所有擱置變更的清單，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="adb6d-123">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span> 
    
    <span data-ttu-id="adb6d-124">當商務用 Skype Server 控制台認可變更時，就會出現 [ **成功發行的語音路由** 設定] 訊息。</span><span class="sxs-lookup"><span data-stu-id="adb6d-124">When Skype for Business Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>
    

