---
title: Lync Server 2013：修改 SIP 中繼設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify SIP trunk configuration settings
ms:assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688104(v=OCS.15)
ms:contentKeyID: 49733703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 809f7a94a4ab211f1bf21483729519cd53de2a2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="39e43-102">在 Lync Server 2013 中修改 SIP 幹線配置設定</span><span class="sxs-lookup"><span data-stu-id="39e43-102">Modify SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39e43-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="39e43-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="39e43-104">SIP 幹線設定設定會定義在服務提供者上，exchange 中繼伺服器與公用交換式電話網絡（PSTN）閘道、IP 公用分支 exchange （PBX）或會話邊界控制器（SBC）之間的關聯性與能力。</span><span class="sxs-lookup"><span data-stu-id="39e43-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="39e43-105">這些設定會以指定的方式執行以下操作：</span><span class="sxs-lookup"><span data-stu-id="39e43-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="39e43-106">是否應該在 trunks 上啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="39e43-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="39e43-107">傳送即時傳輸控制通訊協定（RTCP）資料包的條件。</span><span class="sxs-lookup"><span data-stu-id="39e43-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="39e43-108">每個幹線是否都需要安全的即時通訊協定（SRTP）加密。</span><span class="sxs-lookup"><span data-stu-id="39e43-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="39e43-109">當您安裝 Microsoft Lync Server 2013 時，系統會為您建立一個全域 SIP 幹線配置設定。</span><span class="sxs-lookup"><span data-stu-id="39e43-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="39e43-110">此外，管理員可以在網站範圍或服務範圍（僅限 PSTN 閘道服務）上建立自訂設定集合。</span><span class="sxs-lookup"><span data-stu-id="39e43-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="39e43-111">您可以稍後使用 Lync Server [控制台] 或 [Windows PowerShell] 修改任何這些集合。</span><span class="sxs-lookup"><span data-stu-id="39e43-111">Any of these collections can later be modified using either Lync Server Control Panel or Windows PowerShell.</span></span>

<span data-ttu-id="39e43-112">使用 Lync Server [控制台] 修改 SIP 中繼設定設定時，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="39e43-112">When modifying SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39e43-113">UI 設定</span><span class="sxs-lookup"><span data-stu-id="39e43-113">UI Setting</span></span></th>
<th><span data-ttu-id="39e43-114">PowerShell 參數</span><span class="sxs-lookup"><span data-stu-id="39e43-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="39e43-115">說明</span><span class="sxs-lookup"><span data-stu-id="39e43-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39e43-116">名稱</span><span class="sxs-lookup"><span data-stu-id="39e43-116">Name</span></span></p></td>
<td><p><span data-ttu-id="39e43-117">Identity</span><span class="sxs-lookup"><span data-stu-id="39e43-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="39e43-118">集合的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="39e43-118">Unique identifier for the collection.</span></span> <span data-ttu-id="39e43-119">這個屬性是唯讀的;您無法變更主幹設定集合的身分識別。</span><span class="sxs-lookup"><span data-stu-id="39e43-119">This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39e43-120">說明</span><span class="sxs-lookup"><span data-stu-id="39e43-120">Description</span></span></p></td>
<td><p><span data-ttu-id="39e43-121">說明</span><span class="sxs-lookup"><span data-stu-id="39e43-121">Description</span></span></p></td>
<td><p><span data-ttu-id="39e43-122">提供一種方式，讓系統管理員可以儲存有關設定的附加資訊（例如，主幹設定的用途）。</span><span class="sxs-lookup"><span data-stu-id="39e43-122">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39e43-123">支援的最大早期對話方塊</span><span class="sxs-lookup"><span data-stu-id="39e43-123">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="39e43-124">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="39e43-124">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="39e43-125">在服務提供者上，PSTN 閘道、IP PBX 或 SBC 的分叉回應數目上限，可能會收到傳送到轉送伺服器的邀請。</span><span class="sxs-lookup"><span data-stu-id="39e43-125">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39e43-126">加密支援層級</span><span class="sxs-lookup"><span data-stu-id="39e43-126">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="39e43-127">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="39e43-127">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="39e43-128">指示在服務提供者上的中繼伺服器與 PSTN 閘道、IP PBX 或 SBC 之間保護媒體流量的支援層級。</span><span class="sxs-lookup"><span data-stu-id="39e43-128">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="39e43-129">若是媒體旁路的情況，此值必須與媒體組態中的 EncryptionLevel 設定相容。</span><span class="sxs-lookup"><span data-stu-id="39e43-129">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="39e43-130">媒體設定是使用<a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">新的-CsMediaConfiguration</a>和<a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">CsMediaConfiguration</a> Cmdlet 來設定。</span><span class="sxs-lookup"><span data-stu-id="39e43-130">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="39e43-131">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="39e43-131">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="39e43-132">必要：必須使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="39e43-132">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="39e43-133">[選用]：如果閘道支援，則會使用 SRTP。</span><span class="sxs-lookup"><span data-stu-id="39e43-133">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="39e43-134">不支援：不支援 SRTP 加密，因此將無法使用。</span><span class="sxs-lookup"><span data-stu-id="39e43-134">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="39e43-135">只有在閘道設定為使用傳輸層安全性（TLS）時，才會使用 SRTPMode。</span><span class="sxs-lookup"><span data-stu-id="39e43-135">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS).</span></span> <span data-ttu-id="39e43-136">如果將閘道設定為傳輸控制通訊協定（TCP）作為傳輸，則 SRTPMode 會在內部設定為 [不支援]。</span><span class="sxs-lookup"><span data-stu-id="39e43-136">If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39e43-137">請參閱支援人員</span><span class="sxs-lookup"><span data-stu-id="39e43-137">Refer support</span></span></p></td>
<td><p><span data-ttu-id="39e43-138">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="39e43-138">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="39e43-139">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="39e43-139">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="39e43-140">如果設定為<strong>允許傳送參照閘道</strong>，則表示主幹支援從中繼伺服器接收參考要求。</span><span class="sxs-lookup"><span data-stu-id="39e43-140">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="39e43-141">如果設定為<strong>啟用 [使用協力廠商通話控制</strong>]，則表示3pcc 通訊協定可以用來允許轉接呼叫繞過託管的網站。</span><span class="sxs-lookup"><span data-stu-id="39e43-141">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="39e43-142">3pcc 也稱為&quot;協力廠商控制，&quot;當您使用協力廠商來連接一對呼叫者時（例如，操作員撥打電話給人員 B）。</span><span class="sxs-lookup"><span data-stu-id="39e43-142">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39e43-143">啟用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="39e43-143">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="39e43-144">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="39e43-144">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="39e43-145">指出是否已針對此主幹啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="39e43-145">Indicates whether media bypass is enabled for this trunk.</span></span> <span data-ttu-id="39e43-146">只有在已啟用<strong>集中媒體處理</strong>的情況中，才能啟用媒體旁路功能。</span><span class="sxs-lookup"><span data-stu-id="39e43-146">Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39e43-147">中央媒體處理</span><span class="sxs-lookup"><span data-stu-id="39e43-147">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="39e43-148">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="39e43-148">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="39e43-149">指出是否有已知的媒體端接點。</span><span class="sxs-lookup"><span data-stu-id="39e43-149">Indicates whether there is a well-known media termination point.</span></span> <span data-ttu-id="39e43-150">(舉例來說，PSTN 閘道就是已知的媒體終端點，其中媒體終端的 IP 與訊號終端相同)。</span><span class="sxs-lookup"><span data-stu-id="39e43-150">(An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39e43-151">啟用 RTP 閉鎖</span><span class="sxs-lookup"><span data-stu-id="39e43-151">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="39e43-152">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="39e43-152">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="39e43-153">指出 SIP 主幹是否支援 RTP 鎖定。</span><span class="sxs-lookup"><span data-stu-id="39e43-153">Indicates whether or not the SIP trunks support RTP latching.</span></span> <span data-ttu-id="39e43-154">RTP 鎖定是可以透過 NAT (網路位址轉譯器) 裝置或防火牆進行 RTP/RTCP 連線的技術。</span><span class="sxs-lookup"><span data-stu-id="39e43-154">RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39e43-155">啟用轉寄通話記錄</span><span class="sxs-lookup"><span data-stu-id="39e43-155">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="39e43-156">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="39e43-156">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="39e43-157">指出是否透過主幹轉送通話記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="39e43-157">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39e43-158">啟用前 P 斷言身分識別資料</span><span class="sxs-lookup"><span data-stu-id="39e43-158">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="39e43-159">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="39e43-159">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="39e43-160">指出 P-Asserted-Identity (PAI) 標頭是否要隨通話轉接。</span><span class="sxs-lookup"><span data-stu-id="39e43-160">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="39e43-161">PAI 標頭可用於驗證來電者的身分識別。</span><span class="sxs-lookup"><span data-stu-id="39e43-161">The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39e43-162">啟用輸出路由容錯移轉計時器</span><span class="sxs-lookup"><span data-stu-id="39e43-162">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="39e43-163">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="39e43-163">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="39e43-164">指出閘道不會在10秒內接聽的出站通話，會路由至下一個可用的幹線;如果沒有其他 trunks，則會自動放棄通話。</span><span class="sxs-lookup"><span data-stu-id="39e43-164">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped.</span></span> <span data-ttu-id="39e43-165">組織的網路速度與閘道回應速度若是很慢，可能會造成來電不必要地遭到掛斷。</span><span class="sxs-lookup"><span data-stu-id="39e43-165">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39e43-166">關聯的 PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="39e43-166">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="39e43-167">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="39e43-167">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="39e43-168">指派給主幹的 PSTN 使用方式集合。</span><span class="sxs-lookup"><span data-stu-id="39e43-168">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39e43-169">要測試的已翻譯數位</span><span class="sxs-lookup"><span data-stu-id="39e43-169">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="39e43-170">不適用</span><span class="sxs-lookup"><span data-stu-id="39e43-170">N/A</span></span></p></td>
<td><p><span data-ttu-id="39e43-171">可用於對主幹設定設定執行點對點測試的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="39e43-171">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39e43-172">關聯的翻譯規則</span><span class="sxs-lookup"><span data-stu-id="39e43-172">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="39e43-173">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="39e43-173">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="39e43-174">電話號碼轉譯規則的集合，這些規則會套用至由輸出路由（路由至 PBX 或 PSTN 目的地）所處理的通話。</span><span class="sxs-lookup"><span data-stu-id="39e43-174">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39e43-175">呼叫編號轉譯規則</span><span class="sxs-lookup"><span data-stu-id="39e43-175">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="39e43-176">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="39e43-176">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="39e43-177">指派給主幹的撥出電話號碼轉譯規則集合。</span><span class="sxs-lookup"><span data-stu-id="39e43-177">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39e43-178">要測試的電話號碼</span><span class="sxs-lookup"><span data-stu-id="39e43-178">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="39e43-179">不適用</span><span class="sxs-lookup"><span data-stu-id="39e43-179">N/A</span></span></p></td>
<td><p><span data-ttu-id="39e43-180">可用於對翻譯規則進行特殊測試的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="39e43-180">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39e43-181">通話號碼</span><span class="sxs-lookup"><span data-stu-id="39e43-181">Calling number</span></span></p></td>
<td><p><span data-ttu-id="39e43-182">不適用</span><span class="sxs-lookup"><span data-stu-id="39e43-182">N/A</span></span></p></td>
<td><p><span data-ttu-id="39e43-183">表示要測試的電話號碼為來電者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="39e43-183">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39e43-184">叫用號碼</span><span class="sxs-lookup"><span data-stu-id="39e43-184">Called number</span></span></p></td>
<td><p><span data-ttu-id="39e43-185">不適用</span><span class="sxs-lookup"><span data-stu-id="39e43-185">N/A</span></span></p></td>
<td><p><span data-ttu-id="39e43-186">表示要測試的電話號碼是呼叫者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="39e43-186">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="39e43-187">Lync Server New-cstrunkconfiguration Cmdlet 支援其他無法在 Lync Server [控制台] 中顯示的屬性。</span><span class="sxs-lookup"><span data-stu-id="39e43-187">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="39e43-188">如需詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">new-cstrunkconfiguration</A> Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="39e43-188">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="39e43-189">使用 Lync Server [控制台] 修改 SIP 幹線設定設定</span><span class="sxs-lookup"><span data-stu-id="39e43-189">To modify SIP trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="39e43-190">在 Lync Server [控制台] 中，按一下 [**語音路由**]，然後按一下 [**幹線**設定]。</span><span class="sxs-lookup"><span data-stu-id="39e43-190">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="39e43-191">在 [**幹線**設定] 索引標籤上，按兩下要修改的幹線設定設定。</span><span class="sxs-lookup"><span data-stu-id="39e43-191">On the **Trunk Configuration** tab, double-click the trunk configuration settings to be modified.</span></span> <span data-ttu-id="39e43-192">請注意，您只可以一次編輯一個設定集合。</span><span class="sxs-lookup"><span data-stu-id="39e43-192">Note that you can only edit one collection of settings at a time.</span></span> <span data-ttu-id="39e43-193">如果您想要對多個集合進行相同的變更，請改為使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="39e43-193">If you would like to make the same changes on multiple collections, use Windows PowerShell instead.</span></span>

3.  <span data-ttu-id="39e43-194">在 [**編輯主幹**設定] 對話方塊中，進行適當的選取，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="39e43-194">In the **Edit Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

4.  <span data-ttu-id="39e43-195">集合的**State**屬性會更新為**未提交**。</span><span class="sxs-lookup"><span data-stu-id="39e43-195">The **State** property for the collection will be updated to **Uncommitted**.</span></span> <span data-ttu-id="39e43-196">若要確認變更，並刪除收藏，請按一下 [**認可**]，然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="39e43-196">To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

5.  <span data-ttu-id="39e43-197">在 [**未提交的語音設定**] 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="39e43-197">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="39e43-198">在 [ **Microsoft Lync Server 2013 控制台**] 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="39e43-198">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

