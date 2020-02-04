---
title: Lync Server 2013：常見的會議概念
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common conferencing concepts
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49733762
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91d21526cfcd6d2c78cd67660136e8f7600d1841
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a><span data-ttu-id="25236-102">Lync Server 2013 中的常見會議概念</span><span class="sxs-lookup"><span data-stu-id="25236-102">Common conferencing concepts in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25236-103">_**主題上次修改日期：** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="25236-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="25236-104">所有類型的會議共有幾個概念。</span><span class="sxs-lookup"><span data-stu-id="25236-104">Several concepts are common to all types of conferencing.</span></span> <span data-ttu-id="25236-105">以下各節將說明這些步驟。</span><span class="sxs-lookup"><span data-stu-id="25236-105">These are described in the following sections.</span></span>

<div>

## <a name="policies-and-bandwidth-management"></a><span data-ttu-id="25236-106">原則與頻寬管理</span><span class="sxs-lookup"><span data-stu-id="25236-106">Policies and Bandwidth Management</span></span>

<span data-ttu-id="25236-107">Lync Server 2013 可讓系統管理員針對使用者可以組織的會議類型設定原則。</span><span class="sxs-lookup"><span data-stu-id="25236-107">Lync Server 2013 enables administrators to set policies for the types of meetings that users can organize.</span></span> <span data-ttu-id="25236-108">這可協助您強制實施貴組織的原則並控制頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="25236-108">This helps you enforce your organization’s policies and control bandwidth usage.</span></span> <span data-ttu-id="25236-109">您可以定義各種會議原則，並將他們指派給個別的使用者和使用者群組。</span><span class="sxs-lookup"><span data-stu-id="25236-109">You can define a wide variety of meeting policies, and assign them to individual users and groups of users.</span></span> <span data-ttu-id="25236-110">您也可以設定控制對等交談的原則。</span><span class="sxs-lookup"><span data-stu-id="25236-110">You can also set policies that govern peer-to-peer conversations.</span></span> <span data-ttu-id="25236-111">如需設定會議原則的詳細資訊，請參閱作業檔中的[Lync Server 2013 中的會議原則](lync-server-2013-conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="25236-111">For details about setting conferencing policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md) in the Operations documentation.</span></span> <span data-ttu-id="25236-112">如需頻寬管理的詳細資料，請參閱[Lync server 2013 中的通話許可控制概覽](lync-server-2013-overview-of-call-admission-control.md)，以及[在 lync server 2013 中設定影片頻寬](lync-server-2013-configuring-video-bandwidth.md)。</span><span class="sxs-lookup"><span data-stu-id="25236-112">For details about bandwidth management, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md) and [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

</div>

<div>

## <a name="archiving-and-compliance-features"></a><span data-ttu-id="25236-113">封存與合規性功能</span><span class="sxs-lookup"><span data-stu-id="25236-113">Archiving and Compliance Features</span></span>

<span data-ttu-id="25236-114">如果您的組織必須遵循合規性規範，Lync Server 2013 提供您可以使用的功能。</span><span class="sxs-lookup"><span data-stu-id="25236-114">Lync Server 2013 provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="25236-115">您可以使用存檔功能來封存會議中呈現的內容，以及立即訊息（IM）交談和 IM 會議的內容。</span><span class="sxs-lookup"><span data-stu-id="25236-115">You can use the archiving abilities to archive content presented in meetings, and also the content of instant messaging (IM) conversations and IM conferences.</span></span> <span data-ttu-id="25236-116">如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的存檔規劃](lync-server-2013-planning-for-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="25236-116">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="25236-117">您可以使用 Persistent 聊天伺服器的相容性功能，來封存一段時間內保留的多方或主題式交談。</span><span class="sxs-lookup"><span data-stu-id="25236-117">You can use compliance features of Persistent Chat Server to archive multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="25236-118">如需詳細資訊，請參閱規劃檔中的[Lync server 2013 中的持續聊天伺服器規劃](lync-server-2013-planning-for-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="25236-118">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="monitoring-feature"></a><span data-ttu-id="25236-119">[監視] 功能</span><span class="sxs-lookup"><span data-stu-id="25236-119">Monitoring Feature</span></span>

<span data-ttu-id="25236-120">[監視伺服器] 功能可以捕獲通話詳細資料記錄（CDRs），您可以使用這些記錄來追蹤哪些使用者與使用 Lync Server 2013 的其他使用者交談。</span><span class="sxs-lookup"><span data-stu-id="25236-120">The Monitoring Server feature can capture call detail records (CDRs), which you can use to track which users talk to which other users using Lync Server 2013.</span></span> <span data-ttu-id="25236-121">如需有關部署和設定監視的詳細資料，請參閱[在 Lync Server 2013 中部署監視](lync-server-2013-deploying-monitoring.md)。</span><span class="sxs-lookup"><span data-stu-id="25236-121">For details about deploying and configuring monitoring, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a><span data-ttu-id="25236-122">在會議中啟用外部參與</span><span class="sxs-lookup"><span data-stu-id="25236-122">Enabling External Participation in Conferences</span></span>

<span data-ttu-id="25236-123">您可以讓外部使用者也能在受邀者參與會議時，在 Lync Server 2013 會議中大幅增加投資的好處。</span><span class="sxs-lookup"><span data-stu-id="25236-123">You can greatly increase the benefits of your investment in Lync Server 2013 conferencing by enabling external users to also participate in conferences when invited.</span></span> <span data-ttu-id="25236-124">外部使用者可以包括：</span><span class="sxs-lookup"><span data-stu-id="25236-124">External users can include:</span></span>

  - <span data-ttu-id="25236-125">\*\*\*\*    如果您組織的使用者是在您的防火牆外工作，且正在使用其膝上型電腦或其他 Lync Server 2013 裝置，則您組織的遠端使用者就是自己的使用者。</span><span class="sxs-lookup"><span data-stu-id="25236-125">**Remote Users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server 2013 devices.</span></span>

  - <span data-ttu-id="25236-126">**同盟使用者**   與公司合作的使用者，您可與其他人同時執行 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="25236-126">**Federated Users**   Users from companies you work with who also run Lync Server 2013.</span></span> <span data-ttu-id="25236-127">若要讓您的使用者能夠輕鬆地與這些使用者聯繫，您可以建立與這些公司的聯盟關聯。</span><span class="sxs-lookup"><span data-stu-id="25236-127">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="25236-128">**匿名使用者**   由您的使用者專門邀請之加入特定會議的任何其他外部使用者。</span><span class="sxs-lookup"><span data-stu-id="25236-128">**Anonymous Users**   Any other external users who are invited specifically by your users to join specific conferences.</span></span> <span data-ttu-id="25236-129">貴公司中的會議召集人可以傳送電子郵件給外部使用者的會議邀請。</span><span class="sxs-lookup"><span data-stu-id="25236-129">A meeting organizer in your company can send an email invitation for a conference to an external user.</span></span> <span data-ttu-id="25236-130">電子郵件包含外部使用者可以按一下以加入會議的連結。</span><span class="sxs-lookup"><span data-stu-id="25236-130">The email includes a link that the outside user can click to join the conference.</span></span>

<span data-ttu-id="25236-131">若要啟用任何一種或所有案例，您必須部署邊緣伺服器，以協助您在 Lync Server 2013 部署與外部使用者之間進行安全通訊。</span><span class="sxs-lookup"><span data-stu-id="25236-131">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server 2013 deployment and external users.</span></span> <span data-ttu-id="25236-132">使用 Edge 伺服器的 Lync Server 2013 解決方案比其他解決方案（例如虛擬私人網路（VPN））提供較高的品質。</span><span class="sxs-lookup"><span data-stu-id="25236-132">The Lync Server 2013 solution using Edge Servers provides higher quality media than other solutions such as a virtual private network (VPN).</span></span> <span data-ttu-id="25236-133">如需詳細資訊，請參閱[在 Lync Server 2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="25236-133">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<span data-ttu-id="25236-134">此外，無論您是否部署邊緣伺服器，您都可以讓使用者（無論是組織內部或外部）從標準 PSTN 手機撥入，以加入內部部署的音訊會議。</span><span class="sxs-lookup"><span data-stu-id="25236-134">Additionally, whether or not you deploy Edge Servers, you can enable users (that is, either inside or outside your organization) to dial in from standard PSTN phones to join on-premises audio conferences.</span></span> <span data-ttu-id="25236-135">這是透過部署 Lync Server 2013 電話撥入式會議來完成。</span><span class="sxs-lookup"><span data-stu-id="25236-135">This is accomplished by deploying Lync Server 2013 dial-in conferencing.</span></span>

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a><span data-ttu-id="25236-136">會議類型與用戶端版本之間的相容性</span><span class="sxs-lookup"><span data-stu-id="25236-136">Compatibility Among Meeting Types and Client Versions</span></span>

<span data-ttu-id="25236-137">如果您要讓 Lync Server 2013 與舊版 Office 通訊伺服器及其用戶端互動，您必須注意下列問題：</span><span class="sxs-lookup"><span data-stu-id="25236-137">If you are going to have Lync Server 2013 interoperate with previous versions of Office Communications Server and its clients, you must be aware of the following issues:</span></span>

  - <span data-ttu-id="25236-138">使用 Lync Server 2013 的使用者無法排程 Live Meeting 會議，或修改此類型的任何已遷移會議。</span><span class="sxs-lookup"><span data-stu-id="25236-138">Users using Lync Server 2013 cannot schedule Live Meeting conferences, or modify any migrated meetings of this type.</span></span>

  - <span data-ttu-id="25236-139">使用 Lync Server 2013 的使用者必須在運行 Office 通訊伺服器 2007 R2 的伺服器上安裝 live Meeting 會議（除了 Lync Server 2013 之外），才能參與這些會議。</span><span class="sxs-lookup"><span data-stu-id="25236-139">Users using Lync Server 2013 who need to attend Live Meeting conferences hosted on servers running Office Communications Server 2007 R2 must have the Live Meeting client installed on their computer (in addition to Lync Server 2013) to attend these meetings.</span></span>

  - <span data-ttu-id="25236-140">當 Live Meeting 會議遷移至 Lync Server 2013 時，會議內容不會遷移。</span><span class="sxs-lookup"><span data-stu-id="25236-140">When Live Meeting conferences are migrated to Lync Server 2013, meeting content does not migrate.</span></span> <span data-ttu-id="25236-141">如果需要此內容，必須再次上傳它。</span><span class="sxs-lookup"><span data-stu-id="25236-141">If this content is needed, it must be uploaded again.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

