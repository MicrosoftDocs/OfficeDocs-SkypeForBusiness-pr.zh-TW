---
title: Lync Server 2013：IP 和網路通訊協定支援
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
ms.openlocfilehash: 285ed0d383b09276979ad6e29c390e2fc22a1caf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a>Lync Server 2013 中的 IP 和網路通訊協定支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

Lync Server 2013 支援下列 IP 和網路通訊協定：

  - **IP 通訊協定。**   Lync server 2013 支援伺服器網路的 ip 版本4（IPv4）或 ip 版本6（IPv6）。
    
    <div>
    

    > [!NOTE]  
    > 在啟用雙 IP 堆疊的網路中，Lync Server 2013 可以正常運作。

    
    </div>

  - **SIP 傳輸通訊協定。**   一般情況下，SIP 最少可以使用三種傳輸類型：使用者資料包協定（UDP）、傳輸控制通訊協定（TCP），以及傳輸層安全性（TLS）。 在預設 SIP 傳輸配置中，TLS 會在 TCP 上執行。 TLS 是在 Lync Server 2013 網路中使用。 在網路邊緣，Lync Server 2013 可以在 TCP 上進行交互操作。 Lync Server 2013 不支援 SIP 傳輸的 UDP，因為它不符合企業通訊安全性、可靠性及可伸縮性的最低標準。 如需詳細資訊，請參閱 NextHop 博客文章、「UDP （或不是 UDP），也就是 "at [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369)" 問題。
    
    <div>
    

    > [!NOTE]  
    > 每個博客及其 URL 的內容可能會變更，恕不另行通知。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

