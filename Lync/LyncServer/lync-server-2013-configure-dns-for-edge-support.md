---
title: Lync Server 2013：設定 edge 支援的 DNS
description: Lync Server 2013：設定 edge 支援的 DNS。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 706f4915adda58dbb72b8dd8921e0cc612833718
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555889"
---
# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a>在 Lync Server 2013 中設定 edge 支援的 DNS

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-15_

您必須設定網域名稱系統 (DNS) 內部和外部 edge 介面的記錄，包括 Edge Server 和反向 proxy 介面。 根據預設，Edge Server 並未加入網域，而且不會有完整功能變數名稱 (完整功能變數名稱) 。 Edge Server 只是由 short (機器) 名稱，而不是完整功能變數名稱所參照。 不過，拓撲產生器會使用 Fqdn，而非短名稱。 Edge Server 的名稱必須符合拓撲產生器所使用的 FQDN。 若要這麼做，您可以定義 DNS 尾碼，當與機器名稱合併時，會產生預期的 FQDN。 在 [將 dns 尾碼新增至未加入網域的電腦名稱稱和 Edge Server] 中，使用下列程式，將 DNS 尾碼新增至電腦名稱稱。

<div>


> [!NOTE]  
> 根據預設，DNS 會使用迴圈演算法，以旋轉查詢答案中傳回的資源記錄資料的順序，其中，已查詢的 DNS 功能變數名稱有多個相同類型的資源記錄。 Lync Server 2013 DNS 負載平衡會因 dns 負載平衡機制的一部分，而定為 dns 迴圈。 確認未停用 [迴圈] 設定。 如果您使用不是執行 Windows 作業系統的 DNS 伺服器，請確認是否已啟用迴圈資源記錄排序。



</div>

在「**建立 DNS srv 記錄**」中，使用下列程式來建立及驗證每個 DNS srv 記錄。 使用「**建立 Dns a 記錄**」中的程式，定義外部使用者存取所需的 DNS a 記錄。 若要確認記錄是否已設定且運作正常，請參閱本主題中的「**驗證 DNS 記錄**」。 如需支援外部使用者存取所需的每一筆記錄的詳細資訊，請參閱 [決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)。

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a>將 DNS 尾碼新增至未加入網域之 Edge Server 上的電腦名稱

1.  在電腦上，按一下 **[開始]**，並在 **[電腦]** 上按一下滑鼠右鍵，然後按一下 **[內容]**。

2.  在 **[電腦名稱、網域及工作群組設定]** 下，按一下 **[變更設定]**。

3.  在 **[電腦名稱]** 索引標籤上，按一下 **[變更]**。

4.  在 **[電腦名稱/網域變更]** 中，按一下 **[其他]**。

5.  在 **[DNS 尾碼和 NetBIOS 電腦名稱]** 的 **[這部電腦的主要 DNS 尾碼]** 中，輸入內部網域的名稱 (例如，corp.contoso.com)，然後按三次 **[確定]**。

6.  重新啟動電腦。

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a>建立 DNS SRV 記錄

1.  在適當的 DNS 伺服器上，按一下 [ **開始**]，按一下 [ **控制台**]，按一下 [系統 **管理工具**]，然後按一下 [ **DNS**]。
    
    <div>
    

    > [!IMPORTANT]  
    > 您必須設定 DNS，讓遠端使用者和同盟協力廠商能夠使用： 1) 外部 DNS 查閱的外部 DNS 專案;2) 周邊網路中的 Edge Server 所使用的 DNS 查閱專案， (也稱為 DMZ、隔離區域及遮罩式子網) （包括執行 Lync Server 2013 的內部伺服器記錄）;和 3) 執行 Lync Server 2013 的內部用戶端和伺服器查閱的內部 DNS 專案。

    
    </div>

2.  在 SIP 網域的主控台樹中，展開 [ **正向對應區域**]，然後在安裝 Lync Server 2013 的網域上按一下滑鼠右鍵。

3.  按一下 [ **其他新記錄**]。

4.  在 [ **選取資源記錄類型**] 中，輸入 [ **服務位置 (SRV) **]，然後按一下 [ **建立記錄**]。

5.  提供 DNS SRV 記錄的所有必要資訊。

</div>

<div>

## <a name="to-create-a-dns-a-record"></a>建立 DNS A 記錄

1.  在 DNS 伺服器上，按一下 [ **開始**]，按一下 [ **控制台**]，按一下 [系統 **管理工具**]，然後按一下 [ **DNS**]。

2.  在 SIP 網域的主控台樹中，展開 [ **正向對應區域**]，然後在安裝 Lync Server 2013 的網域上按一下滑鼠右鍵。

3.  按一下 [ **新增主機 () **]。

4.  提供 DNS SRV 記錄的所有必要資訊。

</div>

<div>

## <a name="to-verify-a-dns-record"></a>驗證 DNS 記錄

1.  登入網域中的用戶端電腦。

2.  按一下 **[開始]**，再按一下 **[執行]**。

3.  在命令提示字元中，執行下列命令：
    
        nslookup <FQDN edge interface>

4.  請確認您收到的回復可解析為 FQDN 的適當 IP 位址。

</div>

<div>

## <a name="see-also"></a>另請參閱


[建立 DNS SRV 記錄，以與主控 Exchange UM 整合](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

