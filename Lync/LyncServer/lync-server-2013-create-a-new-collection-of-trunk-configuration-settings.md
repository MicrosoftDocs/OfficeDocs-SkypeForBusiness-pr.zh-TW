---
title: Lync Server 2013：建立新的主幹設定集合
description: Lync Server 2013：建立新的主幹設定集合。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new collection of trunk configuration settings
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49733647
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16ef4bb6393ec2385eaf7c642734bbc803d4dff6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554709"
---
# <a name="create-a-new-collection-of-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="3b34f-103">在 Lync Server 2013 中建立主幹設定的新集合</span><span class="sxs-lookup"><span data-stu-id="3b34f-103">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b34f-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3b34f-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3b34f-p101">SIP 主幹組態設定用於定義中繼伺服器與服務提供者的公用交換電話網路 (PSTN) 閘道、IP 公用交換機 (PBX) 或工作階段邊界控制器 (SBC) 之間的關係和功能。這些設定將指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="3b34f-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="3b34f-107">主幹是否啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="3b34f-107">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="3b34f-108">傳送即時傳輸控制通訊協定 (RTCP) 封包的情況。</span><span class="sxs-lookup"><span data-stu-id="3b34f-108">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="3b34f-109">每個主幹是否需要安全即時通訊協定 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="3b34f-109">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="3b34f-110">當您安裝 Microsoft Lync Server 2013 時，系統會為您建立一個全域 SIP 主幹設定的集合。</span><span class="sxs-lookup"><span data-stu-id="3b34f-110">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="3b34f-111">此外，系統管理員可以在網站範圍或服務範圍 (僅限 PSTN 閘道服務) 建立自訂設定集合。</span><span class="sxs-lookup"><span data-stu-id="3b34f-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="3b34f-112">使用 Lync Server 控制台建立 SIP 主幹設定設定時，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="3b34f-112">When creating SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b34f-113">UI 設定</span><span class="sxs-lookup"><span data-stu-id="3b34f-113">UI Setting</span></span></th>
<th><span data-ttu-id="3b34f-114">PowerShell 參數</span><span class="sxs-lookup"><span data-stu-id="3b34f-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="3b34f-115">描述</span><span class="sxs-lookup"><span data-stu-id="3b34f-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b34f-116">名稱</span><span class="sxs-lookup"><span data-stu-id="3b34f-116">Name</span></span></p></td>
<td><p><span data-ttu-id="3b34f-117">身分識別</span><span class="sxs-lookup"><span data-stu-id="3b34f-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="3b34f-p103">集合的唯一識別碼。此為唯讀屬性，您無法變更主幹組態設定集合的 Identity。</span><span class="sxs-lookup"><span data-stu-id="3b34f-p103">Unique identifier for the collection. This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b34f-120">描述</span><span class="sxs-lookup"><span data-stu-id="3b34f-120">Description</span></span></p></td>
<td><p><span data-ttu-id="3b34f-121">描述</span><span class="sxs-lookup"><span data-stu-id="3b34f-121">Description</span></span></p></td>
<td><p><span data-ttu-id="3b34f-122">為系統管理員提供儲存設定相關資訊 (例如，主幹組態的用途) 的方法。</span><span class="sxs-lookup"><span data-stu-id="3b34f-122">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b34f-123">支援的最大早期對話</span><span class="sxs-lookup"><span data-stu-id="3b34f-123">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="3b34f-124">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="3b34f-124">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="3b34f-125">服務提供者的 PSTN 閘道、IP-PBX 或 SBC 對其傳送到中繼伺服器的 Invite，可接收的分支回應數上限。</span><span class="sxs-lookup"><span data-stu-id="3b34f-125">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b34f-126">加密支援等級</span><span class="sxs-lookup"><span data-stu-id="3b34f-126">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="3b34f-127">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="3b34f-127">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="3b34f-128">指出支援等級，以保護中繼伺服器和服務提供者之 PSTN 閘道、IP-PBX 或 SBC 之間的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="3b34f-128">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="3b34f-129">若是媒體旁路的情況，此值必須與媒體組態中的 EncryptionLevel 設定相容。</span><span class="sxs-lookup"><span data-stu-id="3b34f-129">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="3b34f-130">媒體設定是使用 <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">新的-CsMediaConfiguration</a> 及 <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">CsMediaConfiguration</a> Cmdlet 來設定。</span><span class="sxs-lookup"><span data-stu-id="3b34f-130">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="3b34f-131">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="3b34f-131">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="3b34f-132">Required：必須使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="3b34f-132">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="3b34f-133">Optional：如果閘道支援，即會使用 SRTP。</span><span class="sxs-lookup"><span data-stu-id="3b34f-133">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="3b34f-134">Not Supported：不支援 SRTP 加密，因此不會使用此加密。</span><span class="sxs-lookup"><span data-stu-id="3b34f-134">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="3b34f-p105">只有閘道設定為使用傳輸層安全性 (TLS) 時，才能使用 SRTPMode。如果將閘道設定為在傳輸時使用傳輸控制通訊協定 (TCP)，系統會從內部將 SRTPMode 設為 Not Supported。</span><span class="sxs-lookup"><span data-stu-id="3b34f-p105">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS). If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b34f-137">轉接支援</span><span class="sxs-lookup"><span data-stu-id="3b34f-137">Refer support</span></span></p></td>
<td><p><span data-ttu-id="3b34f-138">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="3b34f-138">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="3b34f-139">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="3b34f-139">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="3b34f-140">如果設定為 <strong>[啟用傳送轉接至閘道]</strong>，表示主幹支援接收來自中繼伺服器的 Refer 要求。</span><span class="sxs-lookup"><span data-stu-id="3b34f-140">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="3b34f-141">如果設定為 <strong>[使用協力廠商撥號控制來啟用轉接]</strong>，表示可以使用 3pcc 通訊協定允許轉接通話略過主控網站。</span><span class="sxs-lookup"><span data-stu-id="3b34f-141">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="3b34f-142">3pcc 也稱為 &quot; 協力廠商控制項， &quot; 當協力廠商用來連接一 (對來電者時，就會發生此事件。例如，操作員撥打某人 a 至 B 的來電) 。</span><span class="sxs-lookup"><span data-stu-id="3b34f-142">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b34f-143">啟用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="3b34f-143">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="3b34f-144">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="3b34f-144">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="3b34f-p107">表示此主幹是否啟用媒體旁路。只有在也啟用 <strong>[集中式媒體處理]</strong> 時，才能啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="3b34f-p107">Indicates whether media bypass is enabled for this trunk. Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b34f-147">集中式媒體處理</span><span class="sxs-lookup"><span data-stu-id="3b34f-147">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="3b34f-148">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="3b34f-148">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="3b34f-p108">指出是否有已知的媒體終端點 (已知的媒體終端點範例是 PSTN 閘道，其媒體終端的 IP 與訊號終端相同)。</span><span class="sxs-lookup"><span data-stu-id="3b34f-p108">Indicates whether there is a well-known media termination point. (An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b34f-151">啟用 RTP 栓</span><span class="sxs-lookup"><span data-stu-id="3b34f-151">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="3b34f-152">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="3b34f-152">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="3b34f-p109">指出 SIP 主幹是否支援 RTP 栓。RTP 栓是一種技術，可讓 RTP/RTCP 透過 NAT (網路位址轉譯器) 裝置或防火牆連線。</span><span class="sxs-lookup"><span data-stu-id="3b34f-p109">Indicates whether or not the SIP trunks support RTP latching. RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b34f-155">啟用轉接來電記錄</span><span class="sxs-lookup"><span data-stu-id="3b34f-155">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="3b34f-156">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="3b34f-156">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="3b34f-157">指出是否將透過主幹來轉接來電記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="3b34f-157">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b34f-158">啟用轉寄 P-Asserted-Identity 資料</span><span class="sxs-lookup"><span data-stu-id="3b34f-158">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="3b34f-159">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="3b34f-159">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="3b34f-p110">指出 P-Asserted-Identity (PAI) 標頭是否會和通話一起轉寄。PAI 標頭提供確認來電者身分識別的方法。</span><span class="sxs-lookup"><span data-stu-id="3b34f-p110">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call. The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b34f-162">啟用輸出路由容錯移轉計時器</span><span class="sxs-lookup"><span data-stu-id="3b34f-162">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="3b34f-163">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="3b34f-163">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="3b34f-p111">指出閘道未在 10 秒內接聽的撥出電話將會被路由傳送到下一個可用的主幹；如果沒有其他主幹，就會自動捨棄此電話。在網路和閘道回應速度緩慢的組織中，這可能會造成電話平白遭到捨棄。</span><span class="sxs-lookup"><span data-stu-id="3b34f-p111">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b34f-166">關聯的 PSTN 使用方式</span><span class="sxs-lookup"><span data-stu-id="3b34f-166">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="3b34f-167">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="3b34f-167">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="3b34f-168">指派給主幹的 PSTN 使用方式集合。</span><span class="sxs-lookup"><span data-stu-id="3b34f-168">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b34f-169">要測試的轉譯號碼</span><span class="sxs-lookup"><span data-stu-id="3b34f-169">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="3b34f-170">不適用</span><span class="sxs-lookup"><span data-stu-id="3b34f-170">N/A</span></span></p></td>
<td><p><span data-ttu-id="3b34f-171">可用於進行主幹組態設定臨機測試的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="3b34f-171">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b34f-172">關聯的轉譯規則</span><span class="sxs-lookup"><span data-stu-id="3b34f-172">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="3b34f-173">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="3b34f-173">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="3b34f-174">套用到由「輸出路由」處理的電話 (路由傳送到 PBX 或 PSTN 目的地的電話) 的電話號碼轉譯規則集合。</span><span class="sxs-lookup"><span data-stu-id="3b34f-174">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b34f-175">撥打號碼轉譯規則</span><span class="sxs-lookup"><span data-stu-id="3b34f-175">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="3b34f-176">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="3b34f-176">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="3b34f-177">指派給主幹的撥出電話號碼轉譯規則集合。</span><span class="sxs-lookup"><span data-stu-id="3b34f-177">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b34f-178">測試的電話號碼</span><span class="sxs-lookup"><span data-stu-id="3b34f-178">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="3b34f-179">不適用</span><span class="sxs-lookup"><span data-stu-id="3b34f-179">N/A</span></span></p></td>
<td><p><span data-ttu-id="3b34f-180">可用於進行轉譯規則臨機測試的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="3b34f-180">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b34f-181">撥打號碼</span><span class="sxs-lookup"><span data-stu-id="3b34f-181">Calling number</span></span></p></td>
<td><p><span data-ttu-id="3b34f-182">不適用</span><span class="sxs-lookup"><span data-stu-id="3b34f-182">N/A</span></span></p></td>
<td><p><span data-ttu-id="3b34f-183">指出要測試的電話號碼是來電者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="3b34f-183">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b34f-184">撥打的號碼</span><span class="sxs-lookup"><span data-stu-id="3b34f-184">Called number</span></span></p></td>
<td><p><span data-ttu-id="3b34f-185">不適用</span><span class="sxs-lookup"><span data-stu-id="3b34f-185">N/A</span></span></p></td>
<td><p><span data-ttu-id="3b34f-186">指出要測試的電話號碼是受話者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="3b34f-186">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="3b34f-187">Lync Server Get-cstrunkconfiguration Cmdlet 支援未顯示在 Lync Server 控制台中的其他屬性。</span><span class="sxs-lookup"><span data-stu-id="3b34f-187">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="3b34f-188">如需詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">get-cstrunkconfiguration</A> Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="3b34f-188">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-create-new-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="3b34f-189">使用 Lync Server 控制台建立新主幹設定設定</span><span class="sxs-lookup"><span data-stu-id="3b34f-189">To create new trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3b34f-190">在 [Lync Server 控制台] 中，按一下 [ **語音路由**]，然後按一下 [ **主幹**設定]。</span><span class="sxs-lookup"><span data-stu-id="3b34f-190">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="3b34f-191">在 **[主幹組態]** 索引標籤上，按一下 **[新增]**，然後按一下 **[站台主幹]** 以建立在網站範圍的新設定，或按一下 **[集區主幹]** 以建立在服務範圍的新設定。</span><span class="sxs-lookup"><span data-stu-id="3b34f-191">On the **Trunk Configuration** tab, click **New**, and then click **Site trunk** to create the new settings at the site scope, or **Pool trunk** to create the new settings at the service scope.</span></span>

3.  <span data-ttu-id="3b34f-p113">在 **[選取站台]** 或 **[選取服務]** 對話方塊中 (顯示的對話方塊會視您是建立網站範圍或服務範圍的設定而定)，選取新組態設定的位置，然後按一下 **[確定]**。如果對話方塊是空白的，表示沒有空間可建立新設定；例如，如果 **[選取站台]** 對話方塊是空白的，表示您所有的網站都已被指派主幹組態設定集合，且每個網站 (及每項服務) 都只能主控一個此類集合。在這種情況下，您可以刪除現有的集合後再建立新集合，或只是修改現有的集合。</span><span class="sxs-lookup"><span data-stu-id="3b34f-p113">In the **Select a Site** or the **Select a Service** dialog box (the dialog box that appears will depend on whether you are creating site-scoped or service-scoped settings) select the location for the new configuration settings and then click **OK**. If the dialog box is blank, that means there is no place to create the new settings; for example, if the **Select a Site** dialog box is blank that means that all of your sites have already been assigned a collection of trunk configuration sites, and each site (and each service) can only host one such collection. In that case, you can either delete the existing collection and create a new collection, or simply modify the existing collection.</span></span>

4.  <span data-ttu-id="3b34f-195">在 **[新主幹組態]** 對話方塊中，選取適當的選項，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3b34f-195">In the **New Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

5.  <span data-ttu-id="3b34f-p114">集合的 **[State]** 屬性將會更新為 **[未認可]**。如果要認可變更，並刪除集合，請依序按一下 **[認可]** 和 **[全部認可]**。</span><span class="sxs-lookup"><span data-stu-id="3b34f-p114">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

6.  <span data-ttu-id="3b34f-198">在 **[未認可的語音組態設定]** 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3b34f-198">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

7.  <span data-ttu-id="3b34f-199">在 **[Microsoft Lync Server 2013 控制台]** 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3b34f-199">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

