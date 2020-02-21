---
title: 將試驗集區連接到舊版 Edge Server
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
ms.openlocfilehash: e48d2450d468ae6a28faef4c1fcacf577262c42f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>將試驗集區連接到舊版 Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-02_

部署 Lync Server 2013 之後, 未設定此網站同盟路由。 為了使用 Office Communications Server 2007 R2 正在使用的同盟的路由，Lync Server 2013 必須設定為使用此路由。

若要啟用 Lync Server 2013 站台能夠使用 BackCompatSite 的 Edge Server 與 Director，請使用拓撲產生器建立舊版 Edge 集區的關聯。

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>使用拓撲產生器來與舊版 Edge 集區建立關聯

1.  在拓撲產生器開啟試驗集區拓撲。

2.  選取您的 Lync Server 2013 網站。

3.  在 [**動作**] 功能表中，按一下 [**編輯內容**]。

4.  在 [**網站同盟路由指派**]，選取 [**啟用 SIP 同盟**]，然後選取 [Office Communications Server 2007 R2 Director 或 Office Communications Server 2007 R2 Edge Server，如果未列出 Director。
    
    ![編輯內容] 對話方塊中，同盟路由] 頁面](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "編輯內容] 對話方塊中，同盟路由] 頁面")  

5.  按一下 [確定]**** 關閉 [編輯內容]**** 頁面。

6.  在拓撲產生器] 下 [Lync Server 2013] 節點中，瀏覽至 [ **Standard Edition server** ] 或 [ **Enterprise Edition 前端集區**以滑鼠右鍵按一下集區，，然後按一下 [**編輯內容]**。

7.  在 [關聯]**** 底下，選取 [關聯 Edge 集區 (適用於媒體元件)]**** 旁邊的核取方塊。

8.  從清單中選取 BackCompatSite 的 Edge Server 介面。
    
    ![編輯內容] 對話方塊中，[一般] 頁面](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "編輯內容] 對話方塊中，[一般] 頁面")  

9.  按一下 [確定]**** 關閉 [編輯內容]**** 頁面。

10. 在 [**拓撲產生器中**，選取最頂端的節點 [ **Lync Server**。

11. 從 [**動作**] 功能表中，[**發行拓撲**]，然後按 [**下一步**。

12. 當 [發行精靈]**** 完成之後，按一下 [完成]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

