---
title: Lync Server 2013：刪除聊天室或類別
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
ms.openlocfilehash: 74cf41679a21612e67c4a793c09ae3484377ef6e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a>在 Lync Server 2013 中刪除聊天室或類別

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

您可以刪除持久的聊天室。 如果您有不再使用的聊天室，您可以將它停用。 如需詳細資訊，請參閱[在 Lync Server 2013 中停用或啟用](lync-server-2013-disabling-or-enabling-a-chat-room.md)聊天室。

持續性聊天管理員可以查詢停用的聊天室，而且可以使用 Windows PowerShell Cmdlet 來定期清除及永久刪除聊天室，請**CsPersistentChatRoom**。

您可以刪除類別。 不過，若要刪除類別，您必須先刪除其底下的所有聊天室，或將聊天室移至新的類別，並將空的類別刪除。 持續聊天伺服器不允許您刪除包含聊天室的類別。 如需詳細資訊，請參閱[在 Lync Server 2013 將聊天室從一個類別移至另一個類別](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)。

如需使用 Windows PowerShell 命令列介面刪除空類別的詳細資訊，請參閱[使用 Windows powershell Cmdlet 來設定持久聊天伺服器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的「會議室管理」。

如需聊天室和類別的詳細資訊，請參閱在[Lync server 2013 中設定會議室](lync-server-2013-configure-rooms.md)，並在部署檔中[設定 lync server 2013](lync-server-2013-configure-categories.md)中的類別。

</div>

<span> </span>

</div>

</div>

</div>

