---
title: Lync Server 2013： 設定聊天室
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
ms.openlocfilehash: 7e78401d0f72f3b29f50453f49f7d7eb66811715
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a>Lync Server 2013 中設定聊天室

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-06_

設定常設聊天室通常用於由使用者或其他中央小組使用 Windows PowerShell 命令列介面;系統管理員通常不會管理聊天室。 不過，如果您必須建立及管理聊天室，您可以使用 Windows PowerShell 命令列介面，或者將自己新增為成員的聊天室並使用 Lync 2013 用戶端。

如需使用 Windows PowerShell 命令列介面來設定聊天室的詳細資訊，請參閱[使用 Windows PowerShell cmdlet 的 Configuring Persistent Chat Server](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 「 聊天室管理 」。

<div>

## <a name="managing-data-in-chat-rooms"></a>管理聊天室中的資料

Persistent Chat Server 可讓使用者藉由將訊息張貼到的常設聊天室共同作業。 將資料保存在伺服器上，和聊天室的成員可以存取資料，包括歷程資料。 不過，具有不同角色的使用者都有不同的存取權的保存的資料，下列清單中所述。

  - 系統管理員可以從任何聊天室時亦可讓資料庫變得太大刪除舊內容 （例如，在特定日期之前已張貼的內容）。 或者，他們可以移除或取代會被視為不適用於特定聊天室的訊息。

  - 使用者，包括訊息作者無法刪除任何聊天室中的內容。

  - 聊天室管理員可以停用聊天室，但是無法刪除聊天室。 已建立之後，只有系統管理員可以刪除聊天室。

刪除郵件時，您無法復原的動作。 不過，如果沒有備份，可以還原已刪除的郵件。 如果啟用常設聊天室規範伺服器，則舊的郵件會保存在規範資料庫。

<div>


> [!NOTE]  
> 此聊天室資料使用適用於 Lync Server 2013，Persistent Chat Server API 應用程式，但不包括種情況下，系統管理員角色的相關資訊。 常設聊天室伺服器 API 無法用來執行任何系統管理員的作業。 您必須在 Lync Server 管理命令介面中執行這些作業。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

