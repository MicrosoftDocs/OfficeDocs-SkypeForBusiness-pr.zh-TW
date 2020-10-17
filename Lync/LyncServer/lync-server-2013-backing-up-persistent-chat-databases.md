---
title: Lync Server 2013：備份持久聊天資料庫
description: Lync Server 2013：備份 Persistent Chat 資料庫。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9885eaf0065f5b558922c056fb1f669a5b821460
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563289"
---
# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a>在 Lync Server 2013 中備份 Persistent 聊天室資料庫

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-17_

Persistent 聊天室內容會儲存在 Persistent Chat (Mgc) 中。 這是應該定期備份的重要業務資料。 除了聊天室內容之外，Persistent Chat 資料庫也會儲存主體 (的相關資訊，例如使用者和使用者群組) ，以及他們必須接觸聊天室和聊天室的角色和存取權。

有兩種方式可以備份 Persistent 聊天資料。

  - SQL Server 備份

  - 此 `Export-CsPersistentChatData` Cmdlet 會將持久聊天資料匯出為檔案

使用 SQL Server 備份所建立的資料，需要更多的磁碟空間（可能會比所建立的20倍多） `Export-CsPersistentChatData` ，但是 SQL Server 備份很可能是管理員所熟悉的程式。

</div>

<span> </span>

</div>

</div>

</div>

