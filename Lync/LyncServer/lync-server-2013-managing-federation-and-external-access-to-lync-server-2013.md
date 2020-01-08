---
title: Lync Server 2013：管理 Lync Server 2013 的同盟與外部存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing federation and external access to Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8eb4dcf6a690e2bab7b834624fb0f695e3e770e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-federation-and-external-access-to-lync-server-2013"></a><span data-ttu-id="be16e-102">管理 Lync Server 2013 的同盟與外部存取</span><span class="sxs-lookup"><span data-stu-id="be16e-102">Managing federation and external access to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be16e-103">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="be16e-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="be16e-104">部署 Edge 伺服器或 Edge 池是支援外部使用者的第一個步驟。</span><span class="sxs-lookup"><span data-stu-id="be16e-104">Deploying an Edge Server or Edge pool is the first step to supporting external users.</span></span> <span data-ttu-id="be16e-105">如需有關部署邊緣伺服器的詳細資訊，請參閱部署檔中的[Lync Server 2013 中的 [部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)]。</span><span class="sxs-lookup"><span data-stu-id="be16e-105">For details about deploying Edge Servers, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<span data-ttu-id="be16e-106">安裝並設定 Lync Server 2013 的內部部署之後，貴組織內的內部使用者就可以與在 Active Directory 網域服務（AD DS）中擁有 SIP 帳戶的其他內部使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="be16e-106">After installing and configuring your internal deployment of Lync Server 2013, internal users in your organization can collaborate with other internal users who have SIP accounts in your Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="be16e-107">共同作業可以包括傳送及接收立即訊息，以及更新目前狀態及參與會議（也稱為「會議」）。</span><span class="sxs-lookup"><span data-stu-id="be16e-107">Collaboration can include sending and receiving instant messages, and update of presence status and participating in conferences (also known as "meetings").</span></span> <span data-ttu-id="be16e-108">您可以啟用並設定外部使用者存取權，以控制支援的外部使用者是否可與內部 Lync 伺服器使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="be16e-108">You enable and configure external user access to control whether supported external users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="be16e-109">外部使用者可以包含您部署的遠端使用者、同盟使用者（包括公用立即訊息（IM）服務提供者）、XMPP 同盟及會議中的匿名參與者。</span><span class="sxs-lookup"><span data-stu-id="be16e-109">External users can include remote users of your deployment, federated users (including supported users of public instant messaging (IM) service providers), XMPP federation and anonymous participants in conferences.</span></span>

<span data-ttu-id="be16e-110">如果您的部署包括安裝 Lync Server 2013 Edge 伺服器或邊緣池，可能的通訊類型的範圍會大大擴大，有幾個選項可供外部使用者存取、與其他 SIP 聯盟網域的成員進行通訊。SIP 聯盟提供者，並 XMPP 聯盟使用者。</span><span class="sxs-lookup"><span data-stu-id="be16e-110">If your deployment included the installation of a Lync Server 2013 Edge Server or an Edge pool, the scope of possible communication types is greatly expanded with a number of options for external user access, communication with members of other SIP federated domains, SIP federated providers, and XMPP federated users.</span></span> <span data-ttu-id="be16e-111">在設定 Edge 伺服器或 Edge 池之後，您可以啟用您想要提供的外部使用者存取類型，並設定控制外部存取的原則。</span><span class="sxs-lookup"><span data-stu-id="be16e-111">After setting up the Edge Server or Edge pool, you enable the types of external user access that you want to provide, and configure the policies to control for the external access.</span></span> <span data-ttu-id="be16e-112">在 Lync Server 2013 中，您可以使用 Lync Server [控制台]、[Lync Server 管理命令介面] 或這兩者（根據任務需求）來啟用及設定外部使用者存取與原則。</span><span class="sxs-lookup"><span data-stu-id="be16e-112">In Lync Server 2013, you enable and configure external user access and policies using the Lync Server Control Panel, the Lync Server Management Shell or both, based on the task requirements.</span></span> <span data-ttu-id="be16e-113">如需這些管理工具的詳細資訊，請參閱 Operations 檔中的[Lync server 2013 系統管理工具](lync-server-2013-lync-server-administrative-tools.md)、 [Lync Server 2013 管理 Shell](lync-server-2013-lync-server-management-shell.md)中的操作檔，以及[安裝 Lync server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)（在作業檔中）。</span><span class="sxs-lookup"><span data-stu-id="be16e-113">For details about these management tools, see [Lync Server 2013 administrative tools](lync-server-2013-lync-server-administrative-tools.md) in the Operations documentation, [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation, and [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md) in the Operations documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="be16e-114">當您設計外部使用者存取的設定與原則時，您必須瞭解原則的優先順序，以及原則的套用方式。</span><span class="sxs-lookup"><span data-stu-id="be16e-114">When you design your configuration and policies for external user access, you must understand the precedence of policies and how the policies are applied.</span></span> <span data-ttu-id="be16e-115">在一個策略層級套用的 Lync Server 原則設定，可以覆寫在其他原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="be16e-115">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="be16e-116">Lync 伺服器策略優先順序為：使用者原則（最大影響）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。</span><span class="sxs-lookup"><span data-stu-id="be16e-116">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="be16e-117">這表示原則設定越接近策略設定的物件，就會受到對物件的影響。</span><span class="sxs-lookup"><span data-stu-id="be16e-117">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="be16e-118">根據預設，不會將任何原則設定為支援外部使用者存取，包括遠端使用者存取、同盟使用者存取，即使您已為組織啟用外部使用者存取支援。</span><span class="sxs-lookup"><span data-stu-id="be16e-118">By default, no policies are configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization.</span></span> <span data-ttu-id="be16e-119">若要控制外部使用者存取的使用方式，您必須設定一或多個原則，以指定每個原則支援的外部使用者存取類型。</span><span class="sxs-lookup"><span data-stu-id="be16e-119">To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy.</span></span> <span data-ttu-id="be16e-120">這包括下列外部存取原則：</span><span class="sxs-lookup"><span data-stu-id="be16e-120">This includes the following external access policies:</span></span>

  - <span data-ttu-id="be16e-121">**全域原則**   當您部署邊緣伺服器時，就會建立全域原則。</span><span class="sxs-lookup"><span data-stu-id="be16e-121">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="be16e-122">根據預設，全域原則中不會啟用任何外部使用者存取選項。</span><span class="sxs-lookup"><span data-stu-id="be16e-122">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="be16e-123">若要支援全域層級的外部使用者存取，您可以將全域原則設定為支援一或多種類型的外部使用者存取選項。</span><span class="sxs-lookup"><span data-stu-id="be16e-123">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="be16e-124">全域原則會套用至貴組織中的所有使用者，但網站原則和使用者原則會覆寫全域原則。</span><span class="sxs-lookup"><span data-stu-id="be16e-124">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="be16e-125">如果您刪除全域原則，就不會將它移除。</span><span class="sxs-lookup"><span data-stu-id="be16e-125">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="be16e-126">相反地，您可以將其重設為預設設定。</span><span class="sxs-lookup"><span data-stu-id="be16e-126">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="be16e-127">**網站原則**   您可以建立並設定一或多個網站原則，以限制外部使用者存取特定網站的支援。</span><span class="sxs-lookup"><span data-stu-id="be16e-127">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="be16e-128">網站原則中的設定優先於全域原則，但僅限該網站原則所涵蓋的特定網站。</span><span class="sxs-lookup"><span data-stu-id="be16e-128">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="be16e-129">例如，如果您在全域原則中啟用遠端使用者存取，您可以指定可停用特定網站之遠端使用者存取權的網站原則。</span><span class="sxs-lookup"><span data-stu-id="be16e-129">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="be16e-130">根據預設，網站原則會套用至該網站的所有使用者，但您可以將使用者原則指派給使用者，以覆寫網站原則設定。</span><span class="sxs-lookup"><span data-stu-id="be16e-130">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="be16e-131">**使用者原則**   您可以建立及設定一或多個使用者原則，以限制對特定使用者的遠端使用者存取權的支援。</span><span class="sxs-lookup"><span data-stu-id="be16e-131">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="be16e-132">使用者原則中的設定會覆寫全域和網站原則，但只適用于指派使用者原則的特定使用者。</span><span class="sxs-lookup"><span data-stu-id="be16e-132">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="be16e-133">例如，如果您在全域原則和網站原則中啟用遠端使用者存取，您可以指定可停用遠端使用者存取的使用者原則，然後將該使用者原則指派給特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="be16e-133">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="be16e-134">如果您建立使用者原則，您必須先將其套用至一或多個使用者，才會生效。</span><span class="sxs-lookup"><span data-stu-id="be16e-134">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<span data-ttu-id="be16e-135">若要判斷您需要建立或編輯哪些設定設定以及哪些原則，請參閱下列決策點：</span><span class="sxs-lookup"><span data-stu-id="be16e-135">To determine which configuration settings and which policies you need to create or edit, refer to the following decision points:</span></span>

<span data-ttu-id="be16e-136">**您想要讓您網域的內部和外部使用者能夠使用立即訊息、Web 會議和音訊/影片進行共同作業嗎？**</span><span class="sxs-lookup"><span data-stu-id="be16e-136">**Do you want to allow internal and external users of your domain to be able to collaborate using instant messaging, Web conferencing, and Audio/Video?**</span></span>

<span data-ttu-id="be16e-137">在 lync [server 2013 中設定控制遠端使用者存取權的原則](lync-server-2013-configure-policies-to-control-remote-user-access.md)，並在[lync Server 2013 中啟用或停用同盟與公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線，以設定相關設定的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="be16e-137">Configure the settings as detailed in the topics [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md), and [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)</span></span>

<span data-ttu-id="be16e-138">**您想要允許匿名使用者出席並邀請您部署中的使用者所託管的會議嗎？**</span><span class="sxs-lookup"><span data-stu-id="be16e-138">**Do you want to allow anonymous users to attend and be invited to conferences hosted by users in your deployment?**</span></span>

<span data-ttu-id="be16e-139">設定相關設定，如主題中的 [[指派會議原則以支援 Lync server 2013 中的匿名使用者](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)]、[在 lync server [2013 中建立或修改會議原則](lync-server-2013-create-or-modify-a-conferencing-policy.md)] 和 [ [lync server 2013 的會議原則設定] 參考](lync-server-2013-conferencing-policy-settings-reference.md)資訊</span><span class="sxs-lookup"><span data-stu-id="be16e-139">Configure the settings as detailed in the topic [Assign conferencing policies to support anonymous users in Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md), [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)</span></span>

<span data-ttu-id="be16e-140">**您想要允許使用者與 SIP 聯盟網域連絡人通訊嗎？**</span><span class="sxs-lookup"><span data-stu-id="be16e-140">**Do you want to allow users to communicate with SIP Federated Domain contacts?**</span></span>

<span data-ttu-id="be16e-141">在 lync server 2013 中設定[策略來控制聯盟使用者存取](lync-server-2013-configure-policies-to-control-federated-user-access.md)、[啟用或停用 lync server 2013 中的同盟與公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線，以及[在 lync server 2013 中管理貴組織的 SIP 聯盟網域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)，即可設定設定的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="be16e-141">Configure the settings as detailed in the topics [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md), and [Manage SIP federated domains for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)</span></span>

<span data-ttu-id="be16e-142">**如果您已啟用與 SIP 同盟網域的通訊，您想要啟用與 XMPP 聯盟夥伴連絡人的通訊嗎？**</span><span class="sxs-lookup"><span data-stu-id="be16e-142">**If you have enabled communication with SIP Federation Domains, do you want to enable communications with XMPP Federated Partner contacts?**</span></span>

<span data-ttu-id="be16e-143">在 lync [server 2013 中設定控制 XMPP 聯盟使用者存取的原則](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)，並在[lync Server 2013 中管理 XMPP 聯盟夥伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)，以設定主題中的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="be16e-143">Configure the settings as detailed in the topic [Configure policies to control XMPP federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) and [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md).</span></span>

<span data-ttu-id="be16e-144">**如果您已啟用與 SIP 聯盟網域的通訊，您是否要啟用 SIP 同盟自動探索？**</span><span class="sxs-lookup"><span data-stu-id="be16e-144">**If you have enabled communication with SIP Federated Domains, do you want to enable SIP Federation automatic discovery?**</span></span>

<span data-ttu-id="be16e-145">設定在[Lync Server 2013 中啟用或停用同盟合作夥伴的探索](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)主題中的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="be16e-145">Configure the settings as detailed in the topic [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="be16e-146">**如果您已啟用與 SIP 同盟網域的通訊，您是否要啟用將免責聲明傳送給同盟連絡人，通知他們您使用的是封存，而且該通訊可能已封存？**</span><span class="sxs-lookup"><span data-stu-id="be16e-146">**If you have enabled communication with SIP Federation Domains, do you want to enable sending a disclaimer to Federated contacts notifying them that you use archiving and that communications may be archived?**</span></span>

<span data-ttu-id="be16e-147">在[Lync Server 2013 的 [聯盟夥伴] 中啟用或停](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)用將封存免責聲明傳送至同盟合作夥伴，以進行設定。</span><span class="sxs-lookup"><span data-stu-id="be16e-147">Configure the settings as detailed in the topic [Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

<span data-ttu-id="be16e-148">**您是否要允許使用者與 SIP 聯盟提供者通訊，以便與公用提供者通訊（例如 Windows Live Messenger、AOL 和 Yahoo\!）？**</span><span class="sxs-lookup"><span data-stu-id="be16e-148">**Do you want to allow users to communicate with SIP Federated Providers that enable communication with public providers, such as Windows Live Messenger, AOL, and Yahoo\!?**</span></span>

<span data-ttu-id="be16e-149">在 lync server 2013 中設定[策略來控制公用使用者存取](lync-server-2013-configure-policies-to-control-public-user-access.md)的相關設定，請在 lync server[2013 中啟用或停用同盟與公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線，以及[在 lync server 2013 中建立或編輯公用 SIP 聯盟提供者](lync-server-2013-create-or-edit-public-sip-federated-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="be16e-149">Configure the settings as detailed in the topics [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)[Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md), and [Create or edit public SIP federated providers in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md).</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="be16e-150">從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。</span><span class="sxs-lookup"><span data-stu-id="be16e-150">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="be16e-151">擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="be16e-151">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="be16e-152">信使，直到服務關閉日期為止。</span><span class="sxs-lookup"><span data-stu-id="be16e-152">Messenger until the service shut down date.</span></span> <span data-ttu-id="be16e-153">AOL 和 Yahoo！的存留期結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="be16e-153">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="be16e-154">已公佈。</span><span class="sxs-lookup"><span data-stu-id="be16e-154">has been announced.</span></span> <span data-ttu-id="be16e-155">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</span><span class="sxs-lookup"><span data-stu-id="be16e-155">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="be16e-156">PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="be16e-156">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="be16e-157">名單.</span><span class="sxs-lookup"><span data-stu-id="be16e-157">Messenger.</span></span> <span data-ttu-id="be16e-158">Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</span><span class="sxs-lookup"><span data-stu-id="be16e-158">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="be16e-159">Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。</span><span class="sxs-lookup"><span data-stu-id="be16e-159">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="be16e-160">與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="be16e-160">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="be16e-161">您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="be16e-161">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="be16e-162">**您是否要允許使用者與 SIP 同盟提供者通訊，這些提供者是執行 Microsoft Office 365、Microsoft Lync Online 和 Microsoft Lync Online 2010 的託管提供者？**</span><span class="sxs-lookup"><span data-stu-id="be16e-162">**Do you want to allow users to communicate with SIP Federated Providers that are hosted providers running Microsoft Office 365, Microsoft Lync Online and Microsoft Lync Online 2010?**</span></span>

<span data-ttu-id="be16e-163">在 lync server [2013 中建立或編輯公用 SIP 聯盟提供者](lync-server-2013-create-or-edit-public-sip-federated-providers.md)的相關設定，請在 lync server [2013 中啟用或停用同盟與公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線，以及[建立或編輯託管 SIP 聯合提供者 Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)</span><span class="sxs-lookup"><span data-stu-id="be16e-163">Configure the settings as detailed in the topics [Create or edit public SIP federated providers in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) and [Create or edit hosted SIP federated providers Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)</span></span>

<span data-ttu-id="be16e-164">**您的部署是在分割（也稱為混合式）網域中設定，有些使用者在內部部署中擁有其主伺服器，而其他使用者則是在線上環境中使用家用伺服器進行設定？**</span><span class="sxs-lookup"><span data-stu-id="be16e-164">**Is your deployment configured in a split (also known as a hybrid) domain, where some users have their home server in an on-premise deployment, and other users are configured with a home server in an online environment?**</span></span>

<span data-ttu-id="be16e-165">在 lync server 2013 中設定[策略來控制聯盟使用者存取](lync-server-2013-configure-policies-to-control-federated-user-access.md)、[啟用或停用 lync server 2013 中的同盟與公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線，以及[建立或編輯託管 SIP 同盟提供者 Lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)的相關設定，如下列主題所述。</span><span class="sxs-lookup"><span data-stu-id="be16e-165">Configure the settings as detailed in the topics [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) and [Create or edit hosted SIP federated providers Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)</span></span>

<span data-ttu-id="be16e-166">如果您想要的表格會列出需求：</span><span class="sxs-lookup"><span data-stu-id="be16e-166">If you prefer a table that lists the requirements:</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be16e-167">同盟與外部存取（跨）同盟或外部存取類型（向下）中的索引標籤</span><span class="sxs-lookup"><span data-stu-id="be16e-167">Tab in Federation and External Access (Across) Federation or External Access Type (Down)</span></span></th>
<th><span data-ttu-id="be16e-168">外部存取原則</span><span class="sxs-lookup"><span data-stu-id="be16e-168">External Access Policy</span></span></th>
<th><span data-ttu-id="be16e-169">存取邊緣配置</span><span class="sxs-lookup"><span data-stu-id="be16e-169">Access Edge Config</span></span></th>
<th><span data-ttu-id="be16e-170">SIP 聯盟網域</span><span class="sxs-lookup"><span data-stu-id="be16e-170">SIP Federated Domains</span></span></th>
<th><span data-ttu-id="be16e-171">SIP 同盟提供者</span><span class="sxs-lookup"><span data-stu-id="be16e-171">SIP Federated Providers</span></span></th>
<th><span data-ttu-id="be16e-172">XMPP 聯盟合作夥伴</span><span class="sxs-lookup"><span data-stu-id="be16e-172">XMPP Federated Partner</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be16e-173">遠端使用者</span><span class="sxs-lookup"><span data-stu-id="be16e-173">Remote Users</span></span></p></td>
<td><p><span data-ttu-id="be16e-174"><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">在 Lync Server 2013 中設定原則以控制遠端使用者存取</a></span><span class="sxs-lookup"><span data-stu-id="be16e-174"><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="be16e-175"><a href="lync-server-2013-enable-or-disable-remote-user-access.md">在 Lync Server 2013 中啟用或停用遠端使用者存取</a></span><span class="sxs-lookup"><span data-stu-id="be16e-175"><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be16e-176">SIP 同盟連絡人</span><span class="sxs-lookup"><span data-stu-id="be16e-176">SIP Federated Contacts</span></span></p></td>
<td><p><span data-ttu-id="be16e-177"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中設定控制同盟使用者存取的原則</a></span><span class="sxs-lookup"><span data-stu-id="be16e-177"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="be16e-178"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></span><span class="sxs-lookup"><span data-stu-id="be16e-178"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="be16e-179"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">在 Lync Server 2013 中啟用或停用探索同盟協力廠商</a></span><span class="sxs-lookup"><span data-stu-id="be16e-179"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="be16e-180"><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">在 Lync Server 2013 中啟用或停用傳送封存免責聲明至同盟合作夥伴的功能</a></span><span class="sxs-lookup"><span data-stu-id="be16e-180"><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="be16e-181"><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">在 Lync Server 2013 中管理組織的 SIP 同盟網域</a></span><span class="sxs-lookup"><span data-stu-id="be16e-181"><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be16e-182">XMPP 同盟連絡人</span><span class="sxs-lookup"><span data-stu-id="be16e-182">XMPP Federated Contacts</span></span></p></td>
<td><p><span data-ttu-id="be16e-183"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中設定控制同盟使用者存取的原則</a></span><span class="sxs-lookup"><span data-stu-id="be16e-183"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="be16e-184"><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">在 Lync Server 2013 中設定原則以控制 XMPP 同盟使用者存取</a></span><span class="sxs-lookup"><span data-stu-id="be16e-184"><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Configure policies to control XMPP federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="be16e-185"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></span><span class="sxs-lookup"><span data-stu-id="be16e-185"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="be16e-186"><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">在 Lync Server 2013 中管理 XMPP 同盟夥伴</a></span><span class="sxs-lookup"><span data-stu-id="be16e-186"><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Manage XMPP federated partners in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be16e-187">分割網域/混合式使用者</span><span class="sxs-lookup"><span data-stu-id="be16e-187">Split Domain / Hybrid Users</span></span></p></td>
<td><p><span data-ttu-id="be16e-188"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中設定控制同盟使用者存取的原則</a></span><span class="sxs-lookup"><span data-stu-id="be16e-188"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="be16e-189"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></span><span class="sxs-lookup"><span data-stu-id="be16e-189"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="be16e-190"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">建立或編輯主控的 SIP 同盟提供者 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="be16e-190"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be16e-191">公用 IM 服務連絡人</span><span class="sxs-lookup"><span data-stu-id="be16e-191">Public IM Service Contacts</span></span></p></td>
<td><p><span data-ttu-id="be16e-192"><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">在 Lync Server 2013 中設定原則以控制公用使用者存取</a></span><span class="sxs-lookup"><span data-stu-id="be16e-192"><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="be16e-193"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></span><span class="sxs-lookup"><span data-stu-id="be16e-193"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="be16e-194"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中建立或編輯公用 SIP 同盟提供者</a></span><span class="sxs-lookup"><span data-stu-id="be16e-194"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be16e-195">匿名使用者對會議與會議的存取權</span><span class="sxs-lookup"><span data-stu-id="be16e-195">Anonymous user access to meetings and conferences</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="be16e-196"><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">在 Lync Server 2013 中指派會議原則以支援匿名使用者</a></span><span class="sxs-lookup"><span data-stu-id="be16e-196"><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Assign conferencing policies to support anonymous users in Lync Server 2013</a></span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="be16e-197">您也必須在 [會議原則] 下考慮下列設定設定：<A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">在 lync server 2013 中建立或修改會議原則</A>，以及<A href="lync-server-2013-conferencing-policy-settings-reference.md">lync Server 2013 的會議原則設定參考</A></span><span class="sxs-lookup"><span data-stu-id="be16e-197">You must also consider the following configuration settings under Conferencing policies: <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">Create or modify a conferencing policy in Lync Server 2013</A> and <A href="lync-server-2013-conferencing-policy-settings-reference.md">Conferencing policy settings reference for Lync Server 2013</A></span></span>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="be16e-198">您可以設定外部使用者存取設定，包括任何您想要用來控制外部使用者存取權的原則，即使您的組織未啟用外部使用者存取權也一樣。</span><span class="sxs-lookup"><span data-stu-id="be16e-198">You can configure external user access settings, including any policies that you want to use to control external user access, even if you have not enabled external user access for your organization.</span></span> <span data-ttu-id="be16e-199">不過，您設定的原則和其他設定只有在您的組織啟用外部使用者存取後才會生效。</span><span class="sxs-lookup"><span data-stu-id="be16e-199">However, the policies and other settings that you configure are in effect only when you have external user access enabled for your organization.</span></span> <span data-ttu-id="be16e-200">外部使用者在停用外部使用者存取權，或未設定外部使用者存取原則支援時，無法與貴組織的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="be16e-200">External users cannot communicate with users of your organization when external user access is disabled or if no external user access policies are configured to support it.</span></span>

<span data-ttu-id="be16e-201">Edge 部署會驗證外部使用者的類型（匿名使用者除外，其由會議 ID 驗證，以及當您建立會議與邀請參與者時傳送給匿名參與者的密碼）。根據您設定 edge 支援的方式來存取。</span><span class="sxs-lookup"><span data-stu-id="be16e-201">Your edge deployment authenticates the types of external users (except for anonymous users, who are authenticated by the conference ID and a passkey that is sent to the anonymous participant when you create the conference and invite participants) and controls access based on how you configure your edge support.</span></span> <span data-ttu-id="be16e-202">若要控制通訊，您可以設定一或多個原則，並設定定義您的部署內部和外部的使用者之間相互通訊方式的設定。</span><span class="sxs-lookup"><span data-stu-id="be16e-202">In order to control communications, you can configure one or more policies and configure settings that define how users inside and outside your deployment communicate with each other.</span></span> <span data-ttu-id="be16e-203">[原則與設定] 包含外部使用者存取的預設全域原則，除了您可以建立並設定以啟用一或多種類型的外部使用者存取特定網站或使用者的網站和使用者原則之外。</span><span class="sxs-lookup"><span data-stu-id="be16e-203">The policies and settings include the default global policy for external user access, in addition to site and user policies that you can create and configure to enable one or more types of external user access for specific sites or users.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="be16e-204">本節內容</span><span class="sxs-lookup"><span data-stu-id="be16e-204">In This Section</span></span>

  - [<span data-ttu-id="be16e-205">在 Lync Server 2013 中管理外部使用存取原則</span><span class="sxs-lookup"><span data-stu-id="be16e-205">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="be16e-206">在 Lync Server 2013 中管理組織的 Access Edge 設定</span><span class="sxs-lookup"><span data-stu-id="be16e-206">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [<span data-ttu-id="be16e-207">在 Lync Server 2013 中管理組織的 SIP 同盟網域</span><span class="sxs-lookup"><span data-stu-id="be16e-207">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [<span data-ttu-id="be16e-208">在 Lync Server 2013 中管理組織的 SIP 同盟提供者</span><span class="sxs-lookup"><span data-stu-id="be16e-208">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [<span data-ttu-id="be16e-209">在 Lync Server 2013 中管理 XMPP 同盟夥伴</span><span class="sxs-lookup"><span data-stu-id="be16e-209">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [<span data-ttu-id="be16e-210">在 Lync Server 2013 中設定 Lync Online 客戶的同盟支援</span><span class="sxs-lookup"><span data-stu-id="be16e-210">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

