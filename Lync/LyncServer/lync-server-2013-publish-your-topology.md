---
title: Lync Server 2013：發行拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bd542db6acedbec75e475045ae2ace6d63d5469
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-your-topology-in-lync-server-2013"></a>在 Lync Server 2013 中發行拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

每當您使用 [拓撲建立器] 來建立拓撲時，您必須將拓撲發佈到中央管理儲存體中的資料庫，才能使用這些資料來部署 Lync Server 2013。 使用下列程式發佈您的拓撲。

<div>

## <a name="to-publish-the-topology"></a>發佈拓撲

1.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。

2.  在拓撲建立器中，于主控台樹狀結構中，以滑鼠右鍵按一下 [ **Lync 2013**]，然後按一下 [**發佈拓撲**]。

3.  在嚮導的 [**歡迎**] 頁面上，按一下 **[下一步]**。

4.  在 [拓撲建立器] 中**找到 [CMS 儲存**] 頁面，按一下 **[下一步]**。

5.  在 [**建立其他資料庫**] 頁面上，按一下 **[下一步]**。

6.  當狀態指出資料庫建立成功時，請執行下列動作：
    
      - 若要查看記錄，請按一下 [**查看記錄**]。
    
      - 若要關閉嚮導，請按一下 **[完成**]。
        
        <div>
        

        > [!IMPORTANT]  
        > 如果這是 Edge 伺服器或 Edge 池的新安裝，您必須從現有的前端伺服器、前端池或標準版伺服器匯出 Edge 伺服器設定。 若要匯出設定，請參閱<A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">匯出 Lync Server 2013 拓撲，然後將它複製到外部媒體以進行 edge 安裝</A>。 您將透過 Lync Server 部署嚮導在邊緣伺服器的設定和部署階段，從外部媒體或網路共用匯入設定檔。<BR>一旦邊緣伺服器可正常運作，且本機建構管理儲存資料庫是與內部部署複製，則會發佈 Lync Server 2013 設定的後續更新，並將其複製到 Edge 伺服器。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

