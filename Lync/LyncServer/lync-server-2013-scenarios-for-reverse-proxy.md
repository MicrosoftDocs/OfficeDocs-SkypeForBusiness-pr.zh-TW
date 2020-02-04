---
title: Lync Server 2013：反向 Proxy 案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82e1dffa55d6af8d131d3a94710c76277cfa75d9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 中的反向 Proxy 案例

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-21_

Lync Server 2013 需要使用反向代理，提供對服務和資源（例如會議和撥入式簡易 Url、通訊錄、會議內容、通訊群組清單展開、行動服務等）的存取權。 Lync Server 2013 中的典型反向 proxy 案例是允許外部用戶端（例如桌面用戶端或 Lync Web App 用戶端）存取控制器或前端伺服器外部 Web 服務。

**反向 proxy 與外部 web 服務**

![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")

在規劃階段，您可以在 Lync Server 2013 部署中定義反向 proxy 的需求。 反向 proxy 可讓您存取下列外部用戶端的功能：

  - Microsoft Lync 2013 桌面用戶端

  - Microsoft Lync Web App

  - Microsoft Lync Mobile

  - Lync Windows Store 應用程式

規劃 Lync Server 2013 部署時，您會將 Lync Server 2013 的實際需求對應到反向 proxy 的功能。

1.  外部用戶端會連線到埠 TCP 443 上的反向 proxy，並將使用安全通訊端層（SSL）或傳輸層安全性（TLS）。 Microsoft Lync Mobile 用戶端可以在埠 TCP 80 上連線，但只會在執行 Lync 探索服務的初始連線時，且系統管理員已設定正確的網域名稱系統（DNS） CNAME （或別名）記錄，並接受此通訊不會加密。

2.  Lync Server 2013 外部 web 服務（在前端伺服器和/或控制器上部署）預期從埠 TCP 4443 上的反向 proxy 進行連線，而且預期該連線將是 SSL/TLS。
    
    <div>
    

    > [!IMPORTANT]  
    > 針對外部 web 服務建議的預設偵聽埠是 HTTP 流量的 TCP 8080，以及 HTTPS 流量的 TCP 4443。 [拓撲建立器] 提供可覆寫預設值並定義您自己的外部 web 服務偵聽埠的機會。 請務必注意，反向 proxy 會與外部 web 服務進行通訊，而外部用戶端則與反向 proxy 進行通訊。 外部用戶端與埠 TCP 443 上的反向 proxy 通訊，但您可以重新定義反向 proxy 與外部 web 服務通訊的埠。 拓撲 Builder 中的選項可覆寫 web 服務的預設偵聽埠，可讓您解決基礎結構中可能會發生的偵聽埠衝突。

    
    </div>

3.  Lync Server 2013 外部 web 服務需要來自用戶端的未修改主機標頭，以找出用戶端嘗試使用的服務和 web 伺服器目錄。 要求應看起來像是來自反向 proxy

4.  外部 web 服務使用已定義的 web 伺服器虛擬目錄（vDir），提供提供給用戶端的服務。 特定的外部可識別 web 服務包括：
    
      - 針對網路會議會議的 [會議] vDir
    
      - 電話撥打電話給手機存取和電話會議的 vDir
    
      - Lync Windows Store app、Lync Mobile 和桌面用戶端 Lync 2013 的 [自動探索] vDir。 在 Lync Server 2013 中的自動探索是由 DNS 名稱 "lyncdiscover" 所知道
    
      - 未定義的服務會透過直接呼叫外部 web 服務的方式，由外部用戶端存取。 例如，通訊群組延伸（DLX）和通訊錄服務（ABS）都是透過直接呼叫外部 web 服務和相關聯的 vDirs 來存取。 用戶端知道 vDir 的實際路徑，並根據此資訊構造統一式記錄定位器（URL）。 用戶端會使用類似以下的 URL 來存取通訊錄服務`https://externalweb.contoso.com/abs/handler`
    
      - 當會議已定義並設定為 Lync Server 拓撲的一部分時，為 Office Web Apps 伺服器
        
        <div>
        

        > [!NOTE]  
        > Office Web Apps 伺服器是一個獨立的角色服務器，且未設定為外部 Web 服務的一部分。 此伺服器會另行發佈，以供用戶端存取。

        
        </div>

5.  針對每個服務定義 SSL 橋接。 外部埠 TCP 443 對應至 TCP 4443 的外部 web 服務埠。 針對未加密的 HTTP，埠 TCP 80 對應至外部 web 服務埠 TCP 8080

6.  規劃反向 proxy 監聽器以發佈 web 伺服器資源

7.  根據將提供的服務，要求並設定反向 proxy 的憑證。 如果使用正確的消費者替換名稱進行設定，則此憑證可以由反向 proxy 伺服器上所有已設定的偵聽程式共用

可用來規劃反向 proxy 部署的資源：

  - [Lync Server 2013 中的資料收集](lync-server-2013-data-collection.md)

  - [Lync Server 2013 中的憑證摘要 - 反向 Proxy](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Lync Server 2013 中的連接埠摘要 - 反向 Proxy](lync-server-2013-port-summary-reverse-proxy.md)

  - [Lync Server 2013 中的 DNS 摘要 - 反向 Proxy](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

