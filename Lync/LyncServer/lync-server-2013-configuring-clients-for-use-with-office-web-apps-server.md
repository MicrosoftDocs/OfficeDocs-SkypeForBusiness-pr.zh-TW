---
title: Lync Server 2013：設定用戶端以搭配使用 Office Web Apps Server
description: Lync Server 2013：設定用戶端以搭配使用 Office Web Apps Server。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b9bd7cf1e76c481c40381234ba1a84cda5500dc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545519"
---
# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a><span data-ttu-id="83041-103">設定 Lync Server 2013 的用戶端以搭配 Office Web Apps Server 使用</span><span class="sxs-lookup"><span data-stu-id="83041-103">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83041-104">_**主題上次修改日期：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="83041-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="83041-105">如果您想要讓使用者體驗 Office Web App 伺服器的完整功能，您應該將這些使用者升級至 Microsoft Lync 2013;只有 Lync 2013 的使用者能夠在 PowerPoint 投影片的實際 PowerPoint 簡報以外的情況中做為滾動。</span><span class="sxs-lookup"><span data-stu-id="83041-105">If you want users to experience the full capabilities of Office Web App Server then you should upgrade those users to Microsoft Lync 2013; only users of Lync 2013 will be able to do such things as scroll through PowerPoint slides independent of the actual PowerPoint presentation.</span></span> <span data-ttu-id="83041-106"> (也就是說，這些使用者可以隨時查看簡報中的任何投影片，而不會干擾實際簡報。 ) 未使用 Lync 2013 的使用者仍可加入線上會議，並查看 PowerPoint 簡報。不過，他們將無法獨立流覽投影片，也無法看到投影片過渡或流覽內嵌影片。</span><span class="sxs-lookup"><span data-stu-id="83041-106">(That is, these users can look at any slide in the presentation at any time, without interfering in any way with the actual presentation.) Users who are not using Lync 2013 will still be able to join online conferences and view the PowerPoint presentation; however, they will not be able to independently scroll through the slides, nor will they be able to see slide transitions or view embedded videos.</span></span>

<span data-ttu-id="83041-107">請注意，Lync 2013 的使用者永遠都可以使用這些功能;即使 PowerPoint 簡報者執行 Microsoft Lync 2010，也是如此。</span><span class="sxs-lookup"><span data-stu-id="83041-107">Note that these capabilities will always be available to users of Lync 2013; this is true even if the PowerPoint presenter is running Microsoft Lync 2010.</span></span> <span data-ttu-id="83041-108">如果由執行 Lync 2010 的使用者主控 PowerPoint 簡報，Lync Server 2013 會與 Office Web Apps Server 協調，以確保 Lync 2013 使用者可以查看該簡報的 Office Web Apps Server 版本。</span><span class="sxs-lookup"><span data-stu-id="83041-108">If a PowerPoint presentation is being hosted by a user running Lync 2010, Lync Server 2013 will coordinate with Office Web Apps Server to make sure that Lync 2013 users will view the Office Web Apps Server version of that presentation.</span></span> <span data-ttu-id="83041-109">若使用者執行的是 Lync 2013 以外的用戶端，Office Web Apps Server 不會提供 PowerPoint 服務。</span><span class="sxs-lookup"><span data-stu-id="83041-109">Office Web Apps Server does not provide PowerPoint services for users running clients other than Lync 2013.</span></span> <span data-ttu-id="83041-110">相反地，這些使用者會連接到會議服務器服務，並以與在 Microsoft Lync Server 2010 中相同的方式來查看 PowerPoint 簡報。</span><span class="sxs-lookup"><span data-stu-id="83041-110">Instead, those users connect to the Conferencing server service and view PowerPoint presentations the same way they did in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="83041-111">這也表示這些使用者只會能夠存取 Lync Server 2010 提供的功能較少的功能。</span><span class="sxs-lookup"><span data-stu-id="83041-111">This also means that these users will only have access to the more-limited capabilities offered by Lync Server 2010.</span></span>

<span data-ttu-id="83041-112">雖然沒有必要的用戶端設定為 Office Web Apps Server (，但將使用者升級至 Lync 2013) 之外，還是建議會議出席者升級到 Internet Explorer 9。</span><span class="sxs-lookup"><span data-stu-id="83041-112">Although no client configuration is required for Office Web Apps Server (other than upgrading users to Lync 2013), it is recommended that conference attendees be upgrade to Internet Explorer 9.</span></span> <span data-ttu-id="83041-113">雖然可以使用 Internet Explorer 8 存取會議，但使用該網頁瀏覽器有一些限制。</span><span class="sxs-lookup"><span data-stu-id="83041-113">Although conferences can be accessed using Internet Explorer 8, there are some limitations to using that Web browser.</span></span> <span data-ttu-id="83041-114">例如，Internet Explorer 8 的使用者將無法將 PowerPoint 階段的大小調整為自訂大小;相反地，它們會限制為使用三個預先定義的階段大小之一。</span><span class="sxs-lookup"><span data-stu-id="83041-114">For example, users of Internet Explorer 8 will not be able to resize the PowerPoint stage to a custom size; instead, they will be limited to using one of three predefined stage sizes.</span></span> <span data-ttu-id="83041-115">同樣地，Internet Explorer 8 使用者將無法播放媒體檔案。</span><span class="sxs-lookup"><span data-stu-id="83041-115">Likewise, Internet Explorer 8 users will not be able to play media files.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

