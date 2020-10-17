---
title: Lync Server 2013：修改預設檔案傳輸篩選器
description: Lync Server 2013：修改預設檔案傳輸篩選器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8091dfebea87b793c56b9a670cfeeeab15ce6c44
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566929"
---
# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a><span data-ttu-id="68ca4-103">在 Lync Server 2013 中修改預設檔案傳輸篩選器</span><span class="sxs-lookup"><span data-stu-id="68ca4-103">Modify the default file transfer filter in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68ca4-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="68ca4-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="68ca4-105">Lync Server 2013 提供通用檔案傳輸篩選器，可在 Lync Server 2013 部署內，封鎖下列與檔相關的活動，以封鎖特定類型的檔案：</span><span class="sxs-lookup"><span data-stu-id="68ca4-105">Lync Server 2013 provides a global file transfer filter that blocks specific types of files during the following file-related activities within your Lync Server 2013 deployment:</span></span>

  - <span data-ttu-id="68ca4-106">立即訊息 (IM) 交談期間的檔案傳輸要求</span><span class="sxs-lookup"><span data-stu-id="68ca4-106">File transfer requests during instant messaging (IM) conversations</span></span>

  - <span data-ttu-id="68ca4-107">在 Office Live Meeting 2007 用戶端中使用講義功能時的檔案上傳與下載</span><span class="sxs-lookup"><span data-stu-id="68ca4-107">File uploads and downloads while using the handout feature in the Office Live Meeting 2007 client</span></span>

  - <span data-ttu-id="68ca4-108">會議期間的多媒體播放</span><span class="sxs-lookup"><span data-stu-id="68ca4-108">Multimedia playback during conferences</span></span>

<span data-ttu-id="68ca4-109">根據您想要封鎖或允許的檔案類型，您可以使用 Lync Server 控制台修改全域篩選器。</span><span class="sxs-lookup"><span data-stu-id="68ca4-109">Depending on the types of files you want to block or allow, you can use Lync Server Control Panel to modify the global filter.</span></span> <span data-ttu-id="68ca4-110">如需有關檔案傳輸篩選的詳細資訊，請參閱 [在 Lync Server 2013 中設定立即訊息 (IM) 的檔案傳送和 URL 篩選](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)。</span><span class="sxs-lookup"><span data-stu-id="68ca4-110">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a><span data-ttu-id="68ca4-111">修改預設檔案傳輸篩選器</span><span class="sxs-lookup"><span data-stu-id="68ca4-111">To modify the default file transfer filter</span></span>

1.  <span data-ttu-id="68ca4-112">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="68ca4-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="68ca4-113">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="68ca4-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="68ca4-114">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="68ca4-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="68ca4-115">在左導覽列中，依序按一下 **[IM 和目前狀態]** 和 **[檔案篩選]**。</span><span class="sxs-lookup"><span data-stu-id="68ca4-115">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="68ca4-116">在 **[檔案篩選]** 頁面上，按兩下 **[全域]** 篩選器。</span><span class="sxs-lookup"><span data-stu-id="68ca4-116">On the **File Filter** page, double-click the **Global** filter.</span></span>

5.  <span data-ttu-id="68ca4-117">在 **[編輯檔案篩選]** 中，選取 **[啟用檔案篩選]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="68ca4-117">In **Edit File Filter**, select the **Enable file filter** check box.</span></span>

6.  <span data-ttu-id="68ca4-118">在 **[檔案傳輸]** 下拉式清單方塊中，按一下 **[全部封鎖]** 或 **[封鎖特定檔案類型]**。</span><span class="sxs-lookup"><span data-stu-id="68ca4-118">In the **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

7.  <span data-ttu-id="68ca4-119">如果您按一下 **[全部封鎖]**，請跳至步驟 9。</span><span class="sxs-lookup"><span data-stu-id="68ca4-119">If you clicked **Block All**, skip to step 9.</span></span>

8.  <span data-ttu-id="68ca4-120">如果您按一下 **[封鎖特定檔案類型]**，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="68ca4-120">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="68ca4-121">按一下 **[選取]**，以修改您要封鎖之副檔名的預設清單。</span><span class="sxs-lookup"><span data-stu-id="68ca4-121">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="68ca4-122">在 **[選取檔案類型]** 中選取您要封鎖或允許的檔案類型，作法是從 **[副檔名]** 下的類別新增或移除其副檔名。</span><span class="sxs-lookup"><span data-stu-id="68ca4-122">In **Select File Type**, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="68ca4-123">如果您未看見所要封鎖的檔案類型副檔名，請在 **[將副檔名新增至清單]** 下的文字方塊中輸入副檔名，然後按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="68ca4-123">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="68ca4-124">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="68ca4-124">Click **OK**.</span></span>

9.  <span data-ttu-id="68ca4-125">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="68ca4-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="68ca4-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="68ca4-126">See Also</span></span>


[<span data-ttu-id="68ca4-127">在 Lync Server 2013 中設定立即訊息 (IM) 的檔案傳送和 URL 篩選</span><span class="sxs-lookup"><span data-stu-id="68ca4-127">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="68ca4-128">在 Lync Server 2013 中為特定網站建立新的檔案傳輸篩選器</span><span class="sxs-lookup"><span data-stu-id="68ca4-128">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="68ca4-129">在 Lync Server 2013 中建立新的 URL 篩選，以處理 IM 交談中的超連結</span><span class="sxs-lookup"><span data-stu-id="68ca4-129">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[<span data-ttu-id="68ca4-130">在 Lync Server 2013 中修改預設 URL 篩選器</span><span class="sxs-lookup"><span data-stu-id="68ca4-130">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

