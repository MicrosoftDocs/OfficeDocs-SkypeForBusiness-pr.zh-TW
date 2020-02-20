---
title: Lync Server 2013： 指派個別使用者原則
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
ms.openlocfilehash: acee046ebe05d87e17cd72ef1c5d8d19830d4ee8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-policies-in-lync-server-2013"></a><span data-ttu-id="453d7-102">指派 Lync Server 2013 中的個別使用者原則</span><span class="sxs-lookup"><span data-stu-id="453d7-102">Assigning per-user policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="453d7-103">_**主題上次修改日期：** 2012年-10-14_</span><span class="sxs-lookup"><span data-stu-id="453d7-103">_**Topic Last Modified:** 2012-10-14_</span></span>

<span data-ttu-id="453d7-104">若要指定原則指派給其他使用者，例如全域原則中定義的設定以外的特定設定，可以指派給使用者或一群使用者的特定原則。</span><span class="sxs-lookup"><span data-stu-id="453d7-104">You can assign certain policies to a user or a group of users in order to specify particular settings that deviate from the settings defined in policies assigned to other users, such as global policies.</span></span> <span data-ttu-id="453d7-105">這些原則稱為個別使用者原則。</span><span class="sxs-lookup"><span data-stu-id="453d7-105">These policies are called per-user policies.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="453d7-106">本章節內容</span><span class="sxs-lookup"><span data-stu-id="453d7-106">In This Section</span></span>

  - [<span data-ttu-id="453d7-107">指派 Lync Server 2013 中的個別使用者會議原則</span><span class="sxs-lookup"><span data-stu-id="453d7-107">Assign a per-user conferencing policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-conferencing-policy.md)

  - [<span data-ttu-id="453d7-108">指派每位使用者用戶端版本原則在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="453d7-108">Assign a per-user client version policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-client-version-policy.md)

  - [<span data-ttu-id="453d7-109">指派 Lync Server 2013 中的每位使用者的 pin 碼原則</span><span class="sxs-lookup"><span data-stu-id="453d7-109">Assign a per-user PIN policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-pin-policy.md)

  - [<span data-ttu-id="453d7-110">指派給 Lync Server 2013 中啟用 Lync 功能之使用者的外部使用者存取原則</span><span class="sxs-lookup"><span data-stu-id="453d7-110">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="453d7-111">指派 Lync Server 2013 中的個別使用者封存原則</span><span class="sxs-lookup"><span data-stu-id="453d7-111">Assign a per-user archiving policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-archiving-policy.md)

  - [<span data-ttu-id="453d7-112">Lync Server 2013 中的個別使用者位置原則指派</span><span class="sxs-lookup"><span data-stu-id="453d7-112">Assign a per-user location policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-location-policy.md)

  - [<span data-ttu-id="453d7-113">Lync Server 2013 中的每一使用者行動性原則指派</span><span class="sxs-lookup"><span data-stu-id="453d7-113">Assign a per-user mobility policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-mobility-policy.md)

  - [<span data-ttu-id="453d7-114">指派 Lync Server 2013 中的個別使用者常設聊天室原則</span><span class="sxs-lookup"><span data-stu-id="453d7-114">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-persistent-chat-policy.md)

  - [<span data-ttu-id="453d7-115">指派 Lync Server 2013 中的個別使用者撥號對應表規劃原則</span><span class="sxs-lookup"><span data-stu-id="453d7-115">Assign a per-user dial plan policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-dial-plan-policy.md)

  - [<span data-ttu-id="453d7-116">指派 Lync Server 2013 中的個別使用者語音原則</span><span class="sxs-lookup"><span data-stu-id="453d7-116">Assign a per-user voice policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-voice-policy.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="453d7-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="453d7-117">See Also</span></span>


[<span data-ttu-id="453d7-118">在 Lync Server 2013 中管理使用者</span><span class="sxs-lookup"><span data-stu-id="453d7-118">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

