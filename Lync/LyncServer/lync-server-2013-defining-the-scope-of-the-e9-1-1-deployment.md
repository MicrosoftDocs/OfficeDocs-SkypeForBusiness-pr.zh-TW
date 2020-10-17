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
ms.openlocfilehash: 27d280580f4d9cae1f6240b554be760d1689daa3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504480"
---
# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a>在 Lync Server 2013 中定義 E9-1-1 部署的範圍

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-06_

將 Microsoft Lync Server 2013 設定為 E9-1-1 之前，您必須規劃 E9-1-1 部署。 應考量的問題包括：

  - **您組織對於 E9-1-1 的原則及法律義務為何？**  
    E9-1-1 對於 PBX (以 E9-1-1 的說法稱為多線電話系統，或 MLTS) 的法律要求會因為各州而有所不同。 您應該向法律小組請教，以瞭解可能對您的相關地理區域中的 Lync Server 部署所套用的義務。

<!-- end list -->

  - **您的企業中有哪些領域需要啟用 E9-1-1？**  
    您可以為整個企業或為選取的位置啟用 E9-1-1。例如，對於位於不同州的辦公室，您可能有不同的 E9-1-1 需求，或者您可能想要排除美國境外的網站。

<!-- end list -->

  - **您要如何將 E9-1-1 部署至分支網站？**  
    在分支網站部署 E9-1-1 時，語音恢復能力是必須要了解的重要概念。 如果您已集中式電子 9-1-1 SIP 主幹，且發生 WAN 中斷，則登入的用戶端可能無法從位置資訊服務取得位置，或無法連線至緊急服務服務提供者。 Lync Server 提供數個策略，用來處理分支辦公室中的語音彈性，包括：具有可恢復的資料網路、在每個分支部署 SIP 主幹，或在中斷期間將緊急呼叫推出至本機閘道。 如需詳細資訊，請參閱 [在 Lync Server 2013 中規劃分支網站語音恢復功能](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。

<!-- end list -->

  - **您是否會為在網路以外工作的使用者啟用 E9-1-1？**  
    自動取得位置僅適用於位於組織網路內部的用戶端，因此您的組織必須決定是否要支援來自外部部署 Lync 用戶端發出的 E9-1-1 電話。例如，若使用者是在家裡工作，或是在客戶網站上，您是否要允許該使用者撥打緊急通話？若用戶端位於企業網路之外，可設定用戶端提示使用者告知其位置。不過根據主要街道地址指南 (MSAG)，這些使用者提供的位置無法預先加以驗證，緊急服務的服務提供者發送方需要以口頭與來電者確定此位置的有效性，才能將電話路由至公共安全勤務中心 (PSAP)。
    
    <div>
    

    > [!NOTE]  
    > 使用 VPN 連線到貴組織網路之使用者的 Lync 用戶端可以挑選內部 IP 位址資訊，但因為這些位址不能用來識別使用者的實際位置，所以從位置資訊服務排除 VPN 子網是必要的。

    
    </div>

<!-- end list -->

  - **您是否要提供路由至美國以外網站的緊急電話？**  
    您可以為公司中不受緊急服務的服務提供者所涵蓋的區域 (例如駐外地點) 提供緊急路由。若要這麼做，請建立新網站，然後為其指派語音原則，並讓此語音原則參照透過本機 PSTN 閘道路由電話的 PSTN 使用方式。

</div>

<span> </span>

</div>

</div>

</div>

