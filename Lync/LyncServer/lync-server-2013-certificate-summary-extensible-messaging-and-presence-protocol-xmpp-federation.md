---
title: Lync Server 2013：憑證摘要-可延伸的訊息和顯示狀態通訊協定 (XMPP) 同盟
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
ms.openlocfilehash: f2dd5f09f9abbfb1e01935552238d966b5060d9a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520638"
---
# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="288ae-102">憑證摘要-可延伸的訊息和顯示狀態通訊協定 (XMPP) 同盟 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="288ae-102">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="288ae-103">_**主題上次修改日期：** 2012-12-23_</span><span class="sxs-lookup"><span data-stu-id="288ae-103">_**Topic Last Modified:** 2012-12-23_</span></span>

<span data-ttu-id="288ae-104">使用可延伸訊息和顯示狀態通訊協定來啟用及建立通訊的憑證需求 (XMPP) 合作夥伴需要 XMPP 網域的其他記錄。</span><span class="sxs-lookup"><span data-stu-id="288ae-104">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require the additional record of your XMPP domains.</span></span> <span data-ttu-id="288ae-105"> (SAN) 中包含在憑證上的記錄，都是可參與 XMPP 通訊的網域。</span><span class="sxs-lookup"><span data-stu-id="288ae-105">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="288ae-106">網域可以是根層級網域 (例如) ，如果您想要對整個網域啟用 XMPP，或可以選取子域 (例如，corp.contoso.com、finance.contoso.com) （如果您為使用者的子集啟用 XMPP）。</span><span class="sxs-lookup"><span data-stu-id="288ae-106">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="288ae-107">可延伸訊息和顯示狀態通訊協定的憑證摘要</span><span class="sxs-lookup"><span data-stu-id="288ae-107">Certificate Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="288ae-108">元件</span><span class="sxs-lookup"><span data-stu-id="288ae-108">Component</span></span></th>
<th><span data-ttu-id="288ae-109">主體名稱</span><span class="sxs-lookup"><span data-stu-id="288ae-109">Subject name</span></span></th>
<th><span data-ttu-id="288ae-110">主體替代名稱 (SAN)/順序</span><span class="sxs-lookup"><span data-stu-id="288ae-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="288ae-111">註解</span><span class="sxs-lookup"><span data-stu-id="288ae-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="288ae-112">指派給 Edge Server 或 Edge 集區的 Access Edge service</span><span class="sxs-lookup"><span data-stu-id="288ae-112">Assign to Access Edge service of Edge Server or Edge pool</span></span></p></td>
<td><p><span data-ttu-id="288ae-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="288ae-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="288ae-114">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="288ae-114">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="288ae-115">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="288ae-115">sip.contoso.com</span></span></p>
<p><span data-ttu-id="288ae-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="288ae-116">sip.fabrikam.com</span></span></p>
<p><span data-ttu-id="288ae-117">contoso.com</span><span class="sxs-lookup"><span data-stu-id="288ae-117">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="288ae-118">前三個 SAN 專案是完整 Edge Server 的一般 SAN 專案。</span><span class="sxs-lookup"><span data-stu-id="288ae-118">The first three SAN entries are the normal SAN entries for a full Edge Server.</span></span> <span data-ttu-id="288ae-119">contoso.com 是在根網域層級與 XMPP 協力廠商同盟的必要項目。</span><span class="sxs-lookup"><span data-stu-id="288ae-119">The contoso.com is the entry required for federation with the XMPP partner at the root domain level.</span></span> <span data-ttu-id="288ae-120">此專案將允許具有尾碼 contoso.com 之所有網域的 XMPP。</span><span class="sxs-lookup"><span data-stu-id="288ae-120">This entry will allow XMPP for all domains with the suffix contoso.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="288ae-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="288ae-121">See Also</span></span>


[<span data-ttu-id="288ae-122">Lync Server 2013 的範例 XMPP 設定– XMPP 與 Google 交談的同盟</span><span class="sxs-lookup"><span data-stu-id="288ae-122">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="288ae-123">在 Lync Server 2013 中規劃 Edge Server 憑證</span><span class="sxs-lookup"><span data-stu-id="288ae-123">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  


[<span data-ttu-id="288ae-124">設定 Lync Server 2013 的 Edge 憑證</span><span class="sxs-lookup"><span data-stu-id="288ae-124">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
[<span data-ttu-id="288ae-125">Request-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="288ae-125">Request-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[<span data-ttu-id="288ae-126">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="288ae-126">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

