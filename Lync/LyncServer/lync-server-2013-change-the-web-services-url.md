---
title: Lync Server 2013：變更 Web 服務 URL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 335c73a56da1d8b9a28e7089a7cc2238724a322b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a>在 Lync Server 2013 中變更 Web 服務 URL

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-11-16_

在您設定前端池和標準版伺服器時，您可以選擇設定外部的網路集群集完全限定功能變數名稱（FQDN）及相關聯的埠。 如果您在執行 Lync Server 部署嚮導時未設定此 URL，您必須手動設定這些設定。 系統管理員通常不需要修改這些設定，因為這些是建議的和預設的埠。

<div>


> [!NOTE]  
> 在設定標準版伺服器時，會進行下列螢幕擷取畫面，因此停用覆寫 FQDN 選項。 在前端池中設定企業版伺服器時，會啟用該選項。



</div>

![編輯 Web 服務池設定][(images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "編輯 Web 服務] 池設定")

<div>

## <a name="to-configure-web-services"></a>若要設定 web 服務

1.  登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。

2.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。

3.  在拓撲建立器中，在 [**標準版前端伺服器**]、[**企業版前端池**] 和 [**目錄池**] 底下的 [主控台] 樹狀結構中，選取 [池名稱]。 以滑鼠右鍵按一下名稱，按一下 [**編輯屬性**]，然後按一下 [ **Web 服務**]。

4.  新增或編輯**外部 Web 服務 FQDN**，然後按一下 **[確定]**。
    
    <div>
    

    > [!WARNING]  
    > 如果您有多個前端池或前端伺服器，外部 Web 服務 FQDN 必須是唯一的。 例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為<STRONG>pool01.contoso.com</STRONG>，則無法將<STRONG>pool01.contoso.com</STRONG>用於另一個前端池或前端伺服器。 如果您也要部署控制器，則為任何主管或主管池定義的外部 Web 服務 FQDN，都必須是與任何其他控制器或主管池以及任何前端池或前端伺服器的唯一名稱。

    
    </div>

5.  確認已針對您的環境正確設定聆聽與已發佈的埠。

6.  針對您環境中的所有標準版伺服器、前端池及控制器池，重複這些步驟。

7.  在主控台樹中，按一下 [ **Lync Server 2013**]，然後在 [**動作**] 窗格中按一下 [**發佈拓撲**]。

當您設定聆聽與發佈埠時，必須注意幾個需求：

  - 所顯示的偵聽埠是針對每個前端伺服器上的網際網路 Information Server （IIS）設定的埠。

  - 對於 IIS，內部和外部的偵聽埠必須不同。 針對外部的偵聽埠，它們通常都是相同的，因為它代表內部網路流量的硬體負載平衡器，另一個代表外部網路流量的反向 proxy 伺服器。

  - 您可以覆寫前部端池、導演或主管池上的內部 web 服務，並定義您自己的 FQDN。
    
    <div>
    

    > [!WARNING]  
    > 如果您決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 都必須是與任何其他的前端池、控制器或主管池都是唯一的。

    
    </div>

  - 已發佈的埠必須在反向 proxy 或硬體負載平衡器上設定為偵聽埠。

  - 對於前端池（範例中未顯示），內部 SIP 池 FQDN 必須與內部 web 服務 FQDN 不同，因為 web 流量是透過硬體負載平衡器所產生，而內部 SIP 池流量則是透過 DNS 負載平衡器進行. 必須符合此需求。

  - Lync Server 標準版部署不需要或允許覆蓋內部 web 服務 FQDN，因為此伺服器無法進行負載平衡。

  - 如果您的環境中有硬體負載平衡器，同時適用于內部 SIP 和網路流量，拓撲建立器就無法進行區別。
    
    Web 服務 Fqdn 應該能輕鬆地彼此區別;這有助於確保 URL 重新導向用戶端傳到適當的伺服器。 例如，如果您有兩個 Fqdn，您可以考慮將一個 meeting.contoso.com 命名為另一個 conferencing.contoso.com。 如果您有 Fqdn 有更相似的名稱（例如 meet1.contoso.com 和 meet2.contoso.com），您可能會遇到重新導向問題。

外部 web 服務與周邊網路中的反向 proxy 搭配運作。 它透過使用這些 web 服務，為用戶端提供外部存取。 在這裡設定的 Fqdn 會在使用者登入時傳送給用戶端，並用於在遠端連線時，將 HTTPS 連線回反向 proxy。 反向 proxy 伺服器會將外部 web 服務 FQDN 轉寄到內部硬體負載平衡器，或直接傳送到該池。 反向 proxy 必須能夠將外部 web 服務 FQDN 解析為內部 Web 服務器的 IP 位址。 外部 web 服務 FDQN 在公用網際網路中必須是可解析的。

如果您的內部伺服器是標準版伺服器，則內部 FQDN 是標準版伺服器 FQDN。 如果您的內部伺服器是 [前端] 池，FQDN 就是硬體負載平衡器虛擬 IP （VIP），負載平衡內部的網路伺服器陣列伺服器。 在有一個以上的企業版伺服器的前端池中需要硬體負載平衡器。 標準版伺服器或單一的企業版前端伺服器不需要負載平衡器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

