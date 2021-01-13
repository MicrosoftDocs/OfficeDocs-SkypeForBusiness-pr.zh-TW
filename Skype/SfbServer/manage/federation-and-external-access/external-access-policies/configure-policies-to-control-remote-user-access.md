---
title: 設定控制遠端使用者存取的原則
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您可以設定一或多個外部使用者存取原則，以控制遠端使用者是否可以與內部商務用 Skype Server 使用者共同作業。 若要控制遠端使用者存取，您可以在全域、網站及使用者層級設定原則。
ms.openlocfilehash: 0fd24f7c57cfaa4a131bcd1648cb1b6e6eb5f05a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817293"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="ec0be-104">在商務用 Skype Server 中設定原則以控制遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="ec0be-104">Configure policies to control remote user access in Skype for Business Server</span></span>

<span data-ttu-id="ec0be-105">您可以設定一或多個外部使用者存取原則，以控制遠端使用者是否可以與內部商務用 Skype Server 使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="ec0be-105">You configure one or more external user access policies to control whether remote users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="ec0be-106">若要控制遠端使用者存取，您可以在全域、網站及使用者層級設定原則。</span><span class="sxs-lookup"><span data-stu-id="ec0be-106">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="ec0be-107">網站原則會覆寫全域原則，而使用者原則會覆寫網站和全域原則。</span><span class="sxs-lookup"><span data-stu-id="ec0be-107">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="ec0be-108">如需您可以設定之原則類型的詳細資訊，請參閱 [管理同盟和外部存取商務用 Skype Server](../managing-federation-and-external-access.md)。</span><span class="sxs-lookup"><span data-stu-id="ec0be-108">For details about the types of policies that you can configure, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span> <span data-ttu-id="ec0be-109">在一個原則層級套用的商務用 Skype 伺服器原則設定，可以覆寫在另一個原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="ec0be-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="ec0be-110">商務用 Skype Server 原則優先順序為：使用者原則 (影響最大) 會覆寫網站原則，然後網站原則會覆寫全域原則 (影響最小)。</span><span class="sxs-lookup"><span data-stu-id="ec0be-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="ec0be-111">也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。</span><span class="sxs-lookup"><span data-stu-id="ec0be-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

> [!NOTE]  
> <span data-ttu-id="ec0be-112">即使您沒有為組織啟用遠端使用者存取，您也可以設定原則來控制遠端使用者存取。</span><span class="sxs-lookup"><span data-stu-id="ec0be-112">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="ec0be-113">不過，您設定的原則只有當您為組織啟用遠端使用者存取時才會生效。</span><span class="sxs-lookup"><span data-stu-id="ec0be-113">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="ec0be-114">此外，如果您指定用來控制遠端使用者存取的使用者原則，此原則只適用于已啟用商務用 Skype 伺服器的使用者，且設定為使用原則。</span><span class="sxs-lookup"><span data-stu-id="ec0be-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="ec0be-115">如需指定可以從遠端位置登入商務用 Skype Server 之使用者的詳細資訊，請參閱 [指派外部使用者存取原則](assign-an-external-user-access-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="ec0be-115">For details about specifying users that can sign in to Skype for Business Server from remote locations, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

<span data-ttu-id="ec0be-116">使用下列程式可設定每個要用來控制遠端使用者存取的外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="ec0be-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>


> [!NOTE]  
> <span data-ttu-id="ec0be-117">此程式說明如何設定原則，只啟用與遠端使用者的通訊，但設定為支援遠端使用者存取的每個原則也可以設定同盟使用者存取和公用使用者存取。</span><span class="sxs-lookup"><span data-stu-id="ec0be-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="ec0be-118">如需設定支援同盟使用者之原則的詳細資訊，請參閱 [在商務用 Skype Server 中設定原則以控制同盟使用者存取](configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="ec0be-118">For details about configuring policies to support federated users, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span> <span data-ttu-id="ec0be-119">如需設定原則以支援公用使用者的詳細資訊，請參閱 [在商務用 Skype Server 中管理組織的 SIP 同盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="ec0be-119">For details about configuring policies to support public users, see [Manage SIP federated providers for your organization in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="ec0be-120">設定外部存取原則以支援遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="ec0be-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="ec0be-121">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="ec0be-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ec0be-122">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="ec0be-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ec0be-123">在左導覽列中，依序按一下 [外部使用者存取] 及 [外部存取原則]。</span><span class="sxs-lookup"><span data-stu-id="ec0be-123">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="ec0be-124">在「外部存取原則」頁面中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="ec0be-124">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="ec0be-125">若要設定全域原則以支援遠端使用者存取，請按一下全域原則，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="ec0be-125">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="ec0be-p105">若要建立新的網站原則，請按一下 **[新增]**，然後按一下 **[站台原則]**。在 **[選取站台]** 的清單中按一下適當網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ec0be-p105">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="ec0be-128">若要建立新的使用者原則，按一下 **[新增]**，再按一下 **[使用者原則]**。</span><span class="sxs-lookup"><span data-stu-id="ec0be-128">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="ec0be-129">在 [ **新增外部存取原則**] 中，在 [ **名稱** ] 欄位中建立唯一的名稱，以指出使用者原則所涵蓋的內容 (例如，針對為遠端使用者) 啟用通訊的使用者原則，請 **EnableRemoteUsers** 。</span><span class="sxs-lookup"><span data-stu-id="ec0be-129">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="ec0be-130">若要變更現有原則，按一下表中所列之適當原則，然後按一下 [編輯]，接著按一下 [顯示詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="ec0be-130">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="ec0be-131">(選用) 如果您想要新增或編輯說明，請在 [說明] 中指定原則資訊。</span><span class="sxs-lookup"><span data-stu-id="ec0be-131">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="ec0be-132">執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="ec0be-132">Do one of the following:</span></span>
    
      - <span data-ttu-id="ec0be-133">若要啟用原則的遠端使用者存取，請選取 [ **啟用與遠端使用者的通訊** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ec0be-133">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="ec0be-134">若要停用原則的遠端使用者存取，請清除 [ **啟用與遠端使用者的通訊** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ec0be-134">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="ec0be-135">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="ec0be-135">Click **Commit**.</span></span>

<span data-ttu-id="ec0be-136">若要啟用遠端使用者存取，您也必須啟用組織中遠端使用者存取的支援。</span><span class="sxs-lookup"><span data-stu-id="ec0be-136">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="ec0be-137">如需詳細資訊，請參閱 [Enable or disable federation and PUBLIC IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="ec0be-137">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="ec0be-138">如果這是使用者原則，您也必須將原則套用至您要能夠遠端連線的使用者。</span><span class="sxs-lookup"><span data-stu-id="ec0be-138">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="ec0be-139">如需詳細資訊，請參閱 [指派外部使用者存取原則](assign-an-external-user-access-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="ec0be-139">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>
