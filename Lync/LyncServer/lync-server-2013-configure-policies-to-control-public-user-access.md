---
title: Lync Server 2013：設定原則以控制公用使用者存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54c92e1da5ea1ea54ae8386cdcdce5054d76609e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a><span data-ttu-id="c38b7-102">在 Lync Server 2013 中設定原則以控制公用使用者存取</span><span class="sxs-lookup"><span data-stu-id="c38b7-102">Configure policies to control public user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c38b7-103">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="c38b7-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="c38b7-104">公用立即訊息 (IM) 連線功能，讓組織中的使用者能夠使用 IM 與公用 IM 服務提供者所提供的 IM 服務使用者通訊，包括 Internet 服務、Yahoo 和 AOL 的 Windows Live 網路 \! 。</span><span class="sxs-lookup"><span data-stu-id="c38b7-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live network of Internet services, Yahoo\!, and AOL.</span></span> <span data-ttu-id="c38b7-105">您可以設定一或多個外部使用者存取原則，以控制公用使用者是否可以與內部 Lync Server 使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="c38b7-105">You configure one or more external user access policies to control whether public users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="c38b7-106">公用立即訊息連線功能是一項附加的功能，可依賴您的部署和使用者的設定。</span><span class="sxs-lookup"><span data-stu-id="c38b7-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="c38b7-107">它也取決於公用 IM 提供者的服務布建。</span><span class="sxs-lookup"><span data-stu-id="c38b7-107">It also depends on the provisioning of the service at the public IM provider.</span></span> <span data-ttu-id="c38b7-108">如需如何布建部署以使用公用提供者的詳細資訊，請參閱《 Microsoft Lync Server、Office 通訊伺服器和即時通訊伺服器的公用 IM 連線布建指南》指南： [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span><span class="sxs-lookup"><span data-stu-id="c38b7-108">For information on how to provision your deployment to use the public providers, see the “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” guide: [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="c38b7-109">從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。</span><span class="sxs-lookup"><span data-stu-id="c38b7-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="c38b7-110">具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="c38b7-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="c38b7-111">信使直到服務關閉日期。</span><span class="sxs-lookup"><span data-stu-id="c38b7-111">Messenger until the service shut down date.</span></span> <span data-ttu-id="c38b7-112">AOL 和 Yahoo！的循環結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="c38b7-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="c38b7-113">已宣告。</span><span class="sxs-lookup"><span data-stu-id="c38b7-113">has been announced.</span></span> <span data-ttu-id="c38b7-114">如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</span><span class="sxs-lookup"><span data-stu-id="c38b7-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="c38b7-115">PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="c38b7-115">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="c38b7-116">信使。</span><span class="sxs-lookup"><span data-stu-id="c38b7-116">Messenger.</span></span> <span data-ttu-id="c38b7-117">Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</span><span class="sxs-lookup"><span data-stu-id="c38b7-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="c38b7-118">Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。</span><span class="sxs-lookup"><span data-stu-id="c38b7-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="c38b7-119">與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="c38b7-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="c38b7-120">隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</span><span class="sxs-lookup"><span data-stu-id="c38b7-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="c38b7-121">若要存取 Microsoft Lync Server 公用 IM 連線布建網站，請使用下列連結： [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span><span class="sxs-lookup"><span data-stu-id="c38b7-121">To access the Microsoft Lync Server Public IM Connectivity Provisioning site, use the following link: [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span></span>

<span data-ttu-id="c38b7-122">若要控制公用使用者存取權，您可以在全域、網站和使用者層級設定原則。</span><span class="sxs-lookup"><span data-stu-id="c38b7-122">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="c38b7-123">如需您可以設定之原則類型的詳細資訊，請參閱部署檔或規劃檔中的在 [Lync Server 2013 中設定外部使用者存取的支援](lync-server-2013-configuring-support-for-external-user-access.md) 。</span><span class="sxs-lookup"><span data-stu-id="c38b7-123">For details about the types of policies that you can configure, see [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in the Deployment documentation or the Planning documentation.</span></span> <span data-ttu-id="c38b7-124">套用於一個原則層級的 Lync Server 原則設定可以覆寫在另一個原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="c38b7-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="c38b7-125">Lync Server 原則優先順序是：使用者原則 (最大的影響) 覆寫網站原則，然後網站原則會覆寫全域原則 (最小影響) 。</span><span class="sxs-lookup"><span data-stu-id="c38b7-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="c38b7-126">也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。</span><span class="sxs-lookup"><span data-stu-id="c38b7-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="c38b7-p106">在 IM 邀請方面，回應將視用戶端軟體而定。除非使用者設定的規則 (亦即，在使用者用戶端的 [允許]\*\*\*\* 和 [封鎖]\*\*\*\* 清單中) 明確封鎖外部傳送者，否則會接受要求。另外，如果使用者已選擇封鎖所有不在其 [允許]\*\*\*\* 清單內的 IM 使用者，IM 邀請也會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="c38b7-p106">In the case of IM invitations, the response depends on the client software. The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists). Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c38b7-130">即便您並未對所屬組織啟用同盟關係，仍可設定原則來控制公用使用者存取。</span><span class="sxs-lookup"><span data-stu-id="c38b7-130">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="c38b7-131">不過，只有當您為組織啟用同盟關係時，所設定的原則才會生效。</span><span class="sxs-lookup"><span data-stu-id="c38b7-131">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="c38b7-132">如需啟用同盟的詳細資訊，請參閱部署檔或作業檔中的 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">啟用或停用 Lync Server 2013 中的遠端使用者存取</A> 。</span><span class="sxs-lookup"><span data-stu-id="c38b7-132">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="c38b7-133">此外，如果您指定用來控制公用使用者存取的使用者原則，此原則只適用于已啟用 Lync Server 且設定為使用原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="c38b7-133">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="c38b7-134">如需指定可登入 Lync Server 之公用使用者的詳細資訊，請參閱部署檔或作業檔中的 <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">指派外部使用者存取原則給 Lync server 2013 中的 lync 啟用使用者</A> 。</span><span class="sxs-lookup"><span data-stu-id="c38b7-134">For details about specifying public users that can sign in to Lync Server, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<span data-ttu-id="c38b7-135">請使用下列步驟來設定原則，以支援一個或多個公用 IM 提供者的使用者存取。</span><span class="sxs-lookup"><span data-stu-id="c38b7-135">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="c38b7-136">設定外部存取原則以支援公用使用者存取</span><span class="sxs-lookup"><span data-stu-id="c38b7-136">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="c38b7-137">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c38b7-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c38b7-138">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="c38b7-138">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c38b7-139">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c38b7-139">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c38b7-140">在左導覽列中，依序按一下 [外部使用者存取]\*\*\*\* 及 [外部存取原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c38b7-140">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="c38b7-141">在「外部存取原則」\*\*\*\* 頁面中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="c38b7-141">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="c38b7-142">若要設定全域原則以支援公用使用者存取，依序按一下全域原則、[編輯]\*\*\*\* 和 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c38b7-142">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="c38b7-p109">若要建立新的網站原則，請按一下 [新增]\*\*\*\*，然後按一下 [站台原則]\*\*\*\*。在 [選取站台]\*\*\*\* 的清單中按一下適當網站，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c38b7-p109">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="c38b7-p110">若要建立新的使用者原則，按一下 [新增]\*\*\*\*，再按一下 [使用者原則]\*\*\*\*。在 [新的外部存取原則]\*\*\*\* 中，於 [名稱]\*\*\*\* 欄位中建立唯一名稱以代表使用者原則的涵蓋範圍 (例如，建立 **EnablePublicUsers** 的使用者原則以啟用公用使用者的通訊功能)。</span><span class="sxs-lookup"><span data-stu-id="c38b7-p110">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="c38b7-147">若要變更現有原則，按一下表中所列之適當原則，然後按一下 [編輯]\*\*\*\*，接著按一下 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c38b7-147">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c38b7-148">(選用) 如果您想要新增或編輯說明，請在 [說明]\*\*\*\* 中指定原則資訊。</span><span class="sxs-lookup"><span data-stu-id="c38b7-148">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="c38b7-149">執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="c38b7-149">Do one of the following:</span></span>
    
      - <span data-ttu-id="c38b7-150">若要啟用原則的公用使用者存取功能，請選取 [啟用與公用使用者的通訊]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c38b7-150">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="c38b7-151">若要停用原則的公用使用者存取功能，請清除 [啟用與公用使用者的通訊]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c38b7-151">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="c38b7-152">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="c38b7-152">Click **Commit**.</span></span>

<span data-ttu-id="c38b7-153">若要啟用公用使用者存取功能，則您必須同時對組織啟用同盟關係支援。</span><span class="sxs-lookup"><span data-stu-id="c38b7-153">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="c38b7-154">如需詳細資訊，請參閱 [Configure 原則 to control 同盟 user access In Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="c38b7-154">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="c38b7-155">如果這是使用者原則，您也必須將該原則套用至您希望能夠與公用使用者共同作業的公用使用者。</span><span class="sxs-lookup"><span data-stu-id="c38b7-155">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> <span data-ttu-id="c38b7-156">如需詳細資訊，請參閱 [在 Lync Server 2013 中指派每個使用者的原則](lync-server-2013-assigning-per-user-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c38b7-156">For details, see [Assigning per-user policies in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c38b7-157">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c38b7-157">See Also</span></span>


[<span data-ttu-id="c38b7-158">在 Lync Server 2013 中建立或編輯公用 SIP 同盟提供者</span><span class="sxs-lookup"><span data-stu-id="c38b7-158">Create or edit public SIP federated providers in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[<span data-ttu-id="c38b7-159">在 Lync Server 2013 中管理組織的 SIP 同盟提供者</span><span class="sxs-lookup"><span data-stu-id="c38b7-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

