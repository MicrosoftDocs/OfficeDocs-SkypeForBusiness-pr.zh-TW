---
title: 設定原則以控制遠端使用者存取
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您可以設定一或多個外部使用者存取原則，以控制遠端使用者是否可以與內部商務用 Skype 伺服器使用者共同作業。 若要控制遠端使用者存取權，您可以在全域、網站和使用者層級設定原則。
ms.openlocfilehash: 7735f15e61654f55a70f18ca032cd6b1613fec58
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818294"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="088db-104">在商務用 Skype Server 中設定控制遠端使用者存取權的原則</span><span class="sxs-lookup"><span data-stu-id="088db-104">Configure policies to control remote user access in Skype for Business Server</span></span>

<span data-ttu-id="088db-105">您可以設定一或多個外部使用者存取原則，以控制遠端使用者是否可以與內部商務用 Skype 伺服器使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="088db-105">You configure one or more external user access policies to control whether remote users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="088db-106">若要控制遠端使用者存取權，您可以在全域、網站和使用者層級設定原則。</span><span class="sxs-lookup"><span data-stu-id="088db-106">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="088db-107">網站原則會覆寫全域原則，而使用者原則會覆寫網站和全域原則。</span><span class="sxs-lookup"><span data-stu-id="088db-107">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="088db-108">如需有關您可以設定之原則類型的詳細資料，請參閱[管理商務用 Skype Server 的同盟及外部存取](../managing-federation-and-external-access.md)。</span><span class="sxs-lookup"><span data-stu-id="088db-108">For details about the types of policies that you can configure, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span> <span data-ttu-id="088db-109">在一個策略層級套用的商務用 Skype 伺服器原則設定，可以覆寫在其他原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="088db-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="088db-110">商務用 Skype Server 原則優先順序為：使用者原則（最具影響力）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。</span><span class="sxs-lookup"><span data-stu-id="088db-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="088db-111">這表示原則設定越接近策略設定的物件，就會受到對物件的影響。</span><span class="sxs-lookup"><span data-stu-id="088db-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

> [!NOTE]  
> <span data-ttu-id="088db-112">您可以設定控制遠端使用者存取的原則，即使您的組織未啟用遠端使用者存取權也一樣。</span><span class="sxs-lookup"><span data-stu-id="088db-112">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="088db-113">不過，您設定的原則只會在您的組織啟用遠端使用者存取時生效。</span><span class="sxs-lookup"><span data-stu-id="088db-113">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="088db-114">此外，如果您指定使用者原則來控制遠端使用者存取，則原則只適用于已啟用商務用 Skype Server 且設定為使用原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="088db-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="088db-115">如需指定可從遠端位置登入商務用 Skype 伺服器的使用者的詳細資料，請參閱[指派外部使用者存取原則](assign-an-external-user-access-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="088db-115">For details about specifying users that can sign in to Skype for Business Server from remote locations, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

<span data-ttu-id="088db-116">使用下列程式來設定您要用來控制遠端使用者存取權的每個外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="088db-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>


> [!NOTE]  
> <span data-ttu-id="088db-117">這個程式說明如何設定原則，只讓它能夠與遠端使用者通訊，但您設定支援遠端使用者存取的每個原則也都可以設定聯盟使用者存取與公用使用者存取。</span><span class="sxs-lookup"><span data-stu-id="088db-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="088db-118">如需有關設定支援同盟使用者之原則的詳細資訊，請參閱[在商務用 Skype Server 中設定控制聯盟使用者存取權的原則](configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="088db-118">For details about configuring policies to support federated users, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span> <span data-ttu-id="088db-119">如需有關設定原則以支援公用使用者的詳細資料，請參閱[在商務用 Skype Server 中管理貴組織的 SIP 同盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="088db-119">For details about configuring policies to support public users, see [Manage SIP federated providers for your organization in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="088db-120">設定外部存取原則以支援遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="088db-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="088db-121">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="088db-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="088db-122">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="088db-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="088db-123">在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**外部存取原則**]。</span><span class="sxs-lookup"><span data-stu-id="088db-123">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="088db-124">在 [**外部存取原則**] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="088db-124">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="088db-125">若要設定全域原則以支援遠端使用者存取，請按一下全域原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="088db-125">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="088db-126">若要建立新的網站原則，請按一下 [**新增**]，然後按一下 [**網站原則**]。</span><span class="sxs-lookup"><span data-stu-id="088db-126">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="088db-127">在 [**選取網站**] 中，從清單中按一下適當的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="088db-127">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="088db-128">若要建立新的使用者原則，請按一下 [**新增**]，然後按一下 [**使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="088db-128">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="088db-129">在**新的外部存取原則**中，在 [name] （**名稱**）欄位中建立一個代表使用者原則所涵蓋內容的唯一名稱（例如，為遠端使用者啟用通訊的使用者原則的**EnableRemoteUsers** ）。</span><span class="sxs-lookup"><span data-stu-id="088db-129">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="088db-130">若要變更現有的原則，請按一下表格中所列的適當原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="088db-130">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="088db-131">可選如果您想要新增或編輯描述，請在 [**描述**] 中指定原則的資訊。</span><span class="sxs-lookup"><span data-stu-id="088db-131">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="088db-132">請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="088db-132">Do one of the following:</span></span>
    
      - <span data-ttu-id="088db-133">若要啟用此原則的遠端使用者存取權，請選取 [**啟用與遠端使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="088db-133">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="088db-134">若要停用遠端使用者對原則的存取權，請清除 [**啟用與遠端使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="088db-134">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="088db-135">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="088db-135">Click **Commit**.</span></span>

<span data-ttu-id="088db-136">若要啟用遠端使用者存取，您也必須在您的組織中啟用遠端使用者存取的支援。</span><span class="sxs-lookup"><span data-stu-id="088db-136">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="088db-137">如需詳細資訊，請參閱[啟用或停用同盟與公用 IM](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)連線。</span><span class="sxs-lookup"><span data-stu-id="088db-137">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="088db-138">如果這是使用者原則，您也必須將原則套用到您想要能夠遠端連線的使用者。</span><span class="sxs-lookup"><span data-stu-id="088db-138">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="088db-139">如需詳細資訊，請參閱[指派外部使用者存取原則](assign-an-external-user-access-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="088db-139">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>
