---
title: Lync Server 2013：自動用戶端登入的 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afd8ac315222a5582bde9802c22ab7b4911ddfe3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a><span data-ttu-id="ceb3e-102">在 Lync Server 2013 中自動用戶端登入的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="ceb3e-102">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ceb3e-103">_**主題上次修改日期：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="ceb3e-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="ceb3e-104">本節說明自動用戶端登入所需的網域名稱系統（DNS）記錄。</span><span class="sxs-lookup"><span data-stu-id="ceb3e-104">This section explains the Domain Name System (DNS) records that are required for automatic client sign-in.</span></span> <span data-ttu-id="ceb3e-105">當您部署標準版 server 或前端池時，您可以將用戶端設定為使用自動探索來登入適當的標準版 server 或前端池。</span><span class="sxs-lookup"><span data-stu-id="ceb3e-105">When you deploy your Standard Edition servers or Front End pools, you can configure your clients to use automatic discovery to sign in to the appropriate Standard Edition server or Front End pool.</span></span> <span data-ttu-id="ceb3e-106">如果您打算要求用戶端手動連線至 Lync Server 2013，您可以略過本主題。</span><span class="sxs-lookup"><span data-stu-id="ceb3e-106">If you plan to require your clients to connect manually to Lync Server 2013, you can skip this topic.</span></span>

<span data-ttu-id="ceb3e-107">若要支援自動用戶端登入，您必須：</span><span class="sxs-lookup"><span data-stu-id="ceb3e-107">To support automatic client sign-in, you must:</span></span>

  - <span data-ttu-id="ceb3e-108">指派單一伺服器或池來發佈及驗證用戶端登入要求。</span><span class="sxs-lookup"><span data-stu-id="ceb3e-108">Designate a single server or pool to distribute and authenticate client sign-in requests.</span></span> <span data-ttu-id="ceb3e-109">這可以是貴組織中託管使用者的現有伺服器或池，或者，您也可以指定專用伺服器或池來主持沒有使用者的目的。</span><span class="sxs-lookup"><span data-stu-id="ceb3e-109">This can be an existing server or pool in your organization that hosts users, or you can designate a dedicated server or pool for this purpose that hosts no users.</span></span> <span data-ttu-id="ceb3e-110">為了提供高可用性，建議您指定此函數的前端池。</span><span class="sxs-lookup"><span data-stu-id="ceb3e-110">For high availability, we recommend that you designate a Front End pool for this function.</span></span>

  - <span data-ttu-id="ceb3e-111">建立內部 DNS SRV 記錄，以支援此伺服器或池的自動用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="ceb3e-111">Create an internal DNS SRV record to support automatic client sign-in for this server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ceb3e-112">在下列記錄需求中，SIP 網域是指指派給使用者的 SIP Uri 的主機部分。</span><span class="sxs-lookup"><span data-stu-id="ceb3e-112">In the following record requirements, SIP domain refers to the host portion of the SIP URIs assigned to users.</span></span> <span data-ttu-id="ceb3e-113">例如，如果 SIP Uri 的形式是 \* @contoso .com，則 contoso.com 是 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="ceb3e-113">For example, if SIP URIs are of the form \*@contoso.com, contoso.com is the SIP domain.</span></span> <span data-ttu-id="ceb3e-114">SIP 網域通常與內部 Active Directory 網域不同。</span><span class="sxs-lookup"><span data-stu-id="ceb3e-114">The SIP domain is often different from the internal Active Directory domain.</span></span> <span data-ttu-id="ceb3e-115">組織也可以支援多個 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="ceb3e-115">An organization can also support multiple SIP domains.</span></span>

    
    </div>

<span data-ttu-id="ceb3e-116">若要為您的用戶端啟用自動設定，您必須建立內部 DNS SRV 記錄，將下列其中一個記錄對應至前端池或標準版伺服器的完整功能變數名稱（FQDN），以從 Lync 分發登入要求台</span><span class="sxs-lookup"><span data-stu-id="ceb3e-116">To enable automatic configuration for your clients, you must create an internal DNS SRV record that maps one of the following records to the fully qualified domain name (FQDN) of the Front End pool or Standard Edition server that distributes sign-in requests from Lync clients:</span></span>

  - <span data-ttu-id="ceb3e-117">\_sipinternaltls.\_tcp。\<網域\> -內部 TLS 連線</span><span class="sxs-lookup"><span data-stu-id="ceb3e-117">\_sipinternaltls.\_tcp.\<domain\> - for internal TLS connections</span></span>

<span data-ttu-id="ceb3e-118">您只需要為前端池或標準版伺服器建立單一 SRV 記錄，或將發佈登入要求。</span><span class="sxs-lookup"><span data-stu-id="ceb3e-118">You only need to create a single SRV record for the Front End pool or Standard Edition server or that will distribute sign-in requests.</span></span>

<span data-ttu-id="ceb3e-119">下表顯示虛構公司 Contoso 所需的一些範例記錄，這些案例支援 contoso.com 和 retail.contoso.com 的 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="ceb3e-119">The following table shows some example records required for the fictitious company Contoso, which supports SIP domains of contoso.com and retail.contoso.com.</span></span>

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a><span data-ttu-id="ceb3e-120">使用多個 SIP 網域自動進行用戶端登入所需的 DNS 記錄範例</span><span class="sxs-lookup"><span data-stu-id="ceb3e-120">Example of DNS Records Required for Automatic Client Sign-in with Multiple SIP Domains</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ceb3e-121">用來散佈登入要求的前端池 FQDN</span><span class="sxs-lookup"><span data-stu-id="ceb3e-121">FQDN of Front End pool used to distribute sign-in requests</span></span></th>
<th><span data-ttu-id="ceb3e-122">SIP 網域</span><span class="sxs-lookup"><span data-stu-id="ceb3e-122">SIP domain</span></span></th>
<th><span data-ttu-id="ceb3e-123">DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="ceb3e-123">DNS SRV record</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ceb3e-124">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ceb3e-124">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ceb3e-125">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ceb3e-125">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ceb3e-126">在 pool01.contoso.com 的埠5061上，_tcp contoso 網域 _sipinternaltls 的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="ceb3e-126">An SRV record for _sipinternaltls._tcp.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ceb3e-127">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ceb3e-127">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ceb3e-128">retail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ceb3e-128">retail.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ceb3e-129">在 pool01.contoso.com 的埠5061上，將 _sipinternaltls. _tcp retail 網域的 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="ceb3e-129">An SRV record for _sipinternaltls._tcp.retail.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="ceb3e-130">根據預設，DNS 記錄的查詢會在使用者名稱和 SRV 記錄中的網域之間，遵循嚴格的功能變數名稱相符。</span><span class="sxs-lookup"><span data-stu-id="ceb3e-130">By default, queries for DNS records adhere to strict domain name matching between the domain in the user name and the SRV record.</span></span> <span data-ttu-id="ceb3e-131">如果您希望用戶端 DNS 查詢改為使用尾碼相符，您可以設定 DisableStrictDNSNaming 組原則。</span><span class="sxs-lookup"><span data-stu-id="ceb3e-131">If you prefer that client DNS queries use suffix matching instead, you can configure the DisableStrictDNSNaming Group Policy.</span></span> <span data-ttu-id="ceb3e-132">如需詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013 中的用戶端和裝置規劃</A>。</span><span class="sxs-lookup"><span data-stu-id="ceb3e-132">For details, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a><span data-ttu-id="ceb3e-133">自動用戶端登入所需的憑證和 DNS 記錄範例</span><span class="sxs-lookup"><span data-stu-id="ceb3e-133">Example of the Certificates and DNS Records Required for Automatic Client Sign-In</span></span>

<span data-ttu-id="ceb3e-134">這個範例在前一個表格中使用相同的範例名稱。</span><span class="sxs-lookup"><span data-stu-id="ceb3e-134">This example uses the same example names in the preceding table.</span></span> <span data-ttu-id="ceb3e-135">Contoso 組織支援 contoso.com 和 retail.contoso.com 的 SIP 網域，且其所有使用者都有下列其中一種形式的 SIP URI：</span><span class="sxs-lookup"><span data-stu-id="ceb3e-135">The Contoso organization supports the SIP domains of contoso.com and retail.contoso.com, and all of its users have a SIP URI in one of the following forms:</span></span>

  - <span data-ttu-id="ceb3e-136">\<使用者\>@retail contoso.com</span><span class="sxs-lookup"><span data-stu-id="ceb3e-136">\<user\>@retail.contoso.com</span></span>

  - <span data-ttu-id="ceb3e-137">\<使用者\>@contoso .com</span><span class="sxs-lookup"><span data-stu-id="ceb3e-137">\<user\>@contoso.com</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

