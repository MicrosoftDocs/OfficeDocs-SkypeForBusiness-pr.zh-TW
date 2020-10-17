---
title: Lync Server 2013：反向 proxy 案例
description: Lync Server 2013：反向 proxy 案例。
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
ms.openlocfilehash: cb714182fd13e42c6295e26ffd1edbb8b6041866
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561989"
---
# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 中的反向 proxy 案例

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-21_

Lync Server 2013 需要反向 proxy，以提供對服務和資源的存取，例如會議和電話撥入式的簡易 URLs、通訊錄、會議內容、通訊群組清單展開、行動服務等等。 Lync Server 2013 中的一般反向 proxy 案例是允許外部用戶端 (例如，桌面用戶端或 Lync Web App 用戶端) 存取 Director 或前端伺服器的外部 Web 服務。

**反向 proxy 和外部 web 服務**

![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")

在規劃階段期間，您可以在 Lync Server 2013 部署中定義反向 proxy 的需求。 反向 proxy 啟用下列外部用戶端的功能存取：

  - Microsoft Lync 2013 桌面用戶端

  - Microsoft Lync Web App

  - Microsoft Lync Mobile

  - Lync Windows Store 應用程式

規劃 Lync Server 2013 部署時，會將 Lync Server 2013 的實際需求對應至反向 proxy 功能。

1.  外部用戶端會連接到埠 TCP 443 上的反向 proxy，並使用安全通訊端層 (SSL) 或傳輸層安全性 (TLS) 。 Microsoft Lync Mobile 用戶端可以在埠 TCP 80 上進行連線，但只有在執行 Lync 探索服務的初始連線時，系統會將正確的網域名稱系統設定 (DNS) CNAME (或別名) 記錄，並接受此通訊不會加密。

2.  Lync Server 2013 在前端伺服器及（或） Director) 上部署的外部 web 服務 (會期望從埠 TCP 4443 上的反向 proxy 進行連線，並且預期會 SSL/TLS 該連線。
    
    <div>
    

    > [!IMPORTANT]  
    > 建議的外部 web 服務預設收聽埠為 TCP 8080，用於 HTTP 流量，TCP 4443 用於 HTTPS 流量。 拓撲產生器提供的機會可以覆寫預設值，並定義您自己的外部 web 服務偵聽埠。 請務必注意，反向 proxy 會與外部 web 服務進行通訊，而外部用戶端則會與反向 proxy 進行通訊。 外部用戶端與埠 TCP 443 上的反向 proxy 進行通訊，但您可以重新定義反向 proxy 與上的外部 web 服務進行通訊的埠。 拓撲產生器中的選項可覆寫 web 服務的預設聆聽埠，可讓您解決基礎結構中可能發生的偵聽埠衝突。

    
    </div>

3.  Lync Server 2013 外部 web 服務期望來自用戶端的未修改主機標頭，以識別用戶端嘗試使用的服務和網頁伺服器目錄。 要求應顯示為來自反向 proxy

4.  [外部 web 服務] 使用定義的網頁伺服器虛擬目錄 (vDir) ，提供提供給用戶端的服務。 特定的外部可識別 web 服務如下：
    
      - Web 會議會議的「開會」 vDir
    
      - 用於電話存取及電話會議的「撥入」 vDir
    
      - Lync Windows Store 應用程式、Lync Mobile 和桌面用戶端 Lync 2013 的「自動探索」 vDir。 Lync Server 2013 中的自動探索是由 DNS 名稱 "lyncdiscover" 所知道
    
      - 未定義的服務會透過直接呼叫外部 web 服務的方式來存取外部用戶端。 例如，通訊群組擴充 (DLX) 和通訊錄服務 (ABS) 是透過直接呼叫外部 web 服務及關聯的 vDirs 來存取。 用戶端知道 vDir 的實際路徑，並根據此資訊建立統一記錄定位器 (URL) 。 用戶端會使用類似于的 URL 來存取通訊錄服務。 `https://externalweb.contoso.com/abs/handler`
    
      - 當會議已定義並設定為 Lync Server 拓撲的一部分時，Office Web Apps Server
        
        <div>
        

        > [!NOTE]  
        > Office Web Apps Server 是個別的角色服務器，未設定為外部 Web 服務的一部分。 此伺服器會另行發佈，以供用戶端存取使用。

        
        </div>

5.  定義每個服務的 SSL 橋接。 外部埠 TCP 443 會對應至 TCP 4443 的外部 web 服務埠。 如果是未加密的 HTTP，埠 TCP 80 會對應至外部 web 服務埠 TCP 8080

6.  規劃反向 proxy 攔截器以發佈網頁伺服器資源

7.  根據所提供的服務，要求並設定反向 proxy 的憑證。 如果使用正確的主體替代名稱加以設定，則反向 proxy 伺服器上的所有已設定監聽器都可以共用此憑證

可用來規劃反向 Proxy 部署的資源：

  - [Lync Server 2013 中的資料收集](lync-server-2013-data-collection.md)

  - [Lync Server 2013 的憑證摘要-反向 proxy](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Lync Server 2013 中的埠摘要-反向 proxy](lync-server-2013-port-summary-reverse-proxy.md)

  - [Lync Server 2013 中的 DNS 摘要-反向 proxy](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

