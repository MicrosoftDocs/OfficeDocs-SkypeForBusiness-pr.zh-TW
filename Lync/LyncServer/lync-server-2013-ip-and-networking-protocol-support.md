---
title: Lync Server 2013： IP 和網路通訊協定支援
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
ms.openlocfilehash: 99a563df5e0eb21bf94b97dd4c578aefea896496
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525240"
---
# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a>Lync Server 2013 中的 IP 和網路通訊協定支援

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

Lync Server 2013 支援下列 IP 和網路通訊協定：

  - **IP 通訊協定。**    Lync Server 2013 支援伺服器網路的 IP 版本 4 (IPv4) 或 IP 版本 6 (IPv6) 。
    
    <div>
    

    > [!NOTE]  
    > 在啟用雙重 IP 堆疊的網路中，Lync Server 2013 可以運作。

    
    </div>

  - **SIP 傳輸通訊協定。**    一般情況下，SIP 至少可以使用三種傳輸類型：使用者資料包協定 (UDP) 、傳輸控制通訊協定 (TCP) 及傳輸層安全性 (TLS) 。 在預設的 SIP 傳輸設定中，TLS 會透過 TCP 執行。 TLS 是在 Lync Server 2013 網路內使用。 在網路的 edge 中，Lync Server 2013 可以透過 TCP 進行交互操作。 Lync Server 2013 不支援 SIP 傳輸的 UDP，因為它不符合企業通訊安全性、可靠性和擴充性的最低標準。 如需詳細資訊，請參閱 NextHop 的博客文章：「UDP （或不是 UDP）」，這是問題的「at」 [https://go.microsoft.com/fwlink/p/?linkId=185369](https://go.microsoft.com/fwlink/p/?linkid=185369) 。
    
    <div>
    

    > [!NOTE]  
    > 每個網誌的內容及其 URL 如有變更，恕不另行通知。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

