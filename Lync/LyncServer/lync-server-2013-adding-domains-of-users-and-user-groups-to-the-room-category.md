---
title: Lync Server 2013： 將網域的使用者與使用者群組新增至聊天室類別
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding domains of users and user groups to the room category
ms:assetid: ee03f2cf-1c84-41c4-b524-d0729be33b8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215884(v=OCS.15)
ms:contentKeyID: 48706013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44138fba7524f74f660073f31a6af075d889ea64
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-domains-of-users-and-user-groups-to-the-room-category-in-lync-server-2013"></a><span data-ttu-id="eda8a-102">將網域的使用者與使用者群組新增至 Lync Server 2013 中的 [會議室] 類別</span><span class="sxs-lookup"><span data-stu-id="eda8a-102">Adding domains of users and user groups to the room category in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eda8a-103">_**上次修改主題：** 2014年-02-07_</span><span class="sxs-lookup"><span data-stu-id="eda8a-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="eda8a-104">若要將大型使用者群組新增至聊天室，請參閱部署文件中的[Lync Server 2013 中的 Configure categories](lync-server-2013-configure-categories.md)和[Manage categories](manage-categories.md) 。</span><span class="sxs-lookup"><span data-stu-id="eda8a-104">To add larger groups of users to a chat room, see [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) and [Manage categories](manage-categories.md) in the Deployment documentation.</span></span> <span data-ttu-id="eda8a-105">例如，此命令會將所有使用者從 active Directory 中的 NorthAmericaUsers OU 加入 NorthAmerica 聊天室時亦可：</span><span class="sxs-lookup"><span data-stu-id="eda8a-105">For example, this command adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=litwareinc,DC=com"}

<span data-ttu-id="eda8a-106">他的命令會將所有成員從 Finance 通訊群組都新增至相同的聊天室：</span><span class="sxs-lookup"><span data-stu-id="eda8a-106">His command adds all the members from the Finance distribution group to the same chat room:</span></span>

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=litwareinc,DC=com"}

</div>

<span> </span>

</div>

</div>

</div>

