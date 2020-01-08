---
title: Lync Server 2013：建立新的主幹設定集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a new collection of trunk configuration settings
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49733647
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4c578fd670661413df0a8fb81cb1ce0316db13f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-collection-of-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="b6ec7-102">在 Lync Server 2013 中建立中繼設定的新集合</span><span class="sxs-lookup"><span data-stu-id="b6ec7-102">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6ec7-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b6ec7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b6ec7-104">SIP 幹線設定設定會定義在服務提供者上，exchange 中繼伺服器與公用交換式電話網絡（PSTN）閘道、IP 公用分支 exchange （PBX）或會話邊界控制器（SBC）之間的關聯性與能力。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="b6ec7-105">這些設定會以指定的方式執行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b6ec7-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="b6ec7-106">是否應該在 trunks 上啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="b6ec7-107">傳送即時傳輸控制通訊協定（RTCP）資料包的條件。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="b6ec7-108">每個幹線是否都需要安全的即時通訊協定（SRTP）加密。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="b6ec7-109">當您安裝 Microsoft Lync Server 2013 時，系統會為您建立一個全域 SIP 幹線配置設定。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="b6ec7-110">此外，管理員可以在網站範圍或服務範圍（僅限 PSTN 閘道服務）上建立自訂設定集合。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="b6ec7-111">使用 Lync Server [控制台] 建立 SIP 中繼設定設定時，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="b6ec7-111">When creating SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b6ec7-112">UI 設定</span><span class="sxs-lookup"><span data-stu-id="b6ec7-112">UI Setting</span></span></th>
<th><span data-ttu-id="b6ec7-113">PowerShell 參數</span><span class="sxs-lookup"><span data-stu-id="b6ec7-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="b6ec7-114">描述</span><span class="sxs-lookup"><span data-stu-id="b6ec7-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6ec7-115">名稱</span><span class="sxs-lookup"><span data-stu-id="b6ec7-115">Name</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-116">Identity</span><span class="sxs-lookup"><span data-stu-id="b6ec7-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-117">集合的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-117">Unique identifier for the collection.</span></span> <span data-ttu-id="b6ec7-118">這個屬性是唯讀的;您無法變更主幹設定集合的身分識別。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-118">This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6ec7-119">描述</span><span class="sxs-lookup"><span data-stu-id="b6ec7-119">Description</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-120">描述</span><span class="sxs-lookup"><span data-stu-id="b6ec7-120">Description</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-121">提供一種方式，讓系統管理員可以儲存有關設定的附加資訊（例如，主幹設定的用途）。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-121">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6ec7-122">支援的最大早期對話方塊</span><span class="sxs-lookup"><span data-stu-id="b6ec7-122">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-123">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="b6ec7-123">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-124">在服務提供者上，PSTN 閘道、IP PBX 或 SBC 的分叉回應數目上限，可能會收到傳送到轉送伺服器的邀請。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-124">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6ec7-125">加密支援層級</span><span class="sxs-lookup"><span data-stu-id="b6ec7-125">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-126">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="b6ec7-126">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-127">指示在服務提供者上的中繼伺服器與 PSTN 閘道、IP PBX 或 SBC 之間保護媒體流量的支援層級。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-127">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="b6ec7-128">若是媒體旁路的情況，此值必須與媒體組態中的 EncryptionLevel 設定相容。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-128">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="b6ec7-129">媒體設定是使用<a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">新的-CsMediaConfiguration</a>和<a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">CsMediaConfiguration</a> Cmdlet 來設定。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-129">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="b6ec7-130">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="b6ec7-130">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="b6ec7-131">必要：必須使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-131">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="b6ec7-132">[選用]：如果閘道支援，則會使用 SRTP。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-132">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="b6ec7-133">不支援：不支援 SRTP 加密，因此將無法使用。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-133">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="b6ec7-134">只有在閘道設定為使用傳輸層安全性（TLS）時，才會使用 SRTPMode。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-134">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS).</span></span> <span data-ttu-id="b6ec7-135">如果將閘道設定為傳輸控制通訊協定（TCP）作為傳輸，則 SRTPMode 會在內部設定為 [不支援]。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-135">If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6ec7-136">請參閱支援人員</span><span class="sxs-lookup"><span data-stu-id="b6ec7-136">Refer support</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-137">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="b6ec7-137">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="b6ec7-138">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="b6ec7-138">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-139">如果設定為<strong>允許傳送參照閘道</strong>，則表示主幹支援從中繼伺服器接收參考要求。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-139">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="b6ec7-140">如果設定為<strong>啟用 [使用協力廠商通話控制</strong>]，則表示3pcc 通訊協定可以用來允許轉接呼叫繞過託管的網站。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-140">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="b6ec7-141">3pcc 也稱為&quot;協力廠商控制，&quot;當您使用協力廠商來連接一對呼叫者時（例如，操作員撥打電話給人員 B）。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-141">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6ec7-142">啟用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="b6ec7-142">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-143">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="b6ec7-143">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-144">指出是否已針對此主幹啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-144">Indicates whether media bypass is enabled for this trunk.</span></span> <span data-ttu-id="b6ec7-145">只有在已啟用<strong>集中媒體處理</strong>的情況中，才能啟用媒體旁路功能。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-145">Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6ec7-146">中央媒體處理</span><span class="sxs-lookup"><span data-stu-id="b6ec7-146">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-147">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="b6ec7-147">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-148">指出是否有已知的媒體端接點。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-148">Indicates whether there is a well-known media termination point.</span></span> <span data-ttu-id="b6ec7-149">(舉例來說，PSTN 閘道就是已知的媒體終端點，其中媒體終端的 IP 與訊號終端相同)。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-149">(An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6ec7-150">啟用 RTP 閉鎖</span><span class="sxs-lookup"><span data-stu-id="b6ec7-150">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-151">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="b6ec7-151">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-152">指出 SIP 主幹是否支援 RTP 鎖定。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-152">Indicates whether or not the SIP trunks support RTP latching.</span></span> <span data-ttu-id="b6ec7-153">RTP 鎖定是可以透過 NAT (網路位址轉譯器) 裝置或防火牆進行 RTP/RTCP 連線的技術。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-153">RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6ec7-154">啟用轉寄通話記錄</span><span class="sxs-lookup"><span data-stu-id="b6ec7-154">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-155">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="b6ec7-155">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-156">指出是否透過主幹轉送通話記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-156">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6ec7-157">啟用前 P 斷言身分識別資料</span><span class="sxs-lookup"><span data-stu-id="b6ec7-157">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-158">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="b6ec7-158">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-159">指出 P-Asserted-Identity (PAI) 標頭是否要隨通話轉接。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-159">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="b6ec7-160">PAI 標頭可用於驗證來電者的身分識別。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-160">The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6ec7-161">啟用輸出路由容錯移轉計時器</span><span class="sxs-lookup"><span data-stu-id="b6ec7-161">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-162">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="b6ec7-162">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-163">指出閘道不會在10秒內接聽的出站通話，會路由至下一個可用的幹線;如果沒有其他 trunks，則會自動放棄通話。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-163">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped.</span></span> <span data-ttu-id="b6ec7-164">組織的網路速度與閘道回應速度若是很慢，可能會造成來電不必要地遭到掛斷。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-164">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6ec7-165">關聯的 PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="b6ec7-165">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-166">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="b6ec7-166">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-167">指派給主幹的 PSTN 使用方式集合。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-167">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6ec7-168">要測試的已翻譯數位</span><span class="sxs-lookup"><span data-stu-id="b6ec7-168">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-169">不適用</span><span class="sxs-lookup"><span data-stu-id="b6ec7-169">N/A</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-170">可用於對主幹設定設定執行點對點測試的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-170">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6ec7-171">關聯的翻譯規則</span><span class="sxs-lookup"><span data-stu-id="b6ec7-171">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-172">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="b6ec7-172">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-173">電話號碼轉譯規則的集合，這些規則會套用至由輸出路由（路由至 PBX 或 PSTN 目的地）所處理的通話。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-173">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6ec7-174">呼叫編號轉譯規則</span><span class="sxs-lookup"><span data-stu-id="b6ec7-174">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-175">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="b6ec7-175">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-176">指派給主幹的撥出電話號碼轉譯規則集合。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-176">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6ec7-177">要測試的電話號碼</span><span class="sxs-lookup"><span data-stu-id="b6ec7-177">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-178">不適用</span><span class="sxs-lookup"><span data-stu-id="b6ec7-178">N/A</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-179">可用於對翻譯規則進行特殊測試的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-179">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6ec7-180">通話號碼</span><span class="sxs-lookup"><span data-stu-id="b6ec7-180">Calling number</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-181">不適用</span><span class="sxs-lookup"><span data-stu-id="b6ec7-181">N/A</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-182">表示要測試的電話號碼為來電者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-182">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6ec7-183">叫用號碼</span><span class="sxs-lookup"><span data-stu-id="b6ec7-183">Called number</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-184">不適用</span><span class="sxs-lookup"><span data-stu-id="b6ec7-184">N/A</span></span></p></td>
<td><p><span data-ttu-id="b6ec7-185">表示要測試的電話號碼是呼叫者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-185">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b6ec7-186">Lync Server New-cstrunkconfiguration Cmdlet 支援其他無法在 Lync Server [控制台] 中顯示的屬性。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-186">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="b6ec7-187">如需詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">新版-new-cstrunkconfiguration</A> Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-187">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-create-new-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="b6ec7-188">使用 Lync Server [控制台] 建立新的主幹設定設定</span><span class="sxs-lookup"><span data-stu-id="b6ec7-188">To create new trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b6ec7-189">在 Lync Server [控制台] 中，按一下 [**語音路由**]，然後按一下 [**幹線**設定]。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-189">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="b6ec7-190">在 [**幹線**設定] 索引標籤上，按一下 [**新增**]，然後按一下 [**網站主幹**]，在網站範圍建立新的設定，或 [**池幹線**]，在服務範圍建立新的設定。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-190">On the **Trunk Configuration** tab, click **New**, and then click **Site trunk** to create the new settings at the site scope, or **Pool trunk** to create the new settings at the service scope.</span></span>

3.  <span data-ttu-id="b6ec7-191">在 [**選取網站**] 或 [**選取服務**] 對話方塊中（出現的對話方塊會視您要建立網站範圍或服務範圍的設定而定）選取新配置設定的位置，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-191">In the **Select a Site** or the **Select a Service** dialog box (the dialog box that appears will depend on whether you are creating site-scoped or service-scoped settings) select the location for the new configuration settings and then click **OK**.</span></span> <span data-ttu-id="b6ec7-192">如果對話方塊是空白的，則表示沒有任何位置可供您建立新的設定;例如，如果 [**選取網站**] 對話方塊為空白，表示您的所有網站都已指派中繼設定網站集合，而每個網站（以及每個服務）只能託管一個此類集合。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-192">If the dialog box is blank, that means there is no place to create the new settings; for example, if the **Select a Site** dialog box is blank that means that all of your sites have already been assigned a collection of trunk configuration sites, and each site (and each service) can only host one such collection.</span></span> <span data-ttu-id="b6ec7-193">在這種情況下，您可以刪除現有的集合並建立新的集合，或只修改現有的集合。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-193">In that case, you can either delete the existing collection and create a new collection, or simply modify the existing collection.</span></span>

4.  <span data-ttu-id="b6ec7-194">在 [**新幹線**設定] 對話方塊中，進行適當的選取，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-194">In the **New Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

5.  <span data-ttu-id="b6ec7-195">集合的**State**屬性會更新為**未提交**。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-195">The **State** property for the collection will be updated to **Uncommitted**.</span></span> <span data-ttu-id="b6ec7-196">若要確認變更，並刪除收藏，請按一下 [**認可**]，然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-196">To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

6.  <span data-ttu-id="b6ec7-197">在 [**未提交的語音設定**] 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-197">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

7.  <span data-ttu-id="b6ec7-198">在 [ **Microsoft Lync Server 2013 控制台**] 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b6ec7-198">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

