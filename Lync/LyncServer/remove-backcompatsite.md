---
title: 移除 BackCompatSite
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe6a3d1dc92e45bc99892e7827394376b6f28b12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a><span data-ttu-id="fa844-102">移除 BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="fa844-102">Remove BackCompatSite</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa844-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="fa844-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="fa844-104">在停用所有的池且已卸載所有邊緣伺服器之後，請執行拓撲產生器合併嚮導來移除**BackCompatSite**。</span><span class="sxs-lookup"><span data-stu-id="fa844-104">After all pools are deactivated and all Edge Servers have been uninstalled, run the Topology Builder Merge wizard to remove the **BackCompatSite**.</span></span>

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a><span data-ttu-id="fa844-105">從拓撲建立器移除 BackCompat 網站</span><span class="sxs-lookup"><span data-stu-id="fa844-105">To remove BackCompat site from Topology Builder</span></span>

1.  <span data-ttu-id="fa844-106">從 [拓撲建立器] 開啟現有的部署。</span><span class="sxs-lookup"><span data-stu-id="fa844-106">Open an existing deployment from Topology Builder.</span></span>

2.  <span data-ttu-id="fa844-107">在 [**動作**] 功能表中，按一下 [**合併 2007 R2 拓撲結構**]。</span><span class="sxs-lookup"><span data-stu-id="fa844-107">In the **Action** menu, click **Merge 2007 R2 Topology**.</span></span>

3.  <span data-ttu-id="fa844-108">請按 [下一步]\*\*\*\* 繼續。</span><span class="sxs-lookup"><span data-stu-id="fa844-108">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="fa844-109">在 [**指定舊版 Edge** ] 頁面上，確定 Edge 伺服器清單是空的。</span><span class="sxs-lookup"><span data-stu-id="fa844-109">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty.</span></span> <span data-ttu-id="fa844-110">如果清單不是空白，請使用 [**移除**] 按鈕來移除所有舊版邊緣伺服器，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fa844-110">If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span></span>
    
    <span data-ttu-id="fa844-111">[![合併拓撲嚮導]，指定 [邊緣設定] 頁面](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "合併拓撲嚮導，指定 [edge 設定] 頁面")</span><span class="sxs-lookup"><span data-stu-id="fa844-111">![Merge Topology Wizard, Specify Edge Setup page](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="fa844-112">在 [**指定內部 SIP 埠設定**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fa844-112">On the **Specify Internal SIP port setting** page, click **Next**.</span></span>

6.  <span data-ttu-id="fa844-113">在 [**摘要**] 頁面上，按一下 **[下一步]** 以開始合併拓撲，以移除舊版網站。</span><span class="sxs-lookup"><span data-stu-id="fa844-113">On the **Summary** page, click **Next** to begin merging the topologies to remove the legacy site.</span></span>

7.  <span data-ttu-id="fa844-114">在 [**狀態**] 欄中，確認此值為 [**成功**]，然後按一下 **[完成**] 以關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="fa844-114">In the **Status** column, verify that the value is **Success** and then click **Finish** to close the wizard.</span></span>

8.  <span data-ttu-id="fa844-115">在 [拓撲建立器] 的左窗格中，展開 [BackCompatSite]，並確認沒有列出任何伺服器。</span><span class="sxs-lookup"><span data-stu-id="fa844-115">In the left pane of Topology Builder, expand the BackCompatSite and ensure no servers are listed.</span></span>

9.  <span data-ttu-id="fa844-116">以滑鼠右鍵按一下**BackCompatSite**，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="fa844-116">Right-click the **BackCompatSite**, and then click **Delete**.</span></span>

10. <span data-ttu-id="fa844-117">在 [**拓撲**建立器] 中，選取最上方的 [ **Lync Server**]。</span><span class="sxs-lookup"><span data-stu-id="fa844-117">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

11. <span data-ttu-id="fa844-118">從 [**動作**] 功能表中，選取 [**發佈拓撲**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fa844-118">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

12. <span data-ttu-id="fa844-119">**發佈嚮導**完成後，請按一下 **[完成**] 以關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="fa844-119">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

