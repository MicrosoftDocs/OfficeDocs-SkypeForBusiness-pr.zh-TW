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
ms.openlocfilehash: 27d2afd025897df4f9b98e235d408a264d2cceb2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a>在 Lync Server 2013 中管理觀察程式節點

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

除了修改在觀察程式節點上執行的綜合交易之外，系統管理員還可以使用**CsWatcherNodeConfiguration** Cmdlet 來執行兩個其他重要的工作：啟用和停用觀察程式節點，以及將觀察程式節點設定為在執行測試時使用內部 url 或外部 url。

根據預設，觀察程式節點是設計來定期執行所有已啟用的綜合交易。 不過，有時候您可能需要暫停這些交易。 例如，如果 [觀察程式] 節點暫時與網路中斷連線，則沒有任何理由執行綜合交易。 若沒有網路連線，這些事務就會保證失敗。 如果您想要暫時停用 [觀察程式] 節點，請從 Lync Server 管理命令介面執行如下所示的命令：

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

這個命令將停用在觀察程式節點上執行的綜合交易（atl-觀察程式-001.litwareinc.com）。 若要繼續執行綜合交易，請將 Enabled 屬性設回 True （$True）：

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> 可使用 Enabled 屬性來開啟或關閉觀察程式節點。 如果您想要永久刪除 [觀察程式] 節點，請使用<STRONG>CsWatcherNodeConfiguration</STRONG> Cmdlet：<BR>移除-CsWatcherNodeConfiguration –身分識別 "atl-watcher-001.litwareinc.com"<BR>該命令會從指定的電腦中移除所有的觀察程式節點設定，這可防止電腦自動執行綜合交易。 不過，命令不會卸載 System Center 代理程式檔案或 Lync Server 2013 系統檔案。



</div>

根據預設，觀察程式節點會在進行測試時使用組織的外部 Url。 不過，您也可以將觀察程式節點設定為使用組織的內部 Url。 這可讓系統管理員驗證位於周邊網路內之使用者的 URL 存取權。 若要將觀察程式節點設定為使用內部 Url，而不是外部 Url，請將 UseInternalWebUrls 屬性設為 True （$True）：

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

如果您將這個屬性重設為預設值 False （$False），則觀察程式就會使用外部 Url：

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

