---
title: Lync Server 2013：規劃 Edge Server 憑證
description: Lync Server 2013：規劃 Edge Server 憑證。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22ec3743256fe3e4c55dba0f6357a85b1ad81cd0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578189"
---
# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a><span data-ttu-id="a512e-103">在 Lync Server 2013 中規劃 Edge Server 憑證</span><span class="sxs-lookup"><span data-stu-id="a512e-103">Plan for Edge Server certificates in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a512e-104">_**主題上次修改日期：** 2012-11-05_</span><span class="sxs-lookup"><span data-stu-id="a512e-104">_**Topic Last Modified:** 2012-11-05_</span></span>

<span data-ttu-id="a512e-105">在 Lync Server 2013 中簡化了 Edge 的憑證建立。</span><span class="sxs-lookup"><span data-stu-id="a512e-105">Certificate creation for Edge is simplified in Lync Server 2013.</span></span>

<span data-ttu-id="a512e-106">**Edge Server 的憑證流程圖表**</span><span class="sxs-lookup"><span data-stu-id="a512e-106">**Certificates Flow Chart for Edge Server**</span></span>

<span data-ttu-id="a512e-107">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span><span class="sxs-lookup"><span data-stu-id="a512e-107">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span></span>

<span data-ttu-id="a512e-108">建立單一公用憑證，請確定您具有為憑證定義的可匯出私密金鑰，並使用憑證嚮導將其指派給下列 Edge Server 外部介面：</span><span class="sxs-lookup"><span data-stu-id="a512e-108">Create a single public certificate, ensure that you have an exportable private key defined for the certificate, and assign it to the following Edge Server external interfaces using the certificate wizard:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a512e-109">Lync Server 不支援萬用字元憑證，除非用來匯總透過反向 proxy 的簡易 URLs。</span><span class="sxs-lookup"><span data-stu-id="a512e-109">Wildcard certificates are not supported in Lync Server, except where used to summarize the Simple URLs through the reverse proxy.</span></span> <span data-ttu-id="a512e-110">您必須為部署所提供的每個 SIP 功能變數名稱、Web 會議 Edge service A/V Edge service 和 XMPP 網域，分別定義不同的主體替代名稱 (SANs) 。</span><span class="sxs-lookup"><span data-stu-id="a512e-110">You must define distinct subject alternate names (SANs) for each SIP domain name, Web Conferencing Edge service, A/V Edge service and XMPP domain offered by your deployment.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a512e-111">在 Lync Server 2013 中引入，在目前憑證到期時間之前，暫存 Audio/Video 驗證憑證需要進行一些額外的規劃。</span><span class="sxs-lookup"><span data-stu-id="a512e-111">Introduced in Lync Server 2013, staging Audio/Video Authentication certificates in advance of the expiration time of the current certificate requires some additional planning.</span></span> <span data-ttu-id="a512e-112">除了一個憑證的外部 Edge 介面具有多種用途之外，您還需要兩個憑證，一個憑證會指派給 Access Edge service 和 Web 會議 Edge service，另一個憑證用於 A/V Edge service。</span><span class="sxs-lookup"><span data-stu-id="a512e-112">Instead of one certificate with multiple purposes for the external Edge interface, you will require two certificates, one assigned to the Access Edge service and Web Conferencing Edge service, and one certificate for the A/V Edge service.</span></span> <span data-ttu-id="a512e-113">如需詳細資訊，請參閱 <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">在 Lync Server 2013 中使用-擲入的暫存 AV 和 OAuth 憑證 Set-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="a512e-113">For additional details, see <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</A></span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a512e-114">在邊際伺服器集區的事件中，您會將具有私密金鑰的憑證匯出至每個 Edge Server，並將憑證指派給每個 Edge Server 服務。</span><span class="sxs-lookup"><span data-stu-id="a512e-114">In the event of a pool of Edge Servers, you export the certificate with the private key to each Edge Server and assign the certificate to each Edge Server service.</span></span> <span data-ttu-id="a512e-115">對內部 Edge Server 憑證執行相同的作業，並以私密金鑰匯出憑證，並指派給每個內部 Edge 介面。</span><span class="sxs-lookup"><span data-stu-id="a512e-115">Do the same for the internal Edge Server certificate, exporting the certificate with the private key and assigning to each internal Edge interface.</span></span>



</div>

  - <span data-ttu-id="a512e-116">確定您已為憑證指派可匯出的私密金鑰</span><span class="sxs-lookup"><span data-stu-id="a512e-116">Ensure that you have an exportable private key assigned for the certificate</span></span>

  - <span data-ttu-id="a512e-117">Access Edge service (稱為憑證嚮導中的「 **外部 SIP 存取 Edge** 」) </span><span class="sxs-lookup"><span data-stu-id="a512e-117">Access Edge service (referred to as **SIP Access Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="a512e-118">Web 會議 Edge service (稱為憑證嚮導中的「 **Web 會議 Edge 外部** 」) </span><span class="sxs-lookup"><span data-stu-id="a512e-118">Web Conferencing Edge service (referred to as **Web Conferencing Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="a512e-119">A/V 驗證服務 (稱為憑證嚮導中的 **A/V Edge 外部**) </span><span class="sxs-lookup"><span data-stu-id="a512e-119">A/V Authentication service (referred to as **A/V Edge External** in the certificate wizard)</span></span>

<span data-ttu-id="a512e-120">使用可匯出的私密金鑰建立單一的內部憑證，將其複製並指派給每個 Edge Server 內部介面：</span><span class="sxs-lookup"><span data-stu-id="a512e-120">Create a single internal certificate with exportable private key, copy and assign it to each of the Edge Server internal interfaces:</span></span>

  - <span data-ttu-id="a512e-121">Edge Server (稱為憑證嚮導中的 **Edge Internal**) </span><span class="sxs-lookup"><span data-stu-id="a512e-121">Edge Server (referred to as **Edge Internal** in the certificate wizard)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a512e-122">您可以針對每個 Edge Server 服務使用不同且不同的憑證。</span><span class="sxs-lookup"><span data-stu-id="a512e-122">It is possible to use separate and distinct certificates for each Edge Server service.</span></span> <span data-ttu-id="a512e-123">選擇個別憑證的最佳原因是您想要使用 A/V Edge service 憑證的新的「滾動憑證」功能。</span><span class="sxs-lookup"><span data-stu-id="a512e-123">A good reason to choose separate certificates is if you want to use the new rolling certificate feature for the A/V Edge service certificate.</span></span> <span data-ttu-id="a512e-124">在此項功能的情況下，建議將「Access Edge service」和「Web 會議 Edge service」的 A/V Edge service 憑證斷開。</span><span class="sxs-lookup"><span data-stu-id="a512e-124">In the case of this feature, decoupling the A/V Edge service certificate from the Access Edge service and Web Conferencing Edge service is recommended.</span></span> <span data-ttu-id="a512e-125">如果您選擇要求、取得並指派各項服務的個別憑證，您必須為 A/V Edge service 要求私密金鑰可匯出 (，這實際上是 A/V 驗證服務) ，而且將相同的憑證指派給每台 Edge Server 上的 A/V Edge 外部介面。</span><span class="sxs-lookup"><span data-stu-id="a512e-125">If you choose to request, acquire and assign separate certificates for each service, you must request that the private key be exportable for the A/V Edge service (again, this is in actuality the A/V Authentication service) and assign the same certificate to the A/V Edge External interface on each Edge Server.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a512e-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a512e-126">See Also</span></span>


[<span data-ttu-id="a512e-127">在 Lync Server 2013 中使用-滾 Set-CsCertificate 中的 AV 和 OAuth 憑證進行暫存</span><span class="sxs-lookup"><span data-stu-id="a512e-127">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[<span data-ttu-id="a512e-128">Lync Server 2013 中影響 Edge Server 規劃的變更</span><span class="sxs-lookup"><span data-stu-id="a512e-128">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

