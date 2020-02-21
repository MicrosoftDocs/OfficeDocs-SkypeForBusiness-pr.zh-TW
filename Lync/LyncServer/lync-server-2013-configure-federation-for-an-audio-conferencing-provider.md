---
title: Lync Server 2013： 設定音訊會議提供者的同盟
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
ms.openlocfilehash: 679fe6ae6f11823d55070508b506864b1839d054
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a><span data-ttu-id="20ac6-102">在 Lync Server 2013 中設定的音訊會議提供者的同盟</span><span class="sxs-lookup"><span data-stu-id="20ac6-102">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20ac6-103">_**上次修改主題：** 2014年-07-24_</span><span class="sxs-lookup"><span data-stu-id="20ac6-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="20ac6-104">如果您想要在混合式部署 （Lync Server 內部部署與 Lync Online） 中使用音訊會議提供者 (ACP)，您需要將您的內部部署 Lync 部署和 ACP 夥伴之間的同盟設定為允許協力程式伺服器。</span><span class="sxs-lookup"><span data-stu-id="20ac6-104">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (Lync Server on-premises with Lync Online), you need to configure federation between your on-premises Lync deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="20ac6-105">您可以設定同盟新增 Edge server （這也稱為 Access Proxy） 與 ACP 協力廠商網域到同盟網域清單為您的內部部署。</span><span class="sxs-lookup"><span data-stu-id="20ac6-105">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="20ac6-106">ACP 夥伴然後必須允許同盟的網域清單中新增您的內部部署 Edge Server 集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="20ac6-106">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="20ac6-107">針對其他 detailsYour ACP 合作夥伴然後需要允許同盟的網域清單中新增您的內部部署 Edge Server 集區的 FQDN，請連絡您 ACP 提供者。</span><span class="sxs-lookup"><span data-stu-id="20ac6-107">Contact your ACP provider for additional detailsYour ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

  - <span data-ttu-id="20ac6-108">**新增 Edge Server 與 ACP 網域為允許同盟網域**</span><span class="sxs-lookup"><span data-stu-id="20ac6-108">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="20ac6-109">若要新增 ACP 網域為允許協力程式伺服器 （允許同盟網域），請遵循[設定支援的 Lync Server 2013 中允許的外部網域](lync-server-2013-configure-support-for-allowed-external-domains.md)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="20ac6-109">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span> <span data-ttu-id="20ac6-110">針對 Edge Server] 新增 ACP 夥伴的 Edge Server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="20ac6-110">For the Edge Server, add the FQDN of the ACP partner’s Edge Server.</span></span> <span data-ttu-id="20ac6-111">您可能需要您取得其 Edge Server，可能也會參照您 ACP 作為其 Access Proxy FQDN 的 ACP 合作夥伴連絡。</span><span class="sxs-lookup"><span data-stu-id="20ac6-111">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

  - <span data-ttu-id="20ac6-112">**ACP 協力廠商提供 Edge Server 集區的 FQDN**</span><span class="sxs-lookup"><span data-stu-id="20ac6-112">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="20ac6-113">ACP 合作夥伴必須設定為允許協力程式伺服器新增您的內部部署網域新增 Edge Server 集區的 FQDN，以允許同盟網域同盟。</span><span class="sxs-lookup"><span data-stu-id="20ac6-113">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

