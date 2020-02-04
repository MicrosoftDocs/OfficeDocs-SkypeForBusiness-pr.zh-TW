---
title: Lync Server 2013：指派每個使用者的原則
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
ms.openlocfilehash: 6b80446d9117a37b86c386132aa80439cb568a98
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-policies-in-lync-server-2013"></a><span data-ttu-id="0c31f-102">在 Lync Server 2013 中指派每個使用者的原則</span><span class="sxs-lookup"><span data-stu-id="0c31f-102">Assigning per-user policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c31f-103">_**主題上次修改日期：** 2012-10-14_</span><span class="sxs-lookup"><span data-stu-id="0c31f-103">_**Topic Last Modified:** 2012-10-14_</span></span>

<span data-ttu-id="0c31f-104">您可以將特定的原則指派給使用者或使用者群組，以指定與指派給其他使用者之原則（例如全域原則）中定義之設定不同的特定設定。</span><span class="sxs-lookup"><span data-stu-id="0c31f-104">You can assign certain policies to a user or a group of users in order to specify particular settings that deviate from the settings defined in policies assigned to other users, such as global policies.</span></span> <span data-ttu-id="0c31f-105">這些原則稱為 [每使用者原則]。</span><span class="sxs-lookup"><span data-stu-id="0c31f-105">These policies are called per-user policies.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0c31f-106">本節內容</span><span class="sxs-lookup"><span data-stu-id="0c31f-106">In This Section</span></span>

  - [<span data-ttu-id="0c31f-107">在 Lync Server 2013 中指派每使用者會議原則</span><span class="sxs-lookup"><span data-stu-id="0c31f-107">Assign a per-user conferencing policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-conferencing-policy.md)

  - [<span data-ttu-id="0c31f-108">在 Lync Server 2013 中指派每使用者用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="0c31f-108">Assign a per-user client version policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-client-version-policy.md)

  - [<span data-ttu-id="0c31f-109">在 Lync Server 2013 中指派每位使用者的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="0c31f-109">Assign a per-user PIN policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-pin-policy.md)

  - [<span data-ttu-id="0c31f-110">在 Lync Server 2013 中將外部使用者存取原則指派給擁有 Lync 功能的使用者</span><span class="sxs-lookup"><span data-stu-id="0c31f-110">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="0c31f-111">在 Lync Server 2013 中指派每個使用者的存檔原則</span><span class="sxs-lookup"><span data-stu-id="0c31f-111">Assign a per-user archiving policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-archiving-policy.md)

  - [<span data-ttu-id="0c31f-112">在 Lync Server 2013 中指派每位使用者的位置原則</span><span class="sxs-lookup"><span data-stu-id="0c31f-112">Assign a per-user location policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-location-policy.md)

  - [<span data-ttu-id="0c31f-113">在 Lync Server 2013 中指派每個使用者的行動原則</span><span class="sxs-lookup"><span data-stu-id="0c31f-113">Assign a per-user mobility policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-mobility-policy.md)

  - [<span data-ttu-id="0c31f-114">指派 Lync Server 2013 中的每個使用者持續聊天原則</span><span class="sxs-lookup"><span data-stu-id="0c31f-114">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-persistent-chat-policy.md)

  - [<span data-ttu-id="0c31f-115">在 Lync Server 2013 中指派每個使用者的撥號方案原則</span><span class="sxs-lookup"><span data-stu-id="0c31f-115">Assign a per-user dial plan policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-dial-plan-policy.md)

  - [<span data-ttu-id="0c31f-116">在 Lync Server 2013 中指派每個使用者的語音原則</span><span class="sxs-lookup"><span data-stu-id="0c31f-116">Assign a per-user voice policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-voice-policy.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0c31f-117">請參閱</span><span class="sxs-lookup"><span data-stu-id="0c31f-117">See Also</span></span>


[<span data-ttu-id="0c31f-118">在 Lync Server 2013 中管理使用者</span><span class="sxs-lookup"><span data-stu-id="0c31f-118">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

