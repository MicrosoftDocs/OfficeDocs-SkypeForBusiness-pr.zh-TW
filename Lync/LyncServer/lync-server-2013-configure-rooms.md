---
title: Lync Server 2013：設定聊天室
description: Lync Server 2013：設定聊天室。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9f5b2ece8cf436fe69c000da73871cb92686d82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542769"
---
# <a name="configure-rooms-in-lync-server-2013"></a>在 Lync Server 2013 中設定聊天室

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

設定 Persistent 聊天室通常是由使用者或其他中央小組處理，使用 Windows PowerShell 命令列介面;管理員通常不會管理聊天室。 不過，如果您必須建立及管理聊天室，您可以使用 [Windows PowerShell] 命令列介面，或將自己新增為聊天室的成員，並使用 Lync 2013 用戶端。

如需使用 Windows PowerShell 命令列介面設定聊天室的詳細資訊，請參閱 [使用 windows PowerShell Cmdlet 設定 Persistent Chat Server](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的「會議室管理」。

<div>

## <a name="managing-data-in-chat-rooms"></a>在聊天室中管理資料

Persistent Chat Server 可讓使用者以電子郵件的方式將郵件張貼到持續聊天室中進行共同作業。 資料會保留在伺服器上，而會議室的成員可以存取資料，包括歷史資料。 不過，具有不同角色的使用者具有不同的保存資料存取權，如下表所述。

  - 管理員可以刪除舊版內容 (例如，在特定日期之前發佈的內容) 從任何聊天室，以防止資料庫變得太大。 或者，他們可以移除或取代視為不適用於特定聊天室的郵件。

  - 使用者（包括郵件作者）無法刪除任何聊天室中的內容。

  - 聊天室管理員可以停用會議室，但無法刪除會議室。 只有管理員可以在建立聊天室之後刪除聊天室。

當郵件刪除時，您無法復原動作。 不過，如果有備份，可還原刪除的郵件。 如果已啟用 Persistent Chat 規範伺服器，則會在規範資料庫中保留舊郵件。

<div>


> [!NOTE]  
> 這種聊天室資料使用量適用于 Lync Server 2013，Persistent Chat Server API 應用程式，但不包括系統管理員角色的情況例外。 Persistent Chat Server API 無法用來執行任何系統管理員的任何作業。 您必須在 Lync Server 管理命令介面中執行這些作業。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

