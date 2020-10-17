---
title: Lync Server 2013：指派每個使用者的原則
description: Lync Server 2013：指派每個使用者的原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user policies
ms:assetid: a4ed0120-d9e5-4eb2-acfd-8de2cb503652
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182561(v=OCS.15)
ms:contentKeyID: 48184971
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a99156f9413926251c27dfee40677976b80b7ea
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563359"
---
# <a name="assigning-per-user-policies-in-lync-server-2013"></a><span data-ttu-id="1dd5c-103">在 Lync Server 2013 中指派每一使用者原則</span><span class="sxs-lookup"><span data-stu-id="1dd5c-103">Assigning per-user policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1dd5c-104">_**主題上次修改日期：** 2012-10-14_</span><span class="sxs-lookup"><span data-stu-id="1dd5c-104">_**Topic Last Modified:** 2012-10-14_</span></span>

<span data-ttu-id="1dd5c-105">您可以將特定原則指派給使用者或使用者群組，以指定與指派給其他使用者之原則中所定義的設定（例如全域原則）不同的特定設定。</span><span class="sxs-lookup"><span data-stu-id="1dd5c-105">You can assign certain policies to a user or a group of users in order to specify particular settings that deviate from the settings defined in policies assigned to other users, such as global policies.</span></span> <span data-ttu-id="1dd5c-106">這些原則稱為各個使用者原則。</span><span class="sxs-lookup"><span data-stu-id="1dd5c-106">These policies are called per-user policies.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1dd5c-107">本章節內容</span><span class="sxs-lookup"><span data-stu-id="1dd5c-107">In This Section</span></span>

  - [<span data-ttu-id="1dd5c-108">在 Lync Server 2013 中指派每個使用者的會議原則</span><span class="sxs-lookup"><span data-stu-id="1dd5c-108">Assign a per-user conferencing policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-conferencing-policy.md)

  - [<span data-ttu-id="1dd5c-109">在 Lync Server 2013 中指派每個使用者的用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="1dd5c-109">Assign a per-user client version policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-client-version-policy.md)

  - [<span data-ttu-id="1dd5c-110">在 Lync Server 2013 中指派每個使用者的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="1dd5c-110">Assign a per-user PIN policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-pin-policy.md)

  - [<span data-ttu-id="1dd5c-111">在 Lync Server 2013 中將外部使用者存取原則指派給啟用 Lync 功能的使用者</span><span class="sxs-lookup"><span data-stu-id="1dd5c-111">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="1dd5c-112">在 Lync Server 2013 中指派每一使用者的封存原則</span><span class="sxs-lookup"><span data-stu-id="1dd5c-112">Assign a per-user archiving policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-archiving-policy.md)

  - [<span data-ttu-id="1dd5c-113">在 Lync Server 2013 中指派每位使用者的位置原則</span><span class="sxs-lookup"><span data-stu-id="1dd5c-113">Assign a per-user location policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-location-policy.md)

  - [<span data-ttu-id="1dd5c-114">在 Lync Server 2013 中指派每個使用者的行動性原則</span><span class="sxs-lookup"><span data-stu-id="1dd5c-114">Assign a per-user mobility policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-mobility-policy.md)

  - [<span data-ttu-id="1dd5c-115">在 Lync Server 2013 中指派每一使用者的持續性聊天原則</span><span class="sxs-lookup"><span data-stu-id="1dd5c-115">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-persistent-chat-policy.md)

  - [<span data-ttu-id="1dd5c-116">在 Lync Server 2013 中指派每個使用者的撥號對應表原則</span><span class="sxs-lookup"><span data-stu-id="1dd5c-116">Assign a per-user dial plan policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-dial-plan-policy.md)

  - [<span data-ttu-id="1dd5c-117">在 Lync Server 2013 中指派每位使用者的語音原則</span><span class="sxs-lookup"><span data-stu-id="1dd5c-117">Assign a per-user voice policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-voice-policy.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1dd5c-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1dd5c-118">See Also</span></span>


[<span data-ttu-id="1dd5c-119">在 Lync Server 2013 中管理使用者</span><span class="sxs-lookup"><span data-stu-id="1dd5c-119">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

