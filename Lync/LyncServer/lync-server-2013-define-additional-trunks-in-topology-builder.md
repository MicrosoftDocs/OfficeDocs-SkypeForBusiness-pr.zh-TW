---
title: Lync Server 2013：在拓撲產生器中定義其他主幹
description: Lync Server 2013：在拓撲產生器中定義其他主幹。
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
ms.openlocfilehash: 57983d3e4d6a47c14f2dcdc153fe6872a33eb6e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567559"
---
# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a>在 Lync Server 2013 中的拓撲產生器中定義其他主幹

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

請遵循下列步驟，使用拓撲產生器來定義您可以將 *對等* 與轉送伺服器產生關聯的其他主幹。 對等使用者可為使用者啟用企業語音，以連線到公用交換電話網路 (PSTN) 。 對等可以是 Internet 電話語音服務提供者的 PSTN 閘道、IP-PBX 或會話邊界控制器 (SBC)  (ITSP) 。 主幹定義轉送伺服器和對等之間的連線。 每個轉送伺服器可以定義多個主幹。 轉送伺服器可以與多個對等專案產生關聯。

主幹是由元組唯一識別的轉送伺服器與閘道之間的邏輯連接：

{轉送伺服器 FQDN、轉送伺服器接聽埠 (TLS 或 TCP) ：閘道 IP 和 FQDN，閘道聆聽埠}

<div>


> [!NOTE]  
> 本主題假設您已安裝具有至少一個組合或獨立轉送伺服器或集區的 PSTN 閘道和根主幹，如在部署檔中的 [在 Lync Server 2013 中的拓撲產生器中 <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">定義閘道</A> ] 所述。



</div>

<div>


> [!NOTE]  
> 本主題假設您已在至少一個中央網站中設定至少一個前端集區或 Standard Edition server，如在 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 中定義及設定前端集區或 Standard edition server</A> ，以及在部署檔中 <A href="lync-server-2013-publish-the-topology.md">發佈 lync server 2013</A> 中所述的拓撲。



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>在轉送伺服器與閘道對等間定義其他主幹

1.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

2.  在 [Lync Server 2013] 底下，您的網站名稱， **共用元件**，以滑鼠右鍵按一下 **主幹** 節點，然後按一下 [ **新增主幹**]。
    
    ![Lync Server 拓撲產生器檔結構畫面](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server 拓撲產生器檔結構畫面")

3.  在 [ **定義新的主幹**] 中，指定可唯一識別主幹的易記名稱。 您不能有兩個具有相同名稱的主幹。
    
    <div>
    

    > [!NOTE]  
    > 如果您指定傳輸層安全性 (TLS) 做為傳輸類型，您必須指定 FQDN 而非轉送伺服器對等的 IP 位址。

    
    </div>

4.  在 [ **關聯的 pstn 閘道**] 底下，選取 PSTN 閘道對等相關聯的主幹。
    
    ![PSTN 閘道對等屬性設定（適用于主幹）](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "PSTN 閘道對等屬性設定（適用于主幹）")

5.  在 [ **適用于 PSTN 閘道的聆聽埠**] 底下，輸入對等 (PSTN 閘道、IP-PBX 或 SBC) 將要從轉送伺服器接收 SIP 郵件的收聽埠，該伺服器將會與此主幹產生關聯。 傳輸控制通訊協定 (TCP) 和5067的傳輸層安全性 (TLS) 的預設對等埠為5066。 Survivable 的預設分支裝置埠是5081的 TCP 和5082的 TLS。

6.  在 [ **SIP 傳輸通訊協定**] 下，按一下對等使用的傳輸類型。
    
    <div>
    

    > [!NOTE]  
    > 基於安全性考慮，強烈建議您將對等部署至可使用 TLS 的轉送伺服器。

    
    </div>

7.  在 [關聯的中繼 **伺服器**] 底下，選取要與此對等的根主幹相關聯的轉送伺服器集區。

8.  在 [關聯的中繼 **伺服器埠**] 底下，輸入轉送伺服器接收來自對等的 SIP 訊息的聆聽埠。
    
    <div>
    

    > [!NOTE]  
    > 在 Lync Server 2013 中有多個主幹支援，無法使用<STRONG>IP/PSTN 閘道</STRONG>的相同<STRONG>關聯轉送伺服器埠</STRONG>和偵聽埠來設定具有不同主幹名稱的兩個主幹

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 在 Lync Server 2013 中有多個主幹支援，可在轉送伺服器上定義多個 SIP 信號埠，以與多個對等機進行通訊。 在定義主幹時，關聯的中繼 <STRONG>伺服器埠</STRONG> 號碼必須位於轉送伺服器所允許之個別通訊埠的偵聽埠範圍內。 此埠範圍是在 [Lync Server 2013 和轉送伺服器集區] 下定義。 在相關的轉送伺服器集區上按一下滑鼠右鍵，然後選取 [ <STRONG>編輯屬性</STRONG>]。 在 <STRONG>[聆聽連接埠]</STRONG> 欄位中指定連接埠範圍。

    
    </div>

9.  按一下 [確定]****。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中的拓撲產生器中修改主幹](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

