---
title: Lync Server 2013：管理觀察程式節點
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94c1e056200a7fc1afec930b7548cfd018c1aa9d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524800"
---
# <a name="managing-watcher-nodes-in-lync-server-2013"></a>在 Lync Server 2013 中管理觀察程式節點

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

除了修改在監看員節點上執行的綜合交易之外，系統管理員也可以使用 **Set-CsWatcherNodeConfiguration** Cmdlet 來執行其他兩項重要工作：啟用與停用監看員節點，以及設定監看員節點於執行測試時使用內部 URL 或外部 URL。

根據預設，監看員節點的設計是會定時執行所有啟用的綜合交易。 不過有時候可能需要暫停那些交易。 例如，如果監看員節點暫時與網路中斷連線，則沒有必要執行綜合交易。 沒有網路連線，那些交易一定會失敗。 如果您想要暫時停用監看員節點，請從 Lync Server 管理命令介面執行類似以下的命令：

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

此命令會停用監看員節點 atl-watcher- 001.litwareinc.com 上的綜合交易執行。若要恢復綜合交易的執行，請將 Enabled 屬性回復至 True ($True) 設定：

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> Enabled 屬性可用於開啟或關閉監看員節點。 如果要永久刪除監看員節點，請使用 <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> Cmdlet：<BR>Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"<BR>此命令會移除指定電腦上所有的監看員節點組態設定，這樣就會防止電腦自動執行綜合交易。 不過，此命令不會卸載 System Center 代理檔或 Lync Server 2013 系統檔案。



</div>

根據預設，監看員節點在進行測試時，會使用組織的外部 URL。不過也可以設定監看員節點使用組織的內部 URL。這讓系統管理員可以驗證位於周邊網路內之使用者的 URL 存取。若要設定監看員節點使用內部 URL 而非外部 URL，請將 UseInternalWebUrls 屬性設為 True ($True)：

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

如果重設此屬性為預設值 False ($False)，監看員就會使用外部 URL：

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

