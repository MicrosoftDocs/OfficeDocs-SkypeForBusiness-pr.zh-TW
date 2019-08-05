---
title: 設定原則以控制公用使用者存取
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ublic 立即訊息 (IM) 連線功能可讓貴組織中的使用者使用 IM 與公用 IM 服務提供者所提供的 IM 服務使用者通訊。
ms.openlocfilehash: 230c3405a9d0a551758bee63fae8f927fdc5af19
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188848"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a><span data-ttu-id="1254b-103">在商務用 Skype Server 中設定控制公用使用者存取權的原則</span><span class="sxs-lookup"><span data-stu-id="1254b-103">Configure policies to control public user access in Skype for Business Server</span></span>

<span data-ttu-id="1254b-104">公用立即訊息 (IM) 連線功能可讓貴組織中的使用者使用 IM 與公用 IM 服務提供者所提供之 IM 服務的使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="1254b-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers.</span></span> <span data-ttu-id="1254b-105">您可以設定一或多個外部使用者存取原則, 以控制公用使用者是否可與內部商務用 Skype 伺服器使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="1254b-105">You configure one or more external user access policies to control whether public users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="1254b-106">公用立即訊息連線能力是一項額外的功能, 可依賴您的部署與使用者的設定。</span><span class="sxs-lookup"><span data-stu-id="1254b-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="1254b-107">它也取決於在公用 IM 提供者上提供服務的功能。</span><span class="sxs-lookup"><span data-stu-id="1254b-107">It also depends on the provisioning of the service at the public IM provider.</span></span> 

<span data-ttu-id="1254b-108">若要控制公用使用者的存取權, 您可以在全域、網站和使用者層級設定原則。</span><span class="sxs-lookup"><span data-stu-id="1254b-108">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="1254b-109">在一個策略層級套用的商務用 Skype 伺服器原則設定, 可以覆寫在其他原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="1254b-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="1254b-110">商務用 Skype Server 原則優先順序為: 使用者原則 (最具影響力) 會覆寫網站原則, 然後網站原則會覆寫全域原則 (最小的影響)。</span><span class="sxs-lookup"><span data-stu-id="1254b-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="1254b-111">這表示原則設定越接近策略設定的物件, 就會受到對物件的影響。</span><span class="sxs-lookup"><span data-stu-id="1254b-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="1254b-112">在 IM 邀請的情況下, 回應會視用戶端軟體而定。</span><span class="sxs-lookup"><span data-stu-id="1254b-112">In the case of IM invitations, the response depends on the client software.</span></span> <span data-ttu-id="1254b-113">除非由使用者設定的規則明確封鎖外部寄件者 (也就是使用者的用戶端**允許**及**封鎖**清單中的設定), 否則就會接受該要求。</span><span class="sxs-lookup"><span data-stu-id="1254b-113">The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists).</span></span> <span data-ttu-id="1254b-114">此外, 如果使用者想要封鎖來自不在其 [**允許**] 清單中的使用者的所有 IM, 也可以封鎖 im 邀請。</span><span class="sxs-lookup"><span data-stu-id="1254b-114">Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>



> [!NOTE]  
> <span data-ttu-id="1254b-115">您可以設定原則來控制公用使用者的存取, 即使您的組織未啟用同盟也一樣。</span><span class="sxs-lookup"><span data-stu-id="1254b-115">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="1254b-116">不過, 您設定的原則只會在您的組織啟用同盟時生效。</span><span class="sxs-lookup"><span data-stu-id="1254b-116">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="1254b-117">如需啟用同盟的詳細資料, 請參閱[啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="1254b-117">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span> <span data-ttu-id="1254b-118">此外, 如果您指定使用者原則來控制公用使用者存取, 則原則只適用于已啟用商務用 Skype Server 且設定為使用原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="1254b-118">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="1254b-119">如需有關指定可以登入商務用 Skype Server 的公用使用者的詳細資料, 請參閱[指派外部使用者存取原則](assign-an-external-user-access-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="1254b-119">For details about specifying public users that can sign in to Skype for Business Server, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>


<span data-ttu-id="1254b-120">使用下列程式來設定原則, 以支援由一或多個公用 IM 提供者的使用者存取。</span><span class="sxs-lookup"><span data-stu-id="1254b-120">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="1254b-121">設定外部存取原則以支援公用使用者存取</span><span class="sxs-lookup"><span data-stu-id="1254b-121">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="1254b-122">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="1254b-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1254b-123">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="1254b-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1254b-124">在左側導覽列中, 按一下 [**外部使用者存取**], 然後按一下 [**外部存取原則**]。</span><span class="sxs-lookup"><span data-stu-id="1254b-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="1254b-125">在 [**外部存取原則**] 頁面上, 執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="1254b-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="1254b-126">若要設定全域原則以支援公用使用者存取, 請按一下全域原則, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="1254b-126">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="1254b-127">若要建立新的網站原則, 請按一下 [**新增**], 然後按一下 [**網站原則**]。</span><span class="sxs-lookup"><span data-stu-id="1254b-127">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="1254b-128">在 [**選取網站**] 中, 從清單中按一下適當的網站, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1254b-128">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="1254b-129">若要建立新的使用者原則, 請按一下 [**新增**], 然後按一下 [**使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="1254b-129">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="1254b-130">在**新的外部存取原則**中, 在 [name] (**名稱**) 欄位中建立唯一的名稱, 以指出使用者原則所涵蓋的內容 (例如, 可為公用使用者進行通訊的使用者原則的**EnablePublicUsers** )。</span><span class="sxs-lookup"><span data-stu-id="1254b-130">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="1254b-131">若要變更現有的原則, 請按一下表格中所列的適當原則, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="1254b-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1254b-132">可選如果您想要新增或編輯描述, 請在 [**描述**] 中指定原則的資訊。</span><span class="sxs-lookup"><span data-stu-id="1254b-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="1254b-133">請執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="1254b-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="1254b-134">若要針對原則啟用公用使用者存取, 請選取 [**啟用與公用使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1254b-134">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="1254b-135">若要停用公用使用者對原則的存取權, 請清除 [**啟用與公用使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1254b-135">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="1254b-136">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1254b-136">Click **Commit**.</span></span>

<span data-ttu-id="1254b-137">若要啟用公用使用者存取, 您也必須在您的組織中啟用同盟支援。</span><span class="sxs-lookup"><span data-stu-id="1254b-137">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="1254b-138">如需詳細資訊, 請參閱[在商務用 Skype Server 中設定控制聯盟使用者存取權的原則](configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="1254b-138">For details, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="1254b-139">如果這是使用者原則, 您也必須將原則套用到您想要能夠與公用使用者共同作業的公用使用者。</span><span class="sxs-lookup"><span data-stu-id="1254b-139">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> 


## <a name="see-also"></a><span data-ttu-id="1254b-140">請參閱</span><span class="sxs-lookup"><span data-stu-id="1254b-140">See Also</span></span>

[<span data-ttu-id="1254b-141">管理貴組織的 SIP 聯盟提供者</span><span class="sxs-lookup"><span data-stu-id="1254b-141">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
