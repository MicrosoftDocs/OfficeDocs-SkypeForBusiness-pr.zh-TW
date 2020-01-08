---
title: 標準移轉案例 - 高層級
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69349b90c6845d8a3f3d5ed13544da4fe4832eb8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a>標準移轉案例 - 高層級

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

當您將 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天遷移至 Lync Server 2013、持續聊天伺服器時，請使用下列專案作為起點。 標準的 Lync Server 2013 遷移路徑如下所示：

  - 貴組織先前已部署 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天，而且您想要部署 Lync Server 2013、持久聊天伺服器。

  - 部署 Lync Server 2013，然後部署持續聊天伺服器池（s）。

  - 準備並規劃持久聊天室的遷移，並判斷適當的時間來關閉系統以進行遷移。

  - 執行適用于遷移的 Windows PowerShell Cmdlet （**Export-CsPersistentChatData**和**Import-CsPersistentChatData**），將內容移至持久聊天伺服器。

  - 確認遷移已成功完成。

  - 停止舊版部署。

  - [設定持久聊天伺服器]，讓舊版用戶端可以連線到 Lync Server 2013、持續聊天伺服器。 這是必要的，因為部署新的用戶端需要一些時間，而且您想要讓擁有舊版用戶端的現有使用者能儘快存取其聊天室。

  - 部署新的用戶端，同時繼續協助確保擁有舊版群組聊天（用戶端）的工人可以存取其聊天室。

</div>

<span> </span>

</div>

</div>

</div>

