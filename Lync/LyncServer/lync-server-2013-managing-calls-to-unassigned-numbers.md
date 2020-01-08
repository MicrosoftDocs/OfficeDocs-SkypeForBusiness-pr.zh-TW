---
title: Lync Server 2013：管理未指派號碼的呼叫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing calls to unassigned numbers
ms:assetid: a45a7546-5ee6-4c1e-ab13-20a71a058f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688167(v=OCS.15)
ms:contentKeyID: 49733772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50a6c7fe05729f705bd7ea752658f7c890188159
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="fd6af-102">管理 Lync Server 2013 中未指派號碼的呼叫</span><span class="sxs-lookup"><span data-stu-id="fd6af-102">Managing calls to unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd6af-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="fd6af-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="fd6af-104">Lync Server 可讓您設定撥入電話號碼對您的組織有效，但不會指派給使用者或電話。</span><span class="sxs-lookup"><span data-stu-id="fd6af-104">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="fd6af-105">您可以使用宣告應用程式，將這些來電轉接至預先確定的目的地（電話號碼、SIP URI 或語音信箱），或播放音訊公告或兩者。</span><span class="sxs-lookup"><span data-stu-id="fd6af-105">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="fd6af-106">您也可以將來電轉接到 Exchange UM 自動語音應答電話號碼。</span><span class="sxs-lookup"><span data-stu-id="fd6af-106">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="fd6af-107">使用下列其中一種方式處理未指定編號的呼叫可協助您避免來電者 misdials 或聽到占線的情況，或 SIP 用戶端收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="fd6af-107">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="fd6af-108">本節說明如何管理未指定的數位範圍，以處理未指派電話號碼的呼叫。</span><span class="sxs-lookup"><span data-stu-id="fd6af-108">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers.</span></span> <span data-ttu-id="fd6af-109">本節也說明如何在災害復原期間管理宣告（如果您在中斷期間想要此功能）。</span><span class="sxs-lookup"><span data-stu-id="fd6af-109">The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fd6af-110">在中斷期間使用未指定的數位處理是選用的。</span><span class="sxs-lookup"><span data-stu-id="fd6af-110">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fd6af-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="fd6af-111">In This Section</span></span>

  - [<span data-ttu-id="fd6af-112">在 Lync Server 2013 中建立公告</span><span class="sxs-lookup"><span data-stu-id="fd6af-112">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="fd6af-113">在 Lync Server 2013 中設定未指派的電話號碼</span><span class="sxs-lookup"><span data-stu-id="fd6af-113">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="fd6af-114">使用 Lync Server 2013 在災害復原期間管理宣告</span><span class="sxs-lookup"><span data-stu-id="fd6af-114">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

