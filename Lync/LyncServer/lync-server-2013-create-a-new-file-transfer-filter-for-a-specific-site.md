---
title: Lync Server 2013：為特定網站建立新的檔案傳輸篩選器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new file transfer filter for a specific site
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48185577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bec5e9e33850fc1da53d370f70b948b7ec6b3f27
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a><span data-ttu-id="215be-102">在 Lync Server 2013 中為特定網站建立新的檔案傳輸篩選器</span><span class="sxs-lookup"><span data-stu-id="215be-102">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="215be-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="215be-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="215be-104">除了修改通用檔案傳輸篩選器之外，您還可以針對 Lync Server 2013 部署中的特定網站，設定自訂檔案傳送篩選器。</span><span class="sxs-lookup"><span data-stu-id="215be-104">In addition to modifying the global file transfer filter, you can configure custom file transfer filters for specific sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="215be-105">如需有關檔案傳輸篩選的詳細資訊，請參閱 [在 Lync Server 2013 中設定立即訊息 (IM) 的檔案傳送和 URL 篩選](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)。</span><span class="sxs-lookup"><span data-stu-id="215be-105">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a><span data-ttu-id="215be-106">若要為特定網站建立檔案傳輸篩選器</span><span class="sxs-lookup"><span data-stu-id="215be-106">To create a file transfer filter for a specific site</span></span>

1.  <span data-ttu-id="215be-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="215be-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="215be-108">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="215be-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="215be-109">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="215be-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="215be-110">在左導覽列中，依序按一下 **[IM 和目前狀態]** 和 **[檔案篩選]**。</span><span class="sxs-lookup"><span data-stu-id="215be-110">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="215be-111">在 [檔案 **篩選** ] 頁面上，按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="215be-111">On the **File Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="215be-112">在 [ **選取網站** ] 對話方塊中，按一下您要建立檔案傳輸篩選的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="215be-112">In the **Select a Site** dialog box, click the site for which you want to create the file transfer filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="215be-113">在 [ **新增檔案篩選器**] 中，按一下 [ **啟用檔篩選** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="215be-113">In **New File Filter**, click the **Enable file filter** check box.</span></span>

7.  <span data-ttu-id="215be-114">在 [ **檔案傳輸** ] 下拉式清單方塊中，按一下 [ **全部封鎖** ] 或 [ **封鎖特定檔案類型**]。</span><span class="sxs-lookup"><span data-stu-id="215be-114">In **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

8.  <span data-ttu-id="215be-115">如果您按一下 [ **全部封鎖**]，請跳至步驟10。</span><span class="sxs-lookup"><span data-stu-id="215be-115">If you clicked **Block All**, skip to step 10.</span></span>

9.  <span data-ttu-id="215be-116">如果您按一下 **[封鎖特定檔案類型]**，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="215be-116">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="215be-117">按一下 **[選取]**，以修改您要封鎖之副檔名的預設清單。</span><span class="sxs-lookup"><span data-stu-id="215be-117">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="215be-118">在 [ **選取檔案類型** ] 對話方塊中，從 **[副檔名]** 底下的類別中新增或移除副檔名，以選取您要封鎖或允許的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="215be-118">In the **Select File Type** dialog box, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="215be-119">如果您未看見所要封鎖的檔案類型副檔名，請在 **[將副檔名新增至清單]** 下的文字方塊中輸入副檔名，然後按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="215be-119">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="215be-120">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="215be-120">Click **OK**.</span></span>

10. <span data-ttu-id="215be-121">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="215be-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="215be-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="215be-122">See Also</span></span>


[<span data-ttu-id="215be-123">在 Lync Server 2013 中設定立即訊息 (IM) 的檔案傳送和 URL 篩選</span><span class="sxs-lookup"><span data-stu-id="215be-123">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="215be-124">在 Lync Server 2013 中建立新的 URL 篩選，以處理 IM 交談中的超連結</span><span class="sxs-lookup"><span data-stu-id="215be-124">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[<span data-ttu-id="215be-125">在 Lync Server 2013 中修改預設檔案傳輸篩選器</span><span class="sxs-lookup"><span data-stu-id="215be-125">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="215be-126">在 Lync Server 2013 中修改預設 URL 篩選器</span><span class="sxs-lookup"><span data-stu-id="215be-126">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

