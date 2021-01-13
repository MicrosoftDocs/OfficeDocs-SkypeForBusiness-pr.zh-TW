---
title: 啟用和停用媒體旁路
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
description: 使用本文中的程式，透過使用商務用 Skype Server 控制台來啟用或停用媒體旁路。
ms.openlocfilehash: cb8bb06c0e15d39733e92f26867917bb4f8e6989
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816493"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="7a0c0-103">在商務用 Skype Server 中啟用及停用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="7a0c0-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="7a0c0-104">使用本文中的程式，透過使用商務用 Skype Server 控制台來啟用或停用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="7a0c0-105">啟用網路媒體旁路</span><span class="sxs-lookup"><span data-stu-id="7a0c0-105">Enable network media bypass</span></span> 

<span data-ttu-id="7a0c0-106">媒體旁路設定會在整個商務用 Skype Server 部署中全域套用。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="7a0c0-107">媒體旁路允許來電略過轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="7a0c0-108">如需有關何時使用媒體旁路的詳細資訊，請參閱 [Plan for media 旁路](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="7a0c0-109">您可以從商務用 Skype Server 控制台啟用及設定媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="7a0c0-110">啟用及設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="7a0c0-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="7a0c0-111">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7a0c0-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7a0c0-113">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **通用**]。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="7a0c0-114">在 **[全域]** 頁面上，按一下 **[全域]** 設定。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="7a0c0-115">永遠只有一個設定，而且永遠稱為 Global。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="7a0c0-116">在 [ **編輯** ] 功能表上，按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="7a0c0-117">在 [ **編輯通用設定** ] 頁面上，按一下 [ **啟用媒體旁路** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="7a0c0-118">請選取下列任一選項：</span><span class="sxs-lookup"><span data-stu-id="7a0c0-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="7a0c0-119">**永遠略過**   選取此選項，可在所有呼叫時嘗試媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="7a0c0-120">如果已啟用 (CAC) 的通話許可控制，此選項將無法使用。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="7a0c0-121">如果未啟用 CAC，請在下列情況下選取此選項：</span><span class="sxs-lookup"><span data-stu-id="7a0c0-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="7a0c0-122">不需要頻寬控制。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="7a0c0-123">不需要微調設定，就能決定何時應該應該發生旁路。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="7a0c0-124">閘道和用戶端之間有完整的連線能力。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="7a0c0-125">**使用網站與地區**   設定  如果啟用 CAC，預設會選取此選項，而且無法變更。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="7a0c0-126">選取此選項時，會使用網路設定網站和區域來決定何時可以進行媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="7a0c0-127">如果您選取此選項，您可以針對未對應的網站，選擇啟用旁路。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="7a0c0-128">只有當您有一個或多個大型網站與沒有頻寬限制的相同區域相關聯時，才會按一下 [為 **未對應的網站啟用旁路** ] 核取方塊 (例如，大型中央網站) ，而且您也有一些分支網站與具有頻寬限制的相同地區相關聯。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="7a0c0-129">當您為未對應的網站啟用旁路時，將會簡化設定，因為您只會指定與分支網站相關聯的子網，而不需要指定所有網站相關聯的所有子網。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="7a0c0-130">如果啟用 CAC，建議您不要選取 [為 **未對應的網站啟用旁路** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="7a0c0-131">按一下 [ **認可** ] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="7a0c0-132">停用網路媒體旁路</span><span class="sxs-lookup"><span data-stu-id="7a0c0-132">Disable network media bypass</span></span>

<span data-ttu-id="7a0c0-133">媒體旁路設定會在整個商務用 Skype Server 部署中全域套用。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="7a0c0-134">媒體旁路允許來電略過轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="7a0c0-135">如需有關何時使用媒體旁路的詳細資訊，請參閱 [Plan for media 旁路](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="7a0c0-136">您可以從商務用 Skype Server 控制台停用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="7a0c0-137">停用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="7a0c0-137">To disable media bypass</span></span>

1.  <span data-ttu-id="7a0c0-138">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7a0c0-139">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7a0c0-140">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **通用**]。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="7a0c0-141">在 **[全域]** 頁面上，按一下 **[全域]** 設定。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-141">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="7a0c0-142">永遠只有一個設定，而且永遠稱為 Global。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-142">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="7a0c0-143">在 [ **編輯** ] 功能表上，按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="7a0c0-144">在 [ **編輯通用設定** ] 頁面上，清除 [ **啟用媒體旁路** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="7a0c0-145">按一下 [ **認可** ] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="7a0c0-145">Click **Commit** to save your changes.</span></span>

  
