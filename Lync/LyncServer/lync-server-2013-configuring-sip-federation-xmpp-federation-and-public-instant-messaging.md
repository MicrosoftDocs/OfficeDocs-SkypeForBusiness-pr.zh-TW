---
title: 設定 SIP 同盟、XMPP 同盟及公用立即訊息
description: 設定 SIP 同盟、XMPP 同盟及公用立即訊息。
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
ms.openlocfilehash: 7b83c29da75c99e7a338bfd7732aec8ec49cbf47
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556959"
---
# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="c1eff-103">在 Lync Server 2013 中設定 SIP 同盟、XMPP 同盟及公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="c1eff-103">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1eff-104">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="c1eff-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="c1eff-105">同盟、公用立即訊息連線及可延伸的訊息和顯示狀態通訊協定 (XMPP) 定義不同類別的外部使用者–同盟使用者。</span><span class="sxs-lookup"><span data-stu-id="c1eff-105">Federation, public instant messaging connectivity and Extensible Messaging and Presence Protocol (XMPP) define a different class of external users – Federated users.</span></span> <span data-ttu-id="c1eff-106">同盟 Lync Server 部署或 XMPP 部署的使用者可以存取有限的一組服務，而且會透過外部部署進行驗證。</span><span class="sxs-lookup"><span data-stu-id="c1eff-106">Users of a federated Lync Server deployment or XMPP deployment have access to a limited set of services and are authenticated by the external deployment.</span></span> <span data-ttu-id="c1eff-107">遠端使用者是 Lync Server 部署的成員，而且可以存取部署所提供的所有服務。</span><span class="sxs-lookup"><span data-stu-id="c1eff-107">Remote users are members of your Lync Server deployment and have access to all services offered by your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="c1eff-108">AOL 和 Yahoo！的循環結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="c1eff-108">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="c1eff-109">已宣告。</span><span class="sxs-lookup"><span data-stu-id="c1eff-109">has been announced.</span></span> <span data-ttu-id="c1eff-110">如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</span><span class="sxs-lookup"><span data-stu-id="c1eff-110">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="c1eff-111">公用立即訊息連線是一種特殊的同盟類型，可讓 Lync Server 用戶端使用 Lync 2013 存取已設定的公用立即訊息夥伴。</span><span class="sxs-lookup"><span data-stu-id="c1eff-111">Public instant messaging connectivity is a special type of federation that allows a Lync Server client to access configured public Instant Messaging partners using the Lync 2013.</span></span> <span data-ttu-id="c1eff-112">目前的公用立即訊息連線夥伴為：</span><span class="sxs-lookup"><span data-stu-id="c1eff-112">The current public instant messaging connectivity partners are:</span></span>

  - <span></span>  
    <span data-ttu-id="c1eff-113">America Online</span><span class="sxs-lookup"><span data-stu-id="c1eff-113">America Online</span></span>

  - <span></span>  
    <span data-ttu-id="c1eff-114">Windows Live</span><span class="sxs-lookup"><span data-stu-id="c1eff-114">Windows Live</span></span>

  - <span></span>  
    <span data-ttu-id="c1eff-115">雅虎\!</span><span class="sxs-lookup"><span data-stu-id="c1eff-115">Yahoo\!</span></span>

<span data-ttu-id="c1eff-116">公用立即訊息連線設定可讓 Lync 使用者透過下列方式存取公用立即訊息連線使用者：</span><span class="sxs-lookup"><span data-stu-id="c1eff-116">A public instant messaging connectivity configuration allows Lync users access to public instant messaging connectivity users by:</span></span>

  - <span data-ttu-id="c1eff-117">IM 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="c1eff-117">IM and Presence</span></span>

  - <span data-ttu-id="c1eff-118">Lync 用戶端中公用立即訊息線上連絡人的可見度</span><span class="sxs-lookup"><span data-stu-id="c1eff-118">Visibility of public instant messaging connectivity contacts in Lync client</span></span>

  - <span data-ttu-id="c1eff-119">與連絡人進行 IM 交談的人員</span><span class="sxs-lookup"><span data-stu-id="c1eff-119">Person to person IM conversations with contacts</span></span>

  - <span data-ttu-id="c1eff-120">使用 Windows Live 使用者的音訊和影片通話</span><span class="sxs-lookup"><span data-stu-id="c1eff-120">Audio and video calls with Windows Live users</span></span>

<span data-ttu-id="c1eff-121">Lync Server 同盟定義 Lync Server 部署與其他 Office 通訊伺服器 2007 R2 或 Lync Server 部署之間的合約。</span><span class="sxs-lookup"><span data-stu-id="c1eff-121">Lync Server federation defines an agreement between your Lync Server deployment and other Office Communications Server 2007 R2 or Lync Server deployments.</span></span> <span data-ttu-id="c1eff-122">Lync Server 同盟設定可讓 Lync 使用者透過下列方式存取同盟使用者：</span><span class="sxs-lookup"><span data-stu-id="c1eff-122">A Lync Server federated configuration allows Lync users access to federated users by:</span></span>

  - <span data-ttu-id="c1eff-123">IM 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="c1eff-123">IM and Presence</span></span>

  - <span data-ttu-id="c1eff-124">在 Lync 用戶端中建立同盟連絡人</span><span class="sxs-lookup"><span data-stu-id="c1eff-124">Creation of federated contacts in the Lync client</span></span>

<span data-ttu-id="c1eff-125">XMPP 同盟會根據可延伸的訊息和顯示狀態通訊協定，定義外部部署。</span><span class="sxs-lookup"><span data-stu-id="c1eff-125">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol.</span></span> <span data-ttu-id="c1eff-126">XMPP 設定可讓 Lync 使用者依下列方式存取允許的 XMPP 網域使用者：</span><span class="sxs-lookup"><span data-stu-id="c1eff-126">An XMPP configuration allows Lync users access to allowed XMPP domain users by:</span></span>

  - <span data-ttu-id="c1eff-127">IM 和目前狀態–僅限人員</span><span class="sxs-lookup"><span data-stu-id="c1eff-127">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="c1eff-128">在 Lync 用戶端中建立 XMPP 同盟連絡人</span><span class="sxs-lookup"><span data-stu-id="c1eff-128">Creation of XMPP federated contacts in the Lync client</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="c1eff-129">Lync Server 2013 的 XMPP 功能會經過測試，並受 Microsoft 支援，以進行與 Google 交談的立即訊息同盟。</span><span class="sxs-lookup"><span data-stu-id="c1eff-129">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="c1eff-130">對於任何其他 XMPP 系統，請聯繫協力廠商廠商，以確認其支援與 Lync Server 2013 的同盟，以及任何部署或疑難排解建議。</span><span class="sxs-lookup"><span data-stu-id="c1eff-130">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a><span data-ttu-id="c1eff-131">Edge Server 外部同盟、公用立即訊息連線和 XMPP 使用者部署程式</span><span class="sxs-lookup"><span data-stu-id="c1eff-131">Edge Server External Federation, Public Instant Messaging Connectivity and XMPP Users Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c1eff-132">階段</span><span class="sxs-lookup"><span data-stu-id="c1eff-132">Phase</span></span></th>
<th><span data-ttu-id="c1eff-133">步驟</span><span class="sxs-lookup"><span data-stu-id="c1eff-133">Steps</span></span></th>
<th><span data-ttu-id="c1eff-134">權限</span><span class="sxs-lookup"><span data-stu-id="c1eff-134">Permissions</span></span></th>
<th><span data-ttu-id="c1eff-135">文件</span><span class="sxs-lookup"><span data-stu-id="c1eff-135">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c1eff-136">決定要新增至現有 Edge 部署的選項</span><span class="sxs-lookup"><span data-stu-id="c1eff-136">Determine the options to add to the existing Edge deployment</span></span></p></td>
<td><p><span data-ttu-id="c1eff-137">執行拓撲產生器以編輯 Edge Server 設定，以及建立及發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="c1eff-137">Run Topology Builder to edit Edge Server settings and create and publish the topology.</span></span> <span data-ttu-id="c1eff-138">您的現有 Edge 拓撲會將中央管理存放區的變更複寫至 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="c1eff-138">Your existing Edge topology will replicate changes from the Central Management store to the Edge Server.</span></span></p></td>
<td><p><span data-ttu-id="c1eff-139">Domain Admins 群組和 RTCUniversalServerAdmins 群組</span><span class="sxs-lookup"><span data-stu-id="c1eff-139">Domain Admins group and RTCUniversalServerAdmins group</span></span></p>



> [!NOTE]
> <span data-ttu-id="c1eff-140">您可以使用本機使用者群組的成員帳戶來編輯拓撲，但發行拓撲需要的帳戶是 Domain Admins 群組和 RTCUniversalServerAdmins 群組的成員帳戶。</span><span class="sxs-lookup"><span data-stu-id="c1eff-140">You can edit a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group</span></span>

</td>
<td><p><span data-ttu-id="c1eff-141"><a href="lync-server-2013-building-an-edge-and-director-topology.md">在 Lync Server 2013 中建立 edge 和 Director 拓撲</a></span><span class="sxs-lookup"><span data-stu-id="c1eff-141"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1eff-142">準備安裝</span><span class="sxs-lookup"><span data-stu-id="c1eff-142">Prepare for setup</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="c1eff-143">確定已符合系統先決條件。</span><span class="sxs-lookup"><span data-stu-id="c1eff-143">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="c1eff-144">設定內部和外部 DNS 記錄，以支援公用立即訊息連線、Lync 同盟及 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="c1eff-144">Configure internal and external DNS records, to support public instant messaging connectivity, Lync Federation and XMPP Federation</span></span></p></li>
<li><p><span data-ttu-id="c1eff-145">在防火牆上設定埠和通訊協定，以支援您要部署的同盟類型</span><span class="sxs-lookup"><span data-stu-id="c1eff-145">Configure ports and protocols at the firewall to support the types of federation that you are deploying</span></span></p></li>
<li><p><span data-ttu-id="c1eff-146">取得及安裝公用憑證。</span><span class="sxs-lookup"><span data-stu-id="c1eff-146">Obtain and install public certificates.</span></span> <span data-ttu-id="c1eff-147">取得憑證所需的時間，視發出憑證的憑證授權單位 (CA) 而定。</span><span class="sxs-lookup"><span data-stu-id="c1eff-147">The time required to obtain certificates depends on which certification authority (CA) issues the certificate.</span></span> <span data-ttu-id="c1eff-148">在部署中這一點是選用的步驟。</span><span class="sxs-lookup"><span data-stu-id="c1eff-148">This step is optional at this point in the deployment.</span></span> <span data-ttu-id="c1eff-149">如果您此時不執行此步驟，則必須在 Edge Server 設定期間執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="c1eff-149">If you do not perform this step at this point, you must do it during Edge Server configuration.</span></span> <span data-ttu-id="c1eff-150">在取得憑證之前，無法啟動 Edge Server 服務</span><span class="sxs-lookup"><span data-stu-id="c1eff-150">The Edge Server service cannot be started until certificates are obtained</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="c1eff-151">視您的組織而定，因為這些角色通常會分割許多工作群組</span><span class="sxs-lookup"><span data-stu-id="c1eff-151">As appropriate to your organization, as these roles are typically split amongst numerous work groups</span></span></p></td>
<td><p><span data-ttu-id="c1eff-152"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">在 Lync Server 2013 中規劃 SIP、XMPP 同盟和公用立即訊息</a></span><span class="sxs-lookup"><span data-stu-id="c1eff-152"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1eff-153">設定同盟案例的 Edge Server</span><span class="sxs-lookup"><span data-stu-id="c1eff-153">Set up Edge Servers for Federation Scenarios</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="c1eff-154">將匯出的拓撲配置檔案傳輸至每一部 Edge Server，或允許複製完成</span><span class="sxs-lookup"><span data-stu-id="c1eff-154">Transport the exported topology configuration file to each Edge Server or allow replication to complete</span></span></p></li>
<li><p><span data-ttu-id="c1eff-155">Re-Run 部署嚮導，以安裝同盟的支援元件</span><span class="sxs-lookup"><span data-stu-id="c1eff-155">Re-Run the Deployment Wizard to install supporting components for Federation</span></span></p></li>
<li><p><span data-ttu-id="c1eff-156">設定 Edge Server</span><span class="sxs-lookup"><span data-stu-id="c1eff-156">Configure the Edge Servers</span></span></p></li>
<li><p><span data-ttu-id="c1eff-157">針對每一部 Edge Server 要求並安裝憑證</span><span class="sxs-lookup"><span data-stu-id="c1eff-157">Request and install certificates for each Edge Server</span></span></p></li>
<li><p><span data-ttu-id="c1eff-158">重新開機 Edge Server 服務</span><span class="sxs-lookup"><span data-stu-id="c1eff-158">Restart the Edge Server services</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="c1eff-159">Administrators 群組</span><span class="sxs-lookup"><span data-stu-id="c1eff-159">Administrators group</span></span></p></td>
<td><p><span data-ttu-id="c1eff-160"><a href="lync-server-2013-setting-up-lync-federation.md">在 Lync Server 2013 中設定 Lync 同盟</a></span><span class="sxs-lookup"><span data-stu-id="c1eff-160"><a href="lync-server-2013-setting-up-lync-federation.md">Setting up Lync federation in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="c1eff-161"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">在 Lync Server 2013 中設定公用立即訊息連線</a></span><span class="sxs-lookup"><span data-stu-id="c1eff-161"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Setting up public instant messaging connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="c1eff-162"><a href="lync-server-2013-setting-up-xmpp-federation.md">在 Lync Server 2013 中設定 XMPP 同盟</a></span><span class="sxs-lookup"><span data-stu-id="c1eff-162"><a href="lync-server-2013-setting-up-xmpp-federation.md">Setting up XMPP federation in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1eff-163">設定外部使用者存取的支援。</span><span class="sxs-lookup"><span data-stu-id="c1eff-163">Configure support for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="c1eff-164">使用 Lync Server 控制台外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="c1eff-164">Use the Lync Server Control Panel External User Access</span></span></p></li>
<li><p><span data-ttu-id="c1eff-165">設定外部存取原則以啟用與同盟使用者或公用使用者的通訊</span><span class="sxs-lookup"><span data-stu-id="c1eff-165">Configure External Access Policy to enable Communications with federated users or public users</span></span></p></li>
<li><p><span data-ttu-id="c1eff-166">設定 SIP 同盟網域以允許或封鎖網域</span><span class="sxs-lookup"><span data-stu-id="c1eff-166">Configure SIP Federated Domains to Allow or Block domains</span></span></p></li>
<li><p><span data-ttu-id="c1eff-167">啟用公用立即訊息連線提供者的 SIP 同盟提供者</span><span class="sxs-lookup"><span data-stu-id="c1eff-167">Enable SIP Federated Providers for public instant messaging connectivity providers</span></span></p></li>
<li><p><span data-ttu-id="c1eff-168">設定每個 XMPP 網域的 XMPP 同盟協力廠商</span><span class="sxs-lookup"><span data-stu-id="c1eff-168">Configure XMPP Federated Partners per XMPP domain</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="c1eff-169">指派給 CSAdministrator 角色的 RTCUniversalServerAdmins 群組或使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="c1eff-169">RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="c1eff-170"><a href="lync-server-2013-configuring-support-for-external-user-access.md">在 Lync Server 2013 中設定外部使用者存取的支援</a></span><span class="sxs-lookup"><span data-stu-id="c1eff-170"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="c1eff-171"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">在 Lync Server 2013 中設定公用提供者的媒體加密</a></span><span class="sxs-lookup"><span data-stu-id="c1eff-171"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configure media encryption for public providers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1eff-172">驗證 Edge Server 設定</span><span class="sxs-lookup"><span data-stu-id="c1eff-172">Verify your Edge Server configuration</span></span></p></td>
<td><p><span data-ttu-id="c1eff-173">驗證服務器連線以及內部伺服器的設定資料複寫</span><span class="sxs-lookup"><span data-stu-id="c1eff-173">Verify server connectivity and replication of configuration data from internal servers</span></span></p></td>
<td><p><span data-ttu-id="c1eff-174">若要驗證複寫，請 RTCUniversalServerAdmins 群組或使用者帳戶指派給使用者連線的 CSAdministrator roleFor 驗證，每種類型的同盟使用者的使用者</span><span class="sxs-lookup"><span data-stu-id="c1eff-174">For verification of replication, RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator roleFor verification of user connectivity, a user for each type of Federated user</span></span></p></td>
<td><p><span data-ttu-id="c1eff-175"><a href="lync-server-2013-verifying-your-edge-deployment.md">在 Lync Server 2013 中驗證 edge 部署</a></span><span class="sxs-lookup"><span data-stu-id="c1eff-175"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="c1eff-176"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Lync Server 2013 的範例 XMPP 設定– XMPP 與 Google 交談的同盟</a></span><span class="sxs-lookup"><span data-stu-id="c1eff-176"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

