---
title: Lync Server 2013：規劃 Edge Server 憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 737e0845b4b9966accd8c450b8a300b4f1bb128e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a><span data-ttu-id="3ca9f-102">在 Lync Server 2013 中規劃 Edge Server 憑證</span><span class="sxs-lookup"><span data-stu-id="3ca9f-102">Plan for Edge Server certificates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ca9f-103">_**主題上次修改日期：** 2012-11-05_</span><span class="sxs-lookup"><span data-stu-id="3ca9f-103">_**Topic Last Modified:** 2012-11-05_</span></span>

<span data-ttu-id="3ca9f-104">在 Lync Server 2013 中簡化了邊緣的證書建立。</span><span class="sxs-lookup"><span data-stu-id="3ca9f-104">Certificate creation for Edge is simplified in Lync Server 2013.</span></span>

<span data-ttu-id="3ca9f-105">**Edge Server 的憑證流程圖**</span><span class="sxs-lookup"><span data-stu-id="3ca9f-105">**Certificates Flow Chart for Edge Server**</span></span>

<span data-ttu-id="3ca9f-106">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span><span class="sxs-lookup"><span data-stu-id="3ca9f-106">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span></span>

<span data-ttu-id="3ca9f-107">建立單一公用憑證，請確定您已為憑證定義可匯出的私密金鑰，然後使用憑證嚮導將它指派給下列 Edge 伺服器外部介面：</span><span class="sxs-lookup"><span data-stu-id="3ca9f-107">Create a single public certificate, ensure that you have an exportable private key defined for the certificate, and assign it to the following Edge Server external interfaces using the certificate wizard:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3ca9f-108">Lync Server 不支援萬用字元憑證，除非使用反向 proxy 來摘要簡單的 Url。</span><span class="sxs-lookup"><span data-stu-id="3ca9f-108">Wildcard certificates are not supported in Lync Server, except where used to summarize the Simple URLs through the reverse proxy.</span></span> <span data-ttu-id="3ca9f-109">您必須針對您的部署提供的每個 SIP 功能變數名稱、網頁會議 Edge 服務、A/V Edge 服務和 XMPP 網域，定義不同的主體替換名稱（San）。</span><span class="sxs-lookup"><span data-stu-id="3ca9f-109">You must define distinct subject alternate names (SANs) for each SIP domain name, Web Conferencing Edge service, A/V Edge service and XMPP domain offered by your deployment.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="3ca9f-110">在 Lync Server 2013 中引入，在目前憑證的到期時間前暫存音訊/視頻驗證憑證需要額外的規劃。</span><span class="sxs-lookup"><span data-stu-id="3ca9f-110">Introduced in Lync Server 2013, staging Audio/Video Authentication certificates in advance of the expiration time of the current certificate requires some additional planning.</span></span> <span data-ttu-id="3ca9f-111">在外部邊緣介面的情況下，不需要使用一個以上用途的憑證，您必須有兩個憑證，一個指派給 [存取邊緣] 服務和 [Web 會議 Edge 服務]，另一個是 A/V 邊緣服務的憑證。</span><span class="sxs-lookup"><span data-stu-id="3ca9f-111">Instead of one certificate with multiple purposes for the external Edge interface, you will require two certificates, one assigned to the Access Edge service and Web Conferencing Edge service, and one certificate for the A/V Edge service.</span></span> <span data-ttu-id="3ca9f-112">如需其他詳細資料，請參閱<A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">使用 CsCertificate 中的 [在 Lync Server 2013 中暫存 AV 和 OAuth 憑證</A>]</span><span class="sxs-lookup"><span data-stu-id="3ca9f-112">For additional details, see <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</A></span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3ca9f-113">在邊緣伺服器池的事件中，您會將擁有私密金鑰的憑證匯出至每個 Edge 伺服器，並將憑證指派給每個 Edge 伺服器服務。</span><span class="sxs-lookup"><span data-stu-id="3ca9f-113">In the event of a pool of Edge Servers, you export the certificate with the private key to each Edge Server and assign the certificate to each Edge Server service.</span></span> <span data-ttu-id="3ca9f-114">對內部邊緣伺服器憑證執行相同的動作，以私密金鑰匯出憑證，並指派給每個內部邊緣介面。</span><span class="sxs-lookup"><span data-stu-id="3ca9f-114">Do the same for the internal Edge Server certificate, exporting the certificate with the private key and assigning to each internal Edge interface.</span></span>



</div>

  - <span data-ttu-id="3ca9f-115">確定您已為憑證指派可匯出的私人金鑰</span><span class="sxs-lookup"><span data-stu-id="3ca9f-115">Ensure that you have an exportable private key assigned for the certificate</span></span>

  - <span data-ttu-id="3ca9f-116">Access Edge 服務（在證書嚮導中稱為**SIP 存取邊緣**）</span><span class="sxs-lookup"><span data-stu-id="3ca9f-116">Access Edge service (referred to as **SIP Access Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="3ca9f-117">網路會議 Edge 服務（在證書嚮導中稱為「**網路會議 Edge 外部**」）</span><span class="sxs-lookup"><span data-stu-id="3ca9f-117">Web Conferencing Edge service (referred to as **Web Conferencing Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="3ca9f-118">A/V 驗證服務（在證書嚮導中稱為**a/v 邊緣**）</span><span class="sxs-lookup"><span data-stu-id="3ca9f-118">A/V Authentication service (referred to as **A/V Edge External** in the certificate wizard)</span></span>

<span data-ttu-id="3ca9f-119">使用可匯出的私密金鑰建立單一的內部憑證，將它複製並指派給每一個 Edge 伺服器內部介面：</span><span class="sxs-lookup"><span data-stu-id="3ca9f-119">Create a single internal certificate with exportable private key, copy and assign it to each of the Edge Server internal interfaces:</span></span>

  - <span data-ttu-id="3ca9f-120">Edge 伺服器（在證書嚮導中稱為**邊緣內部**）</span><span class="sxs-lookup"><span data-stu-id="3ca9f-120">Edge Server (referred to as **Edge Internal** in the certificate wizard)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3ca9f-121">您可以針對每個 Edge 伺服器服務使用不同且不同的憑證。</span><span class="sxs-lookup"><span data-stu-id="3ca9f-121">It is possible to use separate and distinct certificates for each Edge Server service.</span></span> <span data-ttu-id="3ca9f-122">若要使用 A/V 邊緣服務憑證的新的 [滾動憑證] 功能，選擇 [個別憑證] 的最佳原因是。</span><span class="sxs-lookup"><span data-stu-id="3ca9f-122">A good reason to choose separate certificates is if you want to use the new rolling certificate feature for the A/V Edge service certificate.</span></span> <span data-ttu-id="3ca9f-123">在這項功能的情況下，建議您將 A/V Edge 服務憑證與 [存取邊緣服務] 和 [Web 會議 Edge 服務] 相分離。</span><span class="sxs-lookup"><span data-stu-id="3ca9f-123">In the case of this feature, decoupling the A/V Edge service certificate from the Access Edge service and Web Conferencing Edge service is recommended.</span></span> <span data-ttu-id="3ca9f-124">如果您選擇要求、針對每個服務取得並指派個別的憑證，您必須要求將私密金鑰匯出為 A/v 邊緣服務（同樣地，這實際上是 A/V 驗證服務），並將相同的憑證指派給每個 Edge 伺服器上的 A/V 邊緣外部介面。</span><span class="sxs-lookup"><span data-stu-id="3ca9f-124">If you choose to request, acquire and assign separate certificates for each service, you must request that the private key be exportable for the A/V Edge service (again, this is in actuality the A/V Authentication service) and assign the same certificate to the A/V Edge External interface on each Edge Server.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3ca9f-125">請參閱</span><span class="sxs-lookup"><span data-stu-id="3ca9f-125">See Also</span></span>


[<span data-ttu-id="3ca9f-126">使用 CsCertificate 在 Lync Server 2013 中暫存 AV 和 OAuth 憑證</span><span class="sxs-lookup"><span data-stu-id="3ca9f-126">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[<span data-ttu-id="3ca9f-127">在 Lync Server 2013 中會影響 Edge Server 規劃的變更</span><span class="sxs-lookup"><span data-stu-id="3ca9f-127">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

