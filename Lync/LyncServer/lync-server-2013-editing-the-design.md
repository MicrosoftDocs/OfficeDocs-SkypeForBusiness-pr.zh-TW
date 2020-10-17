---
title: Lync Server 2013：編輯設計
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68a1a4257279f786d35c89153e0cf2154b39a6b4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501110"
---
# <a name="editing-the-design-in-lync-server-2013"></a>在 Lync Server 2013 中編輯設計

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

在完成最初的面試問題之後，您可以編輯該網站的 (FQDN) 和 IP 位址的完整功能變數名稱。 若要這麼做，請在 **[全域拓撲]** 頁面上，連按兩下您要編輯的網站。

規劃工具會顯示所選網站的網站拓撲。 在網站頁面的底部有四個索引標籤：

![規劃工具網站拓撲](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "規劃工具網站拓撲")

  - 站台拓撲 – 目前顯示頁面具有如同建議的可見拓撲概觀。

  - Edge Network 圖表– Edge Network 框圖頁面是設計人員在規劃工具中大部分工作的位置。 此圖表會顯示建議的 Lync Server 2013 拓撲的網路設定，以及伺服器、集區的可編輯專案，以及硬體和網域名稱系統 (DNS) 負載平衡器的名稱。

  - Edge Admin 報表 – [Edge Admin 報表] 總共包含四份報表：
    
    ![Edge 管理報告頁面](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edge 管理報告頁面")  
    
      - 摘要報表 – Edge 網路組態設定的一般報表。 如果您將 [ **Edge Network 圖表** ] 頁面上的值編輯為 [拓撲 TCP/IP，並將用於實際部署中的 FQDN 值，則會在此顯示這些位址和名稱。 否則，會顯示預設文字。
    
      - 憑證報表 – 憑證報表會列出拓撲所需憑證的主體名稱和主體替代名稱。
    
      - 防火牆報表 – 防火牆報表會列出在基礎結構中設定周邊防火牆所需的資訊。 這包括 IP 位址 (預設或編輯的值) 、伺服器角色、來源 IP 及埠、目的地 IP 及埠、傳輸通訊協定、應用程式通訊協定，以及相關的附注。
    
      - DNS 報告– DNS 報告會列出您必須建立之 DNS 專案的相關資訊。 包含正常運作所需的記錄類型、FQDN、IP 位址和註解。

  - 網站摘要–網站摘要會顯示您透過回答最初的面試問題或填入 **設計網站**中的值所做的選擇。 也會呈現容量資訊。
    
    <div>
    

    > [!NOTE]  
    > [網站摘要] 頁面上的資訊是針對各項設計所自訂的，無法包含此處詳述的所有區段或資訊。

    
    </div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中編輯網路設定圖表](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

