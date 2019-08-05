---
title: 在商務用 Skype 中匯出或匯入語音路由設定檔
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
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: '摘要: 瞭解如何使用商務用 Skype Server 控制台, 在商務用 Skype Server 中匯出或匯入語音路由設定檔。'
ms.openlocfilehash: 14637694e5604419fcd344b43af98263588f117a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193254"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="40828-103">在商務用 Skype 中匯出或匯入語音路由設定檔</span><span class="sxs-lookup"><span data-stu-id="40828-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="40828-104">**摘要:** 瞭解如何使用商務用 Skype Server 控制台, 在商務用 Skype Server 中匯出或匯入語音路由設定檔。</span><span class="sxs-lookup"><span data-stu-id="40828-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="40828-105">如果您想要儲存語音路由設定, 但不發佈, 請遵循下列步驟來儲存及取得語音路由設定的快照。</span><span class="sxs-lookup"><span data-stu-id="40828-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="40828-106">當您匯入語音路由設定檔案 (vcfg), 但同時又在伺服器上對語音路由設定進行變更時, 商務用 Skype Server [控制台] 中的 [**語音路由**] 群組中的頁面會顯示[已未提交] 變更為 [語音路由]。</span><span class="sxs-lookup"><span data-stu-id="40828-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="40828-107">那些未提交的變更是兩個需要調解的設定之間的差異。</span><span class="sxs-lookup"><span data-stu-id="40828-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="40828-108">如果您已對群組內任何頁面上的設定進行任何未提交的變更, 這些變更就會儲存在匯出的語音設定檔案 (vcfg) 中。</span><span class="sxs-lookup"><span data-stu-id="40828-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="40828-109">這可讓您在發佈變更前, 在多個會話期間進行語音路由設定的變更。</span><span class="sxs-lookup"><span data-stu-id="40828-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="40828-110">匯出語音路由設定</span><span class="sxs-lookup"><span data-stu-id="40828-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="40828-111">以 RTCUniversalServerAdmins 群組的成員或**CsVoiceAdministrator**、 **CsServerAdministrator**或**CsAdministrator**系統管理角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="40828-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="40828-112">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="40828-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="40828-113">在左側導覽列中, 按一下 [**語音路由**]。</span><span class="sxs-lookup"><span data-stu-id="40828-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="40828-114">在 [**動作**] 功能表上, 按一下 [**匯出配置**]。</span><span class="sxs-lookup"><span data-stu-id="40828-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="40828-115">指定位置和檔案名, 然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="40828-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="40828-116">若要匯入語音路由設定</span><span class="sxs-lookup"><span data-stu-id="40828-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="40828-117">以 RTCUniversalServerAdmins 群組的成員或**CsVoiceAdministrator**、 **CsServerAdministrator**或**CsAdministrator**系統管理角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="40828-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="40828-118">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="40828-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="40828-119">在左側導覽列中, 按一下 [**語音路由**]。</span><span class="sxs-lookup"><span data-stu-id="40828-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="40828-120">在 [**動作**] 功能表上, 按一下 [匯**入配置**]。</span><span class="sxs-lookup"><span data-stu-id="40828-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="40828-121">找出您要匯入的設定檔, 然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="40828-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="40828-122">按一下 [**認可**], 然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="40828-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40828-123">每當您匯入語音設定檔案時, 您必須執行 [**全部提交**] 命令才能發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="40828-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="40828-124">如需詳細資訊, 請參閱在作業檔中[發佈商務用 Skype 中的語音路由設定的待處理變更](voice-route-config-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="40828-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

