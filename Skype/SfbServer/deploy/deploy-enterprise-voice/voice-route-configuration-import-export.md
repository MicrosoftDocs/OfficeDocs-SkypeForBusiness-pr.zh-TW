---
title: 在商務用 Skype 中匯出或匯入語音路由設定檔
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
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 摘要：瞭解如何使用商務用 Skype Server 控制台，在商務用 Skype Server 中匯出或匯入語音路由設定檔。
ms.openlocfilehash: df5ca58ebc7b92fea5236b957f4819ed3602d896
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830353"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="b78b3-103">在商務用 Skype 中匯出或匯入語音路由設定檔</span><span class="sxs-lookup"><span data-stu-id="b78b3-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="b78b3-104">**摘要：** 瞭解如何使用商務用 Skype Server 控制台，在商務用 Skype Server 中匯出或匯入語音路由設定檔。</span><span class="sxs-lookup"><span data-stu-id="b78b3-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="b78b3-105">如果您想要儲存語音路由設定，但未發佈它，請遵循下列步驟，儲存並取得您的語音路由設定快照。</span><span class="sxs-lookup"><span data-stu-id="b78b3-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="b78b3-106">當您匯入語音路由設定檔 (。 vcfg) ，但目前在伺服器上對語音路由設定進行變更時，商務用 Skype Server [控制台] 中的 [ **語音路由** ] 群組中的頁面會指出有未認可的變更可供語音路由使用。</span><span class="sxs-lookup"><span data-stu-id="b78b3-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="b78b3-107">這些未認可的變更會使兩個設定出現差異且需要重新調整。</span><span class="sxs-lookup"><span data-stu-id="b78b3-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="b78b3-108">如果您已對群組內任何頁面上的設定進行任何未認可的變更，則所做的變更會儲存在匯出的語音設定檔中 (。 vcfg) 。</span><span class="sxs-lookup"><span data-stu-id="b78b3-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="b78b3-109">這可讓您在發佈變更之前，在多個會話期間進行語音路由設定變更。</span><span class="sxs-lookup"><span data-stu-id="b78b3-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="b78b3-110">若要匯出語音路由設定</span><span class="sxs-lookup"><span data-stu-id="b78b3-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="b78b3-111">以 RTCUniversalServerAdmins 群組成員的身分，或是 **CsVoiceAdministrator**、 **CsServerAdministrator** 或 **CsAdministrator** 系統管理角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="b78b3-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="b78b3-112">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="b78b3-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b78b3-113">在左導覽列中，按一下 **[語音路由]**。</span><span class="sxs-lookup"><span data-stu-id="b78b3-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="b78b3-114">在 **[執行]** 功能表上，按一下 **[匯出設定]**。</span><span class="sxs-lookup"><span data-stu-id="b78b3-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="b78b3-115">指定位置和檔案名稱，然後按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="b78b3-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="b78b3-116">若要匯入語音路由設定</span><span class="sxs-lookup"><span data-stu-id="b78b3-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="b78b3-117">以 RTCUniversalServerAdmins 群組成員的身分，或是 **CsVoiceAdministrator**、 **CsServerAdministrator** 或 **CsAdministrator** 系統管理角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="b78b3-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="b78b3-118">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="b78b3-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b78b3-119">在左導覽列中，按一下 **[語音路由]**。</span><span class="sxs-lookup"><span data-stu-id="b78b3-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="b78b3-120">在 **[執行]** 功能表上，按一下 **[匯入設定]**。</span><span class="sxs-lookup"><span data-stu-id="b78b3-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="b78b3-121">尋找您要匯入的組態檔，然後按一下 **[開啟]**。</span><span class="sxs-lookup"><span data-stu-id="b78b3-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="b78b3-122">依序按一下 **[認可]** 和 **[全部認可]**。</span><span class="sxs-lookup"><span data-stu-id="b78b3-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b78b3-123">每當您匯入語音設定檔時，您必須執行 **[全部認可]** 命令來發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="b78b3-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="b78b3-124">如需詳細資訊，請參閱 Operations 檔中的在 [商務用 Skype 中發佈待定的變更至語音路由](voice-route-config-changes.md) 設定。</span><span class="sxs-lookup"><span data-stu-id="b78b3-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

