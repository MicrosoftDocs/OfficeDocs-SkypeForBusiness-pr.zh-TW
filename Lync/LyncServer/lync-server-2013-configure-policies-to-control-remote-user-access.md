---
title: Lync Server 2013：設定原則以控制遠端使用者存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6e542f2a2d836cce507863347384135f97db445
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="d0c0f-102">在 Lync Server 2013 中設定原則以控制遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="d0c0f-102">Configure policies to control remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0c0f-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="d0c0f-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="d0c0f-104">您可以設定一或多個外部使用者存取原則，以控制遠端使用者是否可以與內部 Lync Server 使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-104">You configure one or more external user access policies to control whether remote users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="d0c0f-105">若要控制遠端使用者存取權，您可以在全域、網站和使用者層級設定原則。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-105">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="d0c0f-106">網站原則會覆寫全域原則，而使用者原則會覆寫網站和全域原則。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-106">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="d0c0f-107">如需有關您可以設定之原則類型的詳細資料，請參閱[管理 Lync Server 2013 的同盟與外部存取](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-107">For details about the types of policies that you can configure, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span> <span data-ttu-id="d0c0f-108">在一個策略層級套用的 Lync Server 原則設定，可以覆寫在其他原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-108">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="d0c0f-109">Lync 伺服器策略優先順序為：使用者原則（最大影響）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-109">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="d0c0f-110">這表示原則設定越接近策略設定的物件，就會受到對物件的影響。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d0c0f-111">您可以設定控制遠端使用者存取的原則，即使您的組織未啟用遠端使用者存取權也一樣。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-111">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="d0c0f-112">不過，您設定的原則只會在您的組織啟用遠端使用者存取時生效。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-112">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="d0c0f-113">如需有關啟用遠端使用者存取權的詳細資料，請參閱<A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM</A>連線。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-113">For details about enabling remote user access, see <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</A>.</span></span> <span data-ttu-id="d0c0f-114">此外，如果您指定使用者原則來控制遠端使用者存取，則原則只適用于已啟用 Lync Server 且設定為使用原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="d0c0f-115">如需指定可從遠端位置登入 Lync Server 的使用者的詳細資料，請參閱<A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">在 Lync server 2013 中將外部使用者存取原則指派給 lync 啟用的使用者</A>。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-115">For details about specifying users that can sign in to Lync Server from remote locations, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="d0c0f-116">使用下列程式來設定您要用來控制遠端使用者存取權的每個外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d0c0f-117">這個程式說明如何設定原則，只讓它能夠與遠端使用者通訊，但您設定支援遠端使用者存取的每個原則也都可以設定聯盟使用者存取與公用使用者存取。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="d0c0f-118">如需有關設定支援同盟使用者之原則的詳細資訊，請參閱<A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中設定控制聯盟使用者存取權的原則</A>。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-118">For details about configuring policies to support federated users, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="d0c0f-119">如需有關設定支援公用使用者之原則的詳細資訊，請參閱<A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中建立或編輯公用 SIP 同盟提供者</A>。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-119">For details about configuring policies to support public users, see <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="d0c0f-120">設定外部存取原則以支援遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="d0c0f-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="d0c0f-121">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d0c0f-122">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d0c0f-123">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d0c0f-124">在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**外部存取原則**]。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="d0c0f-125">在 [**外部存取原則**] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="d0c0f-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="d0c0f-126">若要設定全域原則以支援遠端使用者存取，請按一下全域原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-126">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="d0c0f-127">若要建立新的網站原則，請按一下 [**新增**]，然後按一下 [**網站原則**]。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-127">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="d0c0f-128">在 [**選取網站**] 中，從清單中按一下適當的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-128">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="d0c0f-129">若要建立新的使用者原則，請按一下 [**新增**]，然後按一下 [**使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-129">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="d0c0f-130">在**新的外部存取原則**中，在 [name] （**名稱**）欄位中建立一個代表使用者原則所涵蓋內容的唯一名稱（例如，為遠端使用者啟用通訊的使用者原則的**EnableRemoteUsers** ）。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-130">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="d0c0f-131">若要變更現有的原則，請按一下表格中所列的適當原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="d0c0f-132">可選如果您想要新增或編輯描述，請在 [**描述**] 中指定原則的資訊。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="d0c0f-133">請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="d0c0f-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="d0c0f-134">若要啟用此原則的遠端使用者存取權，請選取 [**啟用與遠端使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-134">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="d0c0f-135">若要停用遠端使用者對原則的存取權，請清除 [**啟用與遠端使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-135">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="d0c0f-136">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-136">Click **Commit**.</span></span>

<span data-ttu-id="d0c0f-137">若要啟用遠端使用者存取，您也必須在您的組織中啟用遠端使用者存取的支援。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-137">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="d0c0f-138">如需詳細資訊，請參閱在部署檔或操作檔中[啟用或停用 Lync Server 2013 中的同盟與公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-138">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="d0c0f-139">如果這是使用者原則，您也必須將原則套用到您想要能夠遠端連線的使用者。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-139">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="d0c0f-140">如需詳細資訊，請參閱在部署檔或操作檔中，[將外部使用者存取原則指派給 Lync Server 2013 中的 lync 啟用使用者](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-140">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

