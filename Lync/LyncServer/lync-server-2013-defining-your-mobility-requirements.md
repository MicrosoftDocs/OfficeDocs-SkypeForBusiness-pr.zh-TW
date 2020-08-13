---
title: Lync Server 2013：定義行動需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2da630e422aaf7068a4252333d5221f552bce525
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a><span data-ttu-id="34ef7-102">定義 Lync Server 2013 的行動需求</span><span class="sxs-lookup"><span data-stu-id="34ef7-102">Defining your mobility requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34ef7-103">_**主題上次修改日期：** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="34ef7-103">_**Topic Last Modified:** 2013-02-14_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="34ef7-104">在 Lync Server 2013 行動功能的規劃階段期間，當您使用 Lync 2010 行動裝置和 Lync 2013 行動用戶端時，決定您的部署步驟。</span><span class="sxs-lookup"><span data-stu-id="34ef7-104">During the planning phase for the Lync Server 2013 mobility feature, when you are using Lync 2010 Mobile and Lync 2013 Mobile clients, you make decisions that determine your deployment steps.</span></span>

<span data-ttu-id="34ef7-105">以下是您必須考慮的決策：</span><span class="sxs-lookup"><span data-stu-id="34ef7-105">Here are the decisions that you must consider:</span></span>

  - <span data-ttu-id="34ef7-106">**您是否要使用 Lync mobile 用戶端的自動探索？**</span><span class="sxs-lookup"><span data-stu-id="34ef7-106">**Do you want to use automatic discovery for Lync mobile clients?**</span></span>
    
    <span data-ttu-id="34ef7-107">如果您想要支援自動探索，您必須建立新的內部及外部網域名稱系統 (DNS) 記錄、將主體替代名稱新增至前端伺服器、Director 及反向 proxy 上的憑證，以及修改反向 proxy 上的現有發佈規則。</span><span class="sxs-lookup"><span data-stu-id="34ef7-107">If you want to support automatic discovery, you need to create new internal and external Domain Name System (DNS) records, add subject alternative names to certificates on the Front End Servers, Directors, and reverse proxy, and modify the existing publishing rules on the reverse proxy.</span></span> <span data-ttu-id="34ef7-108">如需詳細資訊，請參閱[Lync Server 2013 中行動的技術需求](lync-server-2013-technical-requirements-for-mobility.md)。</span><span class="sxs-lookup"><span data-stu-id="34ef7-108">For details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="34ef7-109">透過自動探索，使用者可以自動從公司網路內部或外部的任何地方尋找 Lync Server 2013 Web 服務，而不需要在行動裝置設定中輸入 URLs。</span><span class="sxs-lookup"><span data-stu-id="34ef7-109">With automatic discovery, users can automatically locate Lync Server 2013 Web Services from anywhere inside or outside the corporate network, without entering URLs in their mobile device settings.</span></span>
    
    <span data-ttu-id="34ef7-110">如果您使用手動設定，而不是自動探索，行動使用者必須在行動裝置中手動輸入下列 URLs：</span><span class="sxs-lookup"><span data-stu-id="34ef7-110">If you use manual settings instead of automatic discovery, mobile users need to manually enter the following URLs in their mobile devices:</span></span>
    
      - <span data-ttu-id="34ef7-111">HTTPs:// \< ExtPoolFQDN \> /Autodiscover/autodiscoverservice.svc/Root for external access</span><span class="sxs-lookup"><span data-stu-id="34ef7-111">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>
    
      - <span data-ttu-id="34ef7-112">HTTPs:// \< IntPoolFQDN \> /AutoDiscover/autodiscoverservice-內部存取的 .Svc （根）</span><span class="sxs-lookup"><span data-stu-id="34ef7-112">https://\<IntPoolFQDN\>/AutoDiscover/ autodiscoverservice.svc/Root for internal access</span></span>
    
    <span data-ttu-id="34ef7-113">強烈建議使用自動探索。</span><span class="sxs-lookup"><span data-stu-id="34ef7-113">We strongly recommend using automatic discovery.</span></span> <span data-ttu-id="34ef7-114">手動設定的主要用途是用於疑難排解。</span><span class="sxs-lookup"><span data-stu-id="34ef7-114">The primary use of manual settings is for troubleshooting.</span></span>

  - <span data-ttu-id="34ef7-115">**如果您決定要支援自動探索，是否願意以每個 SIP 網域的主體替代名稱更新反向 proxy 上的憑證？**</span><span class="sxs-lookup"><span data-stu-id="34ef7-115">**If you decide to support automatic discovery, are you willing to update certificates on the reverse proxy with subject alternative names for each SIP domain?**</span></span>
    
    <span data-ttu-id="34ef7-116">如果您有許多 SIP 網域，更新反向 proxy 上的公用憑證會變得非常昂貴。</span><span class="sxs-lookup"><span data-stu-id="34ef7-116">If you have many SIP domains, updating public certificates on the reverse proxy can become very expensive.</span></span> <span data-ttu-id="34ef7-117">如果是這種情況，您可以選擇執行自動探索，讓初始自動探索服務要求在埠80上使用 HTTP，而不是在埠443上使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="34ef7-117">If this is the case, you can choose to implement automatic discovery so that the initial Autodiscover Service request uses HTTP on port 80, instead of using HTTPS on port 443.</span></span> <span data-ttu-id="34ef7-118">不過，這不是建議的方法。</span><span class="sxs-lookup"><span data-stu-id="34ef7-118">However, this is not the recommended approach.</span></span> <span data-ttu-id="34ef7-119">如果您決定選擇此選項，則不需要更新反向 proxy 上的憑證，但是您必須在埠80上建立 HTTP 的 web 發行規則。</span><span class="sxs-lookup"><span data-stu-id="34ef7-119">If you decide to choose this alternative, you do not need to update the certificates on the reverse proxy, but you need to create a web publishing rule for HTTP on port 80.</span></span> <span data-ttu-id="34ef7-120">如需詳細資訊，請參閱[Lync Server 2013 中行動的技術需求](lync-server-2013-technical-requirements-for-mobility.md)。</span><span class="sxs-lookup"><span data-stu-id="34ef7-120">For more details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="34ef7-121">**您想要在公司網路內部和外部都支援 Lync 行動用戶端，還是只支援公司網路內的用戶端？**</span><span class="sxs-lookup"><span data-stu-id="34ef7-121">**Do you want to support Lync mobile clients both internal and external to the corporate network, or support clients only inside the corporate network?**</span></span>
    
    <span data-ttu-id="34ef7-122">如果您想要在網路內部和外部支援行動用戶端，行動裝置可以從任何位置存取行動功能。</span><span class="sxs-lookup"><span data-stu-id="34ef7-122">If you want to support mobile clients internal and external to your network, mobile devices can access mobility features from any location.</span></span> <span data-ttu-id="34ef7-123">預設設定是支援公司網路的內部及外部用戶端。</span><span class="sxs-lookup"><span data-stu-id="34ef7-123">The default configuration is to support clients both internal and external to the corporate network.</span></span>
    
    <span data-ttu-id="34ef7-124">雖然預設設定可讓行動用戶端流量透過外部網站，但您可以將行動用戶端流量限制在內部公司網路中。</span><span class="sxs-lookup"><span data-stu-id="34ef7-124">Although the default configuration enables mobile client traffic to go through the external site, you can restrict mobile client traffic to the internal corporate network.</span></span> <span data-ttu-id="34ef7-125">當您將流量限制為內部網路時，使用者只有在網路內部時，才可以在其行動裝置上使用 Lync 行動應用程式。</span><span class="sxs-lookup"><span data-stu-id="34ef7-125">When you restrict the traffic to the internal network, users can use Lync mobile applications on their mobile devices only when they are inside the network.</span></span>
    
    <span data-ttu-id="34ef7-126">針對使用 Mcx 行動性服務和 Lync 2010 Mobile 支援行動的部署，您可以執行**Set-CsMcxConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="34ef7-126">For deployments that support mobility using the Mcx mobility service and Lync 2010 Mobile, you run the **Set-CsMcxConfiguration** cmdlet.</span></span> <span data-ttu-id="34ef7-127">若要設定僅限內部使用的行動性，請使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="34ef7-127">To set mobility for internal use only, you would use a command similar to the following:</span></span>
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="34ef7-128">UCWA 不需要其他設定。</span><span class="sxs-lookup"><span data-stu-id="34ef7-128">There are no additional configurations required for UCWA.</span></span> <span data-ttu-id="34ef7-129">UCWA 沒有同等的僅限內部配置。</span><span class="sxs-lookup"><span data-stu-id="34ef7-129">UCWA does not have an equivalent internal-only configuration.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="34ef7-130">如果您使用的是 Lync Server 2013 &nbsp; 前端伺服器或前端集區，而且<STRONG>沒有</STRONG>任何 Lync Server 2010 &nbsp; 前端伺服器或前端集區，則不<STRONG>需要以 cookie 為基礎的持久性</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="34ef7-130">If you are using a Lync Server 2013&nbsp;Front End Server or Front End pools and <STRONG>you do not have</STRONG> any Lync Server 2010&nbsp;Front End Servers or Front End pools, <STRONG>there is no requirement for cookie-based persistence</STRONG>.</span></span> <span data-ttu-id="34ef7-131">如果您需要保留任何 Lync Server 2010 &nbsp; 前端伺服器或前端集區，相同的規則仍會在 Lync Server 2010 中套用，以用於 cookie 型暫留。</span><span class="sxs-lookup"><span data-stu-id="34ef7-131">If you need to retain any Lync Server 2010&nbsp;Front End Servers or Front End pools, the same rules still apply as in Lync Server 2010 for cookie-based persistence.</span></span>

    
    </div>

  - <span data-ttu-id="34ef7-132">**您是否要支援 Apple iOS 裝置和 Windows phone 的推播通知？**</span><span class="sxs-lookup"><span data-stu-id="34ef7-132">**Do you want to support push notifications for Apple iOS devices and Windows Phones?**</span></span>
    
    <span data-ttu-id="34ef7-133">如果您支援推播通知，支援的 Apple iOS 裝置和 Windows phone 會收到當行動應用程式非使用中時發生的事件通知。</span><span class="sxs-lookup"><span data-stu-id="34ef7-133">If you support push notifications, supported Apple iOS devices and Windows Phones receive a notification of events that occur when the mobile application is inactive.</span></span> <span data-ttu-id="34ef7-134">您必須設定 Edge Server 才能與雲端式 Lync Server 推播通知服務（位於 Lync Online 資料中心）進行同盟關聯，並執行 Cmdlet 以啟用推播通知。</span><span class="sxs-lookup"><span data-stu-id="34ef7-134">You must configure your Edge Server to have a federation relationship with the cloud-based Lync Server Push Notification Service, which is located in the Lync Online datacenter, and run a cmdlet to enable push notifications.</span></span>
    
    <span data-ttu-id="34ef7-135">如果您想要支援 Wi-Fi 網路的推播通知，除了支援行動裝置供應商的3G 或資料網路上的推播通知之外，您必須開啟企業 Wi-Fi 網路上的埠5223輸出。</span><span class="sxs-lookup"><span data-stu-id="34ef7-135">If you want to support push notifications over your Wi-Fi network, in addition to supporting push notifications over the mobile device providers' 3G or data networks, you must open port 5223 outbound on your enterprise Wi-Fi network.</span></span> <span data-ttu-id="34ef7-136">支援透過 Wi-Fi 網路的推播通知，可支援行動裝置，只使用具有低室內接待的 Wi-Fi 和行動裝置。</span><span class="sxs-lookup"><span data-stu-id="34ef7-136">Supporting push notifications over the Wi-Fi network supports mobile devices that use only Wi-Fi and mobile devices that have poor indoor reception.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="34ef7-137">只有在支援執行 Lync 2010 行動用戶端的 Apple 裝置時，才需要開啟埠 TCP 5223。</span><span class="sxs-lookup"><span data-stu-id="34ef7-137">Opening port TCP 5223 is required only when supporting Apple devices running the Lync 2010 Mobile client.</span></span>

    
    </div>
    
    <span data-ttu-id="34ef7-138">如果不支援推播通知，Apple 行動裝置和 Windows phone 的使用者將不會發現使用中行動應用程式非使用中時所發生的事件（例如立即訊息邀請或錯過的郵件）。</span><span class="sxs-lookup"><span data-stu-id="34ef7-138">If you do not support push notifications, users of Apple mobile devices and Windows Phones will not find out about events—such as instant message invitations or missed messages—that occur when the mobile application is inactive.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="34ef7-139">Apple 裝置上的 Lync 2013 行動用戶端不需要推播通知。</span><span class="sxs-lookup"><span data-stu-id="34ef7-139">Lync 2013 Mobile clients on Apple devices do not require push notification.</span></span> <span data-ttu-id="34ef7-140">在 Windows Phone 上的 Lync 2013 行動用戶端會使用推播通知。</span><span class="sxs-lookup"><span data-stu-id="34ef7-140">The Lync 2013 Mobile clients on Windows Phone use push notification.</span></span> <span data-ttu-id="34ef7-141">規劃推播通知及推播通知的情況，在 Windows Phone 和 Apple 裝置上的 Lync Mobile 會保持不變，但無法執行 Lync 2013 行動用戶端。</span><span class="sxs-lookup"><span data-stu-id="34ef7-141">Planning for push notification and the push notification clearinghouse remain the same for Lync Mobile on Windows Phone and Apple devices that are not able to run the Lync 2013 Mobile client.</span></span>

    
    </div>

  - <span data-ttu-id="34ef7-142">**您是否要讓所有使用者都能存取行動功能，或是否要能夠指定哪些使用者可以存取這些功能？**</span><span class="sxs-lookup"><span data-stu-id="34ef7-142">**Do you want all users to have access to mobility features, or do you want to be able to specify which users have access to these features?**</span></span>
    
    <span data-ttu-id="34ef7-143">該表說明 Lync Server 2013 中使用者可用的功能。</span><span class="sxs-lookup"><span data-stu-id="34ef7-143">The table describes features available to users in Lync Server 2013.</span></span> <span data-ttu-id="34ef7-144">預設值允許透過工作撥打，允許 VoIP) 的語音 over IP (，並啟用行動性。</span><span class="sxs-lookup"><span data-stu-id="34ef7-144">The defaults allow Call via Work, allow Voice over IP (VoIP), and enable Mobility.</span></span> <span data-ttu-id="34ef7-145">以下是可用選項的完整集合：</span><span class="sxs-lookup"><span data-stu-id="34ef7-145">Here is the full set of available options:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="34ef7-146">功能/參數名稱/範圍 (原則參數名稱可能不同) </span><span class="sxs-lookup"><span data-stu-id="34ef7-146">Feature/Parameter Name/Scope (Policy parameter names may not be the same)</span></span></th>
    <th><span data-ttu-id="34ef7-147">描述</span><span class="sxs-lookup"><span data-stu-id="34ef7-147">Description</span></span></th>
    <th><span data-ttu-id="34ef7-148">已導入</span><span class="sxs-lookup"><span data-stu-id="34ef7-148">Introduced</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="34ef7-149">啟用行動性</span><span class="sxs-lookup"><span data-stu-id="34ef7-149">Enable Mobility</span></span></p>
    <p><span data-ttu-id="34ef7-150">參數名稱：<code>EnableMobility</code></span><span class="sxs-lookup"><span data-stu-id="34ef7-150">Parameter Name : <code>EnableMobility</code></span></span></p>
    <p><span data-ttu-id="34ef7-151">範圍： Global/Site/User</span><span class="sxs-lookup"><span data-stu-id="34ef7-151">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="34ef7-152">管理設定若要控制已安裝 Lync Mobile 之指定範圍內的使用者，如果原則設定為 False，使用者就無法登入用戶端。</span><span class="sxs-lookup"><span data-stu-id="34ef7-152">Administrative setting to control users in a given scope that have the Lync Mobile installed, If the policy is set to False, the user would not be able to sign into the client.</span></span></p>
    <p><span data-ttu-id="34ef7-153">預設設定為 True。</span><span class="sxs-lookup"><span data-stu-id="34ef7-153">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="34ef7-154">Lync Server 2010 的累計更新：11月2011</span><span class="sxs-lookup"><span data-stu-id="34ef7-154">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="34ef7-155">啟用外語音</span><span class="sxs-lookup"><span data-stu-id="34ef7-155">Enable Outside Voice</span></span></p>
    <p><span data-ttu-id="34ef7-156">參數名稱：<code>EnableOutsideVoice</code></span><span class="sxs-lookup"><span data-stu-id="34ef7-156">Parameter Name : <code>EnableOutsideVoice</code></span></span></p>
    <p><span data-ttu-id="34ef7-157">範圍： Global/Site/User</span><span class="sxs-lookup"><span data-stu-id="34ef7-157">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="34ef7-158">控制使用者使用「呼叫者」功能的能力，該功能可讓使用者使用其公司電話號碼，而不是其行動電話號碼，撥打和接聽電話。</span><span class="sxs-lookup"><span data-stu-id="34ef7-158">Controls a user’s ability to use Call Via Work, a feature that enables users to make and receive calls by using their work number instead of their mobile number.</span></span> <span data-ttu-id="34ef7-159">若設為 False，使用者將無法使用其行動裝置撥打或接聽其公司電話號碼。</span><span class="sxs-lookup"><span data-stu-id="34ef7-159">If set to False, the user will not be able to make or receive calls by using their work number from their mobile device.</span></span></p>
    <p><span data-ttu-id="34ef7-160">預設設定為 True</span><span class="sxs-lookup"><span data-stu-id="34ef7-160">The default setting is True</span></span></p></td>
    <td><p><span data-ttu-id="34ef7-161">Lync Server 2010 的累計更新：11月2011</span><span class="sxs-lookup"><span data-stu-id="34ef7-161">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="34ef7-162">啟用 IP 音訊和影片</span><span class="sxs-lookup"><span data-stu-id="34ef7-162">Enable IP Audio and Video</span></span></p>
    <p><span data-ttu-id="34ef7-163">參數名稱：<code>EnableIPAudioVideo</code></span><span class="sxs-lookup"><span data-stu-id="34ef7-163">Parameter Name : <code>EnableIPAudioVideo</code></span></span></p>
    <p><span data-ttu-id="34ef7-164">範圍： Global/Site/User</span><span class="sxs-lookup"><span data-stu-id="34ef7-164">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="34ef7-165">控制使用者是否可以使用 VoIP 在其行動裝置上撥打或接聽語音或視頻通話。</span><span class="sxs-lookup"><span data-stu-id="34ef7-165">Controls whether a user can use VoIP to make or receive voice or video calls on their mobile device.</span></span> <span data-ttu-id="34ef7-166">如果設為 False，使用者將無法在其裝置上撥打或接收 VoIP 或視頻通話。</span><span class="sxs-lookup"><span data-stu-id="34ef7-166">If set to False, the user will not be able to make or receive VoIP or video calls on their device.</span></span></p>
    <p><span data-ttu-id="34ef7-167">預設設定為 True。</span><span class="sxs-lookup"><span data-stu-id="34ef7-167">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="34ef7-168">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34ef7-168">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="34ef7-169">需要 IP 音訊的 WiFi</span><span class="sxs-lookup"><span data-stu-id="34ef7-169">Require WiFi for IP Audio</span></span></p>
    <p><span data-ttu-id="34ef7-170">參數名稱：<code>RequireWiFiForIPAudio</code></span><span class="sxs-lookup"><span data-stu-id="34ef7-170">Parameter Name : <code>RequireWiFiForIPAudio</code></span></span></p>
    <p><span data-ttu-id="34ef7-171">範圍： Global/Site/User</span><span class="sxs-lookup"><span data-stu-id="34ef7-171">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="34ef7-172">此設定定義用戶端是否需要在 WiFi 上的 VoIP 上撥打和接聽電話，而不是行動電話資料網路。</span><span class="sxs-lookup"><span data-stu-id="34ef7-172">This setting defines whether the client will be required to make and receive calls over VoIP on WiFi instead of the cellular data network.</span></span> <span data-ttu-id="34ef7-173">如果設為 True，使用者只有在連線至 WiFi 網路時，才能撥打和接收 VoIP 呼叫。</span><span class="sxs-lookup"><span data-stu-id="34ef7-173">If set to True, the user can make and receive VoIP calls only when connected to a WiFi network.</span></span></p>
    <p><span data-ttu-id="34ef7-174">預設設定為 False。</span><span class="sxs-lookup"><span data-stu-id="34ef7-174">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="34ef7-175">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34ef7-175">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="34ef7-176">需要 IP 影片的 WiFi</span><span class="sxs-lookup"><span data-stu-id="34ef7-176">Require WiFi for IP Video</span></span></p>
    <p><span data-ttu-id="34ef7-177">參數名稱：<code>RequireWiFiForIPVideo</code></span><span class="sxs-lookup"><span data-stu-id="34ef7-177">Parameter Name : <code>RequireWiFiForIPVideo</code></span></span></p>
    <p><span data-ttu-id="34ef7-178">範圍： Global/Site/User</span><span class="sxs-lookup"><span data-stu-id="34ef7-178">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="34ef7-179">此設定定義是否需要用戶端在 Wi-Fi，而不是在行動電話資料網路上撥打和接收通話。</span><span class="sxs-lookup"><span data-stu-id="34ef7-179">This setting defines whether the client will be required to make and receive video calls on Wi-Fi instead of on the cellular data network.</span></span> <span data-ttu-id="34ef7-180">如果設為 True，使用者只有在連線至 Wi-Fi 網路時，才能撥打及接收影片通話。</span><span class="sxs-lookup"><span data-stu-id="34ef7-180">If set to True, the user can make and receive video calls only when connected to a Wi-Fi network.</span></span></p>
    <p><span data-ttu-id="34ef7-181">預設設定為 False。</span><span class="sxs-lookup"><span data-stu-id="34ef7-181">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="34ef7-182">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34ef7-182">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="34ef7-183">如需您可以設定之原則設定的描述，以及如何管理原則，請參閱[New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)、 [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)、 [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)、 [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)及[Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)。</span><span class="sxs-lookup"><span data-stu-id="34ef7-183">For a description of the policy settings that you can configure, and how to manage the policies, see [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) and [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).</span></span>

  - <span data-ttu-id="34ef7-184">**您是否要讓未啟用 Enterprise Voice 的使用者能夠使用按一下以加入加入會議？**</span><span class="sxs-lookup"><span data-stu-id="34ef7-184">**Do you want users who are not enabled for Enterprise Voice to be able to use Click to Join to join conferences?**</span></span>
    
    <span data-ttu-id="34ef7-185">若要讓使用者能夠存取行動功能及呼叫透過工作，必須啟用 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="34ef7-185">For users to have access to mobility features and Call via Work, they must be enabled for Enterprise Voice.</span></span> <span data-ttu-id="34ef7-186">不過，未啟用 Enterprise Voice 的使用者可以按一下其行動裝置上的連結，以加入會議，如果他們具有適當的語音原則給他們。</span><span class="sxs-lookup"><span data-stu-id="34ef7-186">However, users who are not enabled for Enterprise Voice can join conferences by clicking the link on their mobile device, if they have an appropriate voice policy assigned to them.</span></span> <span data-ttu-id="34ef7-187">您可以將特定的語音原則指派給這些使用者，或確定存在套用至這些使用者的全域原則或網站層級原則。</span><span class="sxs-lookup"><span data-stu-id="34ef7-187">You can either assign a specific voice policy to these users or make sure that a global policy or site-level policy exists that applies to them.</span></span> <span data-ttu-id="34ef7-188">您指派的語音原則必須具有公用交換電話網路 (PSTN) 使用方式記錄和路由，以定義使用者可以撥出的區域，以加入會議。</span><span class="sxs-lookup"><span data-stu-id="34ef7-188">The voice policy that you assign must have public switched telephone network (PSTN) usage records and routes that define the areas to which users can dial out to join a conference.</span></span> <span data-ttu-id="34ef7-189">如需有關設定語音原則、PSTN 使用方式記錄和路由的詳細資訊，請參閱[在 Lync Server 2013 中設定語音原則、pstn 使用方式記錄和語音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="34ef7-189">For details about setting voice policy, PSTN usage records, and routes, see [Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="34ef7-190">想要使用 [按一下以加入] 的行動使用者需要語音原則，以及相關的 PSTN 使用方式記錄和語音路由，因為按一下行動裝置上的連結會產生來自 Lync Server 2013 的撥出電話。</span><span class="sxs-lookup"><span data-stu-id="34ef7-190">Mobile users who want to use Click to Join require a voice policy, along with the related PSTN usage records and voice routes, because clicking the link on the mobile device results in an outbound call from Lync Server 2013.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="34ef7-191">另請參閱</span><span class="sxs-lookup"><span data-stu-id="34ef7-191">See Also</span></span>


[<span data-ttu-id="34ef7-192">Lync Server 2013 中行動的技術需求</span><span class="sxs-lookup"><span data-stu-id="34ef7-192">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  


[<span data-ttu-id="34ef7-193">在 Lync Server 2013 中設定語音原則、PSTN 使用方式記錄和語音路由</span><span class="sxs-lookup"><span data-stu-id="34ef7-193">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

