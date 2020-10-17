---
title: Lync Server 2013：新增語音信箱功能
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
ms.openlocfilehash: aaeb0aff851064e1e257194cc4d5a67b8eaabfbe
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522260"
---
# <a name="new-voice-mail-feature-in-lync-server-2013"></a><span data-ttu-id="61649-102">Lync Server 2013 中的新語音信箱功能</span><span class="sxs-lookup"><span data-stu-id="61649-102">New voice mail feature in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61649-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="61649-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="61649-104">Lync Server 2013 引進語音信箱轉義程式，這是一種管理語音信箱的增強功能。</span><span class="sxs-lookup"><span data-stu-id="61649-104">Lync Server 2013 introduces Voice mail Escape, an enhancement for managing voice mail.</span></span> <span data-ttu-id="61649-105">這項新功能可以偵測來電何時路由傳送至語音信箱，並防止來電立即路由傳送到使用者的行動電話語音信箱，而不會讓使用者接聽通話的機會。</span><span class="sxs-lookup"><span data-stu-id="61649-105">This new feature can detect when a call has been routed to voice mail, and prevent the call from being immediately routed to the user’s mobile phone voice mail without giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="61649-106">當使用者同時向其行動電話進行同時震鈴，且其行動電話關閉、電池計量不足或超出範圍時，就會發生此案例。</span><span class="sxs-lookup"><span data-stu-id="61649-106">This scenario occurs when the user enables simultaneous ringing to their mobile phone, and their mobile phone is turned off, out of battery, or out of range.</span></span> <span data-ttu-id="61649-107">語音信箱 Escape 會偵測到呼叫已由使用者的行動電話語音信箱立即接聽，並將通話中斷與行動電話語音信箱的通話。</span><span class="sxs-lookup"><span data-stu-id="61649-107">Voicemail Escape detects that the call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="61649-108">通話繼續撥打使用者的其他端點，讓使用者有機會接聽通話。</span><span class="sxs-lookup"><span data-stu-id="61649-108">The call continues to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="61649-109">若使用者沒有接聽來電，來電會路由傳送到公司語音信箱。</span><span class="sxs-lookup"><span data-stu-id="61649-109">If the user does not answer the call, then the call is routed to the corporate voice mail.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="61649-110">另請參閱</span><span class="sxs-lookup"><span data-stu-id="61649-110">See Also</span></span>


[<span data-ttu-id="61649-111">在 Lync Server 2013 中設定語音信箱轉義</span><span class="sxs-lookup"><span data-stu-id="61649-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="61649-112">Lync Server 2013 中新的 Enterprise Voice 功能</span><span class="sxs-lookup"><span data-stu-id="61649-112">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

