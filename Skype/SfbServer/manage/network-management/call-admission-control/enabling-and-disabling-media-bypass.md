---
title: 啟用及停用媒體旁路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 使用本文中的程式, 可以使用商務用 Skype Server 的 [控制台] 來啟用或停用媒體旁路。
ms.openlocfilehash: acfa963e71f3c3b89d0e79648d00871b1ab44616
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188602"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="2a1a9-103">在商務用 Skype Server 中啟用和停用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="2a1a9-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="2a1a9-104">使用本文中的程式, 可以使用商務用 Skype Server 的 [控制台] 來啟用或停用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="2a1a9-105">啟用網路媒體旁路</span><span class="sxs-lookup"><span data-stu-id="2a1a9-105">Enable network media bypass</span></span> 

<span data-ttu-id="2a1a9-106">在商務用 Skype Server 部署中, 媒體旁路設定會全域運用。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="2a1a9-107">[旁路媒體] 允許呼叫繞過中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="2a1a9-108">如需有關何時使用媒體旁路的詳細資料, 請參閱[規劃媒體略過](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="2a1a9-109">您可以從商務用 Skype Server 的 [控制台] 啟用和設定 [媒體旁路]。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="2a1a9-110">啟用和設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="2a1a9-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="2a1a9-111">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2a1a9-112">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2a1a9-113">在左側導覽列中, 按一下 [**網路**設定], 然後按一下 [**全域**]。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="2a1a9-114">在 [**全域**] 頁面上, 按一下 [**全域**配置]。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="2a1a9-115">永遠只有一個設定, 且永遠會將它命名為 Global。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="2a1a9-116">按一下 [**編輯**] 功能表上的 [**查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="2a1a9-117">在 [**編輯全域設定**] 頁面上, 按一下 [**啟用旁路媒體**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="2a1a9-118">選取下列其中一個選項:</span><span class="sxs-lookup"><span data-stu-id="2a1a9-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="2a1a9-119">**[永遠略過**   ] 選取此選項, 即可在所有通話中嘗試媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="2a1a9-120">如果啟用 [通話許可控制 (CAC)], 此選項將無法使用。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="2a1a9-121">如果未啟用 CAC, 請在下列情況下選取此選項:</span><span class="sxs-lookup"><span data-stu-id="2a1a9-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="2a1a9-122">您不需要頻寬控制。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="2a1a9-123">不需要精確的設定來判斷何時應發生旁路。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="2a1a9-124">閘道與用戶端之間有完整的連線能力。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="2a1a9-125">\*\*\*\* 如果啟用了 CAC, 請使用網站和地區設定, 預設會選取此選項, 且無法進行變更。   </span><span class="sxs-lookup"><span data-stu-id="2a1a9-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="2a1a9-126">選取此選項時, 系統會使用網路設定網站和區域來判斷何時可能會略過媒體。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="2a1a9-127">如果您選取此選項, 您可以選擇針對未對應的網站啟用 [旁路]。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="2a1a9-128">只有當您有一個或多個大型網站與不含頻寬限制 (例如大型中央網站) 的同一個區域相關聯時, 請按一下 [**啟用旁路未對應的網站**] 核取方塊, 而且還有一些與您相關聯的分支網站具有頻寬限制的同一個區域。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="2a1a9-129">當您針對未對應的網站啟用 [旁路] 時, 系統會簡化配置, 因為您只需指定與分支網站相關聯的子網, 而不需要指定所有與所有網站相關聯的子網。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="2a1a9-130">如果啟用 CAC, 我們建議您不要選取 [**啟用旁路未對應的網站**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="2a1a9-131">按一下 [**認可**], 儲存您的變更。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="2a1a9-132">停用網路媒體旁路</span><span class="sxs-lookup"><span data-stu-id="2a1a9-132">Disable network media bypass</span></span>

<span data-ttu-id="2a1a9-133">在商務用 Skype Server 部署中, 媒體旁路設定會全域運用。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="2a1a9-134">[旁路媒體] 允許呼叫繞過中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="2a1a9-135">如需有關何時使用媒體旁路的詳細資料, 請參閱[規劃媒體略過](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="2a1a9-136">您可以從商務用 Skype Server 的 [控制台] 停用 [媒體旁路]。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="2a1a9-137">停用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="2a1a9-137">To disable media bypass</span></span>

1.  <span data-ttu-id="2a1a9-138">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2a1a9-139">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2a1a9-140">在左側導覽列中, 按一下 [**網路**設定], 然後按一下 [**全域**]。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="2a1a9-141">在 [**全域**] 頁面上, 按一下 [**全域**配置]。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-141">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="2a1a9-142">永遠只有一個設定, 且永遠會將它命名為 Global。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-142">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="2a1a9-143">按一下 [**編輯**] 功能表上的 [**查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="2a1a9-144">在 [**編輯全域設定**] 頁面上, 清除 [**啟用媒體旁路**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="2a1a9-145">按一下 [**認可**], 儲存您的變更。</span><span class="sxs-lookup"><span data-stu-id="2a1a9-145">Click **Commit** to save your changes.</span></span>

  
