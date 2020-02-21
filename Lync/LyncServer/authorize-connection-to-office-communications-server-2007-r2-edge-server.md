---
title: 授權連線至 Office Communications Server 2007 R2 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a6adeaa07efea62697ecfbd38fede7d2f2191b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>授權連線至 Office Communications Server 2007 R2 Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-28_

在試驗集區中每個 Lync Server 2013 前端伺服器或 Standard Edition server，您必須更新已授權連線至 Office Communications Server 2007 R2 Edge Server 的內部伺服器的清單。 若沒有這些更新，使用舊版 Edge Server 來參與外部音訊/視訊 (A/V) 會議的使用者就不會成功。

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>授權連線至 Office Communications Server 2007 R2 Edge Server

1.  從 Office Communications Server 2007 R2 Edge Server，從 [**系統管理工具**] 群組中，開啟 [**電腦管理**] 嵌入式管理單元。

2.  在主控台樹狀目錄中，展開 [服務和應用程式]****。

3.  以滑鼠右鍵按一下 [Office Communications Server 2007 R2]****，然後按一下 [內容]****。

4.  按一下 [內部]**** 索引標籤。

5.  在 [新增伺服器]**** 底下，按一下 [新增]****。

6.  在 [新增 Office Communications Server]**** 對話方塊中，輸入適當的資訊：
    
      - 指定每個 Lync Server 2013 前端伺服器或 Standard Edition server 和 Lync Server 2013 集區的完整的網域名稱 (FQDN)。
    
      - 如果您指定依其 FQDN 的下一個躍點電腦的集區上設定靜態路由，請指定 Lync Server 2013 Director 的 FQDN。

7.  新增的每個 Lync Server 2013、 前端伺服器、 Standard Edition server、 集區] 和 Director 的項目之後，按一下 [**套用]** ，然後按一下 [**確定**] 關閉 [內容] 頁面。

</div>

</div>

<span> </span>

</div>

</div>

</div>

