---
title: Lync Server 2013：在拓撲建立器中定義其他 trunks
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c55e8073bd1ad1bb2db69096e4e58aa2b148e775
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a>在 Lync Server 2013 的拓撲產生器中定義其他 trunks

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

請依照下列步驟使用拓撲建立器來定義您可以將*對等*與轉送伺服器建立關聯的其他主幹。 對等可為使用者提供可連線至公用交換電話網絡（PSTN）的企業語音功能。 對等可以是 PSTN 閘道、IP PBX，或網際網路電話服務提供者（ITSP）的會話邊界控制器（SBC）。 幹線會在中繼伺服器與對等之間定義此連接。 您可以針對每個中繼伺服器定義多個 trunks。 中繼伺服器可以與多個對等建立關聯。

幹線是由元組唯一識別的中繼伺服器與閘道之間的邏輯連線：

{轉送伺服器 FQDN，中繼伺服器偵聽埠（TLS 或 TCP）：閘道 IP 和 FQDN，閘道偵聽埠}

<div>


> [!NOTE]  
> 本主題假設您已使用至少一個 collocated 或獨立的中繼伺服器或池來設定 PSTN 閘道和根幹線，如在部署檔中的<A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013 定義閘道</A>中所述。



</div>

<div>


> [!NOTE]  
> 本主題假設您已在至少一個中心網站中設定了至少一個前端池或標準版伺服器，如在<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 中定義及設定前端池或標準版伺服器</A>中所述，並在部署檔中<A href="lync-server-2013-publish-the-topology.md">發佈 lync server 2013 中的拓撲</A>。



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>在中繼伺服器與閘道對等之間定義額外主幹

1.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。

2.  在 Lync Server 2013、您的網站名稱、**共用元件**中，以滑鼠右鍵按一下 [ **Trunks** ] 節點，然後按一下 [**新主幹**]。
    
    ![Lync Server 拓撲產生器檔案結構畫面](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server 拓撲產生器檔案結構畫面")

3.  在 [**定義新主幹**] 中，指定要唯一識別主幹的易記名稱。 您不能有兩個名稱相同的 trunks。
    
    <div>
    

    > [!NOTE]  
    > 如果您將傳輸層安全性（TLS）指定為傳輸類型，您必須指定 FQDN，而不是對轉送伺服器對等的 IP 位址。

    
    </div>

4.  在 [**關聯的 PSTN 閘道**] 底下，選取 PSTN 閘道對，以與此幹線建立關聯。
    
    ![主幹之 PSTN 閘道對等的內容設定](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "主幹之 PSTN 閘道對等的內容設定")

5.  在 [ **PSTN 閘道的偵聽埠**] 底下，輸入對等（PSTN 閘道、IP PBX 或 SBC）的偵聽埠，將會從要與此幹線關聯的中繼伺服器接收 SIP 訊息。 預設對等埠是針對傳輸控制通訊協定（TCP）和5067（針對傳輸層安全性（TLS））的5066。 預設的 Survivable 分支裝置埠是適用于 TCP 的5081，以及適用于 TLS 的5082。

6.  在 [ **SIP 傳輸通訊協定**] 底下，按一下對等所使用的傳輸類型。
    
    <div>
    

    > [!NOTE]  
    > 出於安全性考慮，我們強烈建議您將對等部署到可使用 TLS 的中繼伺服器。

    
    </div>

7.  在 [**關聯的中繼伺服器**] 底下，選取 [轉送伺服器] 池以與此對等方的根幹線建立關聯

8.  在 [**關聯的中繼伺服器埠**] 底下，輸入中繼伺服器將從對等接收 SIP 訊息的偵聽埠。
    
    <div>
    

    > [!NOTE]  
    > 在 Lync Server 2013 有多個幹線支援的情況下，您無法使用相同的<STRONG>關聯中繼伺服器埠</STRONG>和<STRONG>偵聽埠（IP/PSTN 閘道</STRONG>）來設定具有不同主幹名稱的兩個 trunks

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 在 Lync Server 2013 有多個幹線支援的情況下，可以在中繼伺服器上定義多個 SIP 信號埠，以便與多個對等進行通訊。 在定義主幹時，<STRONG>關聯的中繼伺服器埠</STRONG>編號必須在中繼伺服器所允許之個別通訊協定的偵聽埠範圍內。 此埠範圍是在 Lync Server 2013 和中繼伺服器池底下定義。 以滑鼠右鍵按一下相關的中繼伺服器池，然後選取 [<STRONG>編輯屬性</STRONG>]。 在 [<STRONG>偵聽埠</STRONG>] 欄位中指定埠範圍。

    
    </div>

9.  按一下 [確定]****。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 的拓撲產生器中修改主幹](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

