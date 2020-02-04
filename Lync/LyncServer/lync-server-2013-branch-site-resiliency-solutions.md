---
title: Lync Server 2013：分支網站恢復解決方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16261d4add87462991c877e85cc6a0ff1e7fdfd4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a><span data-ttu-id="98e18-102">Lync Server 2013 中的分支網站恢復解決方案</span><span class="sxs-lookup"><span data-stu-id="98e18-102">Branch-site resiliency solutions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98e18-103">_**主題上次修改日期：** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="98e18-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="98e18-104">為您的組織提供分支網站復原功能有明顯的優點。</span><span class="sxs-lookup"><span data-stu-id="98e18-104">There are obvious advantages to providing branch-site resiliency to your organization.</span></span> <span data-ttu-id="98e18-105">具體來說，如果您失去中央網站的連線，分支網站使用者將會繼續使用企業語音服務和語音信箱（如果您要設定語音信箱重新路由設定，請參閱[Lync Server 2013 的分支網站復原需求](lync-server-2013-branch-site-resiliency-requirements.md)）。</span><span class="sxs-lookup"><span data-stu-id="98e18-105">Specifically, if you lose the connection to the central site, branch site users will continue to have Enterprise Voice service and voice mail (if you configure voice mail rerouting settings; for details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span></span> <span data-ttu-id="98e18-106">不過，對於使用者少於25名的網站而言，復原方案可能無法提供足夠的投資回報。</span><span class="sxs-lookup"><span data-stu-id="98e18-106">However, for sites with fewer than 25 users, a resiliency solution may not provide a sufficient return on investment.</span></span>

<span data-ttu-id="98e18-107">如果您決定提供分支網站復原，您有三個選項。</span><span class="sxs-lookup"><span data-stu-id="98e18-107">If you decide to provide branch-site resiliency, you have three options.</span></span> <span data-ttu-id="98e18-108">下表可協助您判斷貴組織的最佳選項。</span><span class="sxs-lookup"><span data-stu-id="98e18-108">The following table can help you determine the best option for your organization.</span></span>

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98e18-109">如果您 .。。</span><span class="sxs-lookup"><span data-stu-id="98e18-109">If you…</span></span></th>
<th><span data-ttu-id="98e18-110">我們建議您使用 .。。</span><span class="sxs-lookup"><span data-stu-id="98e18-110">We recommend that you use a…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98e18-111">在分支網站上的25與1000使用者之間主持，如果投資回報不支援完整部署或本機管理支援無法使用</span><span class="sxs-lookup"><span data-stu-id="98e18-111">Host between 25 and 1000 users at your branch site, and if the return on investment does not support a full deployment or where local administrative support is unavailable</span></span></p></td>
<td><p><span data-ttu-id="98e18-112">Survivable 分支裝置</span><span class="sxs-lookup"><span data-stu-id="98e18-112">Survivable Branch Appliance</span></span></p>
<p><span data-ttu-id="98e18-113">Survivable 分支裝置是一個行業標準的刀片式伺服器，其中包含在 Windows Server 2008 R2 上執行的 Lync Server 註冊機構和中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="98e18-113">The Survivable Branch Appliance is an industry-standard blade server with a Lync Server Registrar and Mediation Server running on Windows Server 2008 R2.</span></span> <span data-ttu-id="98e18-114">Survivable 分支裝置也包含公用的交換電話網絡（PSTN）閘道。</span><span class="sxs-lookup"><span data-stu-id="98e18-114">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="98e18-115">合格的協力廠商裝置（由 Survivable 分支裝置（SBA）資格/認證計畫中的 Microsoft 合作夥伴所開發）可在 WAN 發生故障時提供連續 PSTN 連線，但此方法不會提供復原的目前狀態與會議，因為這些功能依賴于中央網站上的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="98e18-115">Qualified third-party devices (developed by Microsoft partners in the Survivable Branch Appliance (SBA) qualification/certification program) provide a continuous PSTN connection in the event of WAN failure, but this approach does not provide resilient presence and conferencing because these features depend on Front End Servers at the central site.</span></span></p>
<p><span data-ttu-id="98e18-116">如需 Survivable 分支裝置的詳細資訊&quot;，請參閱本主題&quot;稍後的 Survivable 分支裝置詳細資料。</span><span class="sxs-lookup"><span data-stu-id="98e18-116">For details about Survivable Branch Appliances, see &quot;Survivable Branch Appliance Details,&quot; later in this topic.</span></span></p>
<p><span data-ttu-id="98e18-117"><strong>注意：</strong>如果您決定還要將 SIP 主幹與您的 Survivable 分支裝置搭配使用，請與您的 Survivable 分支裝置供應商聯繫，以瞭解哪個服務提供者最適合您的組織。</span><span class="sxs-lookup"><span data-stu-id="98e18-117"><strong>Note:</strong> If you decide to also use a SIP trunk with your Survivable Branch Appliance, contact your Survivable Branch Appliance vendor to learn about which service provider is best for your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98e18-118">在您的分支網站上的1000和2000使用者之間主持、缺乏強健的 WAN 連線，且已提供訓練有素的 Lync Server 管理員</span><span class="sxs-lookup"><span data-stu-id="98e18-118">Host between 1000 and 2000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="98e18-119">Survivable 分支伺服器或兩個 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="98e18-119">Survivable Branch Server or two Survivable Branch Appliances.</span></span></p>
<p><span data-ttu-id="98e18-120">Survivable 分支伺服器是一種 Windows Server 會議，其中已有安裝 Lync Server 註冊機構和中繼伺服器軟體的硬體需求。</span><span class="sxs-lookup"><span data-stu-id="98e18-120">The Survivable Branch Server is a Windows Server meeting specified hardware requirements that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="98e18-121">它必須連線至 PSTN 閘道或 SIP 幹線給電話服務提供者。</span><span class="sxs-lookup"><span data-stu-id="98e18-121">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span></p>
<p><span data-ttu-id="98e18-122">如需 Survivable 分支伺服器的詳細資料&quot;，請參閱本主題&quot;稍後的 Survivable 分支伺服器詳細資料。</span><span class="sxs-lookup"><span data-stu-id="98e18-122">For details about Survivable Branch Servers, see &quot;Survivable Branch Server Details,&quot; later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98e18-123">如果您除了適用于5000使用者的語音功能之外，還需要您的目前狀態與會議功能，且已提供訓練有素的 Lync Server 系統管理員</span><span class="sxs-lookup"><span data-stu-id="98e18-123">If you require presence and conferencing features in addition to voice features for up to 5000 users, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="98e18-124">使用標準版伺服器（而不是分支網站）部署成中央網站。</span><span class="sxs-lookup"><span data-stu-id="98e18-124">Deploy as a central site with a Standard Edition server rather than as a branch site.</span></span></p>
<p><span data-ttu-id="98e18-125">全式 Lync Server 部署可在 WAN 發生故障時，提供連續的 PSTN 連線及彈性的目前狀態與會議。</span><span class="sxs-lookup"><span data-stu-id="98e18-125">A full-scale Lync Server deployment provides a continuous PSTN connection and resilient presence and conferencing in the event of WAN failure.</span></span></p>
<p><span data-ttu-id="98e18-126">如需準備此方案的詳細資訊，請參閱<a href="lync-server-2013-planning-for-your-organization.md">Lync server 2013 的組織規劃</a>，<a href="lync-server-2013-determining-your-system-requirements.md">判斷 lync server 2013 的系統需求</a>，<a href="lync-server-2013-determining-your-infrastructure-requirements.md">判斷 lync server 2013 的基礎結構需求</a>，以及規劃檔的其他相關區段。</span><span class="sxs-lookup"><span data-stu-id="98e18-126">For details about preparing for this solution, see <a href="lync-server-2013-planning-for-your-organization.md">Organization planning for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determining your infrastructure requirements for Lync Server 2013</a>, and other relevant sections of the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a><span data-ttu-id="98e18-127">復原拓朴</span><span class="sxs-lookup"><span data-stu-id="98e18-127">Resiliency Topologies</span></span>

<span data-ttu-id="98e18-128">下圖顯示分支網站復原的建議拓撲。</span><span class="sxs-lookup"><span data-stu-id="98e18-128">The following figure shows the recommended topologies for branch-site resiliency.</span></span>

<span data-ttu-id="98e18-129">**分支網站復原選項**</span><span class="sxs-lookup"><span data-stu-id="98e18-129">**Branch site resiliency options**</span></span>

<span data-ttu-id="98e18-130">![語音分支恢復能力選項](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "語音分支恢復能力選項")</span><span class="sxs-lookup"><span data-stu-id="98e18-130">![Voice Branch Resiliency Options](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Voice Branch Resiliency Options")</span></span>

</div>

<div>

## <a name="survivable-branch-appliance-details"></a><span data-ttu-id="98e18-131">Survivable 分支裝置詳細資料</span><span class="sxs-lookup"><span data-stu-id="98e18-131">Survivable Branch Appliance Details</span></span>

<span data-ttu-id="98e18-132">Lync Server Survivable 分支裝置包含下列元件：</span><span class="sxs-lookup"><span data-stu-id="98e18-132">The Lync Server Survivable Branch Appliance includes the following components:</span></span>

  - <span data-ttu-id="98e18-133">[使用者驗證]、[註冊] 和 [呼叫路由] 的註冊機構</span><span class="sxs-lookup"><span data-stu-id="98e18-133">A Registrar for user authentication, registration and call routing</span></span>

  - <span data-ttu-id="98e18-134">在註冊機與 PSTN 閘道之間處理信號的中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="98e18-134">A Mediation Server for handling signaling between the Registrar and a PSTN gateway</span></span>

  - <span data-ttu-id="98e18-135">在 WAN 中斷事件中，將呼叫路由至 PSTN 的 PSTN 閘道作為備用傳輸</span><span class="sxs-lookup"><span data-stu-id="98e18-135">A PSTN gateway for routing calls to the PSTN as a fallback transport in the event of a WAN outage</span></span>

  - <span data-ttu-id="98e18-136">本機使用者資料儲存的 SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="98e18-136">SQL Server Express for local user data storage</span></span>

<span data-ttu-id="98e18-137">Survivable 分支裝置也包含 PSTN trunks、類比埠和乙太網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="98e18-137">The Survivable Branch Appliance also includes PSTN trunks, analog ports, and an Ethernet adapter.</span></span>

<span data-ttu-id="98e18-138">如果分支網站與中央網站的 WAN 連線無法使用，內部分支使用者會繼續向 Survivable 分支裝置註冊機構註冊，並使用 Survivable 分支裝置連線來取得不間斷的語音服務PSTN。</span><span class="sxs-lookup"><span data-stu-id="98e18-138">If the branch site’s WAN connection to a central site becomes unavailable, internal branch users continue to be registered with the Survivable Branch Appliance Registrar and obtain uninterrupted voice service by using the Survivable Branch Appliance connection to the PSTN.</span></span> <span data-ttu-id="98e18-139">從家用或其他遠端位置連線的分支網站使用者，如果無法使用分支網站的 WAN 連結，就能在中央網站上註冊註冊機構伺服器。</span><span class="sxs-lookup"><span data-stu-id="98e18-139">Branch site users who connect from home or other remote locations will be able to register with a Registrar server at a central site if the WAN link to the branch site is unavailable.</span></span> <span data-ttu-id="98e18-140">這些使用者會有完整的整合通訊功能，其中一個例外情況是，分支網站的入站呼叫會移至 [語音信箱]。</span><span class="sxs-lookup"><span data-stu-id="98e18-140">These users will have full unified communications functionality, with the one exception that inbound calls to the branch site will go to voice mail.</span></span> <span data-ttu-id="98e18-141">WAN 連線變為可用時，應將完整的功能還原至分支網站使用者。</span><span class="sxs-lookup"><span data-stu-id="98e18-141">When the WAN connection becomes available, full functionality should be restored to branch site users.</span></span> <span data-ttu-id="98e18-142">容錯移轉至 Survivable 分支裝置，而不是服務的還原，都需要 IT 系統管理員的狀態。</span><span class="sxs-lookup"><span data-stu-id="98e18-142">Neither the failover to the Survivable Branch Appliance nor the restoration of service requires the presence of an IT administrator.</span></span>

<span data-ttu-id="98e18-143">Lync Server 支援最多兩個分支網站上的 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="98e18-143">Lync Server supports up to two Survivable Branch Appliance at a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98e18-144">駐留在 Lync Server Survivable 分支裝置上的使用者無法建立新的聊天室，或無法查看現有聊天室的聊天室卡片。</span><span class="sxs-lookup"><span data-stu-id="98e18-144">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new Chat Rooms or view the Room Card for existing rooms.</span></span>



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a><span data-ttu-id="98e18-145">Survivable 分支裝置部署概述</span><span class="sxs-lookup"><span data-stu-id="98e18-145">Survivable Branch Appliance Deployment Overview</span></span>

<span data-ttu-id="98e18-146">Survivable 分支裝置是由與 Microsoft 合作的原始設備製造商生產，並由增值零售商代表其部署。</span><span class="sxs-lookup"><span data-stu-id="98e18-146">The Survivable Branch Appliance is manufactured by original equipment manufacturers in partnership with Microsoft and deployed on their behalf by value-added retailers.</span></span> <span data-ttu-id="98e18-147">只有在中央網站部署 Lync Server、分支網站的 WAN 連線已就緒，且已針對企業語音啟用分支網站使用者時，才應進行此部署。</span><span class="sxs-lookup"><span data-stu-id="98e18-147">This deployment should occur only after Lync Server has been deployed at the central site, a WAN connection to the branch site is in place, and branch site users are enabled for Enterprise Voice.</span></span>

<span data-ttu-id="98e18-148">如需這些階段的詳細資訊，請參閱部署檔中的[使用 Lync Server 2013 部署 Survivable 分支裝置或伺服器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="98e18-148">For details about these phases, see [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98e18-149">分</span><span class="sxs-lookup"><span data-stu-id="98e18-149">Phase</span></span></th>
<th><span data-ttu-id="98e18-150">步驟</span><span class="sxs-lookup"><span data-stu-id="98e18-150">Steps</span></span></th>
<th><span data-ttu-id="98e18-151">使用者權限</span><span class="sxs-lookup"><span data-stu-id="98e18-151">User Rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98e18-152">為 Survivable 分支裝置設定 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="98e18-152">Set up Active Directory Domain Services for the Survivable Branch Appliance</span></span></p></td>
<td><p><span data-ttu-id="98e18-153"><strong>在中央網站：</strong></span><span class="sxs-lookup"><span data-stu-id="98e18-153"><strong>At the central site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="98e18-154">針對將在分支網站上安裝並啟用 Survivable 分支裝置的技術人員，建立網域使用者帳戶（或企業身分識別）。</span><span class="sxs-lookup"><span data-stu-id="98e18-154">Create a domain user account (or enterprise identity) for the technician who will install and activate the Survivable Branch Appliance at the branch site.</span></span></p></li>
<li><p><span data-ttu-id="98e18-155">在 Active Directory 網域服務中，為 Survivable 分支裝置建立電腦帳戶（並提供適用的完整功能變數名稱（FQDN））。</span><span class="sxs-lookup"><span data-stu-id="98e18-155">Create a computer account (with the applicable fully qualified domain name (FQDN)) for Survivable Branch Appliance in Active Directory Domain Services.</span></span></p></li>
<li><p><span data-ttu-id="98e18-156">在 [拓撲建立器] 中，建立及發佈 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="98e18-156">In Topology Builder, create and publish the Survivable Branch Appliance.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="98e18-157">技術員使用者帳戶必須是 RTCUniversalSBATechnicians 的成員。</span><span class="sxs-lookup"><span data-stu-id="98e18-157">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span> <span data-ttu-id="98e18-158">Survivable 分支裝置必須屬於 [RTCSBAUniversalServices] 群組，當您使用 [拓撲建立器] 時，就會自動進行這個作業。</span><span class="sxs-lookup"><span data-stu-id="98e18-158">The Survivable Branch Appliance must belong to the RTCSBAUniversalServices group, which happens automatically when you use Topology Builder.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98e18-159">安裝並啟動 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="98e18-159">Install, and activate the Survivable Branch Appliance.</span></span></p></td>
<td><p><span data-ttu-id="98e18-160"><strong>在分支網站上：</strong></span><span class="sxs-lookup"><span data-stu-id="98e18-160"><strong>At the branch site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="98e18-161">將 Survivable 分支裝置連線至乙太網路埠和 PSTN 埠。</span><span class="sxs-lookup"><span data-stu-id="98e18-161">Connect the Survivable Branch Appliance to an Ethernet port and PSTN port.</span></span></p></li>
<li><p><span data-ttu-id="98e18-162">啟動 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="98e18-162">Start the Survivable Branch Appliance.</span></span></p></li>
<li><p><span data-ttu-id="98e18-163">使用在中央網站為 Survivable 分支裝置建立的網域使用者帳戶，將 Survivable 分支裝置加入網域。</span><span class="sxs-lookup"><span data-stu-id="98e18-163">Join the Survivable Branch Appliance to the domain, using the domain user account created for the Survivable Branch Appliance at the central site.</span></span> <span data-ttu-id="98e18-164">將 FQDN 和 IP 位址設定為與電腦帳戶中建立的 FQDN 相符。</span><span class="sxs-lookup"><span data-stu-id="98e18-164">Set the FQDN and IP address to match the FQDN created in the computer account.</span></span></p></li>
<li><p><span data-ttu-id="98e18-165">使用 OEM 使用者介面設定 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="98e18-165">Configure the Survivable Branch Appliance using the OEM user interface.</span></span></p></li>
<li><p><span data-ttu-id="98e18-166">測試 PSTN 連線性。</span><span class="sxs-lookup"><span data-stu-id="98e18-166">Test PSTN connectivity.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="98e18-167">技術員使用者帳戶必須是 RTCUniversalSBATechnicians 的成員。</span><span class="sxs-lookup"><span data-stu-id="98e18-167">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a><span data-ttu-id="98e18-168">Survivable 分支伺服器詳細資料</span><span class="sxs-lookup"><span data-stu-id="98e18-168">Survivable Branch Server Details</span></span>

<span data-ttu-id="98e18-169">在拓撲建立器中建立分支網站，將 Survivable 分支伺服器新增到該網站，然後在您要安裝該角色的電腦上執行 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="98e18-169">In Topology Builder create the branch site, add the Survivable Branch Server to that site, and then run the Lync Server Deployment Wizard on the computer where you want to install the role.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="98e18-170">請參閱</span><span class="sxs-lookup"><span data-stu-id="98e18-170">See Also</span></span>


[<span data-ttu-id="98e18-171">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98e18-171">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

