---
title: 設定監視節點以參與 System Center 探索
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
ms.openlocfilehash: 49b34e623b885bb7e85afc258c1d533c2a8feb46
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527000"
---
# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a>設定 Lync Server 2013 中的監看員節點，以參與 System Center 探索

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

為了確保您的監看員節點參與 System Center Operations Manager 的探索程式，您必須在已安裝 System Center Operations Manager 主控台的電腦上完成下列程式：

1.  在 [管理]**** 索引標籤上，按一下 [代理程式管理]****。

2.  用滑鼠右鍵按一下監看員節點電腦的名稱，然後按一下 [內容]****。在 [內容]**** 對話方塊中的 [安全性]**** 索引標籤上，選取 [允許此代理程式作為 Proxy 並探索其他電腦中的受管理物件]****，然後按一下 [確定]****。

將監看員節點設為 Proxy 之後，重新啟動監看員節點電腦。 重新開機電腦之後，請確認該電腦上的 Operations Manager 事件記錄中未記錄任何錯誤事件。 在電腦執行15分鐘之後，請使用 Operations Manager 主控台驗證 lync Server 電腦是否列在 **lync** 類別底下。

</div>

<span> </span>

</div>

</div>

</div>

