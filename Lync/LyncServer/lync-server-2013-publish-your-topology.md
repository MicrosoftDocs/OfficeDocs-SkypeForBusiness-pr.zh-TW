---
title: Lync Server 2013： 發佈您的拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74ca4c34c8c130c5309a3255573b41fce35ef071
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-your-topology-in-lync-server-2013"></a>在 Lync Server 2013 中發佈您的拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-08_

每次您使用拓撲產生器來建置您的拓撲，您必須發佈拓撲中央管理存放區中的資料庫，讓資料可用來部署 Lync Server 2013。 使用下列程序來發佈您的拓撲。

<div>

## <a name="to-publish-the-topology"></a>若要發行拓撲

1.  啟動拓撲產生器： 按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。

2.  在 [拓撲產生器] 的主控台樹狀目錄中，以滑鼠右鍵按一下**Lync 2013**中，，，然後按一下 [**發行拓撲**。

3.  在精靈的 [**歡迎使用**] 頁面中，按一下 [**下一步**]。

4.  在 [**拓撲產生器找到 CMS 存放區**] 頁面上，按一下 [**下一步**]。

5.  在 [**建立其他資料庫**] 頁面上，按一下 [**下一步**]。

6.  當狀態表示已成功建立資料庫時，請執行下列動作：
    
      - 若要檢視記錄檔，請按一下 [**檢視記錄檔**。
    
      - 按一下 **[完成]**，關閉精靈。
        
        <div>
        

        > [!IMPORTANT]  
        > 如果這是 Edge Server 或 Edge 集區的全新安裝，您必須從現存前端伺服器、 前端集區或 Standard Edition server 匯出 Edge Server 組態。 若要匯出設定，請參閱<A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">匯出您的 Lync Server 2013 拓撲，並複製到邊緣安裝的外部媒體</A>。 您將 Edge Server 到 Lync Server 部署精靈的安裝和部署階段期間，組態檔案匯入從外部媒體或網路共用。<BR>一旦 Edge Server 可運作且本機組態管理存放區資料庫已複寫內部部署，將會發行後續更新 Lync Server 2013 設定，並複寫至 Edge Server。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

