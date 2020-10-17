---
title: Lync Server 2013：管理未指派號碼的呼叫
description: Lync Server 2013：管理未指派號碼的呼叫。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing calls to unassigned numbers
ms:assetid: a45a7546-5ee6-4c1e-ab13-20a71a058f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688167(v=OCS.15)
ms:contentKeyID: 49733772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a91c1ec30ea1e942fa3ea27fbcd369572884a52a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569149"
---
# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="d8dcb-103">在 Lync Server 2013 中管理未指派號碼的呼叫</span><span class="sxs-lookup"><span data-stu-id="d8dcb-103">Managing calls to unassigned numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8dcb-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d8dcb-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d8dcb-105">Lync Server 可讓您設定撥打的電話號碼對您的組織有效，但未指派給使用者或電話的來電處理。</span><span class="sxs-lookup"><span data-stu-id="d8dcb-105">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="d8dcb-106">您可以使用宣告應用程式，將這些來電轉接至預先決定的目的地 (電話號碼、SIP URI 或語音信箱) 或播放音訊宣告或兩者皆有）。</span><span class="sxs-lookup"><span data-stu-id="d8dcb-106">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="d8dcb-107">您也可以將這些通話轉接至 Exchange UM 自動語音應答電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d8dcb-107">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="d8dcb-108">使用下列其中一種方式處理未指派號碼的呼叫，可協助您避免來電者 misdials 並聽到占線音的情況，或 SIP 用戶端收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="d8dcb-108">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="d8dcb-109">本節說明如何管理未指派號碼範圍，以處理未指派電話號碼的呼叫。</span><span class="sxs-lookup"><span data-stu-id="d8dcb-109">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers.</span></span> <span data-ttu-id="d8dcb-110">本節也說明當您想要在中斷期間進行這種功能時，如何在嚴重損壞修復過程中管理宣告。</span><span class="sxs-lookup"><span data-stu-id="d8dcb-110">The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d8dcb-111">在中斷期間使用未指派的號碼處理是選用的。</span><span class="sxs-lookup"><span data-stu-id="d8dcb-111">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d8dcb-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="d8dcb-112">In This Section</span></span>

  - [<span data-ttu-id="d8dcb-113">在 Lync Server 2013 中建立宣告</span><span class="sxs-lookup"><span data-stu-id="d8dcb-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="d8dcb-114">在 Lync Server 2013 中設定未指派的電話號碼</span><span class="sxs-lookup"><span data-stu-id="d8dcb-114">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="d8dcb-115">在 Lync Server 2013 中管理發生嚴重損壞修復期間的宣告</span><span class="sxs-lookup"><span data-stu-id="d8dcb-115">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

