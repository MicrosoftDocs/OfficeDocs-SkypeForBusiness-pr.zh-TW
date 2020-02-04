---
title: 設定 SIP 同盟、XMPP 同盟及 Public Instant Messaging
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45abe0b4c32cf236912ad1a0e39f842653817e59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="2285c-102">在 Lync Server 2013 中設定 SIP 同盟、XMPP 同盟及 Public Instant Messaging</span><span class="sxs-lookup"><span data-stu-id="2285c-102">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2285c-103">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="2285c-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="2285c-104">[同盟]、[公用立即訊息連線] 和 [可擴展訊息] 和 [目前狀態通訊協定] （XMPP）定義不同類別的外部使用者-聯盟使用者。</span><span class="sxs-lookup"><span data-stu-id="2285c-104">Federation, public instant messaging connectivity and Extensible Messaging and Presence Protocol (XMPP) define a different class of external users – Federated users.</span></span> <span data-ttu-id="2285c-105">同盟 Lync Server 部署或 XMPP 部署的使用者可以存取一組有限的服務，並由外部部署進行驗證。</span><span class="sxs-lookup"><span data-stu-id="2285c-105">Users of a federated Lync Server deployment or XMPP deployment have access to a limited set of services and are authenticated by the external deployment.</span></span> <span data-ttu-id="2285c-106">遠端使用者是您 Lync Server 部署的成員，且擁有您的部署所提供的所有服務的存取權。</span><span class="sxs-lookup"><span data-stu-id="2285c-106">Remote users are members of your Lync Server deployment and have access to all services offered by your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="2285c-107">AOL 和 Yahoo！的存留期結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="2285c-107">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="2285c-108">已公佈。</span><span class="sxs-lookup"><span data-stu-id="2285c-108">has been announced.</span></span> <span data-ttu-id="2285c-109">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</span><span class="sxs-lookup"><span data-stu-id="2285c-109">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="2285c-110">公用立即訊息連線是一種特殊的同盟類型，可讓 Lync Server 用戶端使用 Lync 2013 存取已設定的公用立即訊息合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="2285c-110">Public instant messaging connectivity is a special type of federation that allows a Lync Server client to access configured public Instant Messaging partners using the Lync 2013.</span></span> <span data-ttu-id="2285c-111">目前的公用立即訊息連線性合作夥伴為：</span><span class="sxs-lookup"><span data-stu-id="2285c-111">The current public instant messaging connectivity partners are:</span></span>

  - <span></span>  
    <span data-ttu-id="2285c-112">美洲線上</span><span class="sxs-lookup"><span data-stu-id="2285c-112">America Online</span></span>

  - <span></span>  
    <span data-ttu-id="2285c-113">Windows Live</span><span class="sxs-lookup"><span data-stu-id="2285c-113">Windows Live</span></span>

  - <span></span>  
    <span data-ttu-id="2285c-114">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="2285c-114">Yahoo\!</span></span>

<span data-ttu-id="2285c-115">公用立即訊息連線設定可讓 Lync 使用者透過以下方式存取公用立即訊息連線使用者：</span><span class="sxs-lookup"><span data-stu-id="2285c-115">A public instant messaging connectivity configuration allows Lync users access to public instant messaging connectivity users by:</span></span>

  - <span data-ttu-id="2285c-116">IM 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="2285c-116">IM and Presence</span></span>

  - <span data-ttu-id="2285c-117">Lync 用戶端中公用立即訊息線上連絡人的可見度</span><span class="sxs-lookup"><span data-stu-id="2285c-117">Visibility of public instant messaging connectivity contacts in Lync client</span></span>

  - <span data-ttu-id="2285c-118">某人與連絡人進行 IM 交談</span><span class="sxs-lookup"><span data-stu-id="2285c-118">Person to person IM conversations with contacts</span></span>

  - <span data-ttu-id="2285c-119">與 Windows Live 使用者進行音訊與視頻通話</span><span class="sxs-lookup"><span data-stu-id="2285c-119">Audio and video calls with Windows Live users</span></span>

<span data-ttu-id="2285c-120">Lync Server 同盟會定義您的 Lync Server 部署與其他 Office 通訊伺服器 2007 R2 或 Lync Server 部署之間的協定。</span><span class="sxs-lookup"><span data-stu-id="2285c-120">Lync Server federation defines an agreement between your Lync Server deployment and other Office Communications Server 2007 R2 or Lync Server deployments.</span></span> <span data-ttu-id="2285c-121">Lync Server 同盟設定可讓 Lync 使用者透過以下方式存取聯盟使用者：</span><span class="sxs-lookup"><span data-stu-id="2285c-121">A Lync Server federated configuration allows Lync users access to federated users by:</span></span>

  - <span data-ttu-id="2285c-122">IM 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="2285c-122">IM and Presence</span></span>

  - <span data-ttu-id="2285c-123">在 Lync 用戶端中建立同盟連絡人</span><span class="sxs-lookup"><span data-stu-id="2285c-123">Creation of federated contacts in the Lync client</span></span>

<span data-ttu-id="2285c-124">XMPP 同盟會根據可擴展的訊息和目前狀態通訊協定來定義外部部署。</span><span class="sxs-lookup"><span data-stu-id="2285c-124">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol.</span></span> <span data-ttu-id="2285c-125">XMPP 設定可讓 Lync 使用者透過以下方式存取允許 XMPP 網域使用者：</span><span class="sxs-lookup"><span data-stu-id="2285c-125">An XMPP configuration allows Lync users access to allowed XMPP domain users by:</span></span>

  - <span data-ttu-id="2285c-126">IM 和目前狀態-僅限人員的人員</span><span class="sxs-lookup"><span data-stu-id="2285c-126">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="2285c-127">在 Lync 用戶端中建立 XMPP 同盟連絡人</span><span class="sxs-lookup"><span data-stu-id="2285c-127">Creation of XMPP federated contacts in the Lync client</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="2285c-128">Lync Server 2013 的 XMPP 功能是由 Microsoft 針對使用 Google 交談的立即訊息同盟進行測試和支援。</span><span class="sxs-lookup"><span data-stu-id="2285c-128">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="2285c-129">針對任何其他 XMPP 系統，請與協力廠商廠商聯繫，確認他們支援 Lync Server 2013 的同盟，以及任何部署或疑難排解建議。</span><span class="sxs-lookup"><span data-stu-id="2285c-129">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a><span data-ttu-id="2285c-130">Edge 伺服器外部同盟、公用立即訊息連線與 XMPP 使用者部署程式</span><span class="sxs-lookup"><span data-stu-id="2285c-130">Edge Server External Federation, Public Instant Messaging Connectivity and XMPP Users Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2285c-131">分</span><span class="sxs-lookup"><span data-stu-id="2285c-131">Phase</span></span></th>
<th><span data-ttu-id="2285c-132">步驟</span><span class="sxs-lookup"><span data-stu-id="2285c-132">Steps</span></span></th>
<th><span data-ttu-id="2285c-133">許可權</span><span class="sxs-lookup"><span data-stu-id="2285c-133">Permissions</span></span></th>
<th><span data-ttu-id="2285c-134">文件</span><span class="sxs-lookup"><span data-stu-id="2285c-134">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2285c-135">決定要新增到現有邊緣部署的選項</span><span class="sxs-lookup"><span data-stu-id="2285c-135">Determine the options to add to the existing Edge deployment</span></span></p></td>
<td><p><span data-ttu-id="2285c-136">執行拓撲建立器以編輯邊緣伺服器設定，並建立和發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="2285c-136">Run Topology Builder to edit Edge Server settings and create and publish the topology.</span></span> <span data-ttu-id="2285c-137">您現有的邊緣拓朴會將變更從中央管理儲存體複製到 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="2285c-137">Your existing Edge topology will replicate changes from the Central Management store to the Edge Server.</span></span></p></td>
<td><p><span data-ttu-id="2285c-138">[網域管理員] 群組和 [RTCUniversalServerAdmins] 群組</span><span class="sxs-lookup"><span data-stu-id="2285c-138">Domain Admins group and RTCUniversalServerAdmins group</span></span></p>



> [!NOTE]
> <span data-ttu-id="2285c-139">您可以使用屬於 [本機使用者] 群組成員的帳戶來編輯拓朴，但發佈拓朴需要網域系統管理員群組和 [RTCUniversalServerAdmins] 群組成員的帳戶。</span><span class="sxs-lookup"><span data-stu-id="2285c-139">You can edit a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group</span></span>

</td>
<td><p><span data-ttu-id="2285c-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">在 Lync Server 2013 中建置 Edge 和 Director 拓撲</a></span><span class="sxs-lookup"><span data-stu-id="2285c-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2285c-141">準備設定</span><span class="sxs-lookup"><span data-stu-id="2285c-141">Prepare for setup</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="2285c-142">確保已滿足系統先決條件。</span><span class="sxs-lookup"><span data-stu-id="2285c-142">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="2285c-143">設定內部和外部 DNS 記錄，以支援公用立即訊息連線、Lync 同盟與 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="2285c-143">Configure internal and external DNS records, to support public instant messaging connectivity, Lync Federation and XMPP Federation</span></span></p></li>
<li><p><span data-ttu-id="2285c-144">在防火牆上設定埠和通訊協定，以支援您要部署的同盟類型</span><span class="sxs-lookup"><span data-stu-id="2285c-144">Configure ports and protocols at the firewall to support the types of federation that you are deploying</span></span></p></li>
<li><p><span data-ttu-id="2285c-145">取得並安裝公用憑證。</span><span class="sxs-lookup"><span data-stu-id="2285c-145">Obtain and install public certificates.</span></span> <span data-ttu-id="2285c-146">取得憑證所需的時間取決於憑證授權單位（CA）所頒發的憑證。</span><span class="sxs-lookup"><span data-stu-id="2285c-146">The time required to obtain certificates depends on which certification authority (CA) issues the certificate.</span></span> <span data-ttu-id="2285c-147">此步驟在部署時是選用的。</span><span class="sxs-lookup"><span data-stu-id="2285c-147">This step is optional at this point in the deployment.</span></span> <span data-ttu-id="2285c-148">如果您目前不執行此步驟，您必須在邊緣伺服器設定期間進行。</span><span class="sxs-lookup"><span data-stu-id="2285c-148">If you do not perform this step at this point, you must do it during Edge Server configuration.</span></span> <span data-ttu-id="2285c-149">在取得證書前，無法啟動 Edge 伺服器服務</span><span class="sxs-lookup"><span data-stu-id="2285c-149">The Edge Server service cannot be started until certificates are obtained</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="2285c-150">視您的組織而定，因為這些角色通常會分割在許多工作群組中</span><span class="sxs-lookup"><span data-stu-id="2285c-150">As appropriate to your organization, as these roles are typically split amongst numerous work groups</span></span></p></td>
<td><p><span data-ttu-id="2285c-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">在 Lync Server 2013 中規劃 SIP、XMPP 同盟及公用立即訊息</a></span><span class="sxs-lookup"><span data-stu-id="2285c-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2285c-152">針對同盟案例設定邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="2285c-152">Set up Edge Servers for Federation Scenarios</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="2285c-153">將匯出的拓撲設定檔案傳輸到每個邊緣伺服器，或允許複製完成</span><span class="sxs-lookup"><span data-stu-id="2285c-153">Transport the exported topology configuration file to each Edge Server or allow replication to complete</span></span></p></li>
<li><p><span data-ttu-id="2285c-154">重新執行部署嚮導來安裝同盟的支援元件</span><span class="sxs-lookup"><span data-stu-id="2285c-154">Re-Run the Deployment Wizard to install supporting components for Federation</span></span></p></li>
<li><p><span data-ttu-id="2285c-155">設定邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="2285c-155">Configure the Edge Servers</span></span></p></li>
<li><p><span data-ttu-id="2285c-156">針對每個 Edge 伺服器要求並安裝證書</span><span class="sxs-lookup"><span data-stu-id="2285c-156">Request and install certificates for each Edge Server</span></span></p></li>
<li><p><span data-ttu-id="2285c-157">重新開機 Edge 伺服器服務</span><span class="sxs-lookup"><span data-stu-id="2285c-157">Restart the Edge Server services</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="2285c-158">[管理員] 群組</span><span class="sxs-lookup"><span data-stu-id="2285c-158">Administrators group</span></span></p></td>
<td><p><span data-ttu-id="2285c-159"><a href="lync-server-2013-setting-up-lync-federation.md">在 Lync Server 2013 中設定 Lync 同盟</a></span><span class="sxs-lookup"><span data-stu-id="2285c-159"><a href="lync-server-2013-setting-up-lync-federation.md">Setting up Lync federation in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="2285c-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">在 Lync Server 2013 中設定 Public Instant Messaging Connectivity</a></span><span class="sxs-lookup"><span data-stu-id="2285c-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Setting up public instant messaging connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="2285c-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">在 Lync Server 2013 中設定 XMPP 同盟</a></span><span class="sxs-lookup"><span data-stu-id="2285c-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Setting up XMPP federation in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2285c-162">設定外部使用者存取的支援。</span><span class="sxs-lookup"><span data-stu-id="2285c-162">Configure support for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="2285c-163">使用 Lync Server [控制台] 外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="2285c-163">Use the Lync Server Control Panel External User Access</span></span></p></li>
<li><p><span data-ttu-id="2285c-164">設定外部存取原則以啟用與聯盟使用者或公用使用者的通訊</span><span class="sxs-lookup"><span data-stu-id="2285c-164">Configure External Access Policy to enable Communications with federated users or public users</span></span></p></li>
<li><p><span data-ttu-id="2285c-165">將 SIP 聯盟網域設定為允許或封鎖網域</span><span class="sxs-lookup"><span data-stu-id="2285c-165">Configure SIP Federated Domains to Allow or Block domains</span></span></p></li>
<li><p><span data-ttu-id="2285c-166">針對公用立即訊息連線提供者啟用 SIP 聯盟提供者</span><span class="sxs-lookup"><span data-stu-id="2285c-166">Enable SIP Federated Providers for public instant messaging connectivity providers</span></span></p></li>
<li><p><span data-ttu-id="2285c-167">針對每個 XMPP 網域設定 XMPP 聯盟合作夥伴</span><span class="sxs-lookup"><span data-stu-id="2285c-167">Configure XMPP Federated Partners per XMPP domain</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="2285c-168">指派給 CSAdministrator 角色的 RTCUniversalServerAdmins 群組或使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="2285c-168">RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="2285c-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">在 Lync Server 2013 中設定外部使用者存取支援</a></span><span class="sxs-lookup"><span data-stu-id="2285c-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="2285c-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">在 Lync Server 2013 中設定公用提供者的媒體加密</a></span><span class="sxs-lookup"><span data-stu-id="2285c-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configure media encryption for public providers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2285c-171">驗證 Edge 伺服器設定</span><span class="sxs-lookup"><span data-stu-id="2285c-171">Verify your Edge Server configuration</span></span></p></td>
<td><p><span data-ttu-id="2285c-172">驗證服務器連線並從內部伺服器複製配置資料</span><span class="sxs-lookup"><span data-stu-id="2285c-172">Verify server connectivity and replication of configuration data from internal servers</span></span></p></td>
<td><p><span data-ttu-id="2285c-173">針對複製、RTCUniversalServerAdmins 群組或使用者帳戶指派給 CSAdministrator roleFor 驗證使用者連線性的使用者，每一種類型的聯盟使用者</span><span class="sxs-lookup"><span data-stu-id="2285c-173">For verification of replication, RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator roleFor verification of user connectivity, a user for each type of Federated user</span></span></p></td>
<td><p><span data-ttu-id="2285c-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">在 Lync Server 2013 中驗證 Edge 部署</a></span><span class="sxs-lookup"><span data-stu-id="2285c-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="2285c-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Lync Server 2013 中的範例 XMPP 設定 – XMPP 與 Google Talk 的同盟</a></span><span class="sxs-lookup"><span data-stu-id="2285c-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

