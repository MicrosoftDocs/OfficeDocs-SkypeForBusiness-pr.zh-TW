---
title: Lync Server 2013：新語音信箱功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New voice mail feature
ms:assetid: 84d13238-67ef-42cc-801a-2d8147ba3b7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688117(v=OCS.15)
ms:contentKeyID: 49733715
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27dbea942488181eb69695f78713c9e126c32aab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-voice-mail-feature-in-lync-server-2013"></a><span data-ttu-id="9e014-102">Lync Server 2013 中的新語音信箱功能</span><span class="sxs-lookup"><span data-stu-id="9e014-102">New voice mail feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e014-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="9e014-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="9e014-104">Lync Server 2013 引入了語音信箱轉義，這是一種管理語音信箱的增強功能。</span><span class="sxs-lookup"><span data-stu-id="9e014-104">Lync Server 2013 introduces Voice mail Escape, an enhancement for managing voice mail.</span></span> <span data-ttu-id="9e014-105">這項新功能可以偵測通話何時傳送至語音信箱，並防止通話立即路由到使用者的行動電話語音信箱，而不給予使用者接聽通話的機會。</span><span class="sxs-lookup"><span data-stu-id="9e014-105">This new feature can detect when a call has been routed to voice mail, and prevent the call from being immediately routed to the user’s mobile phone voice mail without giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="9e014-106">當使用者同時撥打到行動電話，且其行動電話已關閉、不在電池或超出範圍時，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="9e014-106">This scenario occurs when the user enables simultaneous ringing to their mobile phone, and their mobile phone is turned off, out of battery, or out of range.</span></span> <span data-ttu-id="9e014-107">語音信箱轉義會偵測到通話是由使用者的行動電話語音信箱立即應答，然後中斷通話與行動電話語音信箱的連線。</span><span class="sxs-lookup"><span data-stu-id="9e014-107">Voicemail Escape detects that the call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="9e014-108">通話會持續在使用者的其他端點撥打，讓使用者有機會接聽通話。</span><span class="sxs-lookup"><span data-stu-id="9e014-108">The call continues to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="9e014-109">如果使用者沒有接聽電話，通話會路由至公司語音信箱。</span><span class="sxs-lookup"><span data-stu-id="9e014-109">If the user does not answer the call, then the call is routed to the corporate voice mail.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="9e014-110">請參閱</span><span class="sxs-lookup"><span data-stu-id="9e014-110">See Also</span></span>


[<span data-ttu-id="9e014-111">在 Lync Server 2013 中設定語音信箱轉義</span><span class="sxs-lookup"><span data-stu-id="9e014-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="9e014-112">Lync Server 2013 中的新企業語音功能</span><span class="sxs-lookup"><span data-stu-id="9e014-112">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

