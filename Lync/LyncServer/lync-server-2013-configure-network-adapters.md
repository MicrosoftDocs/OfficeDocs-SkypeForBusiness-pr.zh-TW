---
title: Lync Server 2013： 設定網路介面卡
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
ms.openlocfilehash: 7b239d4da0d37280df69f231d7d590f0846f0ee4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a>在 Lync Server 2013 中設定網路介面卡

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-11-07_

您必須指派一或多個 IP 位址給外部網路介面卡，同時至少指派一個 IP 位址給內部網路介面卡。

下列程序，在執行 Forefront Threat Management Gateway (TMG) 2010年或網際網路資訊伺服器應用程式要求路由傳送的伺服器會有兩個網路介面卡：

  - 公用 (外部) 網路介面卡，適用於嘗試連線至您的網站之用戶端 (亦即，通常是透過網際網路)。

  - 私用，或內部網路介面，執行 Lync Server 的內部伺服器的主控 Web 服務。

<div>


> [!IMPORTANT]  
> 類似於 Edge Server，您的預設閘道上設定外部網路介面卡僅。 預設閘道會是將流量導向網際網路之路由器或對外防火牆的 IP 位址。 對於從反向 Proxy 至對內網路介面卡的流量，必須將持續的靜態路由 (例如 Windows Server 中的 route 命令) 使用於包含由 Web 發行規則參照之伺服器的所有子網路。 設定一個持續的路由，不會造成成為路由器的電腦。 如果未啟用 IP 轉寄，電腦做只以將特定目的地是另一個網路，以適當的介面的流量導向。 這基本上設定兩個閘道 – 1 才能做為指向的外部網路，，一個用於內部介面並登入該路由器或其他網路流量的預設值。<BR>然而，如果將網路的路由器設定為摘要路由，可能不需要為所有子網路建立持續路由。建立連線至已定義路由器之網路的持續路由，然後使用該路由器為預設閘道。如果不確定網路的設定方式，而且對需要建立的持續路由需要指引，請諮詢您公司的網路工程師。<BR>反向 proxy 必須能夠解析內部 Director 或前端伺服器的 DNS 主機 (A) 記錄，並在網頁發行規則中使用下一個躍點集區 Fqdn。 就像 Edge Server，基於安全性考量，建議您不需設定為使用位於內部網路 DNS 伺服器的反向 proxy。 這表示在周邊中需要 DNS 伺服器，或者，需要反向 Proxy 上的 HOST 檔案項目會將這每一個 FQDN 解析為伺服器的內部 IP 位址。



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a>設定反向 Proxy 電腦的網路介面卡

1.  在 Windows Server 2008、 Windows Server 2008 R2、 Windows Server 2012 或 Windows Server 2012 R2 伺服器正在執行與反向 proxy，開啟 [按一下**啟動**，指向 **[控制台]**、 [**網路和共用中心**]，然後按一下 [**變更介面卡設定**[**變更介面卡設定**]。

2.  以滑鼠右鍵按一下要用於外部介面的外部網路連線，然後按一下 **[內容]**。

3.  在 **[內容]** 頁面上，按一下 **[網路]** 索引標籤，並按一下 **[這個連線使用下列項目]** 清單中的 **[網際網路通訊協定第 4 版 (TCP/IPv4)]**，然後按一下 **[內容]**。

4.  在 **[網際網路通訊協定 (TCP/IP) 內容]** 頁面上，視需要設定網路介面卡所連接網路子網路的 IP 位址。
    
    <div>
    

    > [!NOTE]  
    > 如果反向 proxy 已經由其他應用程式，如使用 HTTPS/TCP/443，發佈 Outlook Web Access 中，您 [要新增另一個 IP 位址，以便您可以將 Lync Server 2013 Web 服務，在 HTTPS/TCP/443 上發佈而不干擾現有規則及 web 接聽程式，或您要將新的外部 FQDN 名稱新增至主體替代名稱的其中一個取代現有的憑證。

    
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

