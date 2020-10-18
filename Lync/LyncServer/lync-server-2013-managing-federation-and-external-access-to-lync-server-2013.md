---
title: Lync Server 2013：管理 Lync Server 2013 的同盟與外部存取
description: Lync Server 2013：管理 Lync Server 2013 的同盟與外部存取。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing federation and external access to Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1d389c7490fd1884631ed2fc184d590eb42141b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574919"
---
# <a name="managing-federation-and-external-access-to-lync-server-2013"></a><span data-ttu-id="3fdf5-103">管理 Lync Server 2013 的同盟與外部存取</span><span class="sxs-lookup"><span data-stu-id="3fdf5-103">Managing federation and external access to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fdf5-104">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="3fdf5-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="3fdf5-105">支援外部使用者的首要步驟，是部署 Edge Server 或 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-105">Deploying an Edge Server or Edge pool is the first step to supporting external users.</span></span> <span data-ttu-id="3fdf5-106">如需部署 Edge Server 的詳細資訊，請參閱部署檔中的部署 [Lync Server 2013 中的外部使用者存取](lync-server-2013-deploying-external-user-access.md) 。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-106">For details about deploying Edge Servers, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<span data-ttu-id="3fdf5-107">在安裝並設定 Lync Server 2013 的內部部署後，您組織中的內部使用者可以與其他內部使用者共同作業，而這些使用者在您的 Active Directory 網域服務中有 SIP 帳戶 (AD DS) 。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-107">After installing and configuring your internal deployment of Lync Server 2013, internal users in your organization can collaborate with other internal users who have SIP accounts in your Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="3fdf5-108">共同作業可包含傳送和接收立即訊息，以及會議中目前狀態與參加情況的更新。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-108">Collaboration can include sending and receiving instant messages, and update of presence status and participating in conferences (also known as "meetings").</span></span> <span data-ttu-id="3fdf5-109">您可以啟用和設定外部使用者存取，以控制是否支援的外部使用者能夠與內部 Lync Server 使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-109">You enable and configure external user access to control whether supported external users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="3fdf5-110">外部使用者可能包含您部署的遠端使用者、同盟使用者 (包括公用立即訊息 (IM) 服務提供者的支援使用者)、XMPP 同盟與會議的匿名參與者。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-110">External users can include remote users of your deployment, federated users (including supported users of public instant messaging (IM) service providers), XMPP federation and anonymous participants in conferences.</span></span>

<span data-ttu-id="3fdf5-111">如果您的部署包含安裝 Lync Server 2013 Edge Server 或 Edge 集區，則可能的通訊類型的範圍會大大擴充，具有許多選項可供外部使用者存取、與其他 SIP 同盟網域的成員進行通訊、SIP 同盟提供者，以及 XMPP 同盟使用者。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-111">If your deployment included the installation of a Lync Server 2013 Edge Server or an Edge pool, the scope of possible communication types is greatly expanded with a number of options for external user access, communication with members of other SIP federated domains, SIP federated providers, and XMPP federated users.</span></span> <span data-ttu-id="3fdf5-112">在設定 Edge Server 或 Edge 集區之後，請啟用您要提供的外部使用者存取類型，並設定原則以控制外部存取。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-112">After setting up the Edge Server or Edge pool, you enable the types of external user access that you want to provide, and configure the policies to control for the external access.</span></span> <span data-ttu-id="3fdf5-113">在 Lync Server 2013 中，您可以根據任務需求，使用 Lync Server 控制台、Lync Server 管理命令介面或兩者來啟用及設定外部使用者存取和原則。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-113">In Lync Server 2013, you enable and configure external user access and policies using the Lync Server Control Panel, the Lync Server Management Shell or both, based on the task requirements.</span></span> <span data-ttu-id="3fdf5-114">如需這些管理工具的詳細資訊，請參閱 operations 檔中的 [lync server 2013](lync-server-2013-lync-server-administrative-tools.md) 系統管理工具、 [Lync Server 2013 管理命令](lync-server-2013-lync-server-management-shell.md) 介面，並安裝 Operations 檔中的 [lync server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md) 。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-114">For details about these management tools, see [Lync Server 2013 administrative tools](lync-server-2013-lync-server-administrative-tools.md) in the Operations documentation, [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation, and [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md) in the Operations documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3fdf5-115">當您設計外部使用者存取的組態和原則時，必須知道原則的優先順序以及原則的套用方式。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-115">When you design your configuration and policies for external user access, you must understand the precedence of policies and how the policies are applied.</span></span> <span data-ttu-id="3fdf5-116">套用於一個原則層級的 Lync Server 原則設定可以覆寫在另一個原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-116">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="3fdf5-117">Lync Server 原則優先順序是：使用者原則 (最大的影響) 覆寫網站原則，然後網站原則會覆寫全域原則 (最小影響) 。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-117">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="3fdf5-118">也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-118">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="3fdf5-p105">根據預設，沒有原則是設定為支援外部使用者存取 (包括遠端使用者存取、同盟網域使用者存取)，即使您已為組織啟用外部使用者存取也一樣。若要控制外部使用者存取的使用，您必須設定一個或多個原則，並在每個原則指定支援的外部使用者存取類型。這包括下列外部存取原則：</span><span class="sxs-lookup"><span data-stu-id="3fdf5-p105">By default, no policies are configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. This includes the following external access policies:</span></span>

  - <span data-ttu-id="3fdf5-122">**全域原則**   全域原則是在您部署 Edge Server 時建立。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-122">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="3fdf5-123">根據預設，全域原則中不會啟用任何外部使用者存取選項。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-123">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="3fdf5-124">若要在全域層級支援外部使用者存取，您可以設定全域原則來支援一或多個類型的外部使用者存取選項。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-124">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="3fdf5-125">全域原則適用於組織中的所有使用者，但是網站原則和使用者原則會覆寫全域原則。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-125">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="3fdf5-126">如果您刪除全域原則，不會將它移除。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-126">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="3fdf5-127">而是會將它重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-127">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="3fdf5-128">**網站原則**   您可以建立並設定一或多個網站原則，以限制外部使用者對特定網站存取的支援。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-128">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="3fdf5-129">網站原則中的設定會覆寫全域原則，但僅限於該網站原則所涵蓋的特定網站。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-129">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="3fdf5-130">例如，如果您在全域原則中啟用了遠端使用者存取，您可以指定網站原則以對特定網站停用遠端使用者存取。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-130">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="3fdf5-131">根據預設，網站原則會套用至該網站的所有使用者，但您可以指派使用者原則給個別使用者，以覆寫網站原則設定。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-131">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="3fdf5-132">**使用者原則**   您可以建立並設定一或多個使用者原則，以限制遠端使用者對特定網站存取的支援。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-132">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="3fdf5-133">使用者原則中的設定會覆寫全域與網站原則，但僅限於該使用者原則指派的特定使用者。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-133">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="3fdf5-134">例如，如果您在全域原則和網站原則中啟用了遠端使用者存取，您可以指定使用者原則以停用遠端使用者存取，然後將該使用者原則指派給特定使用者。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-134">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="3fdf5-135">如果您建立使用者原則，必須將其套用至一或多個使用者，該原則才能生效。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-135">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<span data-ttu-id="3fdf5-136">若要決定需要建立或編輯哪些組態設定及原則，請參閱下列決策要點：</span><span class="sxs-lookup"><span data-stu-id="3fdf5-136">To determine which configuration settings and which policies you need to create or edit, refer to the following decision points:</span></span>

<span data-ttu-id="3fdf5-137">**您是否要允許您網域的內部及外部使用者能夠使用立即訊息、Web 會議及音訊/視訊來共同作業？**</span><span class="sxs-lookup"><span data-stu-id="3fdf5-137">**Do you want to allow internal and external users of your domain to be able to collaborate using instant messaging, Web conferencing, and Audio/Video?**</span></span>

<span data-ttu-id="3fdf5-138">在 lync server 2013 中設定[原則以控制遠端使用者存取](lync-server-2013-configure-policies-to-control-remote-user-access.md)，以及[啟用或停用 lync server 2013 中的同盟和公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線，以詳細設定設定中的相關設定。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-138">Configure the settings as detailed in the topics [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md), and [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)</span></span>

<span data-ttu-id="3fdf5-139">**您是否要允許匿名使用者加入您部署中使用者所主控的會議，以及收到該會議的邀請？**</span><span class="sxs-lookup"><span data-stu-id="3fdf5-139">**Do you want to allow anonymous users to attend and be invited to conferences hosted by users in your deployment?**</span></span>

<span data-ttu-id="3fdf5-140">在 [[指派會議原則以支援 Lync server 2013 中的匿名使用者](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)] 中，設定相關的設定，並在 lync server [2013 中建立或修改會議原則](lync-server-2013-create-or-modify-a-conferencing-policy.md)，以及[lync server 2013 的會議原則設定參考](lync-server-2013-conferencing-policy-settings-reference.md)中的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-140">Configure the settings as detailed in the topic [Assign conferencing policies to support anonymous users in Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md), [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)</span></span>

<span data-ttu-id="3fdf5-141">**您是否要允許使用者與 SIP 同盟網域連絡人進行通訊？**</span><span class="sxs-lookup"><span data-stu-id="3fdf5-141">**Do you want to allow users to communicate with SIP Federated Domain contacts?**</span></span>

<span data-ttu-id="3fdf5-142">設定各主題的詳細資訊，請在 lync server [2013 中設定控制同盟使用者存取的原則](lync-server-2013-configure-policies-to-control-federated-user-access.md)、 [啟用或停用 lync server 2013 中的同盟和公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線，以及 [在 lync server 2013 中管理組織的 SIP 同盟網域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="3fdf5-142">Configure the settings as detailed in the topics [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md), and [Manage SIP federated domains for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)</span></span>

<span data-ttu-id="3fdf5-143">**若您已啟用與 SIP 同盟網域的通訊，您是否還要啟用與 XMPP 同盟協力廠商連絡人的通訊？**</span><span class="sxs-lookup"><span data-stu-id="3fdf5-143">**If you have enabled communication with SIP Federation Domains, do you want to enable communications with XMPP Federated Partner contacts?**</span></span>

<span data-ttu-id="3fdf5-144">設定如需在 [Lync server 2013 中設定原則以控制 XMPP 同盟使用者存取](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) ，以及 [管理 lync server 2013 中的 XMPP](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)同盟協力廠商，請設定詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-144">Configure the settings as detailed in the topic [Configure policies to control XMPP federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) and [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md).</span></span>

<span data-ttu-id="3fdf5-145">**若您已啟用與 SIP 同盟網域的通訊，您是否要啟用 SIP 同盟自動探索？**</span><span class="sxs-lookup"><span data-stu-id="3fdf5-145">**If you have enabled communication with SIP Federated Domains, do you want to enable SIP Federation automatic discovery?**</span></span>

<span data-ttu-id="3fdf5-146">設定在 [Lync Server 2013 中啟用或停用同盟](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)協力廠商探索主題的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-146">Configure the settings as detailed in the topic [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="3fdf5-147">**若您已啟用與 SIP 同盟網域的通訊，您是否還要啟用傳送免責聲明給同盟連絡人，以通知他們您使用了封裝功能，且可能會封裝通訊內容？**</span><span class="sxs-lookup"><span data-stu-id="3fdf5-147">**If you have enabled communication with SIP Federation Domains, do you want to enable sending a disclaimer to Federated contacts notifying them that you use archiving and that communications may be archived?**</span></span>

<span data-ttu-id="3fdf5-148">設定如需在 [Lync Server 2013 中啟用或停](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)用傳送封存免責聲明至同盟合作夥伴的詳細資訊，請設定相關設定。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-148">Configure the settings as detailed in the topic [Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

<span data-ttu-id="3fdf5-149">**您是否要允許使用者與使用公用提供者通訊的 SIP 同盟提供者（例如 Windows Live Messenger、AOL 和 Yahoo）進行通訊 \! ？**</span><span class="sxs-lookup"><span data-stu-id="3fdf5-149">**Do you want to allow users to communicate with SIP Federated Providers that enable communication with public providers, such as Windows Live Messenger, AOL, and Yahoo\!?**</span></span>

<span data-ttu-id="3fdf5-150">設定相關設定，請在 Lync server[中設定控制公用使用者存取的原則](lync-server-2013-configure-policies-to-control-public-user-access.md)在 lync server 2013 中，[啟用或停用 lync server 2013 中的同盟和公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線，以及[在 lync server 2013 中建立或編輯公用 SIP 同盟提供者](lync-server-2013-create-or-edit-public-sip-federated-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-150">Configure the settings as detailed in the topics [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)[Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md), and [Create or edit public SIP federated providers in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md).</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="3fdf5-151">從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-151">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="3fdf5-152">具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="3fdf5-152">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="3fdf5-153">信使直到服務關閉日期。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-153">Messenger until the service shut down date.</span></span> <span data-ttu-id="3fdf5-154">AOL 和 Yahoo！的循環結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="3fdf5-154">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="3fdf5-155">已宣告。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-155">has been announced.</span></span> <span data-ttu-id="3fdf5-156">如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-156">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="3fdf5-157">PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="3fdf5-157">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="3fdf5-158">信使。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-158">Messenger.</span></span> <span data-ttu-id="3fdf5-159">Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-159">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="3fdf5-160">Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-160">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="3fdf5-161">與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-161">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="3fdf5-162">隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-162">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="3fdf5-163">**您是否要允許使用者與執行 Microsoft 365、Microsoft Lync Online 及 Microsoft Lync Online 2010 之主控供應商的 SIP 同盟提供者通訊？**</span><span class="sxs-lookup"><span data-stu-id="3fdf5-163">**Do you want to allow users to communicate with SIP Federated Providers that are hosted providers running Microsoft 365, Microsoft Lync Online, and Microsoft Lync Online 2010?**</span></span>

<span data-ttu-id="3fdf5-164">設定如需詳細資訊，請在 [lync server 2013 中建立或編輯公用 SIP 同盟提供者](lync-server-2013-create-or-edit-public-sip-federated-providers.md)、 [啟用或停用 lync server 2013 中的同盟和公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 連線，以及 [建立或編輯主控的 Sip 同盟提供者 Lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)</span><span class="sxs-lookup"><span data-stu-id="3fdf5-164">Configure the settings as detailed in the topics [Create or edit public SIP federated providers in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) and [Create or edit hosted SIP federated providers Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)</span></span>

<span data-ttu-id="3fdf5-165">**您是否將部署設定在分割 (也稱為混合) 網域中，且該網域的某些使用者在內部部署中具有自己的主伺服器，而其他使用者則是透過線上環境中的主伺服器加以設定？**</span><span class="sxs-lookup"><span data-stu-id="3fdf5-165">**Is your deployment configured in a split (also known as a hybrid) domain, where some users have their home server in an on-premise deployment, and other users are configured with a home server in an online environment?**</span></span>

<span data-ttu-id="3fdf5-166">設定各主題的詳細資訊在 [Lync server 2013 中設定用來控制同盟使用者存取的原則](lync-server-2013-configure-policies-to-control-federated-user-access.md)、 [啟用或停用 lync server 2013 中的同盟和公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 連線，以及 [建立或編輯主控的 SIP 同盟提供者 lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)</span><span class="sxs-lookup"><span data-stu-id="3fdf5-166">Configure the settings as detailed in the topics [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) and [Create or edit hosted SIP federated providers Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)</span></span>

<span data-ttu-id="3fdf5-167">若您偏好以表格列出需求：</span><span class="sxs-lookup"><span data-stu-id="3fdf5-167">If you prefer a table that lists the requirements:</span></span>


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
<th><span data-ttu-id="3fdf5-168">) 同盟或外部存取類型的 [同盟和外部存取] (中的索引標籤 (向內) </span><span class="sxs-lookup"><span data-stu-id="3fdf5-168">Tab in Federation and External Access (Across) Federation or External Access Type (Down)</span></span></th>
<th><span data-ttu-id="3fdf5-169">外部存取原則</span><span class="sxs-lookup"><span data-stu-id="3fdf5-169">External Access Policy</span></span></th>
<th><span data-ttu-id="3fdf5-170">Access Edge 設定</span><span class="sxs-lookup"><span data-stu-id="3fdf5-170">Access Edge Config</span></span></th>
<th><span data-ttu-id="3fdf5-171">SIP 同盟網域</span><span class="sxs-lookup"><span data-stu-id="3fdf5-171">SIP Federated Domains</span></span></th>
<th><span data-ttu-id="3fdf5-172">SIP 同盟提供者</span><span class="sxs-lookup"><span data-stu-id="3fdf5-172">SIP Federated Providers</span></span></th>
<th><span data-ttu-id="3fdf5-173">XMPP 同盟協力廠商</span><span class="sxs-lookup"><span data-stu-id="3fdf5-173">XMPP Federated Partner</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fdf5-174">遠端使用者</span><span class="sxs-lookup"><span data-stu-id="3fdf5-174">Remote Users</span></span></p></td>
<td><p><span data-ttu-id="3fdf5-175"><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">在 Lync Server 2013 中設定控制遠端使用者存取的原則</a></span><span class="sxs-lookup"><span data-stu-id="3fdf5-175"><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3fdf5-176"><a href="lync-server-2013-enable-or-disable-remote-user-access.md">在 Lync Server 2013 中啟用或停用遠端使用者存取</a></span><span class="sxs-lookup"><span data-stu-id="3fdf5-176"><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fdf5-177">SIP 同盟連絡人</span><span class="sxs-lookup"><span data-stu-id="3fdf5-177">SIP Federated Contacts</span></span></p></td>
<td><p><span data-ttu-id="3fdf5-178"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中設定控制同盟使用者存取的原則</a></span><span class="sxs-lookup"><span data-stu-id="3fdf5-178"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3fdf5-179"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></span><span class="sxs-lookup"><span data-stu-id="3fdf5-179"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="3fdf5-180"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">在 Lync Server 2013 中啟用或停用同盟協力廠商的探索</a></span><span class="sxs-lookup"><span data-stu-id="3fdf5-180"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="3fdf5-181"><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">在 Lync Server 2013 中啟用或停用傳送封存免責聲明至同盟合作夥伴的功能</a></span><span class="sxs-lookup"><span data-stu-id="3fdf5-181"><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3fdf5-182"><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">在 Lync Server 2013 中管理組織的 SIP 同盟網域</a></span><span class="sxs-lookup"><span data-stu-id="3fdf5-182"><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fdf5-183">XMPP 同盟連絡人</span><span class="sxs-lookup"><span data-stu-id="3fdf5-183">XMPP Federated Contacts</span></span></p></td>
<td><p><span data-ttu-id="3fdf5-184"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中設定控制同盟使用者存取的原則</a></span><span class="sxs-lookup"><span data-stu-id="3fdf5-184"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="3fdf5-185"><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">在 Lync Server 2013 中設定原則以控制 XMPP 同盟使用者存取</a></span><span class="sxs-lookup"><span data-stu-id="3fdf5-185"><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Configure policies to control XMPP federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3fdf5-186"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></span><span class="sxs-lookup"><span data-stu-id="3fdf5-186"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="3fdf5-187"><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">在 Lync Server 2013 中管理 XMPP 同盟協力廠商</a></span><span class="sxs-lookup"><span data-stu-id="3fdf5-187"><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Manage XMPP federated partners in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fdf5-188">分割網域 / 混合使用者</span><span class="sxs-lookup"><span data-stu-id="3fdf5-188">Split Domain / Hybrid Users</span></span></p></td>
<td><p><span data-ttu-id="3fdf5-189"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中設定控制同盟使用者存取的原則</a></span><span class="sxs-lookup"><span data-stu-id="3fdf5-189"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3fdf5-190"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></span><span class="sxs-lookup"><span data-stu-id="3fdf5-190"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3fdf5-191"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">建立或編輯主控的 SIP 同盟提供者 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3fdf5-191"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fdf5-192">公用 IM 服務連絡人</span><span class="sxs-lookup"><span data-stu-id="3fdf5-192">Public IM Service Contacts</span></span></p></td>
<td><p><span data-ttu-id="3fdf5-193"><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">在 Lync Server 2013 中設定原則以控制公用使用者存取</a></span><span class="sxs-lookup"><span data-stu-id="3fdf5-193"><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3fdf5-194"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></span><span class="sxs-lookup"><span data-stu-id="3fdf5-194"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3fdf5-195"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中建立或編輯公用 SIP 同盟提供者</a></span><span class="sxs-lookup"><span data-stu-id="3fdf5-195"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fdf5-196">匿名使用者對會議的存取權</span><span class="sxs-lookup"><span data-stu-id="3fdf5-196">Anonymous user access to meetings and conferences</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3fdf5-197"><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">在 Lync Server 2013 中指派會議原則以支援匿名使用者</a></span><span class="sxs-lookup"><span data-stu-id="3fdf5-197"><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Assign conferencing policies to support anonymous users in Lync Server 2013</a></span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="3fdf5-198">您也必須考慮下列設定設定：在 [會議原則] 下 <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">建立或修改 lync server 2013 的會議原則</A> ，以及 <A href="lync-server-2013-conferencing-policy-settings-reference.md">lync Server 2013 的會議原則設定參考</A></span><span class="sxs-lookup"><span data-stu-id="3fdf5-198">You must also consider the following configuration settings under Conferencing policies: <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">Create or modify a conferencing policy in Lync Server 2013</A> and <A href="lync-server-2013-conferencing-policy-settings-reference.md">Conferencing policy settings reference for Lync Server 2013</A></span></span>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3fdf5-p112">您可以設定外部使用者存取設定，包括任何您要用以控制外部使用者存取的原則，即使您並未啟用組織的外部使用者存取亦然。但只有在您啟用組織的外部使用者存取後，您所設定的原則與其他設定才會生效。當外部使用者存取停用，或未設定外部使用者存取原則加以支援時，外部使用者將無法與您組織的使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-p112">You can configure external user access settings, including any policies that you want to use to control external user access, even if you have not enabled external user access for your organization. However, the policies and other settings that you configure are in effect only when you have external user access enabled for your organization. External users cannot communicate with users of your organization when external user access is disabled or if no external user access policies are configured to support it.</span></span>

<span data-ttu-id="3fdf5-p113">您的 Edge 部署會根據您設定 Edge 支援的方式，來驗證外部使用者 (但匿名使用者除外，匿名使用者是由當您建立會議並邀請參與者時，所傳送給匿名參與者的會議 ID 及密碼金鑰加以驗證) 的類型及控制存取。若要控制通訊，您可以設定一或多項原則並設定其他設定，以定義您部署內外之使用者彼此通訊的方式。這些原則及設定包括外部使用者存取的預設全域原則，以及您可以建立並設定以針對特定網站或使用者啟用一或多種外部使用者存取類型的網站與使用者原則。</span><span class="sxs-lookup"><span data-stu-id="3fdf5-p113">Your edge deployment authenticates the types of external users (except for anonymous users, who are authenticated by the conference ID and a passkey that is sent to the anonymous participant when you create the conference and invite participants) and controls access based on how you configure your edge support. In order to control communications, you can configure one or more policies and configure settings that define how users inside and outside your deployment communicate with each other. The policies and settings include the default global policy for external user access, in addition to site and user policies that you can create and configure to enable one or more types of external user access for specific sites or users.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3fdf5-205">本章節內容</span><span class="sxs-lookup"><span data-stu-id="3fdf5-205">In This Section</span></span>

  - [<span data-ttu-id="3fdf5-206">在 Lync Server 2013 中管理外部存取原則</span><span class="sxs-lookup"><span data-stu-id="3fdf5-206">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="3fdf5-207">在 Lync Server 2013 中管理組織的 Access Edge 設定</span><span class="sxs-lookup"><span data-stu-id="3fdf5-207">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [<span data-ttu-id="3fdf5-208">在 Lync Server 2013 中管理組織的 SIP 同盟網域</span><span class="sxs-lookup"><span data-stu-id="3fdf5-208">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [<span data-ttu-id="3fdf5-209">在 Lync Server 2013 中管理組織的 SIP 同盟提供者</span><span class="sxs-lookup"><span data-stu-id="3fdf5-209">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [<span data-ttu-id="3fdf5-210">在 Lync Server 2013 中管理 XMPP 同盟協力廠商</span><span class="sxs-lookup"><span data-stu-id="3fdf5-210">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [<span data-ttu-id="3fdf5-211">在 Lync Server 2013 中為 Lync Online 客戶設定同盟支援</span><span class="sxs-lookup"><span data-stu-id="3fdf5-211">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

