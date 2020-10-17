---
title: Lync Server 2013：修改預設 URL 篩選器
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
ms.openlocfilehash: 4f9d730bcdf17c9f78aee25ba3cec56f99a67086
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515180"
---
# <a name="modify-the-default-url-filter-in-lync-server-2013"></a><span data-ttu-id="d4505-102">在 Lync Server 2013 中修改預設 URL 篩選器</span><span class="sxs-lookup"><span data-stu-id="d4505-102">Modify the default URL filter in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4505-103">_**主題上次修改日期：** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="d4505-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="d4505-104">透過使用立即訊息 (IM) 篩選器，Lync Server 2013 可提供全域 URL 篩選器，以封鎖整個 Lync Server 2013 部署中的使用者間 IM 交談中所包含的特定 URLs。</span><span class="sxs-lookup"><span data-stu-id="d4505-104">By using the instant messaging (IM) filter, Lync Server 2013 provides a global URL filter that blocks specific URLs contained in IM conversations among users throughout your Lync Server 2013 deployment.</span></span> <span data-ttu-id="d4505-105">使用 Lync Server 控制台，您可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d4505-105">By using Lync Server Control Panel, you can do the following:</span></span>

  - <span data-ttu-id="d4505-106">封鎖立即訊息交談中的所有或部分 URL。</span><span class="sxs-lookup"><span data-stu-id="d4505-106">Block all or a subset of URLs in instant message conversations.</span></span>

  - <span data-ttu-id="d4505-p102">允許所有 URL。您可以選擇建立會在每個包含 URL 的立即訊息的開頭處插入的聲明。</span><span class="sxs-lookup"><span data-stu-id="d4505-p102">Allow all URLs. As an option, you can create a notice that is inserted at the beginning of each instant message that contains a URL.</span></span>

  - <span data-ttu-id="d4505-109">允許特定 URL，並在每個包含 URL 的立即訊息中附上警告。</span><span class="sxs-lookup"><span data-stu-id="d4505-109">Allow specific URLs and include a warning with each instant message that contains a URL.</span></span>

<span data-ttu-id="d4505-110">此外，您還可以選擇封鎖包含特定檔案類型的 URL，或是透過僅允許位於伺服器之近端內部網路區域中的 URL (內部網路 URL) 通過伺服器，而封鎖網際網路 URL。</span><span class="sxs-lookup"><span data-stu-id="d4505-110">In addition, you can choose to block URLs that contain specific file types, or block only Internet URLs by allowing URLs that are within the server’s local intranet zone — intranet URLs — to pass through the server.</span></span> <span data-ttu-id="d4505-111">如需 URL 篩選的詳細資訊，請參閱 [在 Lync Server 2013 中設定立即訊息 (IM) 的檔案傳送和 URL 篩選](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)。</span><span class="sxs-lookup"><span data-stu-id="d4505-111">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d4505-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d4505-112">See Also</span></span>


[<span data-ttu-id="d4505-113">在 Lync Server 2013 中設定立即訊息 (IM) 的檔案傳送和 URL 篩選</span><span class="sxs-lookup"><span data-stu-id="d4505-113">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="d4505-114">在 Lync Server 2013 中為特定網站建立新的檔案傳輸篩選器</span><span class="sxs-lookup"><span data-stu-id="d4505-114">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="d4505-115">在 Lync Server 2013 中建立新的 URL 篩選，以處理 IM 交談中的超連結</span><span class="sxs-lookup"><span data-stu-id="d4505-115">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[<span data-ttu-id="d4505-116">在 Lync Server 2013 中修改預設檔案傳輸篩選器</span><span class="sxs-lookup"><span data-stu-id="d4505-116">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

