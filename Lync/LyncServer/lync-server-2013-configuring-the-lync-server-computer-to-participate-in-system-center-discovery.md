---
title: 將 Lync Server 電腦設定為參與 System Center 探索
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
ms.openlocfilehash: 8cec18903f1621d5a616debbbdd16f3c834ac21c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a>將 Lync Server 2013 電腦設定為參與 System Center 探索

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

若要確保您的新 Lync Server agent 參與 System Center Operations Manager 的探索程式，您必須在安裝 System Center Operations Manager 主控台的每台電腦上完成下列程式：

1.  按一下 [**管理**] 索引標籤上的 [**代理程式管理**]。

2.  以滑鼠右鍵按一下電腦的名稱，然後按一下 [**屬性**]。 在 [內容 **] 對話方塊的 [** **安全性**] 索引標籤上，選取 [**允許此代理程式充當 proxy 並探索其他電腦上的 managed 物件**]，然後按一下 **[確定]**。

完成步驟2之後，請重新開機 Health 代理服務。 （重新開機服務將會「強制」探索新的電腦。 如果您不重新開機服務，系統中心作業管理員可能需要4小時的時間才能探索新電腦。 重新開機服務之後，請確認該電腦上的 Operations Manager 事件記錄中沒有記錄任何錯誤事件。

</div>

<span> </span>

</div>

</div>

</div>

