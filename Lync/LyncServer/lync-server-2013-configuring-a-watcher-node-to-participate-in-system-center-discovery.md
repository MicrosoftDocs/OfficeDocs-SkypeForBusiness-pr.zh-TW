---
title: 設定監看員節點以參與 System Center 搜索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a90f07b445da792e0bc3b22967e41d8cd8d2fcc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a>設定監看員節點以參與 System Center 搜索的 Lync Server 2013 中

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-22_

若要確保您的監看員節點參與探索程序中的 System Center Operations Manager，您必須完成下列程序已安裝 System Center Operations Manager 主控台的電腦上：

1.  在 [管理]**** 索引標籤上，按一下 [代理程式管理]****。

2.  用滑鼠右鍵按一下監看員節點電腦的名稱，然後按一下 [內容]****。在 [內容]**** 對話方塊中的 [安全性]**** 索引標籤上，選取 [允許此代理程式作為 Proxy 並探索其他電腦中的受管理物件]****，然後按一下 [確定]****。

將監看員節點設為 Proxy 之後，重新啟動監看員節點電腦。 電腦重新開機之後，請確認沒有錯誤事件會被記錄在 Operations Manager 事件記錄檔，該電腦上。 已經執行之電腦的 15 分鐘左右之後，使用 Operations Manager 主控台中若要確認您的 Lync Server 電腦會列在**Lync**類別下。

</div>

<span> </span>

</div>

</div>

</div>

