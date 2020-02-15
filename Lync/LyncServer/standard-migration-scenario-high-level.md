---
title: 標準移轉案例-高層級
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34084de0af0971018043f230c260adb514f1d460
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a>標準移轉案例-高層級

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-01-30_

將 Lync Server 2010，Group Chat 或： Office Communications Server 2007 R2 群組聊天移轉至 Lync Server 2013，Persistent Chat Server 時，請使用下列項目做為起點。 標準的 Lync Server 2013 移轉方式如下：

  - 您的組織已部署 Lync Server 2010，Group Chat 或 Office Communications Server 2007 R2 群組聊天，以及您想要部署 Lync Server 2013，Persistent Chat Server。

  - 部署 Lync Server 2013，然後將部署 Persistent Chat Server 集區。

  - 準備並規劃移轉您的常設聊天室，並決定適當時機來關閉系統以進行移轉。

  - 執行移轉 （**Export-cspersistentchatdata**與**Import-cspersistentchatdata**） 將內容移至 Persistent Chat Server 的 Windows PowerShell cmdlet。

  - 確認移轉已成功。

  - 解除委任舊版部署。

  - 設定常設聊天室伺服器，以便舊版用戶端可以連線至 Lync Server 2013，Persistent Chat Server。 這是必要的因為所花的時間來部署新的用戶端，而且想要啟用現有的使用者使用舊版用戶端儘速可以存取他們的聊天室。

  - 部署新的用戶端，同時繼續以協助確保與舊版群組聊天 （用戶端） 的工作者可以前往他們的聊天室。

</div>

<span> </span>

</div>

</div>

</div>

