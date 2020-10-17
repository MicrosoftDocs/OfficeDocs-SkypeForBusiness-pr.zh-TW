---
title: 建立新的 URL 篩選器以處理 IM 交談中的超連結
description: 在 IM 交談中建立新的 URL 篩選，以處理超連結。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e583b3e8cbd04279ab7f54b4138a349fa0d1e85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554659"
---
# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a><span data-ttu-id="632a1-103">在 Lync Server 2013 中建立新的 URL 篩選，以處理 IM 交談中的超連結</span><span class="sxs-lookup"><span data-stu-id="632a1-103">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="632a1-104">_**主題上次修改日期：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="632a1-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="632a1-105">除了修改全域 URL 篩選器之外，您還可以在 Lync Server 2013 部署中為個別網站設定自訂 URL 篩選器。</span><span class="sxs-lookup"><span data-stu-id="632a1-105">In addition to modifying the global URL filter, you can configure custom URL filters for individual sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="632a1-106">如需 URL 篩選的詳細資訊，請參閱 [在 Lync Server 2013 中設定立即訊息 (IM) 的檔案傳送和 URL 篩選](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)。</span><span class="sxs-lookup"><span data-stu-id="632a1-106">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-new-url-filter"></a><span data-ttu-id="632a1-107">若要建立新的 URL 篩選</span><span class="sxs-lookup"><span data-stu-id="632a1-107">To create a new URL filter</span></span>

1.  <span data-ttu-id="632a1-108">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="632a1-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="632a1-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="632a1-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="632a1-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="632a1-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="632a1-111">在左導覽列中，按一下 [ **IM 和目前狀態**]，然後按一下 [ **URL 篩選**]。</span><span class="sxs-lookup"><span data-stu-id="632a1-111">In the left navigation bar, click **IM and Presence**, and then click **URL Filter**.</span></span>

4.  <span data-ttu-id="632a1-112">在 [ **URL 篩選** ] 頁面上，按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="632a1-112">On the **URL Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="632a1-113">在 [ **選取網站**] 中，按一下您要建立 URL 篩選的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="632a1-113">In **Select a Site**, click the site for which you want to create the URL filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="632a1-114">在 [ **新增 Url 篩選** ] 對話方塊中，選取 [ **啟用 url 篩選** ] 核取方塊，以啟用網站的 URL 篩選功能。</span><span class="sxs-lookup"><span data-stu-id="632a1-114">In the **New URL Filter** dialog box, select the **Enable URL Filter** check box to enable URL filtering for the site.</span></span>

7.  <span data-ttu-id="632a1-115">若要封鎖任何使用中副檔名已列 **于** [ **編輯檔案篩選**] 中的副檔名的 active URL，請選取 [ **封鎖 URLs** 搭配副檔名] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="632a1-115">To block any active URL that contains a file with an extension listed under **File type extensions to block** in **Edit File Filter**, select the **Block URLs with file extension** check box.</span></span>

8.  <span data-ttu-id="632a1-116">在 [ **超連結首碼** ] 下拉式清單方塊中，按一下對應至您要如何處理立即訊息交談中 URLs 的選項。</span><span class="sxs-lookup"><span data-stu-id="632a1-116">In the **Hyperlink prefix** drop-down list box, click the option that corresponds to how you want to handle URLs in instant message conversations.</span></span>
    
    <span data-ttu-id="632a1-117">[ **允許] 消息** 框可在傳送允許傳送的超連結時，將警告訊息傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="632a1-117">The **Allow message** box enables a warning message to be sent to the user when sending hyperlinks that are allowed to be sent.</span></span>

9.  <span data-ttu-id="632a1-118">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="632a1-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="632a1-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="632a1-119">See Also</span></span>


[<span data-ttu-id="632a1-120">在 Lync Server 2013 中設定立即訊息 (IM) 的檔案傳送和 URL 篩選</span><span class="sxs-lookup"><span data-stu-id="632a1-120">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="632a1-121">在 Lync Server 2013 中為特定網站建立新的檔案傳輸篩選器</span><span class="sxs-lookup"><span data-stu-id="632a1-121">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="632a1-122">在 Lync Server 2013 中修改預設檔案傳輸篩選器</span><span class="sxs-lookup"><span data-stu-id="632a1-122">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="632a1-123">在 Lync Server 2013 中修改預設 URL 篩選器</span><span class="sxs-lookup"><span data-stu-id="632a1-123">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

