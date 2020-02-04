---
title: 將試驗集區連線到舊版 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09858b03c787af034790c94bcbf12ca6ea7ceecf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>將試驗集區連線到舊版 Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

部署 Lync Server 2013 之後，未設定此網站的同盟路線。 若要使用由 Office 通訊伺服器 2007 R2 使用的聯盟路由，必須將 Lync Server 2013 設定為使用此路由。

若要讓 Lync Server 2013 網站使用 BackCompatSite 的控制器和邊緣伺服器，請使用拓撲建立器來關聯舊版 Edge 池。

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>使用拓撲建立器關聯舊版 Edge 池

1.  在拓撲建立器中開啟 [試驗區] 拓撲。

2.  選取您的 Lync Server 2013 網站。

3.  在 [**動作**] 功能表上，按一下 [**編輯屬性**]。

4.  在 [**網站同盟路由指派**] 底下，選取 [**啟用 SIP 同盟**]，然後選取 [Office 通訊伺服器 2007 r2 控制器]，或 [Office 通訊伺服器 2007 r2 Edge 伺服器] （如果沒有列出主管）。
    
    ![[編輯內容] 對話方塊，[同盟路由] 頁面](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "[編輯內容] 對話方塊，[同盟路由] 頁面")  

5.  按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。

6.  在 [拓撲建立器] 中，在 [Lync Server 2013] 節點底下，流覽至 [**標準版] 伺服器**或 [**企業版] 前端池**，以滑鼠右鍵按一下該池，然後按一下 [**編輯屬性**]。

7.  在 [**關聯**性] 底下，選取 [關聯邊緣池] 旁的核取方塊 **（適用于媒體元件）**。

8.  從清單中選取 BackCompatSite 的邊緣伺服器介面。
    
    ![[編輯內容] 對話方塊，[一般] 頁面](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "[編輯內容] 對話方塊，[一般] 頁面")  

9.  按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。

10. 在 [**拓撲**建立器] 中，選取最頂端的節點 [ **Lync Server**]。

11. 在 [**動作**] 功能表中，按一下 [**發佈拓撲**]，然後按一下 **[下一步]**。

12. **發佈嚮導**完成後，請按一下 **[完成]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

