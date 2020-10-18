---
title: Lync Server 2013：分支網站恢復解決方案
description: Lync Server 2013：分支網站恢復解決方案。
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
ms.openlocfilehash: 796ed22344f02bca16571ff5f156c6bb80b1fcfd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572959"
---
# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a><span data-ttu-id="29b20-103">Lync Server 2013 中的分支網站恢復解決方案</span><span class="sxs-lookup"><span data-stu-id="29b20-103">Branch-site resiliency solutions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29b20-104">_**主題上次修改日期：** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="29b20-104">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="29b20-105">為您的組織提供分支網站恢復能力的好處是顯而易見的。</span><span class="sxs-lookup"><span data-stu-id="29b20-105">There are obvious advantages to providing branch-site resiliency to your organization.</span></span> <span data-ttu-id="29b20-106">具體而言，如果您失去中央網站的連線，分支網站使用者將繼續擁有 Enterprise Voice service 和 Voice mail (（如果您設定語音信箱重新路由設定）。如需詳細資訊，請參閱 [Lync Server 2013) 的分支網站恢復需求](lync-server-2013-branch-site-resiliency-requirements.md) 。</span><span class="sxs-lookup"><span data-stu-id="29b20-106">Specifically, if you lose the connection to the central site, branch site users will continue to have Enterprise Voice service and voice mail (if you configure voice mail rerouting settings; for details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span></span> <span data-ttu-id="29b20-107">但對於使用者人數低於 25 位的網站而言，恢復能力解決方案所提供的投資報酬率可能不夠。</span><span class="sxs-lookup"><span data-stu-id="29b20-107">However, for sites with fewer than 25 users, a resiliency solution may not provide a sufficient return on investment.</span></span>

<span data-ttu-id="29b20-p102">如果您決定要提供分支網站恢復能力，您有三個選項。下表可協助您判斷最適合您的組織之選項。</span><span class="sxs-lookup"><span data-stu-id="29b20-p102">If you decide to provide branch-site resiliency, you have three options. The following table can help you determine the best option for your organization.</span></span>

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29b20-110">如果您...</span><span class="sxs-lookup"><span data-stu-id="29b20-110">If you…</span></span></th>
<th><span data-ttu-id="29b20-111">建議您使用...</span><span class="sxs-lookup"><span data-stu-id="29b20-111">We recommend that you use a…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29b20-112">在您的分支網站上主控 25 到 1000 名使用者，且投資報酬率不足以支應完整部署，或是不具本機管理支援</span><span class="sxs-lookup"><span data-stu-id="29b20-112">Host between 25 and 1000 users at your branch site, and if the return on investment does not support a full deployment or where local administrative support is unavailable</span></span></p></td>
<td><p><span data-ttu-id="29b20-113">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="29b20-113">Survivable Branch Appliance</span></span></p>
<p><span data-ttu-id="29b20-114">Survivable 分支裝置是業界標準的刀片伺服器，具有在 Windows Server 2008 R2 上執行的 Lync Server 註冊機構和轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="29b20-114">The Survivable Branch Appliance is an industry-standard blade server with a Lync Server Registrar and Mediation Server running on Windows Server 2008 R2.</span></span> <span data-ttu-id="29b20-115">Survivable Branch 裝置也包含公用交換電話網路 (PSTN) 閘道。</span><span class="sxs-lookup"><span data-stu-id="29b20-115">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="29b20-116">合格的第三方裝置 (由參與 Survivable Branch Appliance (SBA) 資格/認證方案的 Microsoft 協力廠商所開發) 在 WAN 失效時仍可提供持續的 PSTN 連線，但這個方法無法提供可恢復的顯示狀態與會議功能，因為這些功能依存於中央網站上的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="29b20-116">Qualified third-party devices (developed by Microsoft partners in the Survivable Branch Appliance (SBA) qualification/certification program) provide a continuous PSTN connection in the event of WAN failure, but this approach does not provide resilient presence and conferencing because these features depend on Front End Servers at the central site.</span></span></p>
<p><span data-ttu-id="29b20-117">如需 Survivable 分支裝置的詳細資訊，請參閱 &quot; &quot; 本主題稍後的 Survivable Branch 裝置詳細資料。</span><span class="sxs-lookup"><span data-stu-id="29b20-117">For details about Survivable Branch Appliances, see &quot;Survivable Branch Appliance Details,&quot; later in this topic.</span></span></p>
<p><span data-ttu-id="29b20-118"><strong>附注：</strong> 如果您決定同時將 SIP 主幹與 Survivable 分支裝置搭配使用，請與您的 Survivable 分支裝置廠商聯繫，以瞭解哪一種服務提供者最適合您的組織。</span><span class="sxs-lookup"><span data-stu-id="29b20-118"><strong>Note:</strong> If you decide to also use a SIP trunk with your Survivable Branch Appliance, contact your Survivable Branch Appliance vendor to learn about which service provider is best for your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29b20-119">在分支網站上的1000和2000使用者間主機、缺乏彈性的 WAN 連線，且已訓練有素的 Lync Server 系統管理員可用</span><span class="sxs-lookup"><span data-stu-id="29b20-119">Host between 1000 and 2000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="29b20-120">Survivable 分支伺服器或兩個 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="29b20-120">Survivable Branch Server or two Survivable Branch Appliances.</span></span></p>
<p><span data-ttu-id="29b20-121">Survivable 分支伺服器是 Windows Server 會議指定的硬體需求，其上已安裝 Lync Server 註冊機構和轉送伺服器軟體。</span><span class="sxs-lookup"><span data-stu-id="29b20-121">The Survivable Branch Server is a Windows Server meeting specified hardware requirements that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="29b20-122">該伺服器必須將 PSTN 閘道或 SIP 主幹連線至電話服務提供者。</span><span class="sxs-lookup"><span data-stu-id="29b20-122">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span></p>
<p><span data-ttu-id="29b20-123">如需 Survivable 分支伺服器的詳細資訊，請參閱 &quot; &quot; 本主題稍後的 Survivable Branch Server details。</span><span class="sxs-lookup"><span data-stu-id="29b20-123">For details about Survivable Branch Servers, see &quot;Survivable Branch Server Details,&quot; later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29b20-124">如果您除了語音功能之外，還需要最多5000名使用者的目前狀態與會議功能，且有訓練有素的 Lync Server 系統管理員可用</span><span class="sxs-lookup"><span data-stu-id="29b20-124">If you require presence and conferencing features in addition to voice features for up to 5000 users, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="29b20-125">以 Standard Edition Server 部署為中央網站，而非分支網站。</span><span class="sxs-lookup"><span data-stu-id="29b20-125">Deploy as a central site with a Standard Edition server rather than as a branch site.</span></span></p>
<p><span data-ttu-id="29b20-126">在發生 WAN 失敗時，完整的 Lync 伺服器部署會提供連續的 PSTN 連線和彈性顯示功能和會議。</span><span class="sxs-lookup"><span data-stu-id="29b20-126">A full-scale Lync Server deployment provides a continuous PSTN connection and resilient presence and conferencing in the event of WAN failure.</span></span></p>
<p><span data-ttu-id="29b20-127">如需準備此方案的詳細資訊，請參閱 <a href="lync-server-2013-planning-for-your-organization.md">組織規劃 Lync server 2013</a>， <a href="lync-server-2013-determining-your-system-requirements.md">判斷 lync server 2013 的系統需求</a>， <a href="lync-server-2013-determining-your-infrastructure-requirements.md">判斷 lync server 2013 的基礎結構需求</a>，以及規劃檔的其他相關章節。</span><span class="sxs-lookup"><span data-stu-id="29b20-127">For details about preparing for this solution, see <a href="lync-server-2013-planning-for-your-organization.md">Organization planning for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determining your infrastructure requirements for Lync Server 2013</a>, and other relevant sections of the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a><span data-ttu-id="29b20-128">恢復能力拓撲</span><span class="sxs-lookup"><span data-stu-id="29b20-128">Resiliency Topologies</span></span>

<span data-ttu-id="29b20-129">下圖顯示分支網站恢復能力所適用的建議拓撲。</span><span class="sxs-lookup"><span data-stu-id="29b20-129">The following figure shows the recommended topologies for branch-site resiliency.</span></span>

<span data-ttu-id="29b20-130">**分支網站恢復能力選項**</span><span class="sxs-lookup"><span data-stu-id="29b20-130">**Branch site resiliency options**</span></span>

<span data-ttu-id="29b20-131">![語音分支恢復選項](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "語音分支恢復選項")</span><span class="sxs-lookup"><span data-stu-id="29b20-131">![Voice Branch Resiliency Options](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Voice Branch Resiliency Options")</span></span>

</div>

<div>

## <a name="survivable-branch-appliance-details"></a><span data-ttu-id="29b20-132">Survivable Branch Appliance 詳細資料</span><span class="sxs-lookup"><span data-stu-id="29b20-132">Survivable Branch Appliance Details</span></span>

<span data-ttu-id="29b20-133">Lync Server Survivable Branch 裝置包含下列元件：</span><span class="sxs-lookup"><span data-stu-id="29b20-133">The Lync Server Survivable Branch Appliance includes the following components:</span></span>

  - <span data-ttu-id="29b20-134">使用者驗證、登錄與通話路由所需的登錄器</span><span class="sxs-lookup"><span data-stu-id="29b20-134">A Registrar for user authentication, registration and call routing</span></span>

  - <span data-ttu-id="29b20-135">用以處理登錄器與 PSTN 閘道間往來訊號的中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="29b20-135">A Mediation Server for handling signaling between the Registrar and a PSTN gateway</span></span>

  - <span data-ttu-id="29b20-136">在 WAN 中斷時，用以將通話路由至 PSTN 作為後援傳輸的 PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="29b20-136">A PSTN gateway for routing calls to the PSTN as a fallback transport in the event of a WAN outage</span></span>

  - <span data-ttu-id="29b20-137">供本機使用者存放資料的 SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="29b20-137">SQL Server Express for local user data storage</span></span>

<span data-ttu-id="29b20-138">Survivable 分支裝置也包含 PSTN 主幹、類比埠和乙太網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="29b20-138">The Survivable Branch Appliance also includes PSTN trunks, analog ports, and an Ethernet adapter.</span></span>

<span data-ttu-id="29b20-139">如果分支網站與中央網站之間的 WAN 連線無法使用，則內部分支使用者仍會向 Survivable Branch 裝置註冊機構註冊，並使用 Survivable Branch 裝置連接至 PSTN，以取得不間斷的語音服務。</span><span class="sxs-lookup"><span data-stu-id="29b20-139">If the branch site’s WAN connection to a central site becomes unavailable, internal branch users continue to be registered with the Survivable Branch Appliance Registrar and obtain uninterrupted voice service by using the Survivable Branch Appliance connection to the PSTN.</span></span> <span data-ttu-id="29b20-140">當分支網站的 WAN 連結無法使用時，從家中或其他遠端位置連線的分支網站使用者將可使用中央網站上的登錄器伺服器進行登錄。</span><span class="sxs-lookup"><span data-stu-id="29b20-140">Branch site users who connect from home or other remote locations will be able to register with a Registrar server at a central site if the WAN link to the branch site is unavailable.</span></span> <span data-ttu-id="29b20-141">這些使用者將可擁有完整的整合通訊功能，但有一例外，傳入分支網站的來電會轉接至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="29b20-141">These users will have full unified communications functionality, with the one exception that inbound calls to the branch site will go to voice mail.</span></span> <span data-ttu-id="29b20-142">當 WAN 連線恢復時，分支網站使用者即應可重獲完整的功能。</span><span class="sxs-lookup"><span data-stu-id="29b20-142">When the WAN connection becomes available, full functionality should be restored to branch site users.</span></span> <span data-ttu-id="29b20-143">容錯移轉至 Survivable Branch 裝置或服務的還原，都不需要有 IT 系統管理員的狀態。</span><span class="sxs-lookup"><span data-stu-id="29b20-143">Neither the failover to the Survivable Branch Appliance nor the restoration of service requires the presence of an IT administrator.</span></span>

<span data-ttu-id="29b20-144">Lync Server 在分支網站上支援最多兩個 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="29b20-144">Lync Server supports up to two Survivable Branch Appliance at a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="29b20-145">在 Lync Server Survivable Branch 裝置上的使用者無法建立新聊天室或查看現有聊天室的會議室卡片。</span><span class="sxs-lookup"><span data-stu-id="29b20-145">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new Chat Rooms or view the Room Card for existing rooms.</span></span>



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a><span data-ttu-id="29b20-146">Survivable Branch Appliance 部署概觀</span><span class="sxs-lookup"><span data-stu-id="29b20-146">Survivable Branch Appliance Deployment Overview</span></span>

<span data-ttu-id="29b20-147">Survivable 分支裝置是由原始設備製造商生產，與 Microsoft 合作，並由增值零售商自行部署。</span><span class="sxs-lookup"><span data-stu-id="29b20-147">The Survivable Branch Appliance is manufactured by original equipment manufacturers in partnership with Microsoft and deployed on their behalf by value-added retailers.</span></span> <span data-ttu-id="29b20-148">只有在中央網站部署 Lync Server 之後，才會發生此部署，分支網站的 WAN 連線會就地存在，且會為企業語音啟用分支網站使用者。</span><span class="sxs-lookup"><span data-stu-id="29b20-148">This deployment should occur only after Lync Server has been deployed at the central site, a WAN connection to the branch site is in place, and branch site users are enabled for Enterprise Voice.</span></span>

<span data-ttu-id="29b20-149">如需這些階段的詳細資訊，請參閱部署檔中的 [部署 Survivable Branch 裝置或含 Lync Server 2013 的伺服器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="29b20-149">For details about these phases, see [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29b20-150">階段</span><span class="sxs-lookup"><span data-stu-id="29b20-150">Phase</span></span></th>
<th><span data-ttu-id="29b20-151">步驟</span><span class="sxs-lookup"><span data-stu-id="29b20-151">Steps</span></span></th>
<th><span data-ttu-id="29b20-152">使用者權限</span><span class="sxs-lookup"><span data-stu-id="29b20-152">User Rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29b20-153">為 Survivable Branch 裝置設定 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="29b20-153">Set up Active Directory Domain Services for the Survivable Branch Appliance</span></span></p></td>
<td><p><span data-ttu-id="29b20-154"><strong>在中央網站上：</strong></span><span class="sxs-lookup"><span data-stu-id="29b20-154"><strong>At the central site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="29b20-155">在分支網站上，為將安裝及啟動 Survivable 分支裝置的技術人員建立網域使用者帳戶 (或企業身分識別) 。</span><span class="sxs-lookup"><span data-stu-id="29b20-155">Create a domain user account (or enterprise identity) for the technician who will install and activate the Survivable Branch Appliance at the branch site.</span></span></p></li>
<li><p><span data-ttu-id="29b20-156">使用 Active Directory 網域服務中 Survivable Branch 裝置的適用的完整功能變數名稱 (FQDN) # A3，建立電腦帳戶 (。</span><span class="sxs-lookup"><span data-stu-id="29b20-156">Create a computer account (with the applicable fully qualified domain name (FQDN)) for Survivable Branch Appliance in Active Directory Domain Services.</span></span></p></li>
<li><p><span data-ttu-id="29b20-157">在 [拓撲產生器] 中，建立併發布 Survivable Branch 裝置。</span><span class="sxs-lookup"><span data-stu-id="29b20-157">In Topology Builder, create and publish the Survivable Branch Appliance.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="29b20-158">技術人員的使用者帳戶必須是 RTCUniversalSBATechnicians 的成員。</span><span class="sxs-lookup"><span data-stu-id="29b20-158">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span> <span data-ttu-id="29b20-159">Survivable 分支裝置必須屬於 RTCSBAUniversalServices 群組，這會在您使用拓撲產生器時自動進行。</span><span class="sxs-lookup"><span data-stu-id="29b20-159">The Survivable Branch Appliance must belong to the RTCSBAUniversalServices group, which happens automatically when you use Topology Builder.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29b20-160">安裝和啟動 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="29b20-160">Install, and activate the Survivable Branch Appliance.</span></span></p></td>
<td><p><span data-ttu-id="29b20-161"><strong>在分支網站上：</strong></span><span class="sxs-lookup"><span data-stu-id="29b20-161"><strong>At the branch site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="29b20-162">將 Survivable 分支裝置連接至乙太網路埠和 PSTN 埠。</span><span class="sxs-lookup"><span data-stu-id="29b20-162">Connect the Survivable Branch Appliance to an Ethernet port and PSTN port.</span></span></p></li>
<li><p><span data-ttu-id="29b20-163">啟動 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="29b20-163">Start the Survivable Branch Appliance.</span></span></p></li>
<li><p><span data-ttu-id="29b20-164">使用在中央網站為 Survivable Branch 裝置建立的網域使用者帳戶，將 Survivable 分支裝置加入網域。</span><span class="sxs-lookup"><span data-stu-id="29b20-164">Join the Survivable Branch Appliance to the domain, using the domain user account created for the Survivable Branch Appliance at the central site.</span></span> <span data-ttu-id="29b20-165">設定 FQDN 與 IP 位址，使其符合在電腦帳戶中建立的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="29b20-165">Set the FQDN and IP address to match the FQDN created in the computer account.</span></span></p></li>
<li><p><span data-ttu-id="29b20-166">使用 OEM 使用者介面設定 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="29b20-166">Configure the Survivable Branch Appliance using the OEM user interface.</span></span></p></li>
<li><p><span data-ttu-id="29b20-167">測試 PSTN 連線。</span><span class="sxs-lookup"><span data-stu-id="29b20-167">Test PSTN connectivity.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="29b20-168">技術人員的使用者帳戶必須是 RTCUniversalSBATechnicians 的成員。</span><span class="sxs-lookup"><span data-stu-id="29b20-168">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a><span data-ttu-id="29b20-169">Survivable Branch Server 詳細資料</span><span class="sxs-lookup"><span data-stu-id="29b20-169">Survivable Branch Server Details</span></span>

<span data-ttu-id="29b20-170">在 [拓撲產生器] 中，建立分支網站，將 Survivable 分支伺服器新增至該網站，然後在您要安裝該角色的電腦上執行 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="29b20-170">In Topology Builder create the branch site, add the Survivable Branch Server to that site, and then run the Lync Server Deployment Wizard on the computer where you want to install the role.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="29b20-171">另請參閱</span><span class="sxs-lookup"><span data-stu-id="29b20-171">See Also</span></span>


[<span data-ttu-id="29b20-172">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29b20-172">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

