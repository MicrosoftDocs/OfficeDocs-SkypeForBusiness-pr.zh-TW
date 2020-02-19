---
title: 將試驗集區連接到舊版 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1eea7d203638e891dbda1b91c53967a4632cc1df
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>將試驗集區連接到舊版 Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-29_

部署 Lync Server 2013 之後, 您要設定您的站台同盟路由。 若要使用 Lync Server 2010 正在使用的同盟的路由，Lync Server 2013 必須設定為使用此路由。

若要啟用 Lync Server 2013 站台能夠使用 Lync Server 2010 部署的 Edge Server 與 Director，請使用拓撲產生器建立舊版 Edge 集區的關聯。

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>使用拓撲產生器來與舊版 Edge 集區建立關聯

1.  開啟**拓撲產生器]**。

2.  選取您的網站，也就是 [ **Lync Server** ] 節點的正下方。

3.  在 [動作]**** 功能表上，按一下 [編輯屬性]****。

4.  在左窗格中，選取 [**同盟路由**]。

5.  在 [**站台同盟路由指派**]，選取 [**啟用 SIP 同盟**]，然後選取 [Lync Server 2010 Director 或 Lync Server 2010 Edge Server，如果未列出 Director。
    
    ![編輯同盟路由] 頁面上的屬性](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "編輯同盟路由] 頁面上的屬性")  

6.  按一下 [確定]**** 關閉 [編輯內容]**** 頁面。

7.  在拓撲產生器] 下 [Lync Server 2013] 節點中，瀏覽至 [ **Standard Edition server** ] 或 [ **Enterprise Edition 前端集區**以滑鼠右鍵按一下集區，，然後按一下 [**編輯內容]**。

8.  在 [關聯]**** 底下，選取 [關聯 Edge 集區 (適用於媒體元件)]**** 旁邊的核取方塊。

9.  從清單中，選取舊版 Edge Server。
    
    ![編輯內容] 對話方塊中，選取舊版 Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "編輯內容] 對話方塊中，選取舊版 Edge")  

10. 按一下 [確定]**** 關閉 [編輯內容]**** 頁面。

11. 在 [**拓撲產生器中**，選取最頂端的節點 [ **Lync Server**。

12. 從 [**動作**] 功能表中，[**發行拓撲**]，然後按 [**下一步**。

13. 當 [發行精靈]**** 完成之後，按一下 [完成]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

