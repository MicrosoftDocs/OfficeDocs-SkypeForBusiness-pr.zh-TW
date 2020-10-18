---
title: Lync Server 2013：還原持久聊天資料
description: Lync Server 2013：復原 Persistent Chat data。
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
ms.openlocfilehash: 7c75683e151daaadab8374ed5b41886da9a3aea3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575512"
---
# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a><span data-ttu-id="2c080-103">在 Lync Server 2013 中還原 Persistent Chat 資料</span><span class="sxs-lookup"><span data-stu-id="2c080-103">Restoring Persistent Chat data in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c080-104">_**主題上次修改日期：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="2c080-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="2c080-105">Persistent 聊天室內容會儲存在 Persistent Chat (mgc) 中。</span><span class="sxs-lookup"><span data-stu-id="2c080-105">Persistent Chat room content is stored in the Persistent Chat database (mgc.mdf).</span></span> <span data-ttu-id="2c080-106">這是應該定期備份的重要業務資料。</span><span class="sxs-lookup"><span data-stu-id="2c080-106">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="2c080-107">除了聊天室內容之外，主體 (（例如使用者和群組）) 以及必須與聊天室內容和聊天室內容之間的角色和存取，也會儲存在 Persistent Chat 資料庫中。</span><span class="sxs-lookup"><span data-stu-id="2c080-107">In addition to the chat room content, principals (such as users and groups) and the roles and access that they have to chat rooms and chat room content, is also stored in the Persistent Chat database.</span></span>

<span data-ttu-id="2c080-108">還原持久聊天資料的方式取決於您用來備份它的方法。</span><span class="sxs-lookup"><span data-stu-id="2c080-108">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span>

  - <span data-ttu-id="2c080-109">如果您使用 SQL Server 備份程式，您必須使用 SQL Server 還原程式。</span><span class="sxs-lookup"><span data-stu-id="2c080-109">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span>

  - <span data-ttu-id="2c080-110">如果您使用 **Export-CsPersistentChatData** Cmdlet 來備份 Persistent 聊天資料，則必須使用 **Import-CsPersistentChatData** Cmdlet 來還原資料。</span><span class="sxs-lookup"><span data-stu-id="2c080-110">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

