---
title: Lync Server 2013：設定原則以控制公用使用者存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e259082aa73d4354e8e4aa93eb7a0cc8d7ed7a6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a><span data-ttu-id="b605b-102">在 Lync Server 2013 中設定原則以控制公用使用者存取</span><span class="sxs-lookup"><span data-stu-id="b605b-102">Configure policies to control public user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b605b-103">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="b605b-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="b605b-104">公用立即訊息（IM）連線功能可讓貴組織中的使用者使用 IM 與公用 IM 服務提供者所提供之 IM 服務的使用者通訊，包括 Internet 服務、Yahoo\!和 AOL 提供的 Windows Live 網路。</span><span class="sxs-lookup"><span data-stu-id="b605b-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live network of Internet services, Yahoo\!, and AOL.</span></span> <span data-ttu-id="b605b-105">您可以設定一或多個外部使用者存取原則，以控制公用使用者是否可與內部 Lync 伺服器使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="b605b-105">You configure one or more external user access policies to control whether public users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="b605b-106">公用立即訊息連線能力是一項額外的功能，可依賴您的部署與使用者的設定。</span><span class="sxs-lookup"><span data-stu-id="b605b-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="b605b-107">它也取決於在公用 IM 提供者上提供服務的功能。</span><span class="sxs-lookup"><span data-stu-id="b605b-107">It also depends on the provisioning of the service at the public IM provider.</span></span> <span data-ttu-id="b605b-108">如需如何將您的部署設定為使用公用提供者的相關資訊，請參閱「適用于 Microsoft Lync Server、Office 通訊伺服器與即時通訊伺服器的公用 IM 連線設定指南」指南：[http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)</span><span class="sxs-lookup"><span data-stu-id="b605b-108">For information on how to provision your deployment to use the public providers, see the “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” guide: [http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="b605b-109">從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。</span><span class="sxs-lookup"><span data-stu-id="b605b-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="b605b-110">擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="b605b-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="b605b-111">信使，直到服務關閉日期為止。</span><span class="sxs-lookup"><span data-stu-id="b605b-111">Messenger until the service shut down date.</span></span> <span data-ttu-id="b605b-112">AOL 和 Yahoo！的存留期結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="b605b-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="b605b-113">已公佈。</span><span class="sxs-lookup"><span data-stu-id="b605b-113">has been announced.</span></span> <span data-ttu-id="b605b-114">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</span><span class="sxs-lookup"><span data-stu-id="b605b-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="b605b-115">PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="b605b-115">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="b605b-116">名單.</span><span class="sxs-lookup"><span data-stu-id="b605b-116">Messenger.</span></span> <span data-ttu-id="b605b-117">Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</span><span class="sxs-lookup"><span data-stu-id="b605b-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="b605b-118">Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。</span><span class="sxs-lookup"><span data-stu-id="b605b-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="b605b-119">與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="b605b-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="b605b-120">您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="b605b-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="b605b-121">若要存取 Microsoft Lync Server 公用 IM 連線提供網站，請使用下列連結：[http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)</span><span class="sxs-lookup"><span data-stu-id="b605b-121">To access the Microsoft Lync Server Public IM Connectivity Provisioning site, use the following link: [http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)</span></span>

<span data-ttu-id="b605b-122">若要控制公用使用者的存取權，您可以在全域、網站和使用者層級設定原則。</span><span class="sxs-lookup"><span data-stu-id="b605b-122">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="b605b-123">如需有關您可以設定之原則類型的詳細資料，請參閱在部署檔或規劃檔中，設定[Lync Server 2013 中的外部使用者存取支援](lync-server-2013-configuring-support-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="b605b-123">For details about the types of policies that you can configure, see [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in the Deployment documentation or the Planning documentation.</span></span> <span data-ttu-id="b605b-124">在一個策略層級套用的 Lync Server 原則設定，可以覆寫在其他原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="b605b-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="b605b-125">Lync 伺服器策略優先順序為：使用者原則（最大影響）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。</span><span class="sxs-lookup"><span data-stu-id="b605b-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="b605b-126">這表示原則設定越接近策略設定的物件，就會受到對物件的影響。</span><span class="sxs-lookup"><span data-stu-id="b605b-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="b605b-127">在 IM 邀請的情況下，回應會視用戶端軟體而定。</span><span class="sxs-lookup"><span data-stu-id="b605b-127">In the case of IM invitations, the response depends on the client software.</span></span> <span data-ttu-id="b605b-128">除非由使用者設定的規則明確封鎖外部寄件者（也就是使用者的用戶端**允許**及**封鎖**清單中的設定），否則就會接受該要求。</span><span class="sxs-lookup"><span data-stu-id="b605b-128">The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists).</span></span> <span data-ttu-id="b605b-129">此外，如果使用者想要封鎖來自不在其 [**允許**] 清單中的使用者的所有 IM，也可以封鎖 im 邀請。</span><span class="sxs-lookup"><span data-stu-id="b605b-129">Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b605b-130">您可以設定原則來控制公用使用者的存取，即使您的組織未啟用同盟也一樣。</span><span class="sxs-lookup"><span data-stu-id="b605b-130">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="b605b-131">不過，您設定的原則只會在您的組織啟用同盟時生效。</span><span class="sxs-lookup"><span data-stu-id="b605b-131">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="b605b-132">如需啟用同盟的詳細資料，請參閱在部署檔或操作檔中<A href="lync-server-2013-enable-or-disable-remote-user-access.md">啟用或停用 Lync Server 2013 中的遠端使用者存取</A>。</span><span class="sxs-lookup"><span data-stu-id="b605b-132">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="b605b-133">此外，如果您指定使用者原則來控制公用使用者存取，則原則只適用于已啟用 Lync Server 且設定為使用原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="b605b-133">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="b605b-134">如需指定可以登入 Lync Server 之公用使用者的詳細資料，請參閱在部署檔或操作檔中，<A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">將外部使用者存取原則指派給 Lync server 2013 中的 lync 啟用使用者</A>。</span><span class="sxs-lookup"><span data-stu-id="b605b-134">For details about specifying public users that can sign in to Lync Server, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<span data-ttu-id="b605b-135">使用下列程式來設定原則，以支援由一或多個公用 IM 提供者的使用者存取。</span><span class="sxs-lookup"><span data-stu-id="b605b-135">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="b605b-136">設定外部存取原則以支援公用使用者存取</span><span class="sxs-lookup"><span data-stu-id="b605b-136">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="b605b-137">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b605b-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b605b-138">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="b605b-138">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b605b-139">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="b605b-139">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b605b-140">在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**外部存取原則**]。</span><span class="sxs-lookup"><span data-stu-id="b605b-140">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="b605b-141">在 [**外部存取原則**] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="b605b-141">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="b605b-142">若要設定全域原則以支援公用使用者存取，請按一下全域原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="b605b-142">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="b605b-143">若要建立新的網站原則，請按一下 [**新增**]，然後按一下 [**網站原則**]。</span><span class="sxs-lookup"><span data-stu-id="b605b-143">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="b605b-144">在 [**選取網站**] 中，從清單中按一下適當的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b605b-144">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="b605b-145">若要建立新的使用者原則，請按一下 [**新增**]，然後按一下 [**使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="b605b-145">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="b605b-146">在**新的外部存取原則**中，在 [name] （**名稱**）欄位中建立唯一的名稱，以指出使用者原則所涵蓋的內容（例如，可為公用使用者進行通訊的使用者原則的**EnablePublicUsers** ）。</span><span class="sxs-lookup"><span data-stu-id="b605b-146">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="b605b-147">若要變更現有的原則，請按一下表格中所列的適當原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="b605b-147">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b605b-148">可選如果您想要新增或編輯描述，請在 [**描述**] 中指定原則的資訊。</span><span class="sxs-lookup"><span data-stu-id="b605b-148">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="b605b-149">請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="b605b-149">Do one of the following:</span></span>
    
      - <span data-ttu-id="b605b-150">若要針對原則啟用公用使用者存取，請選取 [**啟用與公用使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b605b-150">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="b605b-151">若要停用公用使用者對原則的存取權，請清除 [**啟用與公用使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b605b-151">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="b605b-152">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b605b-152">Click **Commit**.</span></span>

<span data-ttu-id="b605b-153">若要啟用公用使用者存取，您也必須在您的組織中啟用同盟支援。</span><span class="sxs-lookup"><span data-stu-id="b605b-153">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="b605b-154">如需詳細資訊，請參閱[在 Lync Server 2013 中設定控制聯盟使用者存取權的原則](lync-server-2013-configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="b605b-154">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="b605b-155">如果這是使用者原則，您也必須將原則套用到您想要能夠與公用使用者共同作業的公用使用者。</span><span class="sxs-lookup"><span data-stu-id="b605b-155">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> <span data-ttu-id="b605b-156">如需詳細資訊，請參閱[在 Lync Server 2013 中指派每個使用者的原則](lync-server-2013-assigning-per-user-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b605b-156">For details, see [Assigning per-user policies in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b605b-157">請參閱</span><span class="sxs-lookup"><span data-stu-id="b605b-157">See Also</span></span>


[<span data-ttu-id="b605b-158">在 Lync Server 2013 中建立或編輯公用 SIP 同盟提供者</span><span class="sxs-lookup"><span data-stu-id="b605b-158">Create or edit public SIP federated providers in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[<span data-ttu-id="b605b-159">在 Lync Server 2013 中管理組織的 SIP 同盟提供者</span><span class="sxs-lookup"><span data-stu-id="b605b-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

