---
title: Lync Server 2013：針對音訊會議提供者設定同盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure federation for an audio conferencing provider
ms:assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn510996(v=OCS.15)
ms:contentKeyID: 60595883
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30bf49947034f995b10551985450f560bc1d3693
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a><span data-ttu-id="d4fd4-102">在 Lync Server 2013 中設定音訊會議提供者的同盟</span><span class="sxs-lookup"><span data-stu-id="d4fd4-102">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4fd4-103">_**主題上次修改日期：** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="d4fd4-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="d4fd4-104">如果您想要在混合式部署（使用 Lync Online 的 Lync Server 內部部署）中使用音訊會議提供者（ACP），則必須在您的內部部署 Lync 部署和 ACP 夥伴之間，將同盟設定為允許的合作夥伴伺服器。</span><span class="sxs-lookup"><span data-stu-id="d4fd4-104">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (Lync Server on-premises with Lync Online), you need to configure federation between your on-premises Lync deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="d4fd4-105">您可以將 ACP 夥伴網域和 Edge 伺服器（也稱為 [存取代理伺服器]）新增到內部部署的 [聯盟網域] 清單中，以設定同盟。</span><span class="sxs-lookup"><span data-stu-id="d4fd4-105">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="d4fd4-106">您的 ACP 合作夥伴接著需要將內部部署邊緣伺服器池的 FQDN 新增到其允許的聯盟網域清單。</span><span class="sxs-lookup"><span data-stu-id="d4fd4-106">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="d4fd4-107">請與您的 ACP 提供者聯繫，以取得其他 detailsYour ACP 合作夥伴，然後需要將內部部署邊緣伺服器池的 FQDN 新增到其允許的聯盟網域清單。</span><span class="sxs-lookup"><span data-stu-id="d4fd4-107">Contact your ACP provider for additional detailsYour ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

  - <span data-ttu-id="d4fd4-108">**新增 ACP 網域和 Edge 伺服器作為允許的聯盟網域**</span><span class="sxs-lookup"><span data-stu-id="d4fd4-108">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="d4fd4-109">若要將 ACP 網域新增為允許的夥伴伺服器（允許聯盟網域），請遵循在[Lync Server 2013 中設定支援的外部網域](lync-server-2013-configure-support-for-allowed-external-domains.md)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="d4fd4-109">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span> <span data-ttu-id="d4fd4-110">針對 Edge 伺服器，新增 ACP 合作夥伴邊緣伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d4fd4-110">For the Edge Server, add the FQDN of the ACP partner’s Edge Server.</span></span> <span data-ttu-id="d4fd4-111">您可能需要與您的 ACP 夥伴聯繫，以取得其 Edge 伺服器的 FQDN，您的 ACP 也可能會將其稱為存取 Proxy。</span><span class="sxs-lookup"><span data-stu-id="d4fd4-111">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

  - <span data-ttu-id="d4fd4-112">**將 Edge 伺服器池的 FQDN 提供給 ACP 合作夥伴**</span><span class="sxs-lookup"><span data-stu-id="d4fd4-112">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="d4fd4-113">ACP 合作夥伴需要設定同盟，只要將 Edge 伺服器池的 FQDN 新增為允許的聯盟網域，即可將您的內部部署網域新增為允許的合作夥伴伺服器。</span><span class="sxs-lookup"><span data-stu-id="d4fd4-113">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

