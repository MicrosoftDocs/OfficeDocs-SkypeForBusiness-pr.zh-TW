---
title: 授權連線到 Office 通訊伺服器 2007 R2 Edge 伺服器
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
ms.openlocfilehash: 8dbce32a12f05dff768d23a2bdccfe1b84a567cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>授權連線到 Office 通訊伺服器 2007 R2 Edge 伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

針對您的試用池中的每個 Lync Server 2013 前端伺服器或標準版伺服器，您必須更新已獲授權連線至 Office 通訊伺服器 2007 R2 Edge 伺服器的內部伺服器清單。 如果沒有這些更新，則使用舊版 Edge 伺服器加入的使用者的外部音訊/視覺（A/V）會議將無法運作。

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>授權連線到 Office 通訊伺服器 2007 R2 Edge 伺服器

1.  從 [Office 通訊伺服器 2007 R2 Edge 伺服器] 的 [**管理工具**] 群組中，開啟 [**電腦管理**] 管理單元。

2.  在主控台樹中，展開 [**服務和應用程式**]。

3.  以滑鼠右鍵按一下 [ **Office 通訊伺服器 2007 R2**]，然後按一下 [**屬性**]。

4.  按一下 [**內部**] 索引標籤。

5.  在 [**新增伺服器**] 底下，按一下 [**新增**]。

6.  在 [**新增 Office 通訊伺服器**] 對話方塊中，輸入適當的資訊：
    
      - 指定每個 Lync Server 2013 前端伺服器或標準版伺服器的完整功能變數名稱（FQDN），以及 Lync Server 2013 池。
    
      - 如果您已在以其 FQDN 指定下一個躍點電腦的池中設定靜態路由，請指定 Lync Server 2013 控制器的 FQDN。

7.  針對每個 Lync Server 2013、[前端伺服器]、[標準版伺服器]、[池] 和 [控制器] 新增專案後，請按一下 [套用] **，然後按一下** **[確定]** 以關閉 [屬性] 頁面。

</div>

</div>

<span> </span>

</div>

</div>

</div>

