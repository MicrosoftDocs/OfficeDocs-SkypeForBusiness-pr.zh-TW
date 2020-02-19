---
title: DNS 摘要-SIP，XMPP 同盟及 public instant messaging
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
ms.openlocfilehash: 253a00a07d1d76e77c9a753f6442151beda7c801
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="0450d-102">DNS 摘要-SIP，XMPP 同盟和公用立即訊息在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0450d-102">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0450d-103">_**主題上次修改日期：** 2017年-03-09_</span><span class="sxs-lookup"><span data-stu-id="0450d-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="0450d-104">會定義與 Office Communications Server 或 Lync Server 的協力廠商的同盟所需的網域名稱系統 (DNS) 記錄取決於您的決定，若要允許的其他觀點來看協力廠商網域的 DNS 的自動探索。</span><span class="sxs-lookup"><span data-stu-id="0450d-104">The Domain Name System (DNS) records that will be required for defining a federation with Office Communications Server or Lync Server partners is determined by your decision to either allow automatic DNS discovery of your domain by other perspective partners.</span></span> <span data-ttu-id="0450d-105">如果您將發佈\_sipfederationtls。\_tcp。</span><span class="sxs-lookup"><span data-stu-id="0450d-105">If you publish the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="0450d-106">\* \<SIP 網域名稱\>\* SRV 記錄，任何其他 SIP 同盟的網域將能夠 「 探索 」 同盟。</span><span class="sxs-lookup"><span data-stu-id="0450d-106">*\<SIP domain name\>* SRV record, any other SIP federated domain will be able to “discover” your federation.</span></span> <span data-ttu-id="0450d-107">您可以控制哪些同盟的網域可以與彼此您藉由使用允許的網域和封鎖的網域設定 Lync Server 控制台中，或設定使用 Lync Server 管理命令介面和**取得**、**設定**、**新增**、**移除 CsAllowedDomain**及**New-csblockeddomain** PowerShell cmdlet 的允許或封鎖的網域組態。</span><span class="sxs-lookup"><span data-stu-id="0450d-107">You can control which federated domains can communicate with you by using the Allows domains and Blocked Domains settings in the Lync Server Control Panel, or by setting the allowed or blocked domains configuration using the Lync Server Management Shell and the **Get**, **Set**, **New**, **Remove-CsAllowedDomain** and **-CsBlockedDomain** PowerShell cmdlets.</span></span> <span data-ttu-id="0450d-108">如需如何進行這些設定以及 PowerShell Cmdlet 的用法之詳細資訊，請參閱本主題最後的**相關主題**。</span><span class="sxs-lookup"><span data-stu-id="0450d-108">For additional information on how to configure theses settings and the use of the PowerShell cmdlets, see **Related Topics** at the end of this topic.</span></span>

<span data-ttu-id="0450d-109">DNS 記錄摘要表格會說明針對開放或可公開同盟的必要輸入。</span><span class="sxs-lookup"><span data-stu-id="0450d-109">The DNS records summary table depicts the required entries for an open, or discoverable, federation.</span></span> <span data-ttu-id="0450d-110">如果您不想要實作同盟探索，您可以決定未設定\_sipfederationtls。\_tcp。</span><span class="sxs-lookup"><span data-stu-id="0450d-110">If you do not want to implement Federation Discovery, You can decide to not configure the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="0450d-111">\* \<SIP 網域名稱\>\* 記錄。</span><span class="sxs-lookup"><span data-stu-id="0450d-111">*\<SIP domain name\>* record.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="0450d-112">有特定案例，您必須有 _sipfederationtls._tcp。</span><span class="sxs-lookup"><span data-stu-id="0450d-112">There are specific scenarios in which you must have the _sipfederationtls._tcp.</span></span> <span data-ttu-id="0450d-113"><EM> &lt;SIP 網域名稱&gt;</EM>SRV 記錄，但您不想讓探索同盟。</span><span class="sxs-lookup"><span data-stu-id="0450d-113"><EM>&lt;SIP domain name&gt;</EM> SRV record, but you do not want to have a discoverable federation.</span></span> <span data-ttu-id="0450d-114">其中一種情況是您為您的使用者部署行動性的位置。</span><span class="sxs-lookup"><span data-stu-id="0450d-114">One such instance is where you have deployed mobility for your users.</span></span> <span data-ttu-id="0450d-115">行動推播通知結算所 (PNCH) 是一種特殊類型的 Apple iPhone 或 iPad 使用 Lync 2010 Mobile 用戶端或使用 Lync 2010 Mobile 或 Lync 2013 行動用戶端的 Windows Phone 上的 Microsoft Lync 行動用戶端所用同盟。</span><span class="sxs-lookup"><span data-stu-id="0450d-115">The mobility push notification clearinghouse (PNCH) is a special type of federation that is used for Microsoft Lync Mobile clients on Apple iPhone or iPad using the Lync 2010 Mobile client or Windows Phone using the Lync 2010 Mobile or Lync 2013 Mobile clients.</span></span> <span data-ttu-id="0450d-116">_Sipfederationtls._tcp。</span><span class="sxs-lookup"><span data-stu-id="0450d-116">The _sipfederationtls._tcp.</span></span> <span data-ttu-id="0450d-117"><EM> &lt;SIP 網域名稱&gt;</EM>SRV 記錄會在行動性和推入通知的情況下使用。</span><span class="sxs-lookup"><span data-stu-id="0450d-117"><EM>&lt;SIP domain name&gt;</EM> SRV record is used in the case of mobility and push notification.</span></span> <span data-ttu-id="0450d-118">若要降低此問題，並控制您可測知性，清除 [<STRONG>啟用協力廠商網域探索</STRONG>] 以關閉 [探索] 設定。</span><span class="sxs-lookup"><span data-stu-id="0450d-118">To mitigate this issue and control your discoverability, clear the setting <STRONG>Enable partner domain discovery</STRONG> to turn off discovery.</span></span>



</div>

<span data-ttu-id="0450d-119">若要設定可延伸訊息和顯示狀態通訊協定 (XMPP) 部署，您可以建立兩個網域名稱系統 (DNS) 記錄會將記錄解析至 Edge Server 或 Edge 集區的 [Access Edge service 的外部 DNS 伺服器中。</span><span class="sxs-lookup"><span data-stu-id="0450d-119">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two domain name system (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<span data-ttu-id="0450d-120">當您設定網域名稱系統 (DNS) 的 public instant messaging 連線時，您會發現支援外部使用者的設定將支援公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="0450d-120">When you configure domain name system (DNS) for public instant messaging connectivity, you will find that the configuration that supports external users will support public IM connectivity.</span></span> <span data-ttu-id="0450d-121">如果您已設定您的 Edge Server 或 Edge 集區，您應該有支援公用 IM 連線所需的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="0450d-121">If you have already configured your Edge Server or Edge pool, you should have the DNS records necessary to support public IM connectivity.</span></span>

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a><span data-ttu-id="0450d-122">DNS 摘要-SIP 同盟包括 Public Instant Messaging 連線</span><span class="sxs-lookup"><span data-stu-id="0450d-122">DNS Summary - SIP Federation including Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0450d-123">位置/類型/連接埠</span><span class="sxs-lookup"><span data-stu-id="0450d-123">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="0450d-124">FQDN</span><span class="sxs-lookup"><span data-stu-id="0450d-124">FQDN</span></span></th>
<th><span data-ttu-id="0450d-125">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="0450d-125">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="0450d-126">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="0450d-126">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0450d-127">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="0450d-127">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="0450d-128">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0450d-128">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0450d-129">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0450d-129">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0450d-130">Access Edge service 的外部介面所需的 DNS 自動探索其他潛在同盟協力廠商同盟，就所謂的 「 允許的 SIP 網域 」 （先前版本稱為增強型的同盟）。啟用 Lync 之使用者的所有 SIP 網域，依需要重複執行</span><span class="sxs-lookup"><span data-stu-id="0450d-130">Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="0450d-131">行動性和推播通知結算所都必須使用此 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="0450d-131">This SRV record is required for mobility and the push notification clearing house.</span></span> <span data-ttu-id="0450d-132">在情況下是多個 SIP 網域，建立及發佈會有 Lync 行動用戶端的每個網域的 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="0450d-132">In cases where there is more than one SIP domain, create and publish an SRV record for each domain that will have Lync Mobile clients.</span></span> <span data-ttu-id="0450d-133">推入通知服務和 Apple 推播通知服務可能無法運作如預期般是否有不部署支援的每個 SIP 網域的明確 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="0450d-133">The Push Notification Service and Apple Push Notification service may not operate as expected if there is not an explicit SRV record for each SIP domain that the deployment supports.</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="0450d-134">DNS 摘要-Extensible Messaging and Presence Protocol (XMPP)</span><span class="sxs-lookup"><span data-stu-id="0450d-134">DNS Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0450d-135">位置/類型/連接埠</span><span class="sxs-lookup"><span data-stu-id="0450d-135">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="0450d-136">FQDN</span><span class="sxs-lookup"><span data-stu-id="0450d-136">FQDN</span></span></th>
<th><span data-ttu-id="0450d-137">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="0450d-137">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="0450d-138">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="0450d-138">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0450d-139">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="0450d-139">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="0450d-140">_xmpp server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0450d-140">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0450d-141">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0450d-141">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0450d-142">XMPP proxy 外部介面的 Access Edge 服務或 Edge 集區。視您的 Lync 所有內部 SIP 網域重複啟用與 XMPP 連絡人的連絡人允許透過全域原則、 使用者所在的網站原則或使用者原則套用到的外部存取原則設定的位置的使用者啟用 Lync 功能的使用者。</span><span class="sxs-lookup"><span data-stu-id="0450d-142">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="0450d-143">允許的 XMPP 網域也必須設定 XMPP 同盟協力廠商原則中。</span><span class="sxs-lookup"><span data-stu-id="0450d-143">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="0450d-144">請參閱如需詳細資訊<strong>請參閱</strong>主題</span><span class="sxs-lookup"><span data-stu-id="0450d-144">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0450d-145">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="0450d-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0450d-146">xmpp.contoso.com (範例)</span><span class="sxs-lookup"><span data-stu-id="0450d-146">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="0450d-147">IP 位址的 Access Edge service 上您的 Edge Server 或 Edge 集區裝載 XMPP proxy</span><span class="sxs-lookup"><span data-stu-id="0450d-147">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="0450d-148">指向 Access Edge service 或裝載 XMPP proxy 服務的 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="0450d-148">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="0450d-149">一般而言，您建立的 SRV 記錄會指向此主機 (A 或 AAAA) 記錄</span><span class="sxs-lookup"><span data-stu-id="0450d-149">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0450d-150">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0450d-150">See Also</span></span>


[<span data-ttu-id="0450d-151">設定 Lync Server 2013 中的 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="0450d-151">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="0450d-152">設定 Lync Server 2013 中的推入通知</span><span class="sxs-lookup"><span data-stu-id="0450d-152">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
[<span data-ttu-id="0450d-153">啟用或停用 Lync Server 2013 中的同盟協力廠商的探索</span><span class="sxs-lookup"><span data-stu-id="0450d-153">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[<span data-ttu-id="0450d-154">Lync Server 2013 中的外部使用者存取的案例</span><span class="sxs-lookup"><span data-stu-id="0450d-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="0450d-155">決定針對 Lync Server 2013 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="0450d-155">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="0450d-156">管理 Lync Server 2013 中組織的 SIP 同盟網域</span><span class="sxs-lookup"><span data-stu-id="0450d-156">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

