---
title: Lync Server 2013：修改預設的檔案傳輸篩選器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 475f6e9b599af9ba6db80fdb174d3b38e5df6b00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a><span data-ttu-id="71ae4-102">在 Lync Server 2013 中修改預設的檔案傳輸篩選器</span><span class="sxs-lookup"><span data-stu-id="71ae4-102">Modify the default file transfer filter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71ae4-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="71ae4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="71ae4-104">Lync Server 2013 提供通用檔案傳輸篩選器，可在 Lync Server 2013 部署中的下列與檔案相關的活動中封鎖特定類型的檔案：</span><span class="sxs-lookup"><span data-stu-id="71ae4-104">Lync Server 2013 provides a global file transfer filter that blocks specific types of files during the following file-related activities within your Lync Server 2013 deployment:</span></span>

  - <span data-ttu-id="71ae4-105">在立即訊息（IM）交談期間的檔案傳輸要求</span><span class="sxs-lookup"><span data-stu-id="71ae4-105">File transfer requests during instant messaging (IM) conversations</span></span>

  - <span data-ttu-id="71ae4-106">使用 Office Live Meeting 2007 用戶端中的講義功能時的檔案上傳和下載</span><span class="sxs-lookup"><span data-stu-id="71ae4-106">File uploads and downloads while using the handout feature in the Office Live Meeting 2007 client</span></span>

  - <span data-ttu-id="71ae4-107">在會議期間進行多媒體播放</span><span class="sxs-lookup"><span data-stu-id="71ae4-107">Multimedia playback during conferences</span></span>

<span data-ttu-id="71ae4-108">視您想要封鎖或允許的檔案類型而定，您可以使用 Lync Server [控制台] 來修改全域篩選器。</span><span class="sxs-lookup"><span data-stu-id="71ae4-108">Depending on the types of files you want to block or allow, you can use Lync Server Control Panel to modify the global filter.</span></span> <span data-ttu-id="71ae4-109">如需檔案傳輸篩選的詳細資料，請參閱[在 Lync Server 2013 中設定立即訊息（IM）的檔案傳輸與 URL 篩選](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)。</span><span class="sxs-lookup"><span data-stu-id="71ae4-109">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a><span data-ttu-id="71ae4-110">修改預設的檔案傳輸篩選器</span><span class="sxs-lookup"><span data-stu-id="71ae4-110">To modify the default file transfer filter</span></span>

1.  <span data-ttu-id="71ae4-111">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="71ae4-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="71ae4-112">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="71ae4-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="71ae4-113">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="71ae4-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="71ae4-114">在左側導覽列中，按一下 [ **IM 和目前狀態**]，然後按一下 [檔案**篩選**]。</span><span class="sxs-lookup"><span data-stu-id="71ae4-114">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="71ae4-115">在 [檔案**篩選**] 頁面上，按兩下 [**全域**篩選器]。</span><span class="sxs-lookup"><span data-stu-id="71ae4-115">On the **File Filter** page, double-click the **Global** filter.</span></span>

5.  <span data-ttu-id="71ae4-116">在 [**編輯檔案篩選器**] 中，選取 [**啟用檔案篩選**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="71ae4-116">In **Edit File Filter**, select the **Enable file filter** check box.</span></span>

6.  <span data-ttu-id="71ae4-117">在 [檔案**傳輸**] 下拉式清單方塊中，按一下 [**全部封鎖**] 或 [**封鎖特定檔案類型**]。</span><span class="sxs-lookup"><span data-stu-id="71ae4-117">In the **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

7.  <span data-ttu-id="71ae4-118">如果您已按一下 [**全部封鎖**]，請跳至步驟9。</span><span class="sxs-lookup"><span data-stu-id="71ae4-118">If you clicked **Block All**, skip to step 9.</span></span>

8.  <span data-ttu-id="71ae4-119">如果您按一下 [**封鎖特定檔案類型**]，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="71ae4-119">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="71ae4-120">按一下 [**選取**]，修改您想要封鎖的檔案類型延伸預設清單。</span><span class="sxs-lookup"><span data-stu-id="71ae4-120">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="71ae4-121">在 [**選取檔案類型**] 中，從 [**檔案類型延伸**] 底下的類別中新增或移除副檔名，以選取您要封鎖或允許的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="71ae4-121">In **Select File Type**, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="71ae4-122">如果您沒有看到想要封鎖之檔案類型的副檔名，請在 [**新增檔案類型延伸至] 清單**中的文字方塊中輸入副檔名，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="71ae4-122">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="71ae4-123">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="71ae4-123">Click **OK**.</span></span>

9.  <span data-ttu-id="71ae4-124">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="71ae4-124">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="71ae4-125">請參閱</span><span class="sxs-lookup"><span data-stu-id="71ae4-125">See Also</span></span>


[<span data-ttu-id="71ae4-126">在 Lync Server 2013 中設定立即訊息（IM）的檔案傳輸與 URL 篩選</span><span class="sxs-lookup"><span data-stu-id="71ae4-126">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="71ae4-127">針對特定網站在 Lync Server 2013 中建立新的檔案傳輸篩選器</span><span class="sxs-lookup"><span data-stu-id="71ae4-127">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="71ae4-128">在 Lync Server 2013 中建立新的 URL 篩選，以處理 IM 交談中的超連結</span><span class="sxs-lookup"><span data-stu-id="71ae4-128">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[<span data-ttu-id="71ae4-129">在 Lync Server 2013 中修改預設的 URL 篩選</span><span class="sxs-lookup"><span data-stu-id="71ae4-129">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

