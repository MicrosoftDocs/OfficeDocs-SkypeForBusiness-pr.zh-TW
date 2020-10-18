---
title: Lync Server 2013：變更 Web 服務 URL
description: Lync Server 2013：變更 Web 服務 URL。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78a7a9b70d475aa952a43d215a8e5cd2068911e6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576349"
---
# <a name="change-the-web-services-url-in-lync-server-2013"></a>在 Lync Server 2013 中變更 Web 服務 URL

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-11-16_

當您設定前端集區和 Standard Edition Server 時，可以選擇設定外部 Web 伺服器陣列完整網域名稱 (FQDN) 和相關聯的連接埠。 如果您在執行 Lync Server 部署嚮導時未設定此 URL，則需要手動設定這些設定。 系統管理員通常不需要修改這些設定，因為這些是建議值和預設連接埠。

<div>


> [!NOTE]  
> 設定 Standard Edition server 時採用下列螢幕擷取畫面，因此會停用覆寫 FQDN 選項。 設定前端集區中的 Enterprise Edition 伺服器時，會啟用該選項。



</div>

![編輯 Web 服務集區設定](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "編輯 Web 服務集區設定")

<div>

## <a name="to-configure-web-services"></a>設定 web 服務

1.  以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。

2.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

3.  在 [拓撲產生器] 的 [ **Standard Edition 前端伺服器**]、[ **Enterprise Edition 前端**集區] 和 [ **目錄**集區] 下的主控台樹中，選取集區名稱。 用滑鼠右鍵按一下名稱，然後依序按一下 **[編輯內容]** 和 **[Web 服務]**。

4.  新增或編輯 **[外部 Web 服務 FQDN]**，然後按一下 **[確定]**。
    
    <div>
    

    > [!WARNING]  
    > 如果您有一個以上的前端集區或前端伺服器，則外部 Web 服務 FQDN 必須是唯一的。 例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為 <STRONG>pool01.contoso.com</STRONG>，則無法將 <STRONG>pool01.contoso.com</STRONG> 用於另一個前端集區或前端伺服器。 如果您也要部署 Director，則為任何 Director 或 Director 集區定義的外部 Web 服務 FQDN，都必須與任何其他 Director 或 Director 集區以及任何前端集區或前端伺服器都是唯一的。

    
    </div>

5.  確認環境中已正確設定聆聽和發行的連接埠。

6.  針對環境中的所有 Standard Edition Server、前端集區和 Director 集區，重複執行這些步驟。

7.  在主控台樹狀目錄中，按一下 **[Lync Server 2013]**，然後在 **[動作]** 窗格中，按一下 **[發行拓撲]**。

設定聆聽和發行連接埠時，有一些需求應注意：

  - 顯示的聆聽連接埠是每部前端伺服器上的 Internet Information Server (IIS) 所設定的連接埠。

  - IIS 的內部和外部聆聽連接埠必須不同。以外部聆聽連接埠而言，這些通常相同，因為一個代表內部 Web 流量的硬體負載平衡器，另一個代表外部 Web 流量的反向 Proxy 伺服器。

  - 您可以覆寫前端集區、Director 或 Director 集區上的內部 web 服務，並定義您自己的 FQDN。
    
    <div>
    

    > [!WARNING]  
    > 如果您決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 必須與其他任何前端集區、Director 或 Director 集區是唯一的。

    
    </div>

  - 在反向 Proxy 或硬體負載平衡器上，必須設定發行的連接埠作為聆聽連接埠。

  - 以前端集區而言 (範例中未顯示)，內部 SIP 集區 FQDN 與內部 Web 服務 FQDN 必須不同，因為 Web 流量是經過硬體負載平衡器而來，而內部 SIP 流量則是經過 DNS 負載平衡器而來。必須符合此需求。

  - Lync Server Standard Edition 部署不需要，也不允許覆蓋內部 web 服務 FQDN，因為這種伺服器無法進行負載平衡。

  - [！注意] 如果您的環境中有硬體負載平衡器，供內部 SIP 和網頁流量使用，則拓撲產生器無法進行區別。
    
    Web 服務 Fqdn 應該易於彼此區別;這可協助確保 URL 重新導向會向適當的伺服器取得用戶端。 例如，如果您有兩個 Fqdn，您可以考慮命名一個 meeting.contoso.com 及另一個 conferencing.contoso.com。 如果您有 Fqdn 具有更類似的名稱，例如 meet1.contoso.com 和 meet2.contoso.com，您可能會執行重新導向的問題。

外部 Web 服務會搭配周邊網路中的反向 Proxy 一起運作。 它會使用這些 web 服務，提供用戶端的外部存取權。 此處設定的 FQDN 會在用戶端登入時傳送給用戶端，並在進行遠端連線時用來建立連回反向 Proxy 的 HTTPS 連線。 反向 Proxy 伺服器會將外部 Web 服務 FQDN 轉到內部硬體負載平衡器，或直接轉到集區。 反向 Proxy 必須能夠將外部 Web 服務 FQDN 解析為內部 Web 伺服器的 IP 位址。 外部 Web 服務 FDQN 必須可在公用網際網路中受到解析。

如果您的內部伺服器為 Standard Edition server，則內部 FQDN 為 Standard Edition server FQDN。 如果內部伺服器是前端集區，則 FQDN 是會對內部 Web 伺服陣列伺服器進行負載平衡的硬體負載平衡器虛擬 IP (VIP)。 在具有多部 Enterprise Edition Server 的前端集區中，需要硬體負載平衡器。 Standard Edition Server 或單一 Enterprise Edition 前端伺服器則不需要負載平衡器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

