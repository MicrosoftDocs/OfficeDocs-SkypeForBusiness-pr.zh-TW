---
title: Lync Server 2013：設定 Edge 支援的 DNS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79e1712b3425c7cce4020799b37f10aba894aeb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a>在 Lync Server 2013 中設定 Edge 支援的 DNS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-15_

您必須設定內部和外部邊緣介面的網域名稱系統（DNS）記錄，包括 Edge 伺服器與反向 proxy 介面。 根據預設，Edge 伺服器不會加入網域，也不會有完整的功能變數名稱（完整功能變數名稱）。 Edge 伺服器只是由短（電腦）名稱所參照，而不是以完整的功能變數名稱來引用。 不過，拓撲產生器使用 Fqdn，而不是簡稱。 Edge 伺服器的名稱必須與拓撲建立器所使用的 FQDN 相符。 若要這樣做，您可以定義一個 DNS 尾碼，在與電腦名稱稱結合時，會產生預期的 FQDN。 您可以在 [電腦名稱稱] 和 [Edge 伺服器（未加入網域）] 中，使用下列程式，將 DNS 尾碼新增到電腦名稱稱中。

<div>


> [!NOTE]  
> 根據預設，DNS 會使用迴圈法演算法來旋轉查詢答案中傳回的資源記錄資料順序，這些記錄是針對已查詢的 DNS 功能變數名稱，有多個相同類型的資源記錄。 Lync Server 2013 DNS 負載平衡，視 dns 負載平衡機制的一部分而定。 確認沒有停用迴圈設定。 如果您使用的 DNS 伺服器不是執行 Windows 作業系統，請確認已啟用 [迴圈式資源記錄排序]。



</div>

您可以在「**建立 DNS SRV 記錄**」中使用下列程式來建立並驗證每個 DNS srv 記錄。 使用 [**建立 DNS a 記錄**] 中的程式，定義外部使用者存取所需的 DNS a 記錄。 若要確認記錄是否已正確設定且正常運作，請參閱本主題中的「**驗證 DNS 記錄**」。 如需支援外部使用者存取所需的每一筆記錄的詳細資訊，請參閱[判斷 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)。

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a>在未加入網域的邊緣伺服器上將 DNS 尾碼新增到電腦名稱稱

1.  在電腦上，按一下 [**開始**]，以滑鼠右鍵按一下 [**電腦**]，然後按一下 [**屬性**]。

2.  在 [**電腦名稱稱、網域及工作組設定**] 底下，按一下 [**變更設定**]。

3.  按一下 [**電腦名稱稱**] 索引標籤上的 [**變更**]。

4.  在 [**電腦名稱稱/網域變更**] 中，按一下 [**更多**]。

5.  在 [ **DNS 尾碼及 NetBIOS 電腦名稱稱**]**的 [此電腦的主要 DNS 尾碼**] 中，輸入您的內部網功能變數名稱稱（例如，corp.contoso.com），然後按一下 **[確定]** 三次。

6.  重新開機電腦。

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a>建立 DNS SRV 記錄

1.  在適當的 DNS 伺服器上，按一下 [**開始**]，按一下 [**控制台**]，按一下 [**管理工具**]，然後按一下 [ **DNS**]。
    
    <div>
    

    > [!IMPORTANT]  
    > 您需要設定 DNS，讓遠端使用者和聯盟夥伴的外部 DNS 查閱都有：1）外部 DNS 專案;2）用於周邊網路（也稱為 DMZ、網路隔離區域及遮罩子網）中的邊緣伺服器所使用的 DNS 查閱專案，包括執行 Lync Server 2013 的內部伺服器的記錄;與3）內部 DNS 專案，可供執行 Lync Server 2013 的內部用戶端和伺服器進行查閱。

    
    </div>

2.  在您 SIP 網域的 [主控台樹] 中，展開 [**轉寄查閱區域**]，然後以滑鼠右鍵按一下安裝 Lync Server 2013 的網域。

3.  按一下 [**其他新記錄**]。

4.  在 [**選取資源記錄類型**] 中，輸入 [**服務位置（SRV）**]，然後按一下 [**建立記錄**]。

5.  提供 DNS SRV 記錄所需的所有資訊。

</div>

<div>

## <a name="to-create-a-dns-a-record"></a>建立 DNS A 記錄

1.  在 DNS 伺服器上，按一下 [**開始**]，按一下 [**控制台**]，按一下 [**管理工具**]，然後按一下 [ **DNS**]。

2.  在您 SIP 網域的 [主控台樹] 中，展開 [**轉寄查閱區域**]，然後以滑鼠右鍵按一下安裝 Lync Server 2013 的網域。

3.  按一下 **[新增主機（A）**]。

4.  提供 DNS SRV 記錄所需的所有資訊。

</div>

<div>

## <a name="to-verify-a-dns-record"></a>驗證 DNS 記錄

1.  登入網域中的用戶端電腦。

2.  按一下 [**開始**]，然後按一下 [**執行**]。

3.  在命令提示字元中，執行下列命令：
    
        nslookup <FQDN edge interface>

4.  確認您收到的回復會解析為適當的 FQDN IP 位址。

</div>

<div>

## <a name="see-also"></a>請參閱


[針對與主控 Exchange UM 的整合建立 DNS SRV 記錄](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[針對 Lync Server 2013 判定 DNS 需求](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

