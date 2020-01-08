---
title: Lync Server 2013 簡介
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df182c8d58d6f1e60b164fbb28299945f6a8cba3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a><span data-ttu-id="a0c54-102">Lync Server 2013 簡介</span><span class="sxs-lookup"><span data-stu-id="a0c54-102">Introduction to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0c54-103">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="a0c54-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="a0c54-104">Lync Server 2013 及其用戶端軟體（例如 Lync 2013）可讓您的使用者以新的方式連線並保持連線，無論其物理位置為何。</span><span class="sxs-lookup"><span data-stu-id="a0c54-104">Lync Server 2013 and its client software, such as Lync 2013, enable your users to connect in new ways and to stay connected, regardless of their physical location.</span></span> <span data-ttu-id="a0c54-105">Lync 和 Lync Server 會將人們在單一用戶端介面中通訊的不同方式整合在一起，並以單一管理基礎結構的方式來管理。</span><span class="sxs-lookup"><span data-stu-id="a0c54-105">Lync and Lync Server bring together the different ways that people communicate in a single client interface, are deployed as a unified platform, and are administered through a single management infrastructure.</span></span>

<span data-ttu-id="a0c54-106">此表格和下列各節說明 Lync Server 針對您的使用者提供的主要功能集或*工作負荷*。</span><span class="sxs-lookup"><span data-stu-id="a0c54-106">This table and the following sections illustrate the major feature sets, or *workloads*, that Lync Server provides for your users.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0c54-107">負載</span><span class="sxs-lookup"><span data-stu-id="a0c54-107">Workload</span></span></th>
<th><span data-ttu-id="a0c54-108">描述</span><span class="sxs-lookup"><span data-stu-id="a0c54-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0c54-109">IM 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="a0c54-109">IM and presence</span></span></p></td>
<td><p><span data-ttu-id="a0c54-110">[立即訊息（IM）] 與「目前狀態」可協助您的使用者以更有效率的方式與其他人找到並溝通。</span><span class="sxs-lookup"><span data-stu-id="a0c54-110">Instant messaging (IM) and presence help your users find and communicate with one another efficiently and effectively.</span></span></p>
<p><span data-ttu-id="a0c54-111">IM 會提供包含交談記錄的立即訊息平臺，並支援與公用 IM 網路（例如 MSN/Windows Live、Yahoo！、AOL 和 Google 交談）使用者的公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="a0c54-111">IM provides an instant messaging platform with conversation history, and supports public IM connectivity with users of public IM networks such as MSN/Windows Live, Yahoo!, AOL, and Google Talk.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="a0c54-112">從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。</span><span class="sxs-lookup"><span data-stu-id="a0c54-112">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="a0c54-113">擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="a0c54-113">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="a0c54-114">信使，直到服務關閉日期為止。</span><span class="sxs-lookup"><span data-stu-id="a0c54-114">Messenger until the service shut down date.</span></span> <span data-ttu-id="a0c54-115">AOL 和 Yahoo！的存留期結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="a0c54-115">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="a0c54-116">已公佈。</span><span class="sxs-lookup"><span data-stu-id="a0c54-116">has been announced.</span></span> <span data-ttu-id="a0c54-117">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</span><span class="sxs-lookup"><span data-stu-id="a0c54-117">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="a0c54-118">PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="a0c54-118">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="a0c54-119">名單.</span><span class="sxs-lookup"><span data-stu-id="a0c54-119">Messenger.</span></span> <span data-ttu-id="a0c54-120">Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</span><span class="sxs-lookup"><span data-stu-id="a0c54-120">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="a0c54-121">Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。</span><span class="sxs-lookup"><span data-stu-id="a0c54-121">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="a0c54-122">與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="a0c54-122">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="a0c54-123">您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="a0c54-123">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div>
<p><span data-ttu-id="a0c54-124">目前狀態會建立並顯示使用者的個人可用性，以及透過使用通用狀態（例如 [<strong>可用</strong>] 或 [<strong>忙碌</strong>]），以及更詳細的狀態（例如，<strong>立即返回</strong>和 [<strong>請勿打擾</strong>]）來進行溝通。</span><span class="sxs-lookup"><span data-stu-id="a0c54-124">Presence establishes and displays a user’s personal availability and willingness to communicate through the use of common states such as <strong>Available</strong> or <strong>Busy</strong>, as well as more detailed states such as <strong>Be Right Back</strong> and <strong>Do Not Disturb</strong>.</span></span> <span data-ttu-id="a0c54-125">這個豐富的目前狀態資訊可讓其他使用者立即進行有效的通訊選項。</span><span class="sxs-lookup"><span data-stu-id="a0c54-125">This rich presence information enables other users to immediately make effective communication choices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0c54-126">會議</span><span class="sxs-lookup"><span data-stu-id="a0c54-126">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="a0c54-127">Lync 伺服器支援針對排程與臨時會議進行 IM 會議、音訊會議、網路會議、視訊會議及應用程式共用等支援。</span><span class="sxs-lookup"><span data-stu-id="a0c54-127">Lync Server includes support for IM conferencing, audio conferencing, web conferencing, video conferencing, and application sharing, for both scheduled and impromptu meetings.</span></span> <span data-ttu-id="a0c54-128">單一用戶端支援所有這些會議類型。</span><span class="sxs-lookup"><span data-stu-id="a0c54-128">All these meeting types are supported with a single client.</span></span> <span data-ttu-id="a0c54-129">Lync Server 也支援電話撥入式會議，讓公開交換電話網絡（PSTN）電話的使用者可以參與會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="a0c54-129">Lync Server also supports dial-in conferencing so that users of public switched telephone network (PSTN) phones can participate in the audio portion of conferences.</span></span></p>
<p><span data-ttu-id="a0c54-130">會議可以即時地以無縫方式變更和放大。</span><span class="sxs-lookup"><span data-stu-id="a0c54-130">Conferences can seamlessly change and grow in real time.</span></span> <span data-ttu-id="a0c54-131">例如，單一會議可以在幾個使用者之間立即訊息的方式開始，並透過桌面共用和較大的觀眾立即、輕鬆且不中斷交談流程來上報音訊會議。</span><span class="sxs-lookup"><span data-stu-id="a0c54-131">For example, a single conference can start as just instant messages between a few users, and escalate to an audio conference with desktop sharing and a larger audience instantly, easily, and without interrupting the conversation flow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0c54-132">企業語音</span><span class="sxs-lookup"><span data-stu-id="a0c54-132">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="a0c54-133"><em>企業語音</em>是 Lync Server 中的 [透過網際網路通訊協定（VoIP）] 提供的語音。</span><span class="sxs-lookup"><span data-stu-id="a0c54-133"><em>Enterprise Voice</em> is the Voice over Internet Protocol (VoIP) offering in Lync Server.</span></span> <span data-ttu-id="a0c54-134">它會提供語音選項來加強或取代傳統的專用分支 exchange （PBX）系統。</span><span class="sxs-lookup"><span data-stu-id="a0c54-134">It delivers a voice option to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="a0c54-135">除了 IP PBX 的完整電話功能之外，企業語音已整合為豐富的目前狀態、IM、共同作業和會議。</span><span class="sxs-lookup"><span data-stu-id="a0c54-135">In addition to the complete telephony capabilities of an IP PBX, Enterprise Voice is integrated with rich presence, IM, collaboration, and meetings.</span></span> <span data-ttu-id="a0c54-136">您可以直接支援通話應答、保留、繼續、傳輸、轉寄和轉移等功能，而個人化速度撥號金鑰會由連絡人清單取代，自動 intercom 會以 IM 取代。</span><span class="sxs-lookup"><span data-stu-id="a0c54-136">Features such as call answer, hold, resume, transfer, forward and divert are supported directly, while personalized speed dialing keys are replaced by Contacts lists, and automatic intercom is replaced with IM.</span></span></p>
<p><span data-ttu-id="a0c54-137">企業語音支援透過呼叫許可控制（CAC）、分支辦公室留存以及資料復原的延伸選項，提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="a0c54-137">Enterprise Voice supports high availability through call admission control (CAC), branch office survivability, and extended options for data resiliency.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0c54-138">支援遠端使用者</span><span class="sxs-lookup"><span data-stu-id="a0c54-138">Support for remote users</span></span></p></td>
<td><p><span data-ttu-id="a0c54-139">您可以透過部署稱為 [ <em>Edge 伺服器</em>] 的伺服器，為這些遠端使用者提供連線，以提供完整的 Lync 伺服器功能供您組織防火牆以外的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="a0c54-139">You can provide full Lync Server functionality for users who are currently outside your organization’s firewalls by deploying servers called <em>Edge Servers</em> to provide a connection for these remote users.</span></span> <span data-ttu-id="a0c54-140">這些遠端使用者可以使用安裝了 Lync 2013、手機或網頁介面的個人電腦，連線至會議。</span><span class="sxs-lookup"><span data-stu-id="a0c54-140">These remote users can connect to conferences by using a personal computer with Lync 2013 installed, the phone, or a web interface.</span></span></p>
<p><span data-ttu-id="a0c54-141">部署 Edge 伺服器也能讓您與合作夥伴或供應商組織<em>聯盟</em>。</span><span class="sxs-lookup"><span data-stu-id="a0c54-141">Deploying Edge Servers also enables you to <em>federate</em> with partner or vendor organizations.</span></span> <span data-ttu-id="a0c54-142">同盟關聯可讓您的使用者將聯盟使用者放在連絡人清單、exchange 目前狀態資訊與這些使用者的立即訊息，並邀請他們加入語音通話、視頻通話及會議。</span><span class="sxs-lookup"><span data-stu-id="a0c54-142">A federated relationship enables your users to put federated users on their Contacts lists, exchange presence information and instant messages with these users, and invite them to audio calls, video calls, and conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0c54-143">行動用戶端支援</span><span class="sxs-lookup"><span data-stu-id="a0c54-143">Mobile client support</span></span></p></td>
<td><p><span data-ttu-id="a0c54-144">此外，使用 Lync Server 行動服務，您的使用者可以在使用支援的 Apple iOS、Android、Windows Phone 或 Nokia 行動裝置時存取 Lync 功能，並以傳送和接收立即訊息、查看連絡人的方式執行這類活動。並查看目前狀態。</span><span class="sxs-lookup"><span data-stu-id="a0c54-144">Additionally, with Lync Server mobility services, your users can access Lync functionality when using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices and perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="a0c54-145">此外，行動裝置支援一些企業語音功能，例如按一下以加入會議、透過工作撥打電話、單一號碼達到、語音信箱及未接來電。</span><span class="sxs-lookup"><span data-stu-id="a0c54-145">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="a0c54-146">對於不支援在背景中執行之應用程式的行動裝置，也支援推播通知。</span><span class="sxs-lookup"><span data-stu-id="a0c54-146">Push notifications are also supported for mobile devices that do not support applications running in the background.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0c54-147">與其他產品整合</span><span class="sxs-lookup"><span data-stu-id="a0c54-147">Integration with other products</span></span></p></td>
<td><p><span data-ttu-id="a0c54-148">Lync Server 與數個其他產品整合，為您的使用者和系統管理員帶來額外的好處。</span><span class="sxs-lookup"><span data-stu-id="a0c54-148">Lync Server integrates with several other products to provide additional benefits to your users and administrators.</span></span></p>
<p><span data-ttu-id="a0c54-149">會議工具已整合至 Outlook，讓召集人可以一次性排程會議或啟動臨時會議，並讓出席者輕鬆加入會議。</span><span class="sxs-lookup"><span data-stu-id="a0c54-149">Meeting tools are integrated into Outlook to enable organizers to schedule a meeting or start an impromptu conference with a single click and make it just as easy for attendees to join.</span></span></p>
<p><span data-ttu-id="a0c54-150">目前狀態資訊已整合至 Outlook 和 SharePoint 中。</span><span class="sxs-lookup"><span data-stu-id="a0c54-150">Presence information is integrated into Outlook and SharePoint.</span></span></p>
<p><span data-ttu-id="a0c54-151">Exchange 整合通訊（UM）提供數個整合功能。</span><span class="sxs-lookup"><span data-stu-id="a0c54-151">Exchange Unified Messaging (UM) provides several integration features.</span></span> <span data-ttu-id="a0c54-152">使用者可以查看在 Lync Server 中是否有新的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="a0c54-152">Users can see if they have new voice mail within Lync Server.</span></span> <span data-ttu-id="a0c54-153">他們可以按一下 Outlook 訊息中的 [播放] 按鈕來聽到音訊語音信箱，或在通知訊息中查看語音信箱。</span><span class="sxs-lookup"><span data-stu-id="a0c54-153">They can click a play button in the Outlook message to hear the audio voice mail, or view a transcription of the voice mail in the notification message.</span></span></p>
<p><span data-ttu-id="a0c54-154">此外，使用 Exchange 2013 執行 Lync Server 2013 時，您可以透過兩個產品的用戶端存取多個新功能（例如，這是 Exchange 2013 資料庫中的連絡人），以及高解析度的相片。</span><span class="sxs-lookup"><span data-stu-id="a0c54-154">Additionally, running Lync Server 2013 with Exchange 2013 enables several new features such as a unified contact store which can be accessed by clients of both products, as well as high-resolution photos for contacts which are stored in the Exchange 2013 database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0c54-155">簡單的部署</span><span class="sxs-lookup"><span data-stu-id="a0c54-155">Simple deployment</span></span></p></td>
<td><p><span data-ttu-id="a0c54-156">為了協助您規劃及部署伺服器和用戶端，Lync Server 提供拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="a0c54-156">To help you plan and deploy your servers and clients, Lync Server provides the Topology Builder.</span></span></p>
<p><span data-ttu-id="a0c54-157">[拓撲建立器] 是 Lync Server 的安裝元件。</span><span class="sxs-lookup"><span data-stu-id="a0c54-157">Topology Builder is an installation component of Lync Server.</span></span> <span data-ttu-id="a0c54-158">您可以使用 [拓撲建立器] 來建立、調整及發佈您規劃的拓撲。</span><span class="sxs-lookup"><span data-stu-id="a0c54-158">You use Topology Builder to create, adjust and publish your planned topology.</span></span> <span data-ttu-id="a0c54-159">它也會在您開始伺服器安裝之前驗證您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="a0c54-159">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="a0c54-160">當您在個別伺服器上安裝 Lync Server 時，安裝程式會以拓撲中的指示方式來部署伺服器。</span><span class="sxs-lookup"><span data-stu-id="a0c54-160">When you install Lync Server on individual servers, the installation program deploys the server as directed in the topology.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0c54-161">簡單的管理</span><span class="sxs-lookup"><span data-stu-id="a0c54-161">Simple management</span></span></p></td>
<td><p><span data-ttu-id="a0c54-162">在您部署 Lync Server 之後，它會提供下列功能強大且精簡的管理工具：</span><span class="sxs-lookup"><span data-stu-id="a0c54-162">After you deploy Lync Server, it offers the following powerful and streamlined management tools:</span></span></p>
<ul>
<li><p><span data-ttu-id="a0c54-163">中央設定管理，可讓您集中管理變更，並將這些變更快速複製到整個部署。</span><span class="sxs-lookup"><span data-stu-id="a0c54-163">Central configuration management, which enables you to manage changes centrally and have them replicated quickly to the entire deployment.</span></span></p></li>
<li><p><span data-ttu-id="a0c54-164">Lync Server 控制台，為系統管理員提供的 web 圖形使用者介面。</span><span class="sxs-lookup"><span data-stu-id="a0c54-164">Lync Server Control Panel, a web-based graphical user interface for administrators.</span></span> <span data-ttu-id="a0c54-165">透過這個以 web 為基礎的 UI，Lync Server 系統管理員可以從公司網路的任何地方管理其系統，而不需要在電腦上安裝專用管理軟體。</span><span class="sxs-lookup"><span data-stu-id="a0c54-165">With this web-based UI, Lync Server administrators can manage their systems from anywhere on the corporate network, without needing specialized management software installed on their computers.</span></span></p></li>
<li><p><span data-ttu-id="a0c54-166">Lync Server 管理命令介面命令列管理工具，以 Windows PowerShell 命令列介面為基礎。</span><span class="sxs-lookup"><span data-stu-id="a0c54-166">Lync Server Management Shell command-line management tool, which is based on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="a0c54-167">它提供豐富的命令集來管理產品的所有方面，並讓 Lync Server 系統管理員使用熟悉的工具自動化重複的工作。</span><span class="sxs-lookup"><span data-stu-id="a0c54-167">It provides a rich command set for administration of all aspects of the product, and enables Lync Server administrators to automate repetitive tasks using a familiar tool.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a0c54-168">雖然 IM 和目前狀態功能會在每個 Lync Server 部署中自動安裝，但您可以選擇是否要部署會議、企業語音及遠端使用者存取，以根據貴組織的需求來調整您的部署。</span><span class="sxs-lookup"><span data-stu-id="a0c54-168">While the IM and presence features are automatically installed in every Lync Server deployment, you can choose whether to deploy conferencing, Enterprise Voice, and remote user access, to tailor your deployment to your organization’s needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a0c54-169">本節內容</span><span class="sxs-lookup"><span data-stu-id="a0c54-169">In This Section</span></span>

  - [<span data-ttu-id="a0c54-170">Lync Server 2013 中的 IM 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="a0c54-170">IM and presence in Lync Server 2013</span></span>](lync-server-2013-im-and-presence.md)

  - [<span data-ttu-id="a0c54-171">Lync Server 2013 中的會議</span><span class="sxs-lookup"><span data-stu-id="a0c54-171">Conferencing in Lync Server 2013</span></span>](lync-server-2013-conferencing.md)

  - [<span data-ttu-id="a0c54-172">Lync Server 2013 中的企業語音</span><span class="sxs-lookup"><span data-stu-id="a0c54-172">Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice.md)

  - [<span data-ttu-id="a0c54-173">使用 Lync Server 2013 的延展性</span><span class="sxs-lookup"><span data-stu-id="a0c54-173">Scalability with Lync Server 2013</span></span>](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

