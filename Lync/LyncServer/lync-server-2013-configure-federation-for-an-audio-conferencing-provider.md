---
title: Lync Server 2013：設定音訊會議提供者的同盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation for an audio conferencing provider
ms:assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn510996(v=OCS.15)
ms:contentKeyID: 60595883
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cebbac17955f812bf07a368064156b57b0c0ddd9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537090"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a><span data-ttu-id="4bebf-102">在 Lync Server 2013 中設定音訊會議提供者的同盟</span><span class="sxs-lookup"><span data-stu-id="4bebf-102">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bebf-103">_**主題上次修改日期：** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="4bebf-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="4bebf-104">若要在混合部署中使用音訊會議提供者 (ACP)  (Lync Server 內部部署與 Lync Online) ，您必須設定內部部署 Lync 部署與 ACP 夥伴之間的同盟為允許的夥伴伺服器。</span><span class="sxs-lookup"><span data-stu-id="4bebf-104">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (Lync Server on-premises with Lync Online), you need to configure federation between your on-premises Lync deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="4bebf-105">您可以新增 ACP partner domain 及 Edge server (此設定同盟也稱為存取 Proxy) 內部部署的同盟網域清單。</span><span class="sxs-lookup"><span data-stu-id="4bebf-105">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="4bebf-106">您的 ACP 合作夥伴必須將您的內部部署 Edge Server 集區的 FQDN 新增至其允許的同盟網域清單。</span><span class="sxs-lookup"><span data-stu-id="4bebf-106">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="4bebf-107">請與您的 ACP provider 聯繫以取得其他 detailsYour ACP partner，然後必須將內部部署 Edge Server 集區的 FQDN 新增至其允許的同盟網域清單。</span><span class="sxs-lookup"><span data-stu-id="4bebf-107">Contact your ACP provider for additional detailsYour ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

  - <span data-ttu-id="4bebf-108">**將 ACP 網域和 Edge Server 新增為允許的同盟網域**</span><span class="sxs-lookup"><span data-stu-id="4bebf-108">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="4bebf-109">若要將 ACP 網域新增為允許的同盟伺服器 (允許的同盟網域) ，請遵循在 [Lync Server 2013 中為允許的外部網域設定支援](lync-server-2013-configure-support-for-allowed-external-domains.md)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="4bebf-109">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span> <span data-ttu-id="4bebf-110">針對 Edge Server，新增 ACP partner Edge Server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="4bebf-110">For the Edge Server, add the FQDN of the ACP partner’s Edge Server.</span></span> <span data-ttu-id="4bebf-111">您可能需要聯繫 ACP 合作夥伴，以取得其 Edge Server 的 FQDN，而您的 ACP 也可能會將其稱為存取 Proxy。</span><span class="sxs-lookup"><span data-stu-id="4bebf-111">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

  - <span data-ttu-id="4bebf-112">**將 Edge Server 集區的 FQDN 提供給 ACP partner**</span><span class="sxs-lookup"><span data-stu-id="4bebf-112">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="4bebf-113">ACP 合作夥伴必須將 Edge Server 集區的 FQDN 新增為允許的同盟網域，才能設定同盟以將您的內部部署網域新增為允許的夥伴伺服器。</span><span class="sxs-lookup"><span data-stu-id="4bebf-113">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

