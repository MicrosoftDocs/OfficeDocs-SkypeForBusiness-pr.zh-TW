---
title: Lync Server 2013： 在拓撲產生器中定義其他主幹
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
ms.openlocfilehash: 9f4c31dc9b3e23f591e1084ba649bf00a4c8a0f3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a>在 Lync Server 2013 中的拓撲產生器中定義其他主幹

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-04_

請遵循下列步驟，使用拓撲產生器來定義要您可以將關聯的*對等*中繼伺服器的其他主幹。 對等網路提供連線至公用交換的電話網路 (PSTN) 啟用 Enterprise Voice 的使用者。 PSTN 閘道、 IP PBX 或工作階段界限控制器 (SBC) 的網際網路電話語音服務提供者 (ITSP)，可以是對等。 主幹定義此中繼伺服器和對等之間的連線。 每個中繼伺服器，您可以定義多個主幹。 中繼伺服器可與多個對等相關聯。

主幹是中繼伺服器與專門由 tuple 識別閘道之間的邏輯連接：

{中繼伺服器 FQDN] 中，中繼伺服器接聽連接埠 （TLS 或 TCP）： 閘道 IP 與 FQDN、 閘道聆聽連接埠}

<div>


> [!NOTE]  
> 本主題假設您所安裝的 PSTN 閘道與根主幹，且至少一個使用組合式還是獨立式中繼伺服器或集區中所述<A href="lync-server-2013-define-a-gateway-in-topology-builder.md">定義在 Lync Server 2013 中的拓撲產生器的閘道</A>部署文件中。



</div>

<div>


> [!NOTE]  
> 本主題假設您已設定至少一個前端集區或 Standard Edition server 在至少一個中央網站中所述<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">定義和設定 Lync Server 2013 中的前端集區或 Standard Edition server</A>和<A href="lync-server-2013-publish-the-topology.md">發佈 Lync Server 2013 中的拓撲</A>中部署文件。



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>若要定義中繼伺服器和閘道對等之間的其他主幹

1.  啟動拓撲產生器： 按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。

2.  在 [Lync Server 2013 中，您的網站名稱，**共用元件**，以滑鼠右鍵按一下 [**主幹**] 節點中，然後再按一下 [**新主幹**。
    
    ![Lync Server 拓撲產生器檔案結構畫面](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server 拓撲產生器檔案結構畫面")

3.  在 [**定義新的主幹**，指定來唯一地識別主幹的易記名稱。 您不能有相同名稱的兩個主幹。
    
    <div>
    

    > [!NOTE]  
    > 如果您指定傳輸層安全性 (TLS) 作為傳輸類型，您必須指定的 FQDN，而不是對等的中繼伺服器的 IP 位址。

    
    </div>

4.  在 [**關聯的 PSTN 閘道**] 中，選取要與此主幹建立關聯的 PSTN 閘道對等。
    
    ![主幹的 PSTN 閘道對等的屬性設定](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "主幹的 PSTN 閘道對等的屬性設定")

5.  [ **PSTN 閘道的聆聽連接埠**，] 下方輸入 [聆聽連接埠，對等網路 （PSTN 閘道、 IP-PBX 或 SBC） 會接收 SIP 訊息是要與此主幹建立關聯的中繼伺服器。 預設的對等網路連接埠是 5066 傳輸控制通訊協定 (TCP) 及 5067 用於傳輸層安全性 (TLS)。 預設 Survivable Branch Appliance 連接埠是 5081 tcp 和 tls 5082。

6.  在 [ **SIP 傳輸通訊協定**] 下按一下對等使用的傳輸類型。
    
    <div>
    

    > [!NOTE]  
    > 基於安全性考量，我們強烈建議您將對等部署至中繼伺服器可以使用 TLS。

    
    </div>

7.  在 [**相關中繼伺服器**，選取要與此對等的根主幹建立關聯的中繼伺服器集區

8.  在 [**相關中繼伺服器連接埠**，輸入中繼伺服器將會從對等接收 SIP 訊息的聆聽連接埠。
    
    <div>
    

    > [!NOTE]  
    > 支援多個主幹 Lync Server 2013 中，兩個不同主幹名稱的主幹不能設定同一個<STRONG>相關聯的中繼伺服器連接埠</STRONG>與<STRONG>IP/PSTN 閘道的聆聽連接埠</STRONG>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 支援多個主幹 Lync Server 2013 中，多個 SIP 訊號連接埠可定義通訊中繼伺服器上具有多個對等。 定義主幹時, 的<STRONG>相關聯的中繼伺服器連接埠</STRONG>號碼必須範圍內的個別中繼伺服器所允許的通訊協定的聆聽連接埠。 此連接埠範圍定義在 Lync Server 2013 和中繼伺服器集區之下。 以滑鼠右鍵按一下相關的中繼伺服器集區]，然後選取 [<STRONG>編輯內容]</STRONG>。 在 <STRONG>[聆聽連接埠]</STRONG> 欄位中指定連接埠範圍。

    
    </div>

9.  按一下 [確定]****。

</div>

<div>

## <a name="see-also"></a>另請參閱


[修改主幹在 Lync Server 2013 中的拓撲產生器](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

