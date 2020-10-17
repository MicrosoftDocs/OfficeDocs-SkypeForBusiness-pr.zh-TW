---
title: Lync Server 2013 簡介
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2878f47fcace98bbd9e156f24c2b87e85faf728
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525230"
---
# <a name="introduction-to-lync-server-2013"></a><span data-ttu-id="b29fa-102">Lync Server 2013 簡介</span><span class="sxs-lookup"><span data-stu-id="b29fa-102">Introduction to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b29fa-103">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="b29fa-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="b29fa-104">Lync Server 2013 及其用戶端軟體（如 Lync 2013）可讓您的使用者以新的方式連線並保持連線，不論其物理位置為何。</span><span class="sxs-lookup"><span data-stu-id="b29fa-104">Lync Server 2013 and its client software, such as Lync 2013, enable your users to connect in new ways and to stay connected, regardless of their physical location.</span></span> <span data-ttu-id="b29fa-105">Lync 和 Lync Server 會集中在單一用戶端介面中通訊的不同方式，以整合平臺的方式部署，並透過單一管理基礎結構進行管理。</span><span class="sxs-lookup"><span data-stu-id="b29fa-105">Lync and Lync Server bring together the different ways that people communicate in a single client interface, are deployed as a unified platform, and are administered through a single management infrastructure.</span></span>

<span data-ttu-id="b29fa-106">此表格及下列各節說明 Lync Server 為您的使用者提供的主要功能組或 *工作負載*。</span><span class="sxs-lookup"><span data-stu-id="b29fa-106">This table and the following sections illustrate the major feature sets, or *workloads*, that Lync Server provides for your users.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b29fa-107">工作負載</span><span class="sxs-lookup"><span data-stu-id="b29fa-107">Workload</span></span></th>
<th><span data-ttu-id="b29fa-108">描述</span><span class="sxs-lookup"><span data-stu-id="b29fa-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b29fa-109">IM 與顯示狀態</span><span class="sxs-lookup"><span data-stu-id="b29fa-109">IM and presence</span></span></p></td>
<td><p><span data-ttu-id="b29fa-110">立即訊息 (IM) 與顯示狀態，可協助您的使用者有效且有效地尋找及與彼此進行通訊。</span><span class="sxs-lookup"><span data-stu-id="b29fa-110">Instant messaging (IM) and presence help your users find and communicate with one another efficiently and effectively.</span></span></p>
<p><span data-ttu-id="b29fa-111">IM 可提供「立即訊息平臺」與「交談記錄」，並支援與公用 IM 網路的使用者進行公用 IM 連線，例如 MSN/Windows Live、Yahoo！、AOL 和 Google 交談。</span><span class="sxs-lookup"><span data-stu-id="b29fa-111">IM provides an instant messaging platform with conversation history, and supports public IM connectivity with users of public IM networks such as MSN/Windows Live, Yahoo!, AOL, and Google Talk.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="b29fa-112">從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。</span><span class="sxs-lookup"><span data-stu-id="b29fa-112">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="b29fa-113">具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="b29fa-113">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="b29fa-114">信使直到服務關閉日期。</span><span class="sxs-lookup"><span data-stu-id="b29fa-114">Messenger until the service shut down date.</span></span> <span data-ttu-id="b29fa-115">AOL 和 Yahoo！的循環結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="b29fa-115">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="b29fa-116">已宣告。</span><span class="sxs-lookup"><span data-stu-id="b29fa-116">has been announced.</span></span> <span data-ttu-id="b29fa-117">如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</span><span class="sxs-lookup"><span data-stu-id="b29fa-117">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="b29fa-118">PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="b29fa-118">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="b29fa-119">信使。</span><span class="sxs-lookup"><span data-stu-id="b29fa-119">Messenger.</span></span> <span data-ttu-id="b29fa-120">Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</span><span class="sxs-lookup"><span data-stu-id="b29fa-120">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="b29fa-121">Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。</span><span class="sxs-lookup"><span data-stu-id="b29fa-121">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="b29fa-122">與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="b29fa-122">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="b29fa-123">隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</span><span class="sxs-lookup"><span data-stu-id="b29fa-123">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div>
<p><span data-ttu-id="b29fa-124"><strong>目前</strong>狀態會建立並顯示使用者的個人可用性和意願，以透過使用的常見狀態（如正確或<strong>忙碌</strong>）進行通訊，以及更詳細的狀態，如正確，也就<strong>是</strong>「<strong>請勿打擾</strong>」。</span><span class="sxs-lookup"><span data-stu-id="b29fa-124">Presence establishes and displays a user’s personal availability and willingness to communicate through the use of common states such as <strong>Available</strong> or <strong>Busy</strong>, as well as more detailed states such as <strong>Be Right Back</strong> and <strong>Do Not Disturb</strong>.</span></span> <span data-ttu-id="b29fa-125">這種豐富的目前狀態資訊可讓其他使用者立即進行有效的通訊選擇。</span><span class="sxs-lookup"><span data-stu-id="b29fa-125">This rich presence information enables other users to immediately make effective communication choices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b29fa-126">會議</span><span class="sxs-lookup"><span data-stu-id="b29fa-126">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="b29fa-127">Lync Server 包含對排程和即時會議的 IM 會議、音訊會議、web 會議、影片會議和應用程式共用的支援。</span><span class="sxs-lookup"><span data-stu-id="b29fa-127">Lync Server includes support for IM conferencing, audio conferencing, web conferencing, video conferencing, and application sharing, for both scheduled and impromptu meetings.</span></span> <span data-ttu-id="b29fa-128">所有這些會議類型都支援單一用戶端。</span><span class="sxs-lookup"><span data-stu-id="b29fa-128">All these meeting types are supported with a single client.</span></span> <span data-ttu-id="b29fa-129">Lync Server 也支援電話撥入式會議，讓公用交換電話網路 (PSTN) 電話的使用者可以參與會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="b29fa-129">Lync Server also supports dial-in conferencing so that users of public switched telephone network (PSTN) phones can participate in the audio portion of conferences.</span></span></p>
<p><span data-ttu-id="b29fa-130">會議可以即時無縫地變更與成長。</span><span class="sxs-lookup"><span data-stu-id="b29fa-130">Conferences can seamlessly change and grow in real time.</span></span> <span data-ttu-id="b29fa-131">例如，單一會議可以在少數使用者之間開始立即訊息，並透過桌面共用和較大的物件立即、輕鬆且不中斷交談流程的方式升級至音訊會議。</span><span class="sxs-lookup"><span data-stu-id="b29fa-131">For example, a single conference can start as just instant messages between a few users, and escalate to an audio conference with desktop sharing and a larger audience instantly, easily, and without interrupting the conversation flow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b29fa-132">設定使用者</span><span class="sxs-lookup"><span data-stu-id="b29fa-132">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="b29fa-133"><em>Enterprise voice</em> 是 Lync Server 中) 提供的語音 Over 網際網路通訊協定 (VoIP。</span><span class="sxs-lookup"><span data-stu-id="b29fa-133"><em>Enterprise Voice</em> is the Voice over Internet Protocol (VoIP) offering in Lync Server.</span></span> <span data-ttu-id="b29fa-134">它會提供語音選項，以加強或取代傳統專用交換機 exchange (PBX) 系統。</span><span class="sxs-lookup"><span data-stu-id="b29fa-134">It delivers a voice option to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="b29fa-135">除了 IP PBX 的完整電話語音功能之外，企業語音已與豐富的目前狀態、IM、共同作業和會議整合。</span><span class="sxs-lookup"><span data-stu-id="b29fa-135">In addition to the complete telephony capabilities of an IP PBX, Enterprise Voice is integrated with rich presence, IM, collaboration, and meetings.</span></span> <span data-ttu-id="b29fa-136">可直接支援通話答案、保留、繼續、轉接、轉寄和轉移等功能，而個人化速度撥號機碼會取代為連絡人清單，而自動 intercom 會取代為 IM。</span><span class="sxs-lookup"><span data-stu-id="b29fa-136">Features such as call answer, hold, resume, transfer, forward and divert are supported directly, while personalized speed dialing keys are replaced by Contacts lists, and automatic intercom is replaced with IM.</span></span></p>
<p><span data-ttu-id="b29fa-137">Enterprise Voice 支援通過通話許可控制的高可用性 (CAC) 、分支機搆留存能力，以及資料恢復的延伸選項。</span><span class="sxs-lookup"><span data-stu-id="b29fa-137">Enterprise Voice supports high availability through call admission control (CAC), branch office survivability, and extended options for data resiliency.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b29fa-138">遠端使用者的支援</span><span class="sxs-lookup"><span data-stu-id="b29fa-138">Support for remote users</span></span></p></td>
<td><p><span data-ttu-id="b29fa-139">您可以透過部署稱為 <em>Edge</em> server 的伺服器，為這些遠端使用者提供連線，為目前組織防火牆外部的使用者提供完整的 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="b29fa-139">You can provide full Lync Server functionality for users who are currently outside your organization’s firewalls by deploying servers called <em>Edge Servers</em> to provide a connection for these remote users.</span></span> <span data-ttu-id="b29fa-140">這些遠端使用者可以使用已安裝 Lync 2013 的個人電腦、電話或 web 介面，連線至會議。</span><span class="sxs-lookup"><span data-stu-id="b29fa-140">These remote users can connect to conferences by using a personal computer with Lync 2013 installed, the phone, or a web interface.</span></span></p>
<p><span data-ttu-id="b29fa-141">部署 Edge Server 也可讓您與合作夥伴或廠商組織 <em>聯盟</em> 。</span><span class="sxs-lookup"><span data-stu-id="b29fa-141">Deploying Edge Servers also enables you to <em>federate</em> with partner or vendor organizations.</span></span> <span data-ttu-id="b29fa-142">同盟關聯可讓您的使用者將同盟使用者放在其連絡人清單、exchange 目前狀態資訊和立即訊息與這些使用者，並邀請他們撥打語音通話、影片通話和會議。</span><span class="sxs-lookup"><span data-stu-id="b29fa-142">A federated relationship enables your users to put federated users on their Contacts lists, exchange presence information and instant messages with these users, and invite them to audio calls, video calls, and conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b29fa-143">行動用戶端支援</span><span class="sxs-lookup"><span data-stu-id="b29fa-143">Mobile client support</span></span></p></td>
<td><p><span data-ttu-id="b29fa-144">此外，借助 Lync Server 行動服務，您的使用者可以在使用支援的 Apple iOS、Android、Windows Phone 或 Nokia 行動裝置時存取 Lync 功能，並執行類似傳送和接收立即訊息、查看連絡人及查看顯示狀態等活動。</span><span class="sxs-lookup"><span data-stu-id="b29fa-144">Additionally, with Lync Server mobility services, your users can access Lync functionality when using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices and perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="b29fa-145">此外，行動裝置還可支援某些 Enterprise Voice 功能，例如按一下加入會議、從公司撥號、單一號碼搜尋、語音信箱及未接來電。</span><span class="sxs-lookup"><span data-stu-id="b29fa-145">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="b29fa-146">對於不支援在後臺執行之應用程式的行動裝置，也支援推播通知。</span><span class="sxs-lookup"><span data-stu-id="b29fa-146">Push notifications are also supported for mobile devices that do not support applications running in the background.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b29fa-147">與其他產品整合</span><span class="sxs-lookup"><span data-stu-id="b29fa-147">Integration with other products</span></span></p></td>
<td><p><span data-ttu-id="b29fa-148">Lync Server 會與其他數種產品整合，為您的使用者和系統管理員提供額外的好處。</span><span class="sxs-lookup"><span data-stu-id="b29fa-148">Lync Server integrates with several other products to provide additional benefits to your users and administrators.</span></span></p>
<p><span data-ttu-id="b29fa-149">會議工具已整合至 Outlook，讓召集人可以透過單一按一下來排程會議或啟動即時會議，並使出席者輕鬆加入。</span><span class="sxs-lookup"><span data-stu-id="b29fa-149">Meeting tools are integrated into Outlook to enable organizers to schedule a meeting or start an impromptu conference with a single click and make it just as easy for attendees to join.</span></span></p>
<p><span data-ttu-id="b29fa-150">目前狀態資訊已整合至 Outlook 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="b29fa-150">Presence information is integrated into Outlook and SharePoint.</span></span></p>
<p><span data-ttu-id="b29fa-151">Exchange 整合通訊 (UM) 提供數種整合功能。</span><span class="sxs-lookup"><span data-stu-id="b29fa-151">Exchange Unified Messaging (UM) provides several integration features.</span></span> <span data-ttu-id="b29fa-152">使用者可以查看是否有 Lync Server 中的新語音信箱。</span><span class="sxs-lookup"><span data-stu-id="b29fa-152">Users can see if they have new voice mail within Lync Server.</span></span> <span data-ttu-id="b29fa-153">他們可以按一下 Outlook 訊息中的 [播放] 按鈕，收聽音訊語音信箱，或在通知訊息中查看語音信箱。</span><span class="sxs-lookup"><span data-stu-id="b29fa-153">They can click a play button in the Outlook message to hear the audio voice mail, or view a transcription of the voice mail in the notification message.</span></span></p>
<p><span data-ttu-id="b29fa-154">此外，使用 Exchange 2013 來執行 Lync Server 2013，可啟用多種新功能，例如整合連絡人存放區，可供兩種產品的用戶端存取，以及儲存在 Exchange 2013 資料庫中之連絡人的高解析度相片。</span><span class="sxs-lookup"><span data-stu-id="b29fa-154">Additionally, running Lync Server 2013 with Exchange 2013 enables several new features such as a unified contact store which can be accessed by clients of both products, as well as high-resolution photos for contacts which are stored in the Exchange 2013 database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b29fa-155">簡易部署</span><span class="sxs-lookup"><span data-stu-id="b29fa-155">Simple deployment</span></span></p></td>
<td><p><span data-ttu-id="b29fa-156">為了協助您規劃及部署伺服器及用戶端，Lync Server 會提供拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="b29fa-156">To help you plan and deploy your servers and clients, Lync Server provides the Topology Builder.</span></span></p>
<p><span data-ttu-id="b29fa-157">拓撲產生器是 Lync Server 的安裝元件。</span><span class="sxs-lookup"><span data-stu-id="b29fa-157">Topology Builder is an installation component of Lync Server.</span></span> <span data-ttu-id="b29fa-158">您可以使用拓撲產生器來建立、調整和發行您規劃的拓撲。</span><span class="sxs-lookup"><span data-stu-id="b29fa-158">You use Topology Builder to create, adjust and publish your planned topology.</span></span> <span data-ttu-id="b29fa-159">在您開始伺服器安裝之前，它也會驗證您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="b29fa-159">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="b29fa-160">當您在個別伺服器上安裝 Lync Server 時，安裝程式會以拓撲中的導向方式來部署伺服器。</span><span class="sxs-lookup"><span data-stu-id="b29fa-160">When you install Lync Server on individual servers, the installation program deploys the server as directed in the topology.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b29fa-161">簡易管理</span><span class="sxs-lookup"><span data-stu-id="b29fa-161">Simple management</span></span></p></td>
<td><p><span data-ttu-id="b29fa-162">在您部署 Lync Server 之後，它會提供下列功能強大且簡化的管理工具：</span><span class="sxs-lookup"><span data-stu-id="b29fa-162">After you deploy Lync Server, it offers the following powerful and streamlined management tools:</span></span></p>
<ul>
<li><p><span data-ttu-id="b29fa-163">中央設定管理，可讓您集中管理變更，並將變更快速複寫至整個部署。</span><span class="sxs-lookup"><span data-stu-id="b29fa-163">Central configuration management, which enables you to manage changes centrally and have them replicated quickly to the entire deployment.</span></span></p></li>
<li><p><span data-ttu-id="b29fa-164">Lync Server 控制台，是系統管理員的 web 型圖形使用者介面。</span><span class="sxs-lookup"><span data-stu-id="b29fa-164">Lync Server Control Panel, a web-based graphical user interface for administrators.</span></span> <span data-ttu-id="b29fa-165">透過這種以 web 為基礎的 UI，Lync Server 系統管理員可以從公司網路的任何地方管理其系統，而不需要在其電腦上安裝專門的管理軟體。</span><span class="sxs-lookup"><span data-stu-id="b29fa-165">With this web-based UI, Lync Server administrators can manage their systems from anywhere on the corporate network, without needing specialized management software installed on their computers.</span></span></p></li>
<li><p><span data-ttu-id="b29fa-166">Lync Server 管理命令介面命令列管理工具，以 Windows PowerShell 命令列介面為基礎。</span><span class="sxs-lookup"><span data-stu-id="b29fa-166">Lync Server Management Shell command-line management tool, which is based on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="b29fa-167">它會提供豐富的命令集，以管理產品的各個層面，並讓 Lync Server 系統管理員可以使用熟悉的工具來自動化重複的工作。</span><span class="sxs-lookup"><span data-stu-id="b29fa-167">It provides a rich command set for administration of all aspects of the product, and enables Lync Server administrators to automate repetitive tasks using a familiar tool.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b29fa-168">當 IM 及顯示狀態功能會自動安裝在每個 Lync Server 部署中時，您可以選擇是否要部署會議、Enterprise Voice 及遠端使用者存取，以根據組織的需求來定義您的部署。</span><span class="sxs-lookup"><span data-stu-id="b29fa-168">While the IM and presence features are automatically installed in every Lync Server deployment, you can choose whether to deploy conferencing, Enterprise Voice, and remote user access, to tailor your deployment to your organization’s needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b29fa-169">本章節內容</span><span class="sxs-lookup"><span data-stu-id="b29fa-169">In This Section</span></span>

  - [<span data-ttu-id="b29fa-170">Lync Server 2013 中的 IM 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="b29fa-170">IM and presence in Lync Server 2013</span></span>](lync-server-2013-im-and-presence.md)

  - [<span data-ttu-id="b29fa-171">Lync Server 2013 中的會議</span><span class="sxs-lookup"><span data-stu-id="b29fa-171">Conferencing in Lync Server 2013</span></span>](lync-server-2013-conferencing.md)

  - [<span data-ttu-id="b29fa-172">Lync Server 2013 中的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="b29fa-172">Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice.md)

  - [<span data-ttu-id="b29fa-173">可擴充性搭配 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b29fa-173">Scalability with Lync Server 2013</span></span>](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

