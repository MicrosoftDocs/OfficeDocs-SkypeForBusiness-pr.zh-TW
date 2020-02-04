---
title: Lync Server 2013：針對音訊會議提供者設定同盟
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
ms.openlocfilehash: c5c1ca77b2f68a2285fb15d65c19631323a03bda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a>在 Lync Server 2013 中設定音訊會議提供者的同盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-07-24_

如果您想要在混合式部署（使用 Lync Online 的 Lync Server 內部部署）中使用音訊會議提供者（ACP），則必須在您的內部部署 Lync 部署和 ACP 夥伴之間，將同盟設定為允許的合作夥伴伺服器。 您可以將 ACP 夥伴網域和 Edge 伺服器（也稱為 [存取代理伺服器]）新增到內部部署的 [聯盟網域] 清單中，以設定同盟。 您的 ACP 合作夥伴接著需要將內部部署邊緣伺服器池的 FQDN 新增到其允許的聯盟網域清單。 請與您的 ACP 提供者聯繫，以取得其他 detailsYour ACP 合作夥伴，然後需要將內部部署邊緣伺服器池的 FQDN 新增到其允許的聯盟網域清單。

  - **新增 ACP 網域和 Edge 伺服器作為允許的聯盟網域**
    
    若要將 ACP 網域新增為允許的夥伴伺服器（允許聯盟網域），請遵循在[Lync Server 2013 中設定支援的外部網域](lync-server-2013-configure-support-for-allowed-external-domains.md)中的步驟。 針對 Edge 伺服器，新增 ACP 合作夥伴邊緣伺服器的 FQDN。 您可能需要與您的 ACP 夥伴聯繫，以取得其 Edge 伺服器的 FQDN，您的 ACP 也可能會將其稱為存取 Proxy。

  - **將 Edge 伺服器池的 FQDN 提供給 ACP 合作夥伴**
    
    ACP 合作夥伴需要設定同盟，只要將 Edge 伺服器池的 FQDN 新增為允許的聯盟網域，即可將您的內部部署網域新增為允許的合作夥伴伺服器。

</div>

<span> </span>

</div>

</div>

</div>

