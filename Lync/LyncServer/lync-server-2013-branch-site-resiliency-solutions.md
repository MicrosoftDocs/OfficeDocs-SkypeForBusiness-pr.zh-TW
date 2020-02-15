---
title: Lync Server 2013： 分支網站恢復解決方案
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
ms.openlocfilehash: 019da9259cae95d019f954f275ed36a5f79174e4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a><span data-ttu-id="f1ce0-102">Lync Server 2013 中的分支網站恢復解決方案</span><span class="sxs-lookup"><span data-stu-id="f1ce0-102">Branch-site resiliency solutions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1ce0-103">_**上次修改主題：** 2014年-12-10_</span><span class="sxs-lookup"><span data-stu-id="f1ce0-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="f1ce0-104">為您的組織提供分支網站恢復能力的好處是顯而易見的。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-104">There are obvious advantages to providing branch-site resiliency to your organization.</span></span> <span data-ttu-id="f1ce0-105">具體而言，如果您遺失連線至中央網站，分支網站使用者將繼續擁有企業語音服務和語音信箱 (如果您設定語音信箱重新路由設定; 如需詳細資訊，請參閱[Lync Server 2013 的分支網站恢復能力需求](lync-server-2013-branch-site-resiliency-requirements.md))。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-105">Specifically, if you lose the connection to the central site, branch site users will continue to have Enterprise Voice service and voice mail (if you configure voice mail rerouting settings; for details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span></span> <span data-ttu-id="f1ce0-106">但對於使用者人數低於 25 位的網站而言，恢復能力解決方案所提供的投資報酬率可能不夠。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-106">However, for sites with fewer than 25 users, a resiliency solution may not provide a sufficient return on investment.</span></span>

<span data-ttu-id="f1ce0-p102">如果您決定要提供分支網站恢復能力，您有三個選項。下表可協助您判斷最適合您的組織之選項。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-p102">If you decide to provide branch-site resiliency, you have three options. The following table can help you determine the best option for your organization.</span></span>

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1ce0-109">如果您...</span><span class="sxs-lookup"><span data-stu-id="f1ce0-109">If you…</span></span></th>
<th><span data-ttu-id="f1ce0-110">建議您使用...</span><span class="sxs-lookup"><span data-stu-id="f1ce0-110">We recommend that you use a…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1ce0-111">在您的分支網站上主控 25 到 1000 名使用者，且投資報酬率不足以支應完整部署，或是不具本機管理支援</span><span class="sxs-lookup"><span data-stu-id="f1ce0-111">Host between 25 and 1000 users at your branch site, and if the return on investment does not support a full deployment or where local administrative support is unavailable</span></span></p></td>
<td><p><span data-ttu-id="f1ce0-112">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="f1ce0-112">Survivable Branch Appliance</span></span></p>
<p><span data-ttu-id="f1ce0-113">Survivable Branch Appliance 是 Lync Server 登錄器的業界標準] 刀鋒視窗中伺服器和 Windows Server 2008 R2 上執行的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-113">The Survivable Branch Appliance is an industry-standard blade server with a Lync Server Registrar and Mediation Server running on Windows Server 2008 R2.</span></span> <span data-ttu-id="f1ce0-114">Survivable Branch Appliance 也包含公用交換的電話網路 (PSTN) 閘道。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-114">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="f1ce0-115">合格的第三方裝置 (由參與 Survivable Branch Appliance (SBA) 資格/認證方案的 Microsoft 協力廠商所開發) 在 WAN 失效時仍可提供持續的 PSTN 連線，但這個方法無法提供可恢復的顯示狀態與會議功能，因為這些功能依存於中央網站上的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-115">Qualified third-party devices (developed by Microsoft partners in the Survivable Branch Appliance (SBA) qualification/certification program) provide a continuous PSTN connection in the event of WAN failure, but this approach does not provide resilient presence and conferencing because these features depend on Front End Servers at the central site.</span></span></p>
<p><span data-ttu-id="f1ce0-116">如需 Survivable Branch Appliance 的詳細資訊，請參閱&quot;Survivable Branch Appliance 詳細資料，&quot;本主題稍後。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-116">For details about Survivable Branch Appliances, see &quot;Survivable Branch Appliance Details,&quot; later in this topic.</span></span></p>
<p><span data-ttu-id="f1ce0-117"><strong>附註：</strong>如果您決定也使用 SIP 主幹與您 Survivable Branch Appliance，請連絡您的 Survivable Branch Appliance 廠商連絡，以了解哪些服務提供者最適合您的組織。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-117"><strong>Note:</strong> If you decide to also use a SIP trunk with your Survivable Branch Appliance, contact your Survivable Branch Appliance vendor to learn about which service provider is best for your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1ce0-118">主控 1000年到 2000年分支網站的使用者之間、 缺少可恢復的 WAN 連線，以及擁有經過訓練的 Lync Server 系統管理員</span><span class="sxs-lookup"><span data-stu-id="f1ce0-118">Host between 1000 and 2000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="f1ce0-119">Survivable Branch 伺服器或兩個 Survivable Branch Appliance。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-119">Survivable Branch Server or two Survivable Branch Appliances.</span></span></p>
<p><span data-ttu-id="f1ce0-120">Survivable Branch 伺服器是具有 Lync 伺服器登錄器和中繼伺服器軟體在其上安裝 Windows Server 符合指定的硬體需求。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-120">The Survivable Branch Server is a Windows Server meeting specified hardware requirements that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="f1ce0-121">該伺服器必須將 PSTN 閘道或 SIP 主幹連線至電話服務提供者。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-121">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span></p>
<p><span data-ttu-id="f1ce0-122">如需 Survivable Branch 伺服器的詳細資訊，請參閱&quot;Survivable Branch Server 詳細資料，&quot;本主題稍後。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-122">For details about Survivable Branch Servers, see &quot;Survivable Branch Server Details,&quot; later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1ce0-123">如果您需要的目前狀態和會議功能除了語音功能達 5000 名使用者，並有經過訓練的 Lync Server 系統管理員</span><span class="sxs-lookup"><span data-stu-id="f1ce0-123">If you require presence and conferencing features in addition to voice features for up to 5000 users, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="f1ce0-124">以 Standard Edition Server 部署為中央網站，而非分支網站。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-124">Deploy as a central site with a Standard Edition server rather than as a branch site.</span></span></p>
<p><span data-ttu-id="f1ce0-125">完整規模 Lync Server 部署提供持續的 PSTN 連線可恢復的目前狀態和 WAN 故障時的會議。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-125">A full-scale Lync Server deployment provides a continuous PSTN connection and resilient presence and conferencing in the event of WAN failure.</span></span></p>
<p><span data-ttu-id="f1ce0-126">如需準備針對此解決方案的詳細資訊，請參閱<a href="lync-server-2013-planning-for-your-organization.md">組織規劃 Lync Server 2013</a>、<a href="lync-server-2013-determining-your-system-requirements.md">判斷 Lync Server 2013 系統需求</a>、<a href="lync-server-2013-determining-your-infrastructure-requirements.md">決定 Lync Server 2013 的基礎結構需求</a>，以及規劃文件的其他相關章節。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-126">For details about preparing for this solution, see <a href="lync-server-2013-planning-for-your-organization.md">Organization planning for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determining your infrastructure requirements for Lync Server 2013</a>, and other relevant sections of the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a><span data-ttu-id="f1ce0-127">恢復能力拓撲</span><span class="sxs-lookup"><span data-stu-id="f1ce0-127">Resiliency Topologies</span></span>

<span data-ttu-id="f1ce0-128">下圖顯示分支網站恢復能力所適用的建議拓撲。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-128">The following figure shows the recommended topologies for branch-site resiliency.</span></span>

<span data-ttu-id="f1ce0-129">**分支網站恢復能力選項**</span><span class="sxs-lookup"><span data-stu-id="f1ce0-129">**Branch site resiliency options**</span></span>

<span data-ttu-id="f1ce0-130">![語音分支恢復能力選項](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "語音分支恢復能力選項")</span><span class="sxs-lookup"><span data-stu-id="f1ce0-130">![Voice Branch Resiliency Options](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Voice Branch Resiliency Options")</span></span>

</div>

<div>

## <a name="survivable-branch-appliance-details"></a><span data-ttu-id="f1ce0-131">Survivable Branch Appliance 詳細資料</span><span class="sxs-lookup"><span data-stu-id="f1ce0-131">Survivable Branch Appliance Details</span></span>

<span data-ttu-id="f1ce0-132">Lync Server Survivable Branch Appliance 包含下列元件：</span><span class="sxs-lookup"><span data-stu-id="f1ce0-132">The Lync Server Survivable Branch Appliance includes the following components:</span></span>

  - <span data-ttu-id="f1ce0-133">使用者驗證、登錄與通話路由所需的登錄器</span><span class="sxs-lookup"><span data-stu-id="f1ce0-133">A Registrar for user authentication, registration and call routing</span></span>

  - <span data-ttu-id="f1ce0-134">用以處理登錄器與 PSTN 閘道間往來訊號的中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="f1ce0-134">A Mediation Server for handling signaling between the Registrar and a PSTN gateway</span></span>

  - <span data-ttu-id="f1ce0-135">在 WAN 中斷時，用以將通話路由至 PSTN 作為後援傳輸的 PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="f1ce0-135">A PSTN gateway for routing calls to the PSTN as a fallback transport in the event of a WAN outage</span></span>

  - <span data-ttu-id="f1ce0-136">供本機使用者存放資料的 SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="f1ce0-136">SQL Server Express for local user data storage</span></span>

<span data-ttu-id="f1ce0-137">Survivable Branch Appliance 也包含 PSTN 主幹、 類比連接埠與乙太網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-137">The Survivable Branch Appliance also includes PSTN trunks, analog ports, and an Ethernet adapter.</span></span>

<span data-ttu-id="f1ce0-138">如果分支網站的 WAN 連線至中央網站變成無法使用，內部的分支使用者繼續 Survivable Branch Appliance 註冊機構註冊並使用 Survivable Branch Appliance 的連線，以取得不會中斷的語音服務至 PSTN。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-138">If the branch site’s WAN connection to a central site becomes unavailable, internal branch users continue to be registered with the Survivable Branch Appliance Registrar and obtain uninterrupted voice service by using the Survivable Branch Appliance connection to the PSTN.</span></span> <span data-ttu-id="f1ce0-139">當分支網站的 WAN 連結無法使用時，從家中或其他遠端位置連線的分支網站使用者將可使用中央網站上的登錄器伺服器進行登錄。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-139">Branch site users who connect from home or other remote locations will be able to register with a Registrar server at a central site if the WAN link to the branch site is unavailable.</span></span> <span data-ttu-id="f1ce0-140">這些使用者將可擁有完整的整合通訊功能，但有一例外，傳入分支網站的來電會轉接至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-140">These users will have full unified communications functionality, with the one exception that inbound calls to the branch site will go to voice mail.</span></span> <span data-ttu-id="f1ce0-141">當 WAN 連線恢復時，分支網站使用者即應可重獲完整的功能。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-141">When the WAN connection becomes available, full functionality should be restored to branch site users.</span></span> <span data-ttu-id="f1ce0-142">不在容錯移轉至 Survivable Branch Appliance 或服務的還原要求 IT 系統管理員的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-142">Neither the failover to the Survivable Branch Appliance nor the restoration of service requires the presence of an IT administrator.</span></span>

<span data-ttu-id="f1ce0-143">Lync Server 支援最多兩個 Survivable Branch Appliance 分支網站。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-143">Lync Server supports up to two Survivable Branch Appliance at a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f1ce0-144">位於 Lync Server Survivable Branch Appliance 的使用者將無法建立新聊天室或檢視現有的會議室會議室卡片。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-144">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new Chat Rooms or view the Room Card for existing rooms.</span></span>



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a><span data-ttu-id="f1ce0-145">Survivable Branch Appliance 部署概觀</span><span class="sxs-lookup"><span data-stu-id="f1ce0-145">Survivable Branch Appliance Deployment Overview</span></span>

<span data-ttu-id="f1ce0-146">Survivable Branch Appliance 是生產原始設備製造商，以與 Microsoft 合作關係，及在其代理上部署的加值零售商。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-146">The Survivable Branch Appliance is manufactured by original equipment manufacturers in partnership with Microsoft and deployed on their behalf by value-added retailers.</span></span> <span data-ttu-id="f1ce0-147">在中央網站已部署 Lync Server、 分支站台的 WAN 連線已經準備就緒，及分支網站使用者啟用 Enterprise Voice 之後，才應執行此部署。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-147">This deployment should occur only after Lync Server has been deployed at the central site, a WAN connection to the branch site is in place, and branch site users are enabled for Enterprise Voice.</span></span>

<span data-ttu-id="f1ce0-148">如需這些階段的詳細資訊，請參閱部署文件中的[部署 Survivable Branch Appliance 或 survivable branch Server 與 Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-148">For details about these phases, see [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1ce0-149">階段</span><span class="sxs-lookup"><span data-stu-id="f1ce0-149">Phase</span></span></th>
<th><span data-ttu-id="f1ce0-150">步驟</span><span class="sxs-lookup"><span data-stu-id="f1ce0-150">Steps</span></span></th>
<th><span data-ttu-id="f1ce0-151">使用者權限</span><span class="sxs-lookup"><span data-stu-id="f1ce0-151">User Rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1ce0-152">設定 Survivable Branch Appliance 的 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="f1ce0-152">Set up Active Directory Domain Services for the Survivable Branch Appliance</span></span></p></td>
<td><p><span data-ttu-id="f1ce0-153"><strong>在中央網站上：</strong></span><span class="sxs-lookup"><span data-stu-id="f1ce0-153"><strong>At the central site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="f1ce0-154">將會安裝並啟動 Survivable Branch Appliance 分支網站的技術人員建立網域使用者帳戶 （或企業身分識別）。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-154">Create a domain user account (or enterprise identity) for the technician who will install and activate the Survivable Branch Appliance at the branch site.</span></span></p></li>
<li><p><span data-ttu-id="f1ce0-155">建立 Active Directory 網域服務中的 Survivable Branch Appliance 的電腦帳戶 （適用於完整的網域名稱 (FQDN)）。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-155">Create a computer account (with the applicable fully qualified domain name (FQDN)) for Survivable Branch Appliance in Active Directory Domain Services.</span></span></p></li>
<li><p><span data-ttu-id="f1ce0-156">在拓撲產生器中，建立及發佈 Survivable Branch Appliance。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-156">In Topology Builder, create and publish the Survivable Branch Appliance.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f1ce0-157">技術人員的使用者帳戶必須是 RTCUniversalSBATechnicians 的成員。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-157">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span> <span data-ttu-id="f1ce0-158">Survivable Branch Appliance 必須屬於 [RTCSBAUniversalServices 群組中，當您使用拓撲產生器自動發生。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-158">The Survivable Branch Appliance must belong to the RTCSBAUniversalServices group, which happens automatically when you use Topology Builder.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1ce0-159">安裝並啟動 Survivable Branch Appliance。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-159">Install, and activate the Survivable Branch Appliance.</span></span></p></td>
<td><p><span data-ttu-id="f1ce0-160"><strong>在分支網站上：</strong></span><span class="sxs-lookup"><span data-stu-id="f1ce0-160"><strong>At the branch site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="f1ce0-161">連線至乙太網路連接埠與 PSTN 連接埠的 Survivable Branch Appliance。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-161">Connect the Survivable Branch Appliance to an Ethernet port and PSTN port.</span></span></p></li>
<li><p><span data-ttu-id="f1ce0-162">啟動 Survivable Branch Appliance。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-162">Start the Survivable Branch Appliance.</span></span></p></li>
<li><p><span data-ttu-id="f1ce0-163">將 Survivable Branch Appliance 加入至使用 Survivable Branch appliance 在中央網站建立的網域使用者帳戶的網域。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-163">Join the Survivable Branch Appliance to the domain, using the domain user account created for the Survivable Branch Appliance at the central site.</span></span> <span data-ttu-id="f1ce0-164">設定 FQDN 與 IP 位址，使其符合在電腦帳戶中建立的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-164">Set the FQDN and IP address to match the FQDN created in the computer account.</span></span></p></li>
<li><p><span data-ttu-id="f1ce0-165">設定 Survivable Branch Appliance 使用 OEM 使用者介面。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-165">Configure the Survivable Branch Appliance using the OEM user interface.</span></span></p></li>
<li><p><span data-ttu-id="f1ce0-166">測試 PSTN 連線。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-166">Test PSTN connectivity.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f1ce0-167">技術人員的使用者帳戶必須是 RTCUniversalSBATechnicians 的成員。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-167">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a><span data-ttu-id="f1ce0-168">Survivable Branch Server 詳細資料</span><span class="sxs-lookup"><span data-stu-id="f1ce0-168">Survivable Branch Server Details</span></span>

<span data-ttu-id="f1ce0-169">在拓撲產生器建立分支網站，該網站中，新增 Survivable Branch 伺服器並執行 Lync Server 部署精靈在電腦上您要安裝角色。</span><span class="sxs-lookup"><span data-stu-id="f1ce0-169">In Topology Builder create the branch site, add the Survivable Branch Server to that site, and then run the Lync Server Deployment Wizard on the computer where you want to install the role.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f1ce0-170">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f1ce0-170">See Also</span></span>


[<span data-ttu-id="f1ce0-171">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1ce0-171">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

