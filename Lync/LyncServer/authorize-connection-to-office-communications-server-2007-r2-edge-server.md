---
title: 授權連線至 Office 通訊伺服器 2007 R2 Edge Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: f66f53b5c1aa25324dbd316ad2d72e7d04c42e0f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>授權連線至 Office 通訊伺服器 2007 R2 Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

針對您的試驗集區中的每個 Lync Server 2013 前端伺服器或 Standard Edition server，您必須更新授權連線至 Office 通訊伺服器 2007 R2 Edge Server 的內部伺服器清單。 若沒有這些更新，使用舊版 Edge Server 來參與外部音訊/視訊 (A/V) 會議的使用者就不會成功。

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>授權連線至 Office 通訊伺服器 2007 R2 Edge Server

1.  從 Office 通訊伺服器 2007 R2 Edge Server，從 [系統**管理工具**] 群組中，開啟 [**電腦管理**] 嵌入式管理單元。

2.  在主控台樹狀目錄中，展開 [服務和應用程式]****。

3.  以滑鼠右鍵按一下 [Office Communications Server 2007 R2]****，然後按一下 [內容]****。

4.  按一下 [內部]**** 索引標籤。

5.  在 [新增伺服器]**** 底下，按一下 [新增]****。

6.  在 [新增 Office Communications Server]**** 對話方塊中，輸入適當的資訊：
    
      - 指定每一部 Lync Server 2013 前端伺服器或 Standard Edition server 的完整功能變數名稱（FQDN），以及 Lync Server 2013 集區。
    
      - 如果您已在指定下一個躍點電腦的集區上設定靜態路由，請指定 Lync Server 2013 Director 的 FQDN。

7.  針對每個 Lync Server 2013、前端伺服器、Standard Edition Server、集區和 Director 新增專案後，按一下 [套用] **，然後**按一下 **[確定]** 以關閉 [屬性] 頁面。

</div>

</div>

<span> </span>

</div>

</div>

</div>

