---
title: Lync Server 2013：刪除訊息或清除過時的訊息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a message or purging obsolete messages
ms:assetid: 3f0c612d-6dfd-41a4-a5fe-5ff3448eb0ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215874(v=OCS.15)
ms:contentKeyID: 48706000
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db44ca77d217c1b7bc0bc4d05c56cb9b6ff99ea4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525450"
---
# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a>在 Lync Server 2013 中刪除訊息或清除過時的訊息

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-05_

Persistent Chat 系統管理員可以從 Persistent 聊天室刪除郵件 (，也可以選擇性地將其取代為另一封郵件) 。 管理員也可以清除過時訊息作為持續維護的一部分，以將資料庫的成長最小化。 例如，此 Windows PowerShell 命令會從使用者 kenmyer@litwareinc.com 所張貼的 ITChatRoom 聊天室中移除所有郵件：

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

這個範例會取代所有已移除的郵件，請注意，該郵件已不再可用：

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

如需詳細資訊，請參閱 [test-cspersistentchatmessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) Cmdlet 的 [說明] 主題。

</div>

<span> </span>

</div>

</div>

</div>

