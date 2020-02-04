---
title: Lync Server 2013：憑證摘要-可擴展的訊息和目前狀態通訊協定（XMPP）同盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af2c226397c5225fc26f6dbdf40d12a4bdb1ca0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="d9cd1-102">認證摘要-Lync Server 2013 中的可擴展訊息和目前狀態通訊協定（XMPP）同盟</span><span class="sxs-lookup"><span data-stu-id="d9cd1-102">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9cd1-103">_**主題上次修改日期：** 2012-12-23_</span><span class="sxs-lookup"><span data-stu-id="d9cd1-103">_**Topic Last Modified:** 2012-12-23_</span></span>

<span data-ttu-id="d9cd1-104">啟用和建立使用可擴展訊息和目前狀態通訊協定（XMPP）合作夥伴的憑證需求，需要您 XMPP 網域的其他記錄。</span><span class="sxs-lookup"><span data-stu-id="d9cd1-104">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require the additional record of your XMPP domains.</span></span> <span data-ttu-id="d9cd1-105">在證書中作為消費者備用名稱（SAN）所包含的記錄，就是可參與 XMPP 通訊的網域。</span><span class="sxs-lookup"><span data-stu-id="d9cd1-105">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="d9cd1-106">網域可以是根層級網域（例如，contoso.com），如果您想要為整個網域啟用 XMPP，或可以選取子域（例如，corp.contoso.com、finance.contoso.com），如果您要為使用者的子集啟用 XMPP。</span><span class="sxs-lookup"><span data-stu-id="d9cd1-106">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="d9cd1-107">可擴展訊息和目前狀態通訊協定的憑證摘要</span><span class="sxs-lookup"><span data-stu-id="d9cd1-107">Certificate Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9cd1-108">元件</span><span class="sxs-lookup"><span data-stu-id="d9cd1-108">Component</span></span></th>
<th><span data-ttu-id="d9cd1-109">消費者名稱</span><span class="sxs-lookup"><span data-stu-id="d9cd1-109">Subject name</span></span></th>
<th><span data-ttu-id="d9cd1-110">Subject 替代名稱（SAN）/Order</span><span class="sxs-lookup"><span data-stu-id="d9cd1-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="d9cd1-111">批註</span><span class="sxs-lookup"><span data-stu-id="d9cd1-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9cd1-112">指派給 Edge 伺服器或 Edge 池的存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="d9cd1-112">Assign to Access Edge service of Edge Server or Edge pool</span></span></p></td>
<td><p><span data-ttu-id="d9cd1-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d9cd1-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d9cd1-114">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d9cd1-114">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="d9cd1-115">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d9cd1-115">sip.contoso.com</span></span></p>
<p><span data-ttu-id="d9cd1-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d9cd1-116">sip.fabrikam.com</span></span></p>
<p><span data-ttu-id="d9cd1-117">contoso.com</span><span class="sxs-lookup"><span data-stu-id="d9cd1-117">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d9cd1-118">前三個 SAN 專案是完整邊緣伺服器的一般 SAN 專案。</span><span class="sxs-lookup"><span data-stu-id="d9cd1-118">The first three SAN entries are the normal SAN entries for a full Edge Server.</span></span> <span data-ttu-id="d9cd1-119">Contoso.com 是在根網域層級與 XMPP 夥伴聯盟所需的專案。</span><span class="sxs-lookup"><span data-stu-id="d9cd1-119">The contoso.com is the entry required for federation with the XMPP partner at the root domain level.</span></span> <span data-ttu-id="d9cd1-120">此專案將允許 XMPP 所有網域的 [尾碼 contoso.com]。</span><span class="sxs-lookup"><span data-stu-id="d9cd1-120">This entry will allow XMPP for all domains with the suffix contoso.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d9cd1-121">請參閱</span><span class="sxs-lookup"><span data-stu-id="d9cd1-121">See Also</span></span>


[<span data-ttu-id="d9cd1-122">Lync Server 2013 中的範例 XMPP 設定 – XMPP 與 Google Talk 的同盟</span><span class="sxs-lookup"><span data-stu-id="d9cd1-122">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="d9cd1-123">在 Lync Server 2013 中規劃 Edge Server 憑證</span><span class="sxs-lookup"><span data-stu-id="d9cd1-123">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  


[<span data-ttu-id="d9cd1-124">針對 Lync Server 2013 設定 Edge 憑證</span><span class="sxs-lookup"><span data-stu-id="d9cd1-124">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
[<span data-ttu-id="d9cd1-125">要求-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="d9cd1-125">Request-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[<span data-ttu-id="d9cd1-126">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="d9cd1-126">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

