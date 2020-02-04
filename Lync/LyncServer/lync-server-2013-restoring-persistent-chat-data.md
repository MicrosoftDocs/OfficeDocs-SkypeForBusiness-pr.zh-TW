---
title: Lync Server 2013：還原持續聊天資料
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
ms.openlocfilehash: 5734296a9b3463740b28e6ead33cc64234640432
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a>在 Lync Server 2013 中還原持續聊天資料

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-18_

持續聊天室內容會儲存在持久性聊天資料庫（mgc）。 這是應定期備份的業務關鍵型資料。 除了聊天室內容之外，主體（例如使用者和群組）以及他們對聊天室和聊天室內容所擁有的角色和存取權也會儲存在持久性聊天資料庫中。

您還原持久聊天資料的方式，取決於您用來備份它的方法。

  - 如果您使用的是 SQL Server 備份程式，您必須使用 SQL Server restore 程式。

  - 如果您使用**Export CsPersistentChatData** Cmdlet 來備份持續聊天資料，您必須使用**Import-CsPersistentChatData** Cmdlet 來還原資料。

</div>

<span> </span>

</div>

</div>

</div>

