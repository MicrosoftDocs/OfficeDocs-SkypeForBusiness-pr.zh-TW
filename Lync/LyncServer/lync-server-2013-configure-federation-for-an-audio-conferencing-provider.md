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
ms.openlocfilehash: a85a8ef64d43561a68dca7c850f79cc6a1632fc2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a>在 Lync Server 2013 中設定的音訊會議提供者的同盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-07-24_

如果您想要在混合式部署 （Lync Server 內部部署與 Lync Online） 中使用音訊會議提供者 (ACP)，您需要將您的內部部署 Lync 部署和 ACP 夥伴之間的同盟設定為允許協力程式伺服器。 您可以設定同盟新增 Edge server （這也稱為 Access Proxy） 與 ACP 協力廠商網域到同盟網域清單為您的內部部署。 ACP 夥伴然後必須允許同盟的網域清單中新增您的內部部署 Edge Server 集區的 FQDN。 針對其他 detailsYour ACP 合作夥伴然後需要允許同盟的網域清單中新增您的內部部署 Edge Server 集區的 FQDN，請連絡您 ACP 提供者。

  - **新增 Edge Server 與 ACP 網域為允許同盟網域**
    
    若要新增 ACP 網域為允許協力程式伺服器 （允許同盟網域），請遵循[設定支援的 Lync Server 2013 中允許的外部網域](lync-server-2013-configure-support-for-allowed-external-domains.md)中的步驟。 針對 Edge Server] 新增 ACP 夥伴的 Edge Server 的 FQDN。 您可能需要您取得其 Edge Server，可能也會參照您 ACP 作為其 Access Proxy FQDN 的 ACP 合作夥伴連絡。

  - **ACP 協力廠商提供 Edge Server 集區的 FQDN**
    
    ACP 合作夥伴必須設定為允許協力程式伺服器新增您的內部部署網域新增 Edge Server 集區的 FQDN，以允許同盟網域同盟。

</div>

<span> </span>

</div>

</div>

</div>

