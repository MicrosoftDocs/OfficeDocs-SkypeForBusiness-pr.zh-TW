---
title: Lync Server 2013： 管理未指派號碼的通話
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
ms.openlocfilehash: 12809736c67a4ad606503a3a663532b51a1a191b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="baece-102">管理 Lync Server 2013 中的未指派號碼的通話</span><span class="sxs-lookup"><span data-stu-id="baece-102">Managing calls to unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="baece-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="baece-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="baece-104">Lync Server 可讓您設定的電話上的來電處理時撥打的號碼適用於您的組織，但不指派給使用者或電話。</span><span class="sxs-lookup"><span data-stu-id="baece-104">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="baece-105">您可以使用宣告應用程式，這些將來電轉接給預定的目的地 （電話號碼、 SIP URI 或語音信箱），或播放音訊宣告，或兩者。</span><span class="sxs-lookup"><span data-stu-id="baece-105">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="baece-106">您可以也這些將來電轉接給 Exchange UM 的自動語音應答電話號碼。</span><span class="sxs-lookup"><span data-stu-id="baece-106">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="baece-107">處理通話未指派的號碼，在其中一種方式可協助您避免來電者時，然後聽到忙線中的色調，在情況或 SIP 用戶端會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="baece-107">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="baece-108">本節說明如何管理未指派號碼範圍，來處理未指派的電話號碼的來電。</span><span class="sxs-lookup"><span data-stu-id="baece-108">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers.</span></span> <span data-ttu-id="baece-109">[] 區段中也說明如何災害復原期間管理公告，如果您中斷期間需要此功能。</span><span class="sxs-lookup"><span data-stu-id="baece-109">The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="baece-110">使用未指派的號碼處理中斷期間是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="baece-110">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="baece-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="baece-111">In This Section</span></span>

  - [<span data-ttu-id="baece-112">Lync Server 2013 中建立的宣告</span><span class="sxs-lookup"><span data-stu-id="baece-112">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="baece-113">在 Lync Server 2013 中設定未指派的電話號碼</span><span class="sxs-lookup"><span data-stu-id="baece-113">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="baece-114">Lync Server 2013 中的災害復原期間管理公告</span><span class="sxs-lookup"><span data-stu-id="baece-114">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

