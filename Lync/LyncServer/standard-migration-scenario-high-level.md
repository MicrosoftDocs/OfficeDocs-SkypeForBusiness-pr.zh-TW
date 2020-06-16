---
title: 標準遷移案例-高層級
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0acdf50ac515810b2813a98e9dc1f289e327eba
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a>標準遷移案例-高層級

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

將 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天遷移至 Lync Server 2013、Persistent Chat Server 時，請使用下列專案做為開始點。 標準 Lync Server 2013 遷移路徑如下：

  - 您的組織先前已部署 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天，且您想要部署 Lync Server 2013、Persistent Chat Server。

  - 部署 Lync Server 2013，然後部署 Persistent Chat Server 集區。

  - 準備並規劃您的持續聊天室的遷移，並決定適當的時間來關閉系統進行遷移。

  - 執行 Windows PowerShell Cmdlet 以進行遷移（**Export-CsPersistentChatData**和**Import-CsPersistentChatData**）以將內容移至 Persistent Chat Server。

  - 確認遷移已成功。

  - 解除委任舊版部署。

  - 設定 Persistent Chat Server，使舊版用戶端可以連線至 Lync Server 2013，Persistent Chat Server。 這是必要的，因為部署新的用戶端需要一些時間，而且您想要讓具有舊版用戶端的現有使用者可以儘快存取其聊天室。

  - 部署新的用戶端，同時繼續協助確保具有傳統群組聊天（用戶端）的工作人員可以到達其聊天室。

</div>

<span> </span>

</div>

</div>

</div>

