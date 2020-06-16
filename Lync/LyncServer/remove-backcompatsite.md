---
title: 移除 BackCompatSite
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 792fcf29033a7495a7da340decb561e25084612d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757124"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a><span data-ttu-id="da9c4-102">移除 BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="da9c4-102">Remove BackCompatSite</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da9c4-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="da9c4-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="da9c4-104">停用所有集區並解除安裝所有 Edge Server 之後，請執行 [拓撲產生器合併精靈] 以移除 BackCompatSite\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="da9c4-104">After all pools are deactivated and all Edge Servers have been uninstalled, run the Topology Builder Merge wizard to remove the **BackCompatSite**.</span></span>

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a><span data-ttu-id="da9c4-105">從拓撲產生器移除 BackCompat 網站</span><span class="sxs-lookup"><span data-stu-id="da9c4-105">To remove BackCompat site from Topology Builder</span></span>

1.  <span data-ttu-id="da9c4-106">從拓撲產生器開啟現有的部署。</span><span class="sxs-lookup"><span data-stu-id="da9c4-106">Open an existing deployment from Topology Builder.</span></span>

2.  <span data-ttu-id="da9c4-107">在 [執行]\*\*\*\* 功能表中，按一下 [合併 2007 R2 拓撲]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="da9c4-107">In the **Action** menu, click **Merge 2007 R2 Topology**.</span></span>

3.  <span data-ttu-id="da9c4-108">按 [下一步]\*\*\*\* 繼續。</span><span class="sxs-lookup"><span data-stu-id="da9c4-108">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="da9c4-109">在 [**指定舊版 Edge** ] 頁面上，確定 Edge server 的清單是空的。</span><span class="sxs-lookup"><span data-stu-id="da9c4-109">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty.</span></span> <span data-ttu-id="da9c4-110">若不是空的，請使用 [移除]\*\*\*\* 按鈕移除所有舊版的 Edge Server，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="da9c4-110">If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span></span>
    
    <span data-ttu-id="da9c4-111">![合併拓撲嚮導的 [指定 Edge 安裝] 頁面](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "合併拓撲嚮導的 [指定 Edge 安裝] 頁面")</span><span class="sxs-lookup"><span data-stu-id="da9c4-111">![Merge Topology Wizard, Specify Edge Setup page](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="da9c4-112">在 [指定內部 SIP 連接埠]\*\*\*\* 設定頁面中按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="da9c4-112">On the **Specify Internal SIP port setting** page, click **Next**.</span></span>

6.  <span data-ttu-id="da9c4-113">在 [**摘要**] 頁面上，按一下 **[下一步]** ，以開始合併拓撲，以移除舊版網站。</span><span class="sxs-lookup"><span data-stu-id="da9c4-113">On the **Summary** page, click **Next** to begin merging the topologies to remove the legacy site.</span></span>

7.  <span data-ttu-id="da9c4-114">在 [狀態]\*\*\*\* 欄中，檢查其值是否為 [成功]\*\*\*\*，然後按一下 [完成]\*\*\*\*，以關閉精靈。</span><span class="sxs-lookup"><span data-stu-id="da9c4-114">In the **Status** column, verify that the value is **Success** and then click **Finish** to close the wizard.</span></span>

8.  <span data-ttu-id="da9c4-115">在拓撲產生器的左窗格中，展開 BackCompatSite 並確定沒有列出任何伺服器。</span><span class="sxs-lookup"><span data-stu-id="da9c4-115">In the left pane of Topology Builder, expand the BackCompatSite and ensure no servers are listed.</span></span>

9.  <span data-ttu-id="da9c4-116">以滑鼠右鍵按一下 [BackCompatSite]\*\*\*\*，然後按一下 [刪除]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="da9c4-116">Right-click the **BackCompatSite**, and then click **Delete**.</span></span>

10. <span data-ttu-id="da9c4-117">在 [拓撲產生器]\*\*\*\* 中選取最頂端的節點 [Lync Server]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="da9c4-117">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

11. <span data-ttu-id="da9c4-118">在 **[執行]** 功能表中，選取 **[發行拓撲]**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="da9c4-118">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

12. <span data-ttu-id="da9c4-119">當 [發行精靈]\*\*\*\* 完成之後，按一下 [完成]\*\*\*\*，以關閉精靈。</span><span class="sxs-lookup"><span data-stu-id="da9c4-119">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

