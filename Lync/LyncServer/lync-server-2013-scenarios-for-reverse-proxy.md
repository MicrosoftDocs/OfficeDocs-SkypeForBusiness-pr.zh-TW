---
title: 反向 proxy 的 Lync Server 2013： 案例
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
ms.openlocfilehash: af3b987cfc1a982139aa0151e43918f0ed082034
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 中的反向 proxy 案例

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-01-21_

反向 proxy 所需 Lync Server 2013 中提供的服務和資源，例如會議和撥入簡單 Url、 通訊錄、 會議內容、 通訊群組清單擴充、 行動性服務和其他人存取。 Lync Server 2013 中的一般反向 proxy 案例是允許外部用戶端 （例如，桌面用戶端或 Lync Web App 用戶端） 存取 Director 或前端伺服器的外部 Web 服務。

**反向 proxy 及外部 web 服務**

![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")

在規劃階段，您可以定義反向 proxy 需求 Lync Server 2013 部署中。 反向 proxy 啟用下列外部用戶端存取功能：

  - Microsoft Lync 2013 桌面用戶端

  - Microsoft Lync Web App

  - Microsoft Lync Mobile

  - Lync Windows 市集應用程式

當您在規劃 Lync Server 2013 部署，您會將 Lync Server 2013 的實際需求對應至反向 proxy 功能。

1.  外部用戶端會連線到連接埠 TCP 443 上的反向 proxy，並會使用安全通訊端層 (SSL) 或傳輸層安全性 (TLS)。 Microsoft Lync 行動用戶端可以連線連接埠 TCP 80，但是只有當執行初始連線至 Lync 探索服務及系統管理員已設定適當的網域名稱系統 (DNS) CNAME （或別名） 記錄，並接受該這將不會加密的通訊。

2.  Lync Server 2013 外部 web 服務 （前端伺服器及/或 Director 上部署） 預期從連接埠 TCP 4443 上的反向 proxy 的連線，它會預期連線將 SSL/TLS。
    
    <div>
    

    > [!IMPORTANT]  
    > 外部 web 服務的建議的預設聆聽連接埠是 TCP 8080 HTTP 流量，以及 TCP 4443 用於 HTTPS 流量。 拓撲產生器可提供機會讓覆寫預設值，並定義您自己的外部 web 服務的聆聽連接埠。 請務必注意反向 proxy 進行通訊的外部 web 服務，並與反向 proxy 的外部用戶端進行通訊。 外部用戶端會與連接埠 TCP 443 上的反向 proxy 進行通訊，但是您可以重新定義反向 proxy 會與上的外部 web 服務進行通訊的連接埠。 在拓撲產生器的選項來覆寫預設的聆聽連接埠的 web 服務可讓您解決可能發生在您的基礎結構的聆聽連接埠衝突。

    
    </div>

3.  Lync Server 2013 外部 web 服務預期用戶端來識別哪些服務未修改的主機標頭及 web 伺服器目錄用戶端嘗試使用。 要求應該看起來好像他們來自反向 proxy

4.  外部 web 服務使用定義的 web 伺服器虛擬目錄 (vDir) 提供給用戶端提供服務。 是特定外部識別 web 服務：
    
      - 「 符合 「 vDir web 會議會議
    
      - 適用於電話存取和電話會議 」 Dialin 」 vDir
    
      - Lync Windows 市集應用程式、 Lync Mobile 和 Lync 2013 的桌面用戶端 「 自動探索 」 vDir。 Lync Server 2013 中的自動探索已知 DNS 名稱"lyncdiscover"
    
      - 外部用戶端存取來直接呼叫的外部 web 服務的服務未定義的。 例如，通訊群組擴充 (DLX) 和通訊錄服務 (ABS) 以存取直接呼叫的外部 web 服務和相關聯的 vDirs。 用戶端至 vDir 知道的實際路徑，並建構根據這項資訊統一記錄定位器 (URL)。 用戶端可存取通訊錄服務使用類似的 URL`https://externalweb.contoso.com/abs/handler`
    
      - Office Web Apps Server 時會議是定義及設定 Lync Server 拓撲的一部分
        
        <div>
        

        > [!NOTE]  
        > Office Web Apps Server 是不同的角色伺服器，且未設定的外部 web 服務的一部分。 此伺服器分開發佈的用戶端存取。

        
        </div>

5.  定義 SSL 橋接的每項服務。 外部連接埠 TCP 443 會對應至外部 web 服務的連接埠 TCP 4443。 未加密 http 連接埠 TCP 80 會對應至外部 web 服務連接埠 TCP 8080

6.  若要發佈的 web 伺服器資源的反向 proxy 接聽程式的計劃

7.  要求，並設定為基礎的服務，則會提供反向 proxy 的憑證。 此憑證如果設定正確的主體替代名稱，可以共用的反向 proxy 伺服器上的所有設定接聽程式

可用來規劃反向 Proxy 部署的資源：

  - [Lync Server 2013 中的資料收集](lync-server-2013-data-collection.md)

  - [憑證摘要-Lync Server 2013 中的反向 proxy](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [連接埠摘要-Lync Server 2013 中的反向 proxy](lync-server-2013-port-summary-reverse-proxy.md)

  - [DNS 摘要-Lync Server 2013 中的反向 proxy](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

