---
title: DNS 摘要-SIP、XMPP 同盟和公用立即訊息
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
ms.openlocfilehash: c8c7b36448f2aa8eb895aebeeaddc6187c1831ca
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501190"
---
# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="b4a7f-102">Lync Server 2013 中的 DNS 摘要-SIP、XMPP 同盟和公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="b4a7f-102">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4a7f-103">_**主題上次修改日期：** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="b4a7f-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="b4a7f-104">網域名稱系統 (DNS) 使用 Office 通訊伺服器或 Lync Server 合作夥伴定義同盟所需的記錄，是由您決定是否允許其他全景夥伴對您的網域進行自動 DNS 探索。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-104">The Domain Name System (DNS) records that will be required for defining a federation with Office Communications Server or Lync Server partners is determined by your decision to either allow automatic DNS discovery of your domain by other perspective partners.</span></span> <span data-ttu-id="b4a7f-105">如果您發佈的是 \_ sipfederationtls。 \_Tcp。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-105">If you publish the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="b4a7f-106">*\<SIP domain name\>* SRV 記錄，任何其他 SIP 同盟網域都可以「探索」同盟。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-106">*\<SIP domain name\>* SRV record, any other SIP federated domain will be able to “discover” your federation.</span></span> <span data-ttu-id="b4a7f-107">您可以使用 Lync server [控制台] 中的 [允許網域與封鎖的網域] 設定，或是使用 Lync Server 管理命令介面和 **Get**、 **Set**、 **New**、 **Remove-CsAllowedDomain** 及 **-CsBlockedDomain** PowerShell Cmdlet 來設定允許或封鎖的網域設定，控制哪些同盟網域可以與您通訊。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-107">You can control which federated domains can communicate with you by using the Allows domains and Blocked Domains settings in the Lync Server Control Panel, or by setting the allowed or blocked domains configuration using the Lync Server Management Shell and the **Get**, **Set**, **New**, **Remove-CsAllowedDomain** and **-CsBlockedDomain** PowerShell cmdlets.</span></span> <span data-ttu-id="b4a7f-108">如需如何進行這些設定以及 PowerShell Cmdlet 的用法之詳細資訊，請參閱本主題最後的**相關主題**。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-108">For additional information on how to configure theses settings and the use of the PowerShell cmdlets, see **Related Topics** at the end of this topic.</span></span>

<span data-ttu-id="b4a7f-109">DNS 記錄摘要表格會說明針對開放或可公開同盟的必要輸入。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-109">The DNS records summary table depicts the required entries for an open, or discoverable, federation.</span></span> <span data-ttu-id="b4a7f-110">如果您不想要實施同盟探索，您可以決定不設定 \_ sipfederationtls。 \_Tcp。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-110">If you do not want to implement Federation Discovery, You can decide to not configure the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="b4a7f-111">*\<SIP domain name\>* 記錄。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-111">*\<SIP domain name\>* record.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="b4a7f-112">您必須具有 _sipfederationtls _tcp 的特定案例。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-112">There are specific scenarios in which you must have the _sipfederationtls._tcp.</span></span> <span data-ttu-id="b4a7f-113"><EM> &lt; SIP 功能變數名稱 &gt; </EM> SRV 記錄，但您不想要有可調查的同盟。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-113"><EM>&lt;SIP domain name&gt;</EM> SRV record, but you do not want to have a discoverable federation.</span></span> <span data-ttu-id="b4a7f-114">其中一個實例是您為使用者部署行動性的位置。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-114">One such instance is where you have deployed mobility for your users.</span></span> <span data-ttu-id="b4a7f-115">行動推播通知 clearinghouse (PNCH) 是一種特殊類型的同盟，可供 Apple iPhone 或 iPad 上的 Microsoft Lync Mobile 用戶端使用 lync 2010 行動裝置或 Lync 2013 行動用戶端使用 Lync 2010 Mobile client 或 Windows Phone。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-115">The mobility push notification clearinghouse (PNCH) is a special type of federation that is used for Microsoft Lync Mobile clients on Apple iPhone or iPad using the Lync 2010 Mobile client or Windows Phone using the Lync 2010 Mobile or Lync 2013 Mobile clients.</span></span> <span data-ttu-id="b4a7f-116">_Sipfederationtls _tcp。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-116">The _sipfederationtls._tcp.</span></span> <span data-ttu-id="b4a7f-117"><EM> &lt; SIP 功能變數名稱 &gt; </EM> SRV 記錄是用於行動及推播通知的情況。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-117"><EM>&lt;SIP domain name&gt;</EM> SRV record is used in the case of mobility and push notification.</span></span> <span data-ttu-id="b4a7f-118">若要緩解此問題並控制您的可搜尋性，請清除設定 [ <STRONG>啟用夥伴網域探索</STRONG> ] 以關閉探索。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-118">To mitigate this issue and control your discoverability, clear the setting <STRONG>Enable partner domain discovery</STRONG> to turn off discovery.</span></span>



</div>

<span data-ttu-id="b4a7f-119">若要為您的部署設定可延伸的訊息和顯示狀態通訊協定 (XMPP) ，您可以在外部 DNS 伺服器中建立兩個網域名稱系統 (DNS) 記錄，以將記錄解析為 Edge Server 或 Edge 集區的 Access Edge service。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-119">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two domain name system (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<span data-ttu-id="b4a7f-120">當您設定網域名稱系統 (用於公用立即訊息連線的 DNS) 時，您會發現支援外部使用者的設定將支援公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-120">When you configure domain name system (DNS) for public instant messaging connectivity, you will find that the configuration that supports external users will support public IM connectivity.</span></span> <span data-ttu-id="b4a7f-121">如果您已設定 Edge Server 或 Edge 集區，則應具備支援公用 IM 連線所需的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-121">If you have already configured your Edge Server or Edge pool, you should have the DNS records necessary to support public IM connectivity.</span></span>

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a><span data-ttu-id="b4a7f-122">DNS 摘要-SIP 同盟（包括公用立即訊息連線）</span><span class="sxs-lookup"><span data-stu-id="b4a7f-122">DNS Summary - SIP Federation including Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4a7f-123">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="b4a7f-123">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="b4a7f-124">FQDN</span><span class="sxs-lookup"><span data-stu-id="b4a7f-124">FQDN</span></span></th>
<th><span data-ttu-id="b4a7f-125">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="b4a7f-125">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="b4a7f-126">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="b4a7f-126">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4a7f-127">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="b4a7f-127">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="b4a7f-128">_sipfederationtls _sipfederationtls._tcp .com</span><span class="sxs-lookup"><span data-stu-id="b4a7f-128">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b4a7f-129">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b4a7f-129">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b4a7f-130">Access Edge service 外部介面，可自動將同盟的 DNS 探索至其他潛在同盟協力廠商，也稱為「允許的 SIP 網域」 (在舊版版本) 中稱為「增強型同盟」。視需要針對具有啟用 Lync 功能之使用者的所有 SIP 網域重複</span><span class="sxs-lookup"><span data-stu-id="b4a7f-130">Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="b4a7f-131">行動性和推播通知結算所都必須使用此 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-131">This SRV record is required for mobility and the push notification clearing house.</span></span> <span data-ttu-id="b4a7f-132">在有多個 SIP 網域的情況下，為每一個要具有 Lync 行動用戶端的網域建立併發布 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-132">In cases where there is more than one SIP domain, create and publish an SRV record for each domain that will have Lync Mobile clients.</span></span> <span data-ttu-id="b4a7f-133">如果部署所支援的每個 SIP 網域沒有明確的 SRV 記錄，推播通知服務和 Apple Push Notification 服務可能無法如預期的方式運作。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-133">The Push Notification Service and Apple Push Notification service may not operate as expected if there is not an explicit SRV record for each SIP domain that the deployment supports.</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="b4a7f-134">DNS 摘要-可延伸的訊息和顯示狀態通訊協定 (XMPP) </span><span class="sxs-lookup"><span data-stu-id="b4a7f-134">DNS Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4a7f-135">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="b4a7f-135">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="b4a7f-136">FQDN</span><span class="sxs-lookup"><span data-stu-id="b4a7f-136">FQDN</span></span></th>
<th><span data-ttu-id="b4a7f-137">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="b4a7f-137">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="b4a7f-138">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="b4a7f-138">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4a7f-139">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="b4a7f-139">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="b4a7f-140">_xmpp-server._tcp .com</span><span class="sxs-lookup"><span data-stu-id="b4a7f-140">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b4a7f-141">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b4a7f-141">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b4a7f-142">Access Edge service 或 Edge 集區上的 XMPP proxy 外部介面。針對所有內部 SIP 網域，針對所有內部 SIP 網域，依需要重複此步驟：透過全域原則、使用者所在的網站原則，或套用到啟用 Lync 功能之使用者的使用者原則，可透過外部存取原則的設定允許與 XMPP 聯繫。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-142">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="b4a7f-143">您也必須在 XMPP 同盟協力廠商原則中設定允許的 XMPP 網域。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-143">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="b4a7f-144">如需其他詳細資料，請參閱另 <strong>請</strong> 參閱主題</span><span class="sxs-lookup"><span data-stu-id="b4a7f-144">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4a7f-145">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="b4a7f-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b4a7f-146">xmpp.contoso.com (範例)</span><span class="sxs-lookup"><span data-stu-id="b4a7f-146">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="b4a7f-147">Edge Server 或 Edge 集區上主控 XMPP proxy 的 Access Edge service 的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="b4a7f-147">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="b4a7f-148">指向主控 XMPP proxy 服務的 Access Edge service 或 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="b4a7f-148">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="b4a7f-149">一般而言，您建立的 SRV 記錄會指向此主機 (A 或 AAAA) 記錄</span><span class="sxs-lookup"><span data-stu-id="b4a7f-149">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b4a7f-150">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b4a7f-150">See Also</span></span>


[<span data-ttu-id="b4a7f-151">在 Lync Server 2013 中設定 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="b4a7f-151">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="b4a7f-152">在 Lync Server 2013 中設定推播通知</span><span class="sxs-lookup"><span data-stu-id="b4a7f-152">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
[<span data-ttu-id="b4a7f-153">在 Lync Server 2013 中啟用或停用同盟協力廠商的探索</span><span class="sxs-lookup"><span data-stu-id="b4a7f-153">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[<span data-ttu-id="b4a7f-154">Lync Server 2013 中的外部使用者存取案例</span><span class="sxs-lookup"><span data-stu-id="b4a7f-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="b4a7f-155">決定 Lync Server 2013 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="b4a7f-155">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="b4a7f-156">在 Lync Server 2013 中管理組織的 SIP 同盟網域</span><span class="sxs-lookup"><span data-stu-id="b4a7f-156">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

