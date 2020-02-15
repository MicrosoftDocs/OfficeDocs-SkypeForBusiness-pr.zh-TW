---
title: Lync Server 2013： 使用 Office Web Apps Server 的設定用戶端
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
ms.openlocfilehash: 9bbe3e71ca23216801582d15438590f99625ae88
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "41996598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a><span data-ttu-id="49359-102">設定用戶端的 Lync Server 2013 與 Office Web Apps Server 搭配使用</span><span class="sxs-lookup"><span data-stu-id="49359-102">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49359-103">_**上次修改主題：** 2013年-02-25_</span><span class="sxs-lookup"><span data-stu-id="49359-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="49359-104">如果您想要體驗 Office Web 應用程式伺服器的完整功能的使用者接著您應該這些使用者升級至 Microsoft Lync 2013;只有 Lync 2013 的使用者將能夠變得獨立的實際的 PowerPoint 簡報的 PowerPoint 投影片的捲軸。</span><span class="sxs-lookup"><span data-stu-id="49359-104">If you want users to experience the full capabilities of Office Web App Server then you should upgrade those users to Microsoft Lync 2013; only users of Lync 2013 will be able to do such things as scroll through PowerPoint slides independent of the actual PowerPoint presentation.</span></span> <span data-ttu-id="49359-105">（亦即，這些使用者可以查看在任何時候，簡報中的任何投影片不會以任何方式干擾實際的簡報。）不使用 Lync 2013 的使用者仍然能夠加入線上會議，並檢視 PowerPoint 簡報;不過，他們將無法單獨捲動投影片，也將它們能夠看到投影片切換效果，或檢視內嵌的影片。</span><span class="sxs-lookup"><span data-stu-id="49359-105">(That is, these users can look at any slide in the presentation at any time, without interfering in any way with the actual presentation.) Users who are not using Lync 2013 will still be able to join online conferences and view the PowerPoint presentation; however, they will not be able to independently scroll through the slides, nor will they be able to see slide transitions or view embedded videos.</span></span>

<span data-ttu-id="49359-106">請注意，這些功能將會一律可供使用者使用 Lync 2013;即使 PowerPoint 簡報者正在執行 Microsoft Lync 2010，這是，則為 true。</span><span class="sxs-lookup"><span data-stu-id="49359-106">Note that these capabilities will always be available to users of Lync 2013; this is true even if the PowerPoint presenter is running Microsoft Lync 2010.</span></span> <span data-ttu-id="49359-107">如果正在執行 Lync 2010 使用者所裝載的 PowerPoint 簡報，Lync Server 2013 將居中協調，以確定 Lync 2013 的使用者，將檢視該簡報的 Office Web Apps Server 版本的 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="49359-107">If a PowerPoint presentation is being hosted by a user running Lync 2010, Lync Server 2013 will coordinate with Office Web Apps Server to make sure that Lync 2013 users will view the Office Web Apps Server version of that presentation.</span></span> <span data-ttu-id="49359-108">Office Web Apps Server 不提供 PowerPoint 服務執行 Lync 2013 之外的用戶端的使用者。</span><span class="sxs-lookup"><span data-stu-id="49359-108">Office Web Apps Server does not provide PowerPoint services for users running clients other than Lync 2013.</span></span> <span data-ttu-id="49359-109">相反地，這些使用者連線至會議伺服器服務，以及他們沒有 Microsoft Lync Server 2010 中的相同方式來檢視 PowerPoint 簡報。</span><span class="sxs-lookup"><span data-stu-id="49359-109">Instead, those users connect to the Conferencing server service and view PowerPoint presentations the same way they did in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="49359-110">這也表示這些使用者只能夠存取 Lync Server 2010 所提供的更有限功能。</span><span class="sxs-lookup"><span data-stu-id="49359-110">This also means that these users will only have access to the more-limited capabilities offered by Lync Server 2010.</span></span>

<span data-ttu-id="49359-111">雖然用戶端就不需要設定 Office Web Apps server （不是將使用者升級到 Lync 2013），但建議會議出席者是升級為 Internet Explorer 9。</span><span class="sxs-lookup"><span data-stu-id="49359-111">Although no client configuration is required for Office Web Apps Server (other than upgrading users to Lync 2013), it is recommended that conference attendees be upgrade to Internet Explorer 9.</span></span> <span data-ttu-id="49359-112">雖然可以使用 Internet Explorer 8 來存取會議，但有一些限制使用該網頁瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="49359-112">Although conferences can be accessed using Internet Explorer 8, there are some limitations to using that Web browser.</span></span> <span data-ttu-id="49359-113">例如，使用者的 Internet Explorer 8 無法調整大小以自訂的大小; PowerPoint 階段相反地，他們會使用下列其中一個三個預先定義的階段大小限制。</span><span class="sxs-lookup"><span data-stu-id="49359-113">For example, users of Internet Explorer 8 will not be able to resize the PowerPoint stage to a custom size; instead, they will be limited to using one of three predefined stage sizes.</span></span> <span data-ttu-id="49359-114">同樣地，Internet Explorer 8 使用者將無法播放媒體檔案。</span><span class="sxs-lookup"><span data-stu-id="49359-114">Likewise, Internet Explorer 8 users will not be able to play media files.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

