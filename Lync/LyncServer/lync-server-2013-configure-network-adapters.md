---
title: Lync Server 2013：設定網路介面卡
description: Lync Server 2013：設定網路介面卡。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fa6aaa76c7815c3c14f711bf79eca82c44551ce
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577589"
---
# <a name="configure-network-adapters-in-lync-server-2013"></a>在 Lync Server 2013 中設定網路介面卡

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

您必須指派一或多個 IP 位址給外部網路介面卡，同時至少指派一個 IP 位址給內部網路介面卡。

在下列程式中，執行 Forefront 威脅管理閘道的伺服器 (TMG) 2010 或 Internet Information Server 應用程式要求路由有兩個網路介面卡：

  - 公用 (外部) 網路介面卡，適用於嘗試連線至您的網站之用戶端 (亦即，通常是透過網際網路)。

  - 專用（或內部）網路介面，針對執行主控 Web 服務之 Lync Server 的內部伺服器。

<div>


> [!IMPORTANT]  
> 與 Edge Server 類似，您只會在外部網路介面卡上設定預設閘道。 預設閘道會是將流量導向網際網路之路由器或對外防火牆的 IP 位址。 對於從反向 Proxy 至對內網路介面卡的流量，必須將持續的靜態路由 (例如 Windows Server 中的 route 命令) 使用於包含由 Web 發行規則參照之伺服器的所有子網路。 設定持續性路由不會導致電腦成為路由器。 如果未啟用 IP 轉寄功能，則電腦只會作用於將另一個網路的特定流量定向至適當的介面。 這主要是設定兩個閘道，一個是指向外部網路的預設值，另一個則用於傳送至內部介面的流量，另一個則用於路由器或其他網路。<BR>然而，如果將網路的路由器設定為摘要路由，可能不需要為所有子網路建立持續路由。建立連線至已定義路由器之網路的持續路由，然後使用該路由器為預設閘道。如果不確定網路的設定方式，而且對需要建立的持續路由需要指引，請諮詢您公司的網路工程師。<BR>反向 proxy 必須能夠解析 DNS 主機 (內部 Director 或前端伺服器的) 記錄，以及 web 發佈規則中所使用的下一個躍點集區 Fqdn。 與 Edge Server 一樣，出於安全性考慮，建議您不要設定反向 proxy 使用位於內部網路的 DNS 伺服器。 這表示在周邊中需要 DNS 伺服器，或者，需要反向 Proxy 上的 HOST 檔案項目會將這每一個 FQDN 解析為伺服器的內部 IP 位址。



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a>設定反向 Proxy 電腦的網路介面卡

1.  在 Windows Server 2008、Windows Server 2008 R2、Windows Server 2012 或 Windows Server 2012 R2 伺服器上，以反向 proxy 的身分執行，按一下 [**開始**]，指向 [**控制台**]，按一下 [**網路與共享中心**]，然後按一下 [**變更介面卡設定**]，以開啟 [**變更配接器設定**]。

2.  以滑鼠右鍵按一下要用於外部介面的外部網路連線，然後按一下 **[內容]**。

3.  在 **[內容]** 頁面上，按一下 **[網路]** 索引標籤，並按一下 **[這個連線使用下列項目]** 清單中的 **[網際網路通訊協定第 4 版 (TCP/IPv4)]**，然後按一下 **[內容]**。

4.  在 **[網際網路通訊協定 (TCP/IP) 內容]** 頁面上，視需要設定網路介面卡所連接網路子網路的 IP 位址。
    
    <div>
    

    > [!NOTE]  
    > 如果反向 proxy 已由使用 HTTPS/TCP/443 的其他應用程式使用，例如，若要發佈 Outlook Web Access，您必須新增其他 IP 位址，以便在 HTTPS/TCP/443 上發行 Lync Server 2013 Web 服務，而不會干擾現有的規則和網頁攔截器，或者您必須將現有的憑證取代為主體替代名稱。

    
    </div>

5.  按一下 **[確定]**，然後再按一下 **[確定]**。

6.  在 **[網路連線]** 中，以滑鼠右鍵按一下要用於內部介面的內部網路連線，然後按一下 **[內容]**。

7.  重複步驟 3 到 5，設定內部網路連線。

</div>

</div>

<span> </span>

</div>

</div>

</div>

