---
title: '用戶端自動登入 Lync Server 2013: DNS 需求'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e49d50173439e36bd5bb7f35f668837fe04b46b7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a><span data-ttu-id="eca76-102">DNS 需求的用戶端自動登入 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="eca76-102">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eca76-103">_**主題上次修改日期：** 2012年-06-19_</span><span class="sxs-lookup"><span data-stu-id="eca76-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="eca76-104">本主題將說明自動用戶端登入所需的網域名稱系統 (DNS) 記錄。</span><span class="sxs-lookup"><span data-stu-id="eca76-104">This section explains the Domain Name System (DNS) records that are required for automatic client sign-in.</span></span> <span data-ttu-id="eca76-105">當您部署自己的 Standard Edition Server 或前端集區時，可以設定用戶端使用自動探索功能來登入適當的 Standard Edition Server 或前端集區。</span><span class="sxs-lookup"><span data-stu-id="eca76-105">When you deploy your Standard Edition servers or Front End pools, you can configure your clients to use automatic discovery to sign in to the appropriate Standard Edition server or Front End pool.</span></span> <span data-ttu-id="eca76-106">如果您打算需要您以手動方式連線至 Lync Server 2013 的用戶端，您可以略過此主題。</span><span class="sxs-lookup"><span data-stu-id="eca76-106">If you plan to require your clients to connect manually to Lync Server 2013, you can skip this topic.</span></span>

<span data-ttu-id="eca76-107">若要支援用戶端自動登入，您必須：</span><span class="sxs-lookup"><span data-stu-id="eca76-107">To support automatic client sign-in, you must:</span></span>

  - <span data-ttu-id="eca76-p102">指定單一伺服器或集區，以分送和驗證用戶端登入要求。這可以是您組織中裝載使用者的現有伺服器或集區，或者，您也可以指定不裝載任何使用者的專用伺服器或集區做為此用途。若要達到高可用性，建議您指定前端集區來執行此功能。</span><span class="sxs-lookup"><span data-stu-id="eca76-p102">Designate a single server or pool to distribute and authenticate client sign-in requests. This can be an existing server or pool in your organization that hosts users, or you can designate a dedicated server or pool for this purpose that hosts no users. For high availability, we recommend that you designate a Front End pool for this function.</span></span>

  - <span data-ttu-id="eca76-111">建立內部 DNS SRV 記錄，以支援此伺服器或集區的自動用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="eca76-111">Create an internal DNS SRV record to support automatic client sign-in for this server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eca76-p103">下列記錄需求中，SIP 網域是指已指派給使用者的 SIP URI 的主機部分。例如，如果 SIP URI 的格式為 \*@contoso.com，則 contoso.com 為 SIP 網域。SIP 網域通常與內部 Active Directory 網域不同。組織也可以支援多個 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="eca76-p103">In the following record requirements, SIP domain refers to the host portion of the SIP URIs assigned to users. For example, if SIP URIs are of the form \*@contoso.com, contoso.com is the SIP domain. The SIP domain is often different from the internal Active Directory domain. An organization can also support multiple SIP domains.</span></span>

    
    </div>

<span data-ttu-id="eca76-116">若要啟用用戶端的自動設定，您必須建立內部 DNS SRV 記錄會將下列記錄的其中一個對應到的前端集區的完整的網域名稱 (FQDN) 或分散登入要求 Lync 的 Standard Edition server用戶端：</span><span class="sxs-lookup"><span data-stu-id="eca76-116">To enable automatic configuration for your clients, you must create an internal DNS SRV record that maps one of the following records to the fully qualified domain name (FQDN) of the Front End pool or Standard Edition server that distributes sign-in requests from Lync clients:</span></span>

  - <span data-ttu-id="eca76-117">\_sipinternaltls。\_tcp。\<網域\>-用於內部 TLS 連線</span><span class="sxs-lookup"><span data-stu-id="eca76-117">\_sipinternaltls.\_tcp.\<domain\> - for internal TLS connections</span></span>

<span data-ttu-id="eca76-118">您只需要為會分散登入要求的前端集區或 Standard Edition Server 建立單一 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="eca76-118">You only need to create a single SRV record for the Front End pool or Standard Edition server or that will distribute sign-in requests.</span></span>

<span data-ttu-id="eca76-119">下表顯示一些虛構公司 Contoso 所需的範例記錄，該公司支援 contoso.com 和 retail.contoso.com 這兩個 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="eca76-119">The following table shows some example records required for the fictitious company Contoso, which supports SIP domains of contoso.com and retail.contoso.com.</span></span>

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a><span data-ttu-id="eca76-120">針對多個 SIP 網域進行自動用戶端登入所需之 DNS 記錄的範例</span><span class="sxs-lookup"><span data-stu-id="eca76-120">Example of DNS Records Required for Automatic Client Sign-in with Multiple SIP Domains</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eca76-121">用來分送登入要求之前端集區的 FQDN</span><span class="sxs-lookup"><span data-stu-id="eca76-121">FQDN of Front End pool used to distribute sign-in requests</span></span></th>
<th><span data-ttu-id="eca76-122">SIP 網域</span><span class="sxs-lookup"><span data-stu-id="eca76-122">SIP domain</span></span></th>
<th><span data-ttu-id="eca76-123">DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="eca76-123">DNS SRV record</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eca76-124">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eca76-124">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="eca76-125">contoso.com</span><span class="sxs-lookup"><span data-stu-id="eca76-125">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="eca76-126">_sipinternaltls._tcp.contoso.com 網域 (透過連接埠 5061) 的 SRV 記錄，對應到 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eca76-126">An SRV record for _sipinternaltls._tcp.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eca76-127">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eca76-127">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="eca76-128">retail.contoso.com 這兩個</span><span class="sxs-lookup"><span data-stu-id="eca76-128">retail.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="eca76-129">_sipinternaltls._tcp.retail.contoso.com 網域 (透過連接埠 5061) 的 SRV 記錄，對應到 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eca76-129">An SRV record for _sipinternaltls._tcp.retail.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="eca76-130">根據預設，DNS 記錄的查詢符合使用者名稱中的網域與 SRV 記錄之間的嚴格網域名稱比對。</span><span class="sxs-lookup"><span data-stu-id="eca76-130">By default, queries for DNS records adhere to strict domain name matching between the domain in the user name and the SRV record.</span></span> <span data-ttu-id="eca76-131">如果您想要讓用戶端 DNS 查詢改用尾碼比對，可以設定 DisableStrictDNSNaming 群組原則。</span><span class="sxs-lookup"><span data-stu-id="eca76-131">If you prefer that client DNS queries use suffix matching instead, you can configure the DisableStrictDNSNaming Group Policy.</span></span> <span data-ttu-id="eca76-132">如需詳細資訊，請參閱規劃文件中的<A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for 用戶端和 Lync Server 2013 中的裝置</A>。</span><span class="sxs-lookup"><span data-stu-id="eca76-132">For details, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a><span data-ttu-id="eca76-133">用戶端自動登入所需之憑證和 DNS 記錄的範例</span><span class="sxs-lookup"><span data-stu-id="eca76-133">Example of the Certificates and DNS Records Required for Automatic Client Sign-In</span></span>

<span data-ttu-id="eca76-p105">此範例使用前面表格中的相同範例名稱。Contoso 組織支援 contoso.com 以及 retail.contoso.com 這兩個 SIP 網域，而且其所有的使用者都具有下列其中一種格式的 SIP URI：</span><span class="sxs-lookup"><span data-stu-id="eca76-p105">This example uses the same example names in the preceding table. The Contoso organization supports the SIP domains of contoso.com and retail.contoso.com, and all of its users have a SIP URI in one of the following forms:</span></span>

  - <span data-ttu-id="eca76-136">\<使用者\>@retail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eca76-136">\<user\>@retail.contoso.com</span></span>

  - <span data-ttu-id="eca76-137">\<使用者\>@contoso.com</span><span class="sxs-lookup"><span data-stu-id="eca76-137">\<user\>@contoso.com</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

