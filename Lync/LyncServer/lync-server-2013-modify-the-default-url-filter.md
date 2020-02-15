---
title: Lync Server 2013： 修改預設 URL 篩選器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default URL filter
ms:assetid: 80a472b3-054e-45a6-80fc-9ee2bda28ee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182544(v=OCS.15)
ms:contentKeyID: 48184653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15511ea6b48697cddfebc40c671880a14a545557
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-url-filter-in-lync-server-2013"></a><span data-ttu-id="15167-102">修改 Lync Server 2013 中的預設 URL 篩選器</span><span class="sxs-lookup"><span data-stu-id="15167-102">Modify the default URL filter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15167-103">_**主題上次修改日期：** 2012年-06-26_</span><span class="sxs-lookup"><span data-stu-id="15167-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="15167-104">藉由使用立即訊息 (IM) 篩選器，Lync Server 2013 提供全域的 URL 篩選器來封鎖特定 Url 都會包含在整個 Lync Server 2013 部署的使用者之間的 IM 交談中。</span><span class="sxs-lookup"><span data-stu-id="15167-104">By using the instant messaging (IM) filter, Lync Server 2013 provides a global URL filter that blocks specific URLs contained in IM conversations among users throughout your Lync Server 2013 deployment.</span></span> <span data-ttu-id="15167-105">使用 Lync Server Control Panel，您可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="15167-105">By using Lync Server Control Panel, you can do the following:</span></span>

  - <span data-ttu-id="15167-106">封鎖立即訊息交談中的所有或部分 URL。</span><span class="sxs-lookup"><span data-stu-id="15167-106">Block all or a subset of URLs in instant message conversations.</span></span>

  - <span data-ttu-id="15167-p102">允許所有 URL。您可以選擇建立會在每個包含 URL 的立即訊息的開頭處插入的聲明。</span><span class="sxs-lookup"><span data-stu-id="15167-p102">Allow all URLs. As an option, you can create a notice that is inserted at the beginning of each instant message that contains a URL.</span></span>

  - <span data-ttu-id="15167-109">允許特定 URL，並在每個包含 URL 的立即訊息中附上警告。</span><span class="sxs-lookup"><span data-stu-id="15167-109">Allow specific URLs and include a warning with each instant message that contains a URL.</span></span>

<span data-ttu-id="15167-110">此外，您還可以選擇封鎖包含特定檔案類型的 URL，或是透過僅允許位於伺服器之近端內部網路區域中的 URL (內部網路 URL) 通過伺服器，而封鎖網際網路 URL。</span><span class="sxs-lookup"><span data-stu-id="15167-110">In addition, you can choose to block URLs that contain specific file types, or block only Internet URLs by allowing URLs that are within the server’s local intranet zone — intranet URLs — to pass through the server.</span></span> <span data-ttu-id="15167-111">如需 URL 篩選的詳細資訊，請參閱[設定檔案傳輸和篩選，以便立即訊息 (IM) 在 Lync Server 2013 中的 URL](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)。</span><span class="sxs-lookup"><span data-stu-id="15167-111">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="15167-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="15167-112">See Also</span></span>


[<span data-ttu-id="15167-113">設定檔案傳輸和立即訊息 (IM) 在 Lync Server 2013 中的 URL 篩選</span><span class="sxs-lookup"><span data-stu-id="15167-113">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="15167-114">Lync Server 2013 中建立新的檔案傳輸篩選器的特定站台</span><span class="sxs-lookup"><span data-stu-id="15167-114">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="15167-115">在處理 IM 交談中的超連結的 Lync Server 2013 中建立新的 URL 篩選</span><span class="sxs-lookup"><span data-stu-id="15167-115">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[<span data-ttu-id="15167-116">修改 Lync Server 2013 中的預設檔案傳輸篩選器</span><span class="sxs-lookup"><span data-stu-id="15167-116">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

