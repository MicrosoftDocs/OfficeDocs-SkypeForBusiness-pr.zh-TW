---
title: Lync Server 2013： 編輯設計
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
ms.openlocfilehash: bb643fdbcee35a8b24533bed17d003427a8a0ea8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a>編輯 Lync Server 2013 中的設計

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

完成後的初始採訪問題，您可以編輯網站的 IP 位址與完整的網域名稱 (FQDN)。 若要這麼做，請在 **[全域拓撲]** 頁面上，連按兩下您要編輯的網站。

規劃工具會顯示選取的站台的站台拓撲。 在網站頁面的底部有四個索引標籤：

![規劃工具站台拓撲](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "規劃工具站台拓撲")

  - 站台拓撲 – 目前顯示頁面具有如同建議的可見拓撲概觀。

  - Edge 網狀圖 – [Edge 網狀圖] 頁面上是工作的設計工具其中沒有大部分的規劃工具中。 圖表顯示建議的 Lync Server 2013 拓撲的網路組態，使用可編輯的項目 ip 位址和 Fqdn 伺服器、 集區]，並同時硬體和網域名稱系統 (DNS) 負載平衡器。

  - Edge Admin 報表 – [Edge Admin 報表] 總共包含四份報表：
    
    ![Edge 管理員報告頁面](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edge 管理員報告頁面")  
    
      - 摘要報表 – Edge 網路組態設定的一般報表。 如果您編輯的值在拓樸 TCP/IP **Edge 網狀圖**] 頁面上的 FQDN 值會用於實際部署中，會在這裡表示那些位址和名稱。 否則，會顯示預設文字。
    
      - 憑證報表 – 憑證報表會列出拓撲所需憑證的主體名稱和主體替代名稱。
    
      - 防火牆報表 – 防火牆報表會列出在基礎結構中設定周邊防火牆所需的資訊。 這包括 IP 位址 （預設或編輯的值）、 伺服器角色、 來源 IP 和連接埠、 目的地 IP 和連接埠、 傳輸通訊協定、 應用程式的通訊協定，以及相關的附註。
    
      - DNS 報告 – DNS 報告列出 DNS 項目，您必須建立的相關資訊。 包含正常運作所需的記錄類型、FQDN、IP 位址和註解。

  - 網站摘要 – 網站摘要呈現您藉由回答初始採訪問題，或填寫**設計站台**內的值所做的選擇的概觀。 容量的資訊也會顯示。
    
    <div>
    

    > [!NOTE]  
    > [網站摘要] 頁面上的資訊是針對各項設計所自訂的，無法包含此處詳述的所有區段或資訊。

    
    </div>

<div>

## <a name="see-also"></a>另請參閱


[編輯 Lync Server 2013 中的網路組態圖](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

