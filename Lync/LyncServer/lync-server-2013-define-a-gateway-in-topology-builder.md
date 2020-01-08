---
title: Lync Server 2013：在拓撲建立器中定義閘道
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c9e57ad4e3d8c1692731bcfd4a56dc5c3d05bda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a>在 Lync Server 2013 的拓撲產生器中定義閘道

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

請依照下列步驟使用拓撲 Builder 來定義對等，您可以將該*對等*與中繼伺服器建立關聯，以便為啟用企業語音的使用者提供公用的交換電話網絡（PSTN）連線。 對轉送伺服器的對等可以是 PSTN 閘道、IP PBX 或會話邊界控制器（ITSP），您可以透過設定 SIP 幹線來連線該服務提供者。

<div>


> [!NOTE]  
> 本主題假設您已在至少一個中央網站使用 collocated 或獨立的快顯伺服器設定至少一個內部前端池或標準版伺服器，如在<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 中定義及設定前端池或標準版伺服器</A>，並在部署檔中<A href="lync-server-2013-publish-the-topology.md">發佈 lync server 2013 中的拓撲</A>中所述。 本主題也假設您已確認您的基礎結構符合<A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Lync server 2013 中的企業語音軟體必備</A>元件中所述的先決條件，以及<A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">適用于 lync server 2013 中之企業語音的安全性與設定先決條件</A>。



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a>若要為中繼伺服器定義對等

1.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。

2.  在 [Lync Server 2013]、[您的網站名稱]、[共用元件] 底下，以滑鼠右鍵按一下**PSTN 閘道**節點，然後按一下 [**新 pstn 閘道**]。
    
    ![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")

3.  在 [**定義新的 IP/PSTN 閘道**] 中，輸入對等的完整功能變數名稱（FQDN）或 IP 位址，然後按 **[下一步]**。
    
    ![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")
    
    <div>
    

    > [!NOTE]  
    > 如果您將傳輸層安全性（TLS）指定為傳輸類型，您必須指定 FQDN，而不是對轉送伺服器對等的 IP 位址。

    
    </div>

4.  定義新 PSTN 閘道之 IP 位址的偵聽模式（IPv4 或 IPv6），然後按 **[下一步]**。
    
    ![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")

5.  為 PSTN 閘道定義*根幹線*。 幹線是由元組唯一識別的中繼伺服器與閘道之間的邏輯連線。
    
    {轉送伺服器 FQDN，中繼伺服器偵聽埠（TLS 或 TCP）：閘道 IP 和 FQDN，閘道偵聽埠}
    
      - 在拓撲建立器中定義 PSTN 閘道時，您必須定義根幹線，才能成功將 PSTN 閘道新增到您的拓撲。
    
      - 移除關聯的 PSTN 閘道之後，才能移除根主幹。
    
    ![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")

6.  在 [ **IP/PSTN 閘道偵聽埠**] 底下，輸入閘道、PBX 或 SBC 將用來處理來自中繼伺服器的 SIP 訊息的偵聽埠，該埠會與 PSTN 閘道的根幹線產生關聯。 （根據預設，埠在 PSTN 閘道、PBX 或 SBC 上的傳輸控制通訊協定（TCP）和5067（針對傳輸層安全性（TLS））都是5066。 在分支網站的 Survivable 分支裝置上，預設埠為5081（適用于 TCP，而5082則為 TLS）。）

7.  在 [ **SIP 傳輸通訊協定**] 底下，按一下對等所使用的傳輸類型，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 出於安全性考慮，我們強烈建議您將對等部署到可使用 TLS 的中繼伺服器。

    
    </div>

8.  在 [**關聯的中繼伺服器**] 底下，選取 [中繼伺服器] 池以與此 PSTN 閘道的根幹線建立關聯。

9.  在 [**關聯的中繼伺服器埠**] 底下，輸入中繼伺服器將用於來自閘道的 SIP 訊息的偵聽埠。
    
    <div>
    

    > [!NOTE]  
    > 在 Lync Server 2013 有多個幹線支援的情況下，您可以在轉送伺服器上定義多個 SIP 信號埠，以用於與多個 PSTN 閘道進行通訊。 在定義主幹時，<STRONG>關聯的中繼伺服器埠</STRONG>必須位於中繼伺服器所允許之各個通訊協定的偵聽埠範圍內。 此埠範圍是在 Lync Server 2013 和轉送緩衝集區底下定義。 以滑鼠右鍵按一下感興趣的中繼伺服器池，然後選取 [<STRONG>編輯屬性</STRONG>]。 在 [<STRONG>偵聽埠</STRONG>] 欄位中指定埠範圍。

    
    </div>

10. 按一下 **[完成]**。

<div>


> [!IMPORTANT]  
> 完成這個步驟之前，請確定您定義的對等是執行中的，並使用您所指定的 FQDN 或 IP 位址。



</div>

接著，若要將對等新增到拓撲中，請遵循在部署檔中[發佈 Lync Server 2013](lync-server-2013-publish-the-topology.md)中的拓撲中的程式。 您必須在每次使用 [拓撲建立器] 來建立或修改拓撲時發佈拓撲，才能使用資料來安裝執行 Lync Server 之伺服器的檔案。

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

