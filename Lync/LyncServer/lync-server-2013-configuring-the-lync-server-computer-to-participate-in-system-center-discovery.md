---
title: 設定 Lync Server 電腦以參與 System Center 搜索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b8e95ead01c89f33346a66a8212245c2350894f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a>設定 Lync Server 2013 電腦以參與 System Center 搜索

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-20 個_

若要確保您新的 Lync Server 代理程式參與探索程序中的 System Center Operations Manager，您必須完成下列程序在每一部已安裝 System Center Operations Manager 主控台的電腦上：

1.  在 [管理]**** 索引標籤上，按一下 [代理程式管理]****。

2.  在電腦名稱上按一下滑鼠右鍵，然後按一下 [內容]****。在 [內容]**** 對話方塊中的 [安全性]**** 索引標籤上，選取 [允許此代理程式作為 Proxy 並探索其他電腦中的受管理物件]****，然後按一下 [確定]****。

完成步驟 2 之後，請重新啟動健康狀態代理程式服務 (重新啟動服務會「強制執行」新機器的探索。若您沒有重新啟動服務，則在 4 個小時過後，System Center Operations Manager 才會探索新機器)。重新啟動服務之後，請在該電腦上確認 Operations Manager 事件記錄中沒有記錄任何錯誤事件。

</div>

<span> </span>

</div>

</div>

</div>

