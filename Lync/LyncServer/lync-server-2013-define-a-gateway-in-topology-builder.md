---
title: Lync Server 2013： 在拓撲產生器中定義閘道
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a0c03c286b5d9ad57f1422478bed6b7c3048a73
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a>在 Lync Server 2013 中的拓撲產生器中定義閘道

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-04_

請遵循下列步驟，使用拓撲產生器來定義與建立關聯的中繼伺服器已啟用企業語音之使用者提供連線至公用交換的電話網路 (PSTN)*對等*。 對等網路，到中繼伺服器可以是 PSTN 閘道、 IP PBX 或工作階段界限控制器 (SBC) 的網際網路電話語音服務提供者 (ITSP) 您藉由設定 SIP 主幹連接。

<div>


> [!NOTE]  
> 本主題假設您已設定至少一個內部的前端集區或 Standard Edition server 中使用組合式還是獨立式中繼伺服器，具有至少一個中央網站中所述<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">定義和設定 Lync Server 2013 中的前端集區或 Standard Edition server</A>和<A href="lync-server-2013-publish-the-topology.md">發佈 Lync Server 2013 中的拓撲</A>中部署文件。 本主題也假設您已經驗證您的基礎結構符合<A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Lync Server 2013 中的 Enterprise Voice 的軟體先決條件</A>和<A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Lync Server 2013 中的 Enterprise voice 的安全性和組態必要條件</A>中所述的先決條件。



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a>定義中繼伺服器的對等

1.  啟動拓撲產生器： 按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。

2.  在 [Lync Server 2013 中，您的網站名稱，共用元件]，以滑鼠右鍵按一下 [ **PSTN 閘道**] 節點，然後再按一下 [**新的 PSTN 閘道**。
    
    ![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")

3.  在 **[定義新的 IP/PSTN 閘道]** 中，輸入對等的完整網域名稱 (FQDN) 或 IP 位址，然後按一下 **[下一步]**。
    
    ![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")
    
    <div>
    

    > [!NOTE]  
    > 如果您指定傳輸層安全性 (TLS) 作為傳輸類型，您必須指定的 FQDN，而不是對等的中繼伺服器的 IP 位址。

    
    </div>

4.  定義您新的 PSTN 閘道的 IP 位址的聆聽模式 (IPv4 或 IPv6)，然後按一下 **[下一步]**。
    
    ![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")

5.  定義 PSTN 閘道的*根主幹*。 主幹是中繼伺服器與專門由 tuple 識別閘道之間的邏輯連線。
    
    {中繼伺服器 FQDN] 中，中繼伺服器接聽連接埠 （TLS 或 TCP）： 閘道 IP 與 FQDN、 閘道聆聽連接埠}
    
      - 在拓撲產生器中定義 PSTN 閘道，您必須定義根主幹，才能成功新增至您的拓撲的 PSTN 閘道。
    
      - 必須先移除關聯的 PSTN 閘道，才能移除根主幹。
    
    ![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")

6.  在 [ **IP/PSTN 閘道的聆聽連接埠**，輸入閘道、 PBX 或 SBC 將用來從要與 PSTN 閘道的根主幹建立關聯的中繼伺服器的 SIP 訊息的聆聽連接埠。 （預設的連接埠是 5066 傳輸控制通訊協定 (TCP) 及 5067 PSTN 閘道、 PBX 或 SBC 上的傳輸層安全性 (TLS)。 Survivable Branch Appliance 分支網站，在預設連接埠是 5081 tcp 及 tls 5082）。

7.  在 **[SIP 傳輸通訊協定]** 下，按一下對等使用的傳輸類型，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 基於安全性考量，我們強烈建議您將對等部署至中繼伺服器可以使用 TLS。

    
    </div>

8.  在 [**相關中繼伺服器**，選取要與這個 PSTN 閘道的根主幹建立關聯的中繼伺服器集區。

9.  在 [**相關中繼伺服器連接埠**，輸入中繼伺服器用於來自閘道的 SIP 訊息的聆聽連接埠。
    
    <div>
    

    > [!NOTE]  
    > 支援多個主幹 Lync Server 2013 中，可以定義多個 SIP 信號連接埠中繼伺服器用於與多個 PSTN 閘道的通訊。 定義主幹時,<STRONG>相關聯的中繼伺服器連接埠</STRONG>必須範圍內的個別中繼伺服器所允許的通訊協定的聆聽連接埠。 Lync Server 2013 與中繼集區] 底下定義這個連接埠範圍。 感興趣，中繼伺服器集區上按一下滑鼠右鍵，然後選取 [<STRONG>編輯內容]</STRONG>。 在 <STRONG>[聆聽連接埠]</STRONG> 欄位中指定連接埠範圍。

    
    </div>

10. 按一下 **[完成]**。

<div>


> [!IMPORTANT]  
> 繼續下一個步驟之前，請確定您定義的對等正在執行中，且使用您指定的 FQDN 或 IP 位址。



</div>

接下來，若要新增至拓撲的對等網路，請遵循[發佈 Lync Server 2013 中的拓撲](lync-server-2013-publish-the-topology.md)中部署文件中的程序。 您必須發佈您的拓樸每次您建立或修改您的拓撲，使用拓撲產生器，使資料可以用來安裝在執行 Lync Server 伺服器的檔案。

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

