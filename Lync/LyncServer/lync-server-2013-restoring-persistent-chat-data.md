---
title: Lync Server 2013： 還原常設聊天室資料
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
ms.openlocfilehash: 3c905ee22ed237e908fc72e551f973b6f20fa8f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a><span data-ttu-id="4d1e0-102">還原 Lync Server 2013 中的 [常設聊天室資料</span><span class="sxs-lookup"><span data-stu-id="4d1e0-102">Restoring Persistent Chat data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d1e0-103">_**上次修改主題：** 2013年-02-18_</span><span class="sxs-lookup"><span data-stu-id="4d1e0-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="4d1e0-104">常設聊天室內容儲存在常設聊天室資料庫 (mgc.mdf)。</span><span class="sxs-lookup"><span data-stu-id="4d1e0-104">Persistent Chat room content is stored in the Persistent Chat database (mgc.mdf).</span></span> <span data-ttu-id="4d1e0-105">這是應該定期備份的重要商業資料。</span><span class="sxs-lookup"><span data-stu-id="4d1e0-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="4d1e0-106">除了聊天室內容、 主體 （例如使用者和群組） 的角色和它們對聊天室和聊天室內容的存取也儲存在常設聊天室資料庫。</span><span class="sxs-lookup"><span data-stu-id="4d1e0-106">In addition to the chat room content, principals (such as users and groups) and the roles and access that they have to chat rooms and chat room content, is also stored in the Persistent Chat database.</span></span>

<span data-ttu-id="4d1e0-107">還原您的常設聊天室資料的方式取決於您用來備份它的方法。</span><span class="sxs-lookup"><span data-stu-id="4d1e0-107">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span>

  - <span data-ttu-id="4d1e0-108">如果您使用 SQL Server 備份程序，您必須使用 SQL Server 還原程序。</span><span class="sxs-lookup"><span data-stu-id="4d1e0-108">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span>

  - <span data-ttu-id="4d1e0-109">如果您使用**Export-cspersistentchatdata**指令程式來備份常設聊天室資料，則必須使用**Import-cspersistentchatdata** cmdlet 來還原資料。</span><span class="sxs-lookup"><span data-stu-id="4d1e0-109">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

