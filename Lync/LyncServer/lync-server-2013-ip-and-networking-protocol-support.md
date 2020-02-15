---
title: 'Lync Server 2013: IP 和網路通訊協定支援'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP and networking protocol support
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48185128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a9792ea8365dcd8941b831c43ab0406f9e33b90
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a>Lync Server 2013 中的 IP 和網路通訊協定支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-21_

Lync Server 2013 支援下列 IP 和網路通訊協定：

  - **IP 通訊協定。**   Lync Server 2013 的伺服器網路支援 IP 版本 4 (IPv4) 或 IP 版本 6 (IPv6)。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 可以在啟用雙重 IP 堆疊的網路中運作。

    
    </div>

  - **SIP 傳輸通訊協定。**   SIP 代，可以使用，至少有三種傳輸類型： 使用者資料包通訊協定 (UDP)、 傳輸控制通訊協定 (TCP) 和傳輸層安全性 (TLS)。 在 [預設 SIP 傳輸組態中，TLS 執行 over TCP。 TLS 用在 Lync Server 2013 網路內。 在網路邊緣，Lync Server 2013 可以透過 TCP 交互操作。 Lync Server 2013 不支援 UDP SIP 傳輸因為它不符合企業通訊安全性、 可靠性與延展性的下限標準。 如需詳細資訊，請參閱 NextHop 部落格文章，「 UDP，或不 UDP，是問題，" [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369)。
    
    <div>
    

    > [!NOTE]  
    > 每個網誌的內容及其 URL 如有變更，恕不另行通知。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

