---
title: Lync Server 2013：在 Lync Server 中會影響 Edge Server 規劃的變更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71d13b40430455c87a60c0fadc20980df5a8aa1b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a><span data-ttu-id="24100-102">在 Lync Server 2013 中會影響 Edge Server 規劃的變更</span><span class="sxs-lookup"><span data-stu-id="24100-102">Changes in Lync Server 2013 that affect Edge Server planning</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24100-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="24100-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="24100-104">Lync Server 2013 引入了新功能，可延伸您使用者的功能與通訊方法。</span><span class="sxs-lookup"><span data-stu-id="24100-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="24100-105">此外，Lync Server 2013 也會為現有的服務引入變更，以更好地整合及延伸貴組織所提供的服務。</span><span class="sxs-lookup"><span data-stu-id="24100-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="24100-106">以下是可能會影響您規劃和部署 Lync Server 2013 Edge Server 服務的變更摘要。</span><span class="sxs-lookup"><span data-stu-id="24100-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

<div>

## <a name="support-for-ipv6-addressing"></a><span data-ttu-id="24100-107">支援 IPv6 位址</span><span class="sxs-lookup"><span data-stu-id="24100-107">Support for IPv6 Addressing</span></span>

<span data-ttu-id="24100-108">Lync Server 2013 支援所有 Edge 伺服器服務的 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="24100-108">Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="24100-109">如果您已透過 Windows Server 中的設定提供介面的 IPv6 位址，您可以透過拓撲建立器中的 IP 位址設定，在 Edge 伺服器配置中使用 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="24100-109">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span> <span data-ttu-id="24100-110">此外，可擴展的訊息和目前狀態通訊協定（XMPP）支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="24100-110">Additionally, the extensible messaging and presence protocol (XMPP) supports IPv6.</span></span> <span data-ttu-id="24100-111">不需要其他配置。</span><span class="sxs-lookup"><span data-stu-id="24100-111">No additional configuration is required.</span></span> <span data-ttu-id="24100-112">如果在拓撲中設定 IPv6，XMPP 將會使用 IPv6 （如果需要的話）。</span><span class="sxs-lookup"><span data-stu-id="24100-112">If IPv6 is configured in the topology, XMPP will use IPv6 (where required).</span></span>

<span data-ttu-id="24100-113">在 Lync Server 2013 中增加支援 IPv6 的需求是針對必須發現並解析為 IPv6 位址的記錄，建立網域名稱系統記錄。</span><span class="sxs-lookup"><span data-stu-id="24100-113">An added requirement to support IPv6 in Lync Server 2013 is to create domain name system records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="24100-114">IPv6 DNS 使用定義為**AAAA**並稱為「四 A」的主機記錄。</span><span class="sxs-lookup"><span data-stu-id="24100-114">IPv6 DNS uses host records that are defined as **AAAA** and called “quad-A”.</span></span> <span data-ttu-id="24100-115">其他記錄類型與其 IPv4 對應專案一致。</span><span class="sxs-lookup"><span data-stu-id="24100-115">Other record types are consistent with their IPv4 counterparts.</span></span>

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a><span data-ttu-id="24100-116">支援可擴展訊息和目前狀態通訊協定（XMPP）部署</span><span class="sxs-lookup"><span data-stu-id="24100-116">Support for Extensible Messaging and Presence Protocol (XMPP) Deployment</span></span>

<span data-ttu-id="24100-117">Edge 伺服器會引入完全整合的 XMPP proxy （在 Edge 伺服器上部署）和 XMPP 閘道（在您的前端伺服器上部署）。</span><span class="sxs-lookup"><span data-stu-id="24100-117">Edge Server introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway (deployed on your Front End Servers).</span></span> <span data-ttu-id="24100-118">您可以將 XMPP 同盟部署為選用的元件。</span><span class="sxs-lookup"><span data-stu-id="24100-118">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="24100-119">您可以新增並設定 XMPP proxy 和 XMPP 閘道，讓您的 Microsoft Lync 2013 使用者新增來自 XMPP 合作夥伴的連絡人，以進行立即訊息（IM）和目前狀態。</span><span class="sxs-lookup"><span data-stu-id="24100-119">By adding and configuring the XMPP proxy and XMPP gateway, you can enable your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="24100-120">目前，Edge 伺服器中的 XMPP 服務只會在 Lync Server 用戶端和 XMPP 的連絡人之間提供 IM 和目前狀態。</span><span class="sxs-lookup"><span data-stu-id="24100-120">Currently, the XMPP services in Edge Server only provide IM and presence between Lync Server clients and XMPP-based contacts.</span></span> <span data-ttu-id="24100-121">此外，XMPP 僅託管于一個網站中。</span><span class="sxs-lookup"><span data-stu-id="24100-121">Additionally, XMPP is hosted in only one site.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="24100-122">Lync Server 2013 的 XMPP 功能是由 Microsoft 針對使用 Google 交談的立即訊息同盟進行測試和支援。</span><span class="sxs-lookup"><span data-stu-id="24100-122">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="24100-123">針對任何其他 XMPP 系統，請與協力廠商廠商聯繫，確認他們支援 Lync Server 2013 的同盟，以及任何部署或疑難排解建議。</span><span class="sxs-lookup"><span data-stu-id="24100-123">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a><span data-ttu-id="24100-124">支援將音訊/視頻驗證和伺服器滾動到伺服器驗證憑證</span><span class="sxs-lookup"><span data-stu-id="24100-124">Support for Rolling Audio/Video Authentication and Server to Server Authentication Certificates</span></span>

<span data-ttu-id="24100-125">證書是用來產生向用戶端和 A/V 驗證服務的其他消費者（以及伺服器到伺服器驗證）頒發的權杖。</span><span class="sxs-lookup"><span data-stu-id="24100-125">A certificate is used to generate tokens that are issued to clients and other consumers of the A/V Authentication service and for server to server authentication.</span></span> <span data-ttu-id="24100-126">音訊/視頻驗證憑證的類型為*AudioVideoAuthentication* ，而伺服器到伺服器驗證憑證的類型是*OAuthTokenIssuer*。</span><span class="sxs-lookup"><span data-stu-id="24100-126">The Audio/Video Authentication certificate is of type *AudioVideoAuthentication* and the Server to Server Authentication certificate is of type *OAuthTokenIssuer*.</span></span>

<span data-ttu-id="24100-127">針對音訊/視頻驗證，權杖是用來驗證埠配置要求，而權杖最多可緩存8小時，即權杖的預設存留期。</span><span class="sxs-lookup"><span data-stu-id="24100-127">For Audio/Video Authentication, tokens are used to authenticate port allocation requests, and the tokens are cached for up to 8 hours – the default lifetime of the token.</span></span> <span data-ttu-id="24100-128">在 [標準作業] 下，這是一個非常可靠的方法，可為 A/V 消費者建立並散佈驗證資料。</span><span class="sxs-lookup"><span data-stu-id="24100-128">Under normal operation, this is a very reliable method to create and distribute authentication material to the A/V consumers.</span></span> <span data-ttu-id="24100-129">不過，憑證的生命週期有限，且會在預先定義的日期和時間到期（根據建立日期，以及在建立憑證的認證機構所強制的原則，通常是2年適用于這種類型的憑證）。</span><span class="sxs-lookup"><span data-stu-id="24100-129">However, certificates have a finite lifetime and expire on a predefined date and time (based on creation date and the policies enforced at the certification authority that created the certificate, typically 2 years for this type of certificate).</span></span> <span data-ttu-id="24100-130">當憑證到期時，由過期憑證所建立且由消費者快取的任何權杖都會無效。</span><span class="sxs-lookup"><span data-stu-id="24100-130">When the certificate expires, any tokens created by the expired certificate and cached by consumers become not valid.</span></span> <span data-ttu-id="24100-131">任何使用已過期證書所建立之權杖的嘗試，都會導致媒體轉送分配失敗，而且所有目前的音訊/視頻會話都會失敗。</span><span class="sxs-lookup"><span data-stu-id="24100-131">Any attempts to use a token created with an expired certificate would result in failed Media Relay allocations and any current Audio/Video sessions will fail.</span></span> <span data-ttu-id="24100-132">用戶端需要取得由有效憑證建立的新權杖，才能繼續執行正常的音訊和視頻功能。</span><span class="sxs-lookup"><span data-stu-id="24100-132">The client would need to acquire a new token created by a valid certificate to resume normal Audio and Video functionality.</span></span>

<span data-ttu-id="24100-133">伺服器到伺服器驗證是由要求並套用至部署中所有伺服器的全域憑證所管理。</span><span class="sxs-lookup"><span data-stu-id="24100-133">Server to Server Authentication is managed by a global certificate that is requested and applied to all servers in the deployment.</span></span> <span data-ttu-id="24100-134">憑證負責驗證 Lync Server 2013 中的伺服器，以及驗證 Exchange 2013 和 Microsoft SharePoint Server 2013。</span><span class="sxs-lookup"><span data-stu-id="24100-134">The certificate is responsible for authenticating servers in Lync Server 2013 as well as authenticating to Exchange 2013 and Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="24100-135">如需伺服器驗證服務器驗證運作方式的詳細資訊，請參閱[在 Lync server 2013 中管理伺服器間驗證（OAuth）與合作夥伴應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="24100-135">For more information on how Server to Server Authentication works, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span></span> <span data-ttu-id="24100-136">音訊/視頻驗證程式與伺服器到伺服器驗證處理常式之間的一個非常重要的差異是驗證或權杖的存留期。</span><span class="sxs-lookup"><span data-stu-id="24100-136">One very important difference between the Audio/Video Authentication process and the Server to Server Authentication process is the lifetime of the authentication, or tokens.</span></span> <span data-ttu-id="24100-137">針對音訊/視頻驗證，驗證會在八小時後到期。</span><span class="sxs-lookup"><span data-stu-id="24100-137">For Audio/Video Authentication, the authentication expires after eight hours.</span></span> <span data-ttu-id="24100-138">伺服器對伺服器驗證的存留期為24小時。</span><span class="sxs-lookup"><span data-stu-id="24100-138">Server-to-Server Authentication has a lifetime of 24 hours.</span></span> <span data-ttu-id="24100-139">您必須針對每個憑證類型進行相應的規劃。</span><span class="sxs-lookup"><span data-stu-id="24100-139">You must plan accordingly for each of the certificate types.</span></span>

<span data-ttu-id="24100-140">Lync Server 2013 的新功能是在目前憑證到期前將替換音訊/視頻驗證憑證和伺服器轉移到伺服器驗證憑證的能力。</span><span class="sxs-lookup"><span data-stu-id="24100-140">New for Lync Server 2013 is the ability to stage a replacement Audio/Video Authentication certificate and Server to Server Authentication certificate in advance of the expiration of the current certificate.</span></span> <span data-ttu-id="24100-141">然後使用新憑證來產生新的權杖或新的驗證要求。</span><span class="sxs-lookup"><span data-stu-id="24100-141">The new certificate is then used for generating new tokens or new authentication requests.</span></span> <span data-ttu-id="24100-142">但保留舊憑證以驗證目前的會話與驗證。</span><span class="sxs-lookup"><span data-stu-id="24100-142">but retains the old certificate for verifying the current sessions and authentications..</span></span> <span data-ttu-id="24100-143">完成這個工作是為了有效避免因標記和憑證到期而發生的幾乎所有失敗。</span><span class="sxs-lookup"><span data-stu-id="24100-143">What this accomplishes is to effectively prevent nearly all failures due to token and certificate expirations.</span></span> <span data-ttu-id="24100-144">如需此功能的詳細資訊及如何進行設定，請參閱[使用 CsCertificate 中的 Lync Server 2013 暫存 AV 和 OAuth 憑證](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span><span class="sxs-lookup"><span data-stu-id="24100-144">For details of this feature and how to configure it, see [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span></span>

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a><span data-ttu-id="24100-145">減少對以 Cookie 為基礎的關聯性的依賴性</span><span class="sxs-lookup"><span data-stu-id="24100-145">Reduced Reliance on Cookie-based Affinity</span></span>

<span data-ttu-id="24100-146">在舊版的 Lync Server 和 Office 通訊伺服器中，Web 服務會使用以 cookie 為基礎的相似性，以確保用戶端和 Web 服務會話狀態已維護。</span><span class="sxs-lookup"><span data-stu-id="24100-146">In previous versions of Lync Server and Office Communications Server, cookie-based affinity was used by the Web services to ensure that the client and Web services session state was maintained.</span></span> <span data-ttu-id="24100-147">Lync Server 2013 Web 服務使用內建的關聯機制，可消除 cookie 關聯的大部分需求。</span><span class="sxs-lookup"><span data-stu-id="24100-147">Lync Server 2013 Web services use a built in affinity mechanism that eliminates most of the requirements for cookie-based affinity.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="24100-148">Microsoft Lync 2010 行動用戶端仍必須使用以 cookie 為基礎的關聯性，且需要設定以 cookie 為基礎的關聯性，除非您將所有用戶端轉移到即將到來的 Microsoft Lync 行動用戶端（尚未決定發行日期）。</span><span class="sxs-lookup"><span data-stu-id="24100-148">The Microsoft Lync 2010 Mobile client must still use cookie-based affinity and will require configuration of cookie-based affinity until you have migrated all clients to the upcoming Microsoft Lync Mobile client (Date of release not yet determined).</span></span>



</div>

<span data-ttu-id="24100-149">如需 Lync Server 2013 中以 cookie 為基礎的關聯性的詳細資料，請參閱[Lync server 2013 中的外部使用者存取所需的元件](lync-server-2013-components-required-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="24100-149">For details about cookie-based affinity in Lync Server 2013, see [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

</div>

<div>

## <a name="autodiscover-enhancements"></a><span data-ttu-id="24100-150">自動探索增強功能</span><span class="sxs-lookup"><span data-stu-id="24100-150">AutoDiscover Enhancements</span></span>

<span data-ttu-id="24100-151">Lync Server 2013 中的自動探索功能可讓用戶端找出提供給通訊的其他功能。</span><span class="sxs-lookup"><span data-stu-id="24100-151">The autodiscover feature in Lync Server 2013 enables clients to locate additional features that are made available for communication.</span></span> <span data-ttu-id="24100-152">自動探索是在 Lync Server 2010 的累積更新中開始推出：行動裝置和 Microsoft Lync 2010 行動裝置的年 11 2011 月。</span><span class="sxs-lookup"><span data-stu-id="24100-152">Autodiscover was first introduced in the cumulative update for Lync Server 2010: November 2011 for Mobility and Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="24100-153">自動探索功能（由 DNS 記錄名稱 LyncDiscover 和 LyncDiscoverInternal 提供）可讓用戶端找到並使用行動服務（適用于 Microsoft Lync 2010 行動用戶端）、Microsoft Lync Web App 以及 Lync Web 排程程式，以及與 Microsoft Exchange Server 和 SharePoint Server 的通訊。</span><span class="sxs-lookup"><span data-stu-id="24100-153">The autodiscover feature (also known by the DNS record names LyncDiscover and LyncDiscoverInternal) allows clients to locate and use mobility services (for Microsoft Lync 2010 Mobile clients), the Microsoft Lync Web App, and the Lync Web scheduler, as well as communications with Microsoft Exchange Server and SharePoint Server.</span></span> <span data-ttu-id="24100-154">自動探索是在您的基礎結構和 Lync Server 2013 伺服器的設定和部署中正常安裝。</span><span class="sxs-lookup"><span data-stu-id="24100-154">Autodiscover is installed as normal part of the setup and deployment of your infrastructure and Lync Server 2013 servers.</span></span> <span data-ttu-id="24100-155">[拓撲建立器] 和 [Lync Server 部署] 嚮導會消除 Lync Server 2010 的累積更新中所需的大部分配置工作：2011年11月。</span><span class="sxs-lookup"><span data-stu-id="24100-155">The Topology Builder and Lync Server Deployment Wizard eliminate most of the configuration tasks that were required in cumulative update for Lync Server 2010: November 2011.</span></span>

</div>

<div>

## <a name="services-for-mobile-clients"></a><span data-ttu-id="24100-156">行動用戶端的服務</span><span class="sxs-lookup"><span data-stu-id="24100-156">Services for Mobile Clients</span></span>

<span data-ttu-id="24100-157">在 Lync Server 2010 的累積更新中所述，Lync Server 2013 中的行動服務可讓您使用支援的 Apple iOS、Android、Windows Phone 或 Nokia 行動裝置執行 Lync Mobile 和平板電腦裝置，以執行行動電話2011。活動（例如傳送及接收立即訊息、查看連絡人及查看目前狀態）。</span><span class="sxs-lookup"><span data-stu-id="24100-157">Introduced in the cumulative update for Lync Server 2010: November 2011, mobility services in Lync Server 2013 enable mobile phones running Lync Mobile and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="24100-158">此外，行動裝置支援一些企業語音功能，例如按一下以加入會議、透過工作撥打電話、單一號碼達到、語音信箱及未接來電通知。</span><span class="sxs-lookup"><span data-stu-id="24100-158">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="24100-159">行動服務會使用部署在您前端伺服器上的反向 proxy 與已發佈的服務。</span><span class="sxs-lookup"><span data-stu-id="24100-159">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="24100-160">Edge 伺服器不需要任何變更。</span><span class="sxs-lookup"><span data-stu-id="24100-160">No changes are required to Edge Servers.</span></span> <span data-ttu-id="24100-161">您最簡單的情況是，您需要使用 [輸出 SIP/TCP/5061from] 伺服器執行 Lync Server 存取邊緣服務。</span><span class="sxs-lookup"><span data-stu-id="24100-161">Minimally you need outbound SIP/TCP/5061from the server running the Lync Server Access Edge service.</span></span>



</div>

</div>

<div>

## <a name="director-role-is-optional"></a><span data-ttu-id="24100-162">主管角色是選擇性的</span><span class="sxs-lookup"><span data-stu-id="24100-162">Director Role is Optional</span></span>

<span data-ttu-id="24100-163">在 Lync Server 2013 拓撲中，控制器伺服器的角色沒有變更。</span><span class="sxs-lookup"><span data-stu-id="24100-163">The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="24100-164">它仍會寄存 web 服務、preauthenticates 傳入的使用者要求，並將外部使用者導向其主區。</span><span class="sxs-lookup"><span data-stu-id="24100-164">It still hosts web services, preauthenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="24100-165">透過將主管從建議的角色變更為選用的角色，Microsoft 不想要降低主管的價值。</span><span class="sxs-lookup"><span data-stu-id="24100-165">By changing the Director from a recommended role to an optional role, Microsoft does not intend to diminish the value of the Director.</span></span> <span data-ttu-id="24100-166">目的是要減少伺服器數量及其他硬體需求（例如，控制器的硬體負載平衡器），而不會影響功能和功能。</span><span class="sxs-lookup"><span data-stu-id="24100-166">The intention is to reduce server count and other hardware requirements (for example, hardware load balancers for the Director) without compromising features and functionality.</span></span> <span data-ttu-id="24100-167">因為前端伺服器可以執行與主管所提供服務不受影響的相同作業，所以如果您選擇的話，就可以部署控制器。</span><span class="sxs-lookup"><span data-stu-id="24100-167">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can deploy Directors if you choose to.</span></span> <span data-ttu-id="24100-168">您可以放心地排除主管，讓前端伺服器提供相同的服務來取代控制器。</span><span class="sxs-lookup"><span data-stu-id="24100-168">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in place of a Director.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

