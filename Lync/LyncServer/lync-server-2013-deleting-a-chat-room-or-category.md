---
title: Lync Server 2013：刪除聊天室或類別
description: Lync Server 2013：刪除聊天室或類別。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ef89802171a1eeca7de18ff0a4eb8eb3895f1b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555369"
---
# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a>在 Lync Server 2013 中刪除聊天室或類別

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

可刪除 Persistent 聊天室。 如果您不再想要使用某個聊天室，請將它停用。 如需詳細資訊，請參閱 [停用或啟用 Lync Server 2013 中的](lync-server-2013-disabling-or-enabling-a-chat-room.md)聊天室。

Persistent Chat 系統管理員可以查詢已停用的聊天室，而且可以定期清除和永久刪除聊天室，方法是使用 Windows PowerShell Cmdlet **Remove-CsPersistentChatRoom**。

類別可刪除。 不過，若要刪除類別，您必須先刪除其底下的所有聊天室，或將聊天室移至新的類別，讓空類別成為待刪除的。 Persistent Chat Server 不允許您刪除包含聊天室的類別。 如需詳細資訊，請參閱 [Lync Server 2013 中的將聊天室從某個類別移到另一個類別](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)。

如需使用 Windows PowerShell 命令列介面刪除空類別的詳細資訊，請參閱 [使用 windows PowerShell Cmdlet 設定 Persistent Chat Server](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的「會議室管理」。

如需聊天室和類別的詳細資訊，請參閱部署檔中的在 lync server [2013 中設定聊天室](lync-server-2013-configure-rooms.md) 和 [設定 lync server 2013](lync-server-2013-configure-categories.md) 中的類別。

</div>

<span> </span>

</div>

</div>

</div>

