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
# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a>在 Lync Server 2013 中設定音訊會議提供者的同盟

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-07-24_

若要在混合部署中使用音訊會議提供者 (ACP)  (Lync Server 內部部署與 Lync Online) ，您必須設定內部部署 Lync 部署與 ACP 夥伴之間的同盟為允許的夥伴伺服器。 您可以新增 ACP partner domain 及 Edge server (此設定同盟也稱為存取 Proxy) 內部部署的同盟網域清單。 您的 ACP 合作夥伴必須將您的內部部署 Edge Server 集區的 FQDN 新增至其允許的同盟網域清單。 請與您的 ACP provider 聯繫以取得其他 detailsYour ACP partner，然後必須將內部部署 Edge Server 集區的 FQDN 新增至其允許的同盟網域清單。

  - **將 ACP 網域和 Edge Server 新增為允許的同盟網域**
    
    若要將 ACP 網域新增為允許的同盟伺服器 (允許的同盟網域) ，請遵循在 [Lync Server 2013 中為允許的外部網域設定支援](lync-server-2013-configure-support-for-allowed-external-domains.md)中的步驟。 針對 Edge Server，新增 ACP partner Edge Server 的 FQDN。 您可能需要聯繫 ACP 合作夥伴，以取得其 Edge Server 的 FQDN，而您的 ACP 也可能會將其稱為存取 Proxy。

  - **將 Edge Server 集區的 FQDN 提供給 ACP partner**
    
    ACP 合作夥伴必須將 Edge Server 集區的 FQDN 新增為允許的同盟網域，才能設定同盟以將您的內部部署網域新增為允許的夥伴伺服器。

</div>

<span> </span>

</div>

</div>

</div>

