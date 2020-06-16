---
title: 將試驗集區連線到舊版 Edge Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b83877505bfc9c2accc2057a9ebb1fb62355b3d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>將試驗集區連線到舊版 Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

在部署 Lync Server 2013 之後，未設定此網站的同盟路由。 為了使用 Office 通訊伺服器 2007 R2 所使用的同盟路由，Lync Server 2013 必須設定成使用此路由。

若要讓 Lync Server 2013 網站使用 BackCompatSite 的 Director 和 Edge Server，請使用拓撲產生器建立與舊版 Edge 集區的關聯。

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>使用拓撲產生器來與舊版 Edge 集區建立關聯

1.  在拓撲產生器中開啟試驗集區拓撲。

2.  選取您的 Lync Server 2013 網站。

3.  在 [**動作**] 功能表上，按一下 [**編輯屬性**]。

4.  在 [**網站同盟路由指派**] 底下，選取 [**啟用 SIP 同盟**]，然後選取 [Office 通訊伺服器 2007 r2 Director]，或 Office 通訊伺服器 2007 r2 Edge Server （如果未列出 Director）。
    
    ![[編輯屬性] 對話方塊，[同盟路由] 頁面](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "[編輯屬性] 對話方塊，[同盟路由] 頁面")  

5.  按一下 [確定]**** 關閉 [編輯內容]**** 頁面。

6.  在 [拓撲產生器] 的 [Lync Server 2013] 節點下，流覽至 [ **Standard edition server** ] 或 [ **Enterprise Edition 前端**集區]，以滑鼠右鍵按一下集區，然後按一下 [**編輯屬性**]。

7.  在 [關聯]**** 底下，選取 [關聯 Edge 集區 (適用於媒體元件)]**** 旁邊的核取方塊。

8.  從清單中，選取 BackCompatSite 的 Edge Server 介面。
    
    ![[編輯屬性] 對話方塊，[一般] 頁面](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "[編輯屬性] 對話方塊，[一般] 頁面")  

9.  按一下 [確定]**** 關閉 [編輯內容]**** 頁面。

10. 在 [**拓撲**產生器] 中，選取最頂端的節點 [ **Lync Server**]。

11. 從 [**動作**] 功能表中，按一下 [**發行拓撲**]，然後按 **[下一步]**。

12. 當 [發行精靈]**** 完成之後，按一下 [完成]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

