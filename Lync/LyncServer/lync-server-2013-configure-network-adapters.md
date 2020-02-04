---
title: Lync Server 2013：設定網路介面卡
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
ms.openlocfilehash: 30889a6b145e7256a313c4deedafc74d99499719
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a>在 Lync Server 2013 中設定網路介面卡

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

您必須將一個或多個 IP 位址指派給外部網路介面卡，並將至少一個 IP 位址指派給內部網路介面卡。

在下列程式中，執行 Forefront 威脅管理閘道（TMG）2010或 Internet Information Server 應用程式要求路由的伺服器會有兩個網路介面卡：

  - 公用或外部網路介面卡，適用于嘗試連線至您的網站的用戶端（通常是透過網際網路）。

  - 一種專用或內部網路介面，適用于執行承載 Web 服務之 Lync Server 的內部伺服器。

<div>


> [!IMPORTANT]  
> 與邊緣伺服器類似，您只能在外部網路介面卡上設定預設閘道。 預設閘道將是路由器的 IP 位址，或將流量導向網際網路的外部防火牆。 針對寄件者為從反向 proxy 傳送到內部面向內部網路介面卡的流量，您必須針對所有包含 web 發佈規則所參照之伺服器的子網，使用永久靜態路由（例如 Windows Server 中的 route 命令）。 設定持久路由不會導致電腦成為路由器。 如果沒有啟用 IP 轉寄，電腦只會作用至將特定通信量傳送給另一個網路至適當的介面。 這主要是設定兩個閘道，一個是指向外部網路的預設閘道，另一個是傳送給內部介面並移至路由器或其他網路的通信量。<BR>不過，如果您的網路路由器設定為 [摘要路由]，則可能不需要為所有子網建立持久路由。 建立一個持久路由至定義路由器的網路，然後使用路由器作為預設閘道。 如果您不確定網路的設定方式，而且需要建立何種持久路由的指導方針，請諮詢貴公司的網路工程師。<BR>反向 proxy 必須能夠解析內部控制器或前端伺服器的 DNS 主機（A）記錄，以及 web 發佈規則中使用的下一個躍點池 Fqdn。 與邊緣伺服器一樣，出於安全性考慮，我們建議您不要將反向 proxy 設定為使用位於內部網路中的 DNS 伺服器。 這表示您可能需要在週邊伺服器中都有 DNS 伺服器，否則您需要將這些 Fqdn 解析成伺服器內部 IP 位址的反向 proxy 上的主機檔案專案。



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a>在反向 proxy 電腦上設定網路介面卡

1.  在 Windows Server 2008、Windows Server 2008 R2、Windows Server 2012 或以反向 proxy 身份執行的 Windows Server 2012 R2 伺服器上，按一下 [**開始**]，指向 [**控制台**]，按一下 [**網路和共用中心**]，然後按一下 [**變更配接器設定**]，即可開啟 [**變更配接器設定**]。

2.  以滑鼠右鍵按一下您要用於外部介面的外部網路連線，然後按一下 [**屬性**]。

3.  在 [**屬性**] 頁面上，按一下 [**網路**] 索引標籤，按一下 [**此連線使用下列專案**] 清單中的 **[網際網路通訊協定版本4（TCP/IPv4）** ]，然後按一下 [**屬性**]。

4.  在 [**網際網路通訊協定（tcp/ip）屬性**] 頁面上，針對要連接網路介面卡的網路子網，設定適當的 IP 位址。
    
    <div>
    

    > [!NOTE]  
    > 如果反向 proxy 已由使用 HTTPS/TCP/443 的其他應用程式使用，例如，若要發佈 Outlook Web Access，您需要新增另一個 IP 位址，以便在 HTTPS/TCP/443 上發佈 Lync Server 2013 Web 服務，而不會干擾現有的規則和網頁偵聽程式，或者您需要取代現有的憑證，並將新的外部 FQDN 名稱新增到 subject 替換名稱。

    
    </div>

5.  按一下 **[確定]**，然後按一下 **[確定]**。

6.  在 [**網路**連線] 中，以滑鼠右鍵按一下您要用於內部介面的內部網路連線，然後按一下 [**屬性**]。

7.  重複步驟3到5，設定內部網路連線。

</div>

</div>

<span> </span>

</div>

</div>

</div>

