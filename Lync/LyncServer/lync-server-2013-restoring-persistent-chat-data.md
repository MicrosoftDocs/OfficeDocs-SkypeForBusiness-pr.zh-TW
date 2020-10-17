---
title: Lync Server 2013：還原持久聊天資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Persistent Chat data
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945649(v=OCS.15)
ms:contentKeyID: 51541516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dfe3a6c23e9de159c9024d660caf3f04fe648b7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511406"
---
# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a>在 Lync Server 2013 中還原 Persistent Chat 資料

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-18_

Persistent 聊天室內容會儲存在 Persistent Chat (mgc) 中。 這是應該定期備份的重要業務資料。 除了聊天室內容之外，主體 (（例如使用者和群組）) 以及必須與聊天室內容和聊天室內容之間的角色和存取，也會儲存在 Persistent Chat 資料庫中。

還原持久聊天資料的方式取決於您用來備份它的方法。

  - 如果您使用 SQL Server 備份程式，您必須使用 SQL Server 還原程式。

  - 如果您使用 **Export-CsPersistentChatData** Cmdlet 來備份 Persistent 聊天資料，則必須使用 **Import-CsPersistentChatData** Cmdlet 來還原資料。

</div>

<span> </span>

</div>

</div>

</div>

