---
title: Lync Server 2013：設定聊天室
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
ms.openlocfilehash: 06fea4fcda27eaedd671d833a4f53ed0ddec67c6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a>在 Lync Server 2013 中設定聊天室

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

設定持續性聊天室通常是由使用者或其他中心團隊使用 Windows PowerShell 命令列介面來處理;系統管理員通常不會管理聊天室。 不過，如果您必須建立及管理聊天室，您可以使用 Windows PowerShell 命令列介面，或將自己新增為聊天室的成員，然後使用 Lync 2013 用戶端。

如需使用 Windows PowerShell 命令列介面來設定聊天室的詳細資料，請參閱[使用 Windows powershell Cmdlet 來設定持久聊天伺服器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的「會議室管理」。

<div>

## <a name="managing-data-in-chat-rooms"></a>管理聊天室中的資料

持續聊天伺服器可讓使用者透過將訊息張貼到持久聊天室來共同作業。 資料會保留在伺服器上，而聊天室的成員可以存取資料，包括歷史資料。 不過，擁有不同角色的使用者會有不同的方式存取永久性資料，如下列清單所述。

  - 系統管理員可以從任何聊天室刪除較舊的內容（例如，在特定日期之前發佈的內容），讓資料庫不會變得太大。 或者，他們可以移除或取代被視為不適用於特定聊天室的郵件。

  - 使用者（包括郵件作者）無法刪除任何聊天室中的內容。

  - 聊天室管理員可以停用會議室，但無法刪除會議室。 只有系統管理員才能在已建立聊天室後刪除聊天室。

刪除郵件時，您無法復原該動作。 不過，如果有備份，就可以還原已刪除的郵件。 如果啟用持續性聊天規範伺服器，舊的訊息會保留在合規性資料庫中。

<div>


> [!NOTE]  
> 此聊天室資料使用量適用于 Lync Server 2013、持續聊天伺服器 API 應用程式，但涉及管理員角色的情況除外。 永久聊天伺服器 API 無法用來執行任何管理員的操作。 您必須在 Lync Server 管理命令介面中執行這些作業。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

