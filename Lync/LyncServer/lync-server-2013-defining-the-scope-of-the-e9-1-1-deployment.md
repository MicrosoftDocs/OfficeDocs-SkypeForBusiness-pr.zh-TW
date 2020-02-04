---
title: Lync Server 2013：定義 E9-1-1 部署的範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96f5ac1fb747a3e64be6cc84c44b390de8ce821c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a>在 Lync Server 2013 中定義 E9-1-1 部署的範圍

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-06_

在將 Microsoft Lync Server 2013 設定為 E9-1-1 之前，您必須先規劃您的 E9-1 1 部署。 需要考慮的一些問題包括：

  - **貴組織的原則與 E9-1-1 的法律義務為何？**  
    E9-1-1-1-1-1-1 parlance）中的 Pbx 法律需求（在 E9-1-1 中稱為多行電話系統，或 MLTS）與狀態不同。 您應該向法律小組諮詢，以瞭解在相關地區的 Lync Server 部署中可能適用的義務。

<!-- end list -->

  - **貴企業中需要為 E9 的哪些區域啟用-1-1？**  
    您可以為整個企業或選取的位置啟用 E9-1-1。 例如，您可能會在不同狀態的辦公室中有不同的 E9-1 需求，或者您可能想要排除美國以外的網站

<!-- end list -->

  - **如何將 E9-1-1 部署到分支網站？**  
    語音復原是您在分支網站部署 E9-1-1 時，必須瞭解的重要概念。 如果您使用的是集中式電子 9-1-1 SIP trunks，且發生 WAN 中斷，則登入的用戶端可能無法從位置資訊服務取得位置，或無法連線到緊急服務服務提供者。 Lync Server 提供幾項策略，可處理分支辦公室中的語音復原，包括：具備彈性資料網路、在每個分支部署 SIP 幹線，或在中斷期間將緊急呼叫推出到本機閘道。 如需詳細資訊，請參閱[Lync Server 2013 中的分支網站語音復原規劃](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。

<!-- end list -->

  - **您是否要為在網路外部工作的使用者啟用 E9-1-1？**  
    自動位置採集僅適用于組織網路內部的客戶，所以您的組織必須決定是否支援在非內部部署期間從 Lync 用戶端撥打的 E9。 例如，如果使用者是在家中或從客戶的網站工作，您是否能讓他們放入緊急通話？ 如果用戶端位於商業網路之外，則可將用戶端設定為提示使用者輸入位置。 不過，因為這些使用者提供的位置無法依據主要街道位址指南（MSAG） prevalidated，所以緊急服務服務提供者發送器必須在路由前確認與來電者 verbally 位置的有效性。公用安全應答點（PSAP）的呼叫。
    
    <div>
    

    > [!NOTE]  
    > 使用 VPN 連線到貴組織網路的使用者的 Lync 用戶端可以挑選內部 IP 位址資訊，但因為這些位址無法用來識別使用者的實際位置，所以必須將 VPN 子網排除在位置資訊服務。

    
    </div>

<!-- end list -->

  - **您想要提供緊急呼叫路由至美國以外的網站嗎？**  
    您可能會想要提供緊急路由至您公司不是由緊急服務服務提供者所提供的區域（例如，國際位置）。 若要這樣做，請建立新的網站，然後將語音原則指派給參照 PSTN 使用狀況的網站，以透過本機 PSTN 閘道路由通話。

</div>

<span> </span>

</div>

</div>

</div>

