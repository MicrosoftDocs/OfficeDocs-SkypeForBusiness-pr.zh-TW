---
title: DNS 摘要-SIP、XMPP 同盟及公用立即訊息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c927836377a0c7c14054073a9cf17ce638662450
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="e5be0-102">DNS 摘要-Lync Server 2013 中的 SIP、XMPP 同盟及公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="e5be0-102">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5be0-103">_**主題上次修改日期：** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="e5be0-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="e5be0-104">使用 Office 通訊伺服器或 Lync Server 合作夥伴定義同盟時所需的網域名稱系統（DNS）記錄，是由您決定是否允許其他全景夥伴自動 DNS 探索您的網域。</span><span class="sxs-lookup"><span data-stu-id="e5be0-104">The Domain Name System (DNS) records that will be required for defining a federation with Office Communications Server or Lync Server partners is determined by your decision to either allow automatic DNS discovery of your domain by other perspective partners.</span></span> <span data-ttu-id="e5be0-105">如果您發佈\_sipfederationtls。\_tcp。</span><span class="sxs-lookup"><span data-stu-id="e5be0-105">If you publish the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="e5be0-106">\* \<SIP 功能變數名稱\> \*SRV 記錄，任何其他 SIP 聯盟網域將能夠「探索」您的同盟。</span><span class="sxs-lookup"><span data-stu-id="e5be0-106">*\<SIP domain name\>* SRV record, any other SIP federated domain will be able to “discover” your federation.</span></span> <span data-ttu-id="e5be0-107">您可以透過使用 lync Server [控制台] 中的 [允許網域和封鎖網域] 設定，或使用 Lync Server 管理命令介面以及 [**取得**]、[**設定**]、[**新增**]、[ **CsAllowedDomain** ] 及 [ **CsBlockedDomain** PowerShell] Cmdlet 來控制哪些聯盟網域可以與您通訊。</span><span class="sxs-lookup"><span data-stu-id="e5be0-107">You can control which federated domains can communicate with you by using the Allows domains and Blocked Domains settings in the Lync Server Control Panel, or by setting the allowed or blocked domains configuration using the Lync Server Management Shell and the **Get**, **Set**, **New**, **Remove-CsAllowedDomain** and **-CsBlockedDomain** PowerShell cmdlets.</span></span> <span data-ttu-id="e5be0-108">如需有關如何設定這些設定及如何使用 PowerShell Cmdlet 的其他資訊，請參閱本主題結尾的**相關主題**。</span><span class="sxs-lookup"><span data-stu-id="e5be0-108">For additional information on how to configure theses settings and the use of the PowerShell cmdlets, see **Related Topics** at the end of this topic.</span></span>

<span data-ttu-id="e5be0-109">[DNS 記錄] 摘要表格描述開啟或可探索的同盟聯盟所需的專案。</span><span class="sxs-lookup"><span data-stu-id="e5be0-109">The DNS records summary table depicts the required entries for an open, or discoverable, federation.</span></span> <span data-ttu-id="e5be0-110">如果您不想要實施同盟探索，您可以決定不設定\_sipfederationtls。\_tcp。</span><span class="sxs-lookup"><span data-stu-id="e5be0-110">If you do not want to implement Federation Discovery, You can decide to not configure the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="e5be0-111">\*SIP 功能變數名稱\> \< \*</span><span class="sxs-lookup"><span data-stu-id="e5be0-111">*\<SIP domain name\>* record.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="e5be0-112">在特定情況下，您必須有 _sipfederationtls _tcp。</span><span class="sxs-lookup"><span data-stu-id="e5be0-112">There are specific scenarios in which you must have the _sipfederationtls._tcp.</span></span> <span data-ttu-id="e5be0-113"><EM> &lt;SIP 功能變數名稱&gt; </EM>SRV 記錄，但您不想有可探索的同盟。</span><span class="sxs-lookup"><span data-stu-id="e5be0-113"><EM>&lt;SIP domain name&gt;</EM> SRV record, but you do not want to have a discoverable federation.</span></span> <span data-ttu-id="e5be0-114">其中一個實例就是您為使用者部署行動性的位置。</span><span class="sxs-lookup"><span data-stu-id="e5be0-114">One such instance is where you have deployed mobility for your users.</span></span> <span data-ttu-id="e5be0-115">行動推播通知 clearinghouse （PNCH）是一種特殊類型的同盟，在 Apple iPhone 或 iPad 上使用 Lync 2010 行動用戶端2010或 lync 2013 行動用戶端的 Microsoft Lync Mobile 用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="e5be0-115">The mobility push notification clearinghouse (PNCH) is a special type of federation that is used for Microsoft Lync Mobile clients on Apple iPhone or iPad using the Lync 2010 Mobile client or Windows Phone using the Lync 2010 Mobile or Lync 2013 Mobile clients.</span></span> <span data-ttu-id="e5be0-116">_Sipfederationtls. _tcp。</span><span class="sxs-lookup"><span data-stu-id="e5be0-116">The _sipfederationtls._tcp.</span></span> <span data-ttu-id="e5be0-117"><EM> &lt;SIP 功能變數名稱&gt; </EM>SRV 記錄是在行動與推播通知的情況下使用。</span><span class="sxs-lookup"><span data-stu-id="e5be0-117"><EM>&lt;SIP domain name&gt;</EM> SRV record is used in the case of mobility and push notification.</span></span> <span data-ttu-id="e5be0-118">若要緩解此問題並控制您的可搜尋性，請清除 [<STRONG>啟用合作夥伴網域探索</STRONG>的設定]，以關閉探索。</span><span class="sxs-lookup"><span data-stu-id="e5be0-118">To mitigate this issue and control your discoverability, clear the setting <STRONG>Enable partner domain discovery</STRONG> to turn off discovery.</span></span>



</div>

<span data-ttu-id="e5be0-119">若要為您的部署設定可擴展的訊息和目前狀態通訊協定（XMPP），您可以在外部 DNS 伺服器中建立兩個網域名稱系統（DNS）記錄，將記錄解析成 Edge 伺服器或 Edge 池的存取邊緣服務。</span><span class="sxs-lookup"><span data-stu-id="e5be0-119">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two domain name system (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<span data-ttu-id="e5be0-120">當您設定網域名稱系統（DNS）以取得公用立即訊息連線時，您會發現支援外部使用者的設定將支援公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="e5be0-120">When you configure domain name system (DNS) for public instant messaging connectivity, you will find that the configuration that supports external users will support public IM connectivity.</span></span> <span data-ttu-id="e5be0-121">如果您已設定 Edge 伺服器或 Edge 池，您應該擁有支援公用 IM 連線所需的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="e5be0-121">If you have already configured your Edge Server or Edge pool, you should have the DNS records necessary to support public IM connectivity.</span></span>

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a><span data-ttu-id="e5be0-122">DNS 摘要-SIP 同盟，包括公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="e5be0-122">DNS Summary - SIP Federation including Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5be0-123">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="e5be0-123">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="e5be0-124">稱</span><span class="sxs-lookup"><span data-stu-id="e5be0-124">FQDN</span></span></th>
<th><span data-ttu-id="e5be0-125">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="e5be0-125">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="e5be0-126">地圖/批註</span><span class="sxs-lookup"><span data-stu-id="e5be0-126">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5be0-127">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="e5be0-127">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="e5be0-128">_sipfederationtls. _tcp. .com</span><span class="sxs-lookup"><span data-stu-id="e5be0-128">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e5be0-129">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e5be0-129">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e5be0-130">Access Edge 服務外部介面需要將同盟自動 DNS 探索到其他潛在的同盟夥伴，且稱為「允許的 SIP 網域」（在先前的版本中稱為「增強聯盟」）。在已啟用 Lync 功能的使用者的情況中，針對所有 SIP 網域重複上述動作</span><span class="sxs-lookup"><span data-stu-id="e5be0-130">Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="e5be0-131">行動與推播通知結算所需要這個 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="e5be0-131">This SRV record is required for mobility and the push notification clearing house.</span></span> <span data-ttu-id="e5be0-132">在有多個 SIP 網域的情況下，為每一個要有 Lync 行動用戶端的網域建立併發布 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="e5be0-132">In cases where there is more than one SIP domain, create and publish an SRV record for each domain that will have Lync Mobile clients.</span></span> <span data-ttu-id="e5be0-133">如果部署支援的每個 SIP 網域沒有明確的 SRV 記錄，則推播通知服務和 Apple 推播通知服務可能無法如期運作。</span><span class="sxs-lookup"><span data-stu-id="e5be0-133">The Push Notification Service and Apple Push Notification service may not operate as expected if there is not an explicit SRV record for each SIP domain that the deployment supports.</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="e5be0-134">DNS 摘要-可擴展的訊息和目前狀態通訊協定（XMPP）</span><span class="sxs-lookup"><span data-stu-id="e5be0-134">DNS Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5be0-135">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="e5be0-135">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="e5be0-136">稱</span><span class="sxs-lookup"><span data-stu-id="e5be0-136">FQDN</span></span></th>
<th><span data-ttu-id="e5be0-137">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="e5be0-137">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="e5be0-138">地圖/批註</span><span class="sxs-lookup"><span data-stu-id="e5be0-138">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5be0-139">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="e5be0-139">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="e5be0-140">_xmpp-_tcp. .com</span><span class="sxs-lookup"><span data-stu-id="e5be0-140">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e5be0-141">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e5be0-141">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e5be0-142">XMPP [存取邊緣服務] 或 [Edge] 池中的 [proxy 外部介面]。在已啟用 Lync 功能的使用者中，針對所有內部 SIP 網域重複上述步驟，可透過全域原則、使用者所處的網站原則，或套用使用者原則來設定外部存取原則。啟用 Lync 的使用者。</span><span class="sxs-lookup"><span data-stu-id="e5be0-142">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="e5be0-143">您也必須在 XMPP 聯盟夥伴原則中設定允許的 XMPP 網域。</span><span class="sxs-lookup"><span data-stu-id="e5be0-143">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="e5be0-144">如需其他詳細資料，請參閱另<strong>請</strong>參閱中的主題</span><span class="sxs-lookup"><span data-stu-id="e5be0-144">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5be0-145">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="e5be0-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e5be0-146">xmpp.contoso.com （例如）</span><span class="sxs-lookup"><span data-stu-id="e5be0-146">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="e5be0-147">Edge 伺服器或邊緣池託管 XMPP proxy 的存取邊緣服務的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e5be0-147">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="e5be0-148">指向託管 XMPP proxy 服務的存取邊緣服務或 Edge 池。</span><span class="sxs-lookup"><span data-stu-id="e5be0-148">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="e5be0-149">通常，您所建立的 SRV 記錄會指向這個主機（A 或 AAAA）記錄</span><span class="sxs-lookup"><span data-stu-id="e5be0-149">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e5be0-150">請參閱</span><span class="sxs-lookup"><span data-stu-id="e5be0-150">See Also</span></span>


[<span data-ttu-id="e5be0-151">在 Lync Server 2013 中設定 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="e5be0-151">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="e5be0-152">在 Lync Server 2013 中設定推播通知</span><span class="sxs-lookup"><span data-stu-id="e5be0-152">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
[<span data-ttu-id="e5be0-153">在 Lync Server 2013 中啟用或停用探索同盟協力廠商</span><span class="sxs-lookup"><span data-stu-id="e5be0-153">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[<span data-ttu-id="e5be0-154">Lync Server 2013 中的外部使用者存取案例</span><span class="sxs-lookup"><span data-stu-id="e5be0-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="e5be0-155">針對 Lync Server 2013 判定 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="e5be0-155">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="e5be0-156">在 Lync Server 2013 中管理組織的 SIP 同盟網域</span><span class="sxs-lookup"><span data-stu-id="e5be0-156">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

