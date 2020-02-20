---
title: Lync Server 2013： 將聊天室從某個類別移至另一個
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bde33220c13b5a484f66131ce6090d57d3b9bae
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a>將聊天室從某個類別移至 Lync Server 2013 中的另一個

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

我們建議您不要變更的常設聊天室類別之後建立的聊天室。 不過，如果聊天室管理員擁有其他類別的「建立者」**** 權限，即可將一個類別中的聊天室移到另一個類別。 未刪除或重新建立聊天室。 這是與資料庫的關聯出現變更。

變更聊天室類別的機會應該很少。類別會決定允許的聊天室成員資格，因此，將聊天室移到另一個類別時，將清除新類別不再支援的所有系統存取控制清單 (SACL)。例如，如果使用者原先是聊天室的成員，但不再是新類別中的 **AllowedMember**，將修改聊天室成員資格，並且從聊天室移除該使用者。

如需使用 Windows PowerShell 命令列介面移動聊天室的詳細資訊，請參閱[使用 Windows PowerShell cmdlet 的 Configuring Persistent Chat Server](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 「 聊天室管理 」。

如需設定聊天室的詳細資訊，請參閱部署文件中的[Lync Server 2013 中的 Configure rooms](lync-server-2013-configure-rooms.md) 。

</div>

<span> </span>

</div>

</div>

</div>

