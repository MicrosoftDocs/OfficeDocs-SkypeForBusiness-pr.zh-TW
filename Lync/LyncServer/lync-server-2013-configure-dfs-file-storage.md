---
title: Lync Server 2013： 設定 DFS 檔案儲存空間
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5ce6be2a3fce1f334e9e4b1d14ea41a3dd57a6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a><span data-ttu-id="7cbb3-102">設定 Lync Server 2013 的 DFS 檔案儲存空間</span><span class="sxs-lookup"><span data-stu-id="7cbb3-102">Configure DFS file storage for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cbb3-103">_**主題上次修改日期：** 2016年-05-23_</span><span class="sxs-lookup"><span data-stu-id="7cbb3-103">_**Topic Last Modified:** 2016-05-23_</span></span>

<span data-ttu-id="7cbb3-104">Lync Server 2013 支援使用檔案共用上分散式檔案系統 」 (DFS)。</span><span class="sxs-lookup"><span data-stu-id="7cbb3-104">Lync Server 2013 supports using file shares on a Distributed File System (DFS).</span></span> <span data-ttu-id="7cbb3-105">如需 DFS Windows Server 2008 的詳細資訊，請參閱 DFS 逐步指南的 Windows Server 2008 在[http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)。若要使用 DFS，Lync Server 2013 則需要下列項目：</span><span class="sxs-lookup"><span data-stu-id="7cbb3-105">For details about DFS for Windows Server 2008, see the DFS Step-by-Step Guide for Windows Server 2008 at [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).To use a DFS, Lync Server 2013 requires the following:</span></span>

  - <span data-ttu-id="7cbb3-106">命名空間是以網域為基礎</span><span class="sxs-lookup"><span data-stu-id="7cbb3-106">Namespaces are domain based</span></span>

  - <span data-ttu-id="7cbb3-107">所有命名空間伺服器正在執行 Windows 2008 的最小值</span><span class="sxs-lookup"><span data-stu-id="7cbb3-107">All namespace servers are running a minimum of Windows 2008</span></span>

<span data-ttu-id="7cbb3-108">Lync Server 2013 安裝程式需要共用資料夾的權限允許完整存取系統管理員。</span><span class="sxs-lookup"><span data-stu-id="7cbb3-108">Lync Server 2013 setup requires that permissions on shared folder allow full access to Administrator.</span></span> <span data-ttu-id="7cbb3-109">Lync Server 2013 然後會使用 NTFS ACL 的檔案權限的資料夾。</span><span class="sxs-lookup"><span data-stu-id="7cbb3-109">Lync Server 2013 will then use NTFS file permissions to ACL the folders.</span></span> <span data-ttu-id="7cbb3-110">繼承 DFS 共用權限不會用來限制存取。</span><span class="sxs-lookup"><span data-stu-id="7cbb3-110">Inherited DFS share permissions will not be used to restrict access.</span></span>

<span data-ttu-id="7cbb3-111">如需關於檔案共用需求的詳細資訊，請參閱支援文件中的[Lync Server 2013 中支援的檔案儲存空間](lync-server-2013-file-storage-support.md)。</span><span class="sxs-lookup"><span data-stu-id="7cbb3-111">For more details about File Share requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7cbb3-112">您可能會尋找設定非 DFS 共用資訊。</span><span class="sxs-lookup"><span data-stu-id="7cbb3-112">You may be looking for information on configuring a non-DFS share.</span></span> <span data-ttu-id="7cbb3-113">如果是的話，請參閱<A href="lync-server-2013-hardware-setup.md">Lync Server 2013 的硬體設定</A>。</span><span class="sxs-lookup"><span data-stu-id="7cbb3-113">If so, check out <A href="lync-server-2013-hardware-setup.md">Hardware setup for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="7cbb3-114">下列程序說明如何正確設定共用的資料夾權限 （如 DFS 安裝指南所述），使用 [DFS 命名空間精靈。</span><span class="sxs-lookup"><span data-stu-id="7cbb3-114">The following procedure describes how to correctly configure shared folder permissions using the DFS Namespace Wizard (as described in DFS setup guide).</span></span>

<div>

## <a name="to-configure-shared-folder-permissions"></a><span data-ttu-id="7cbb3-115">若要設定共用的資料夾權限</span><span class="sxs-lookup"><span data-stu-id="7cbb3-115">To configure shared folder permissions</span></span>

1.  <span data-ttu-id="7cbb3-116">按一下 [**開始**、 指向 [**所有程式]**、 指向 [**系統管理工具**]，然後按一下 [ **DFS 管理**]。</span><span class="sxs-lookup"><span data-stu-id="7cbb3-116">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **DFS Management**.</span></span>

2.  <span data-ttu-id="7cbb3-117">在 [DFS 管理] 嵌入式管理單元的主控台樹狀目錄中，命名空間伺服器 (例如 filesrv1.contoso.com)，以滑鼠右鍵按一下，然後按一下 [**編輯設定**。</span><span class="sxs-lookup"><span data-stu-id="7cbb3-117">In the console tree of the DFS Management snap-in, right-click the namespace server (for example filesrv1.contoso.com), and then click **Edit Settings**.</span></span>

3.  <span data-ttu-id="7cbb3-118">選取 [**共用資料夾權限**]。</span><span class="sxs-lookup"><span data-stu-id="7cbb3-118">Select **Shared Folder Permissions**.</span></span>

4.  <span data-ttu-id="7cbb3-119">選取 [**使用自訂權限**。</span><span class="sxs-lookup"><span data-stu-id="7cbb3-119">Select **Use Custom Permissions**.</span></span>

5.  <span data-ttu-id="7cbb3-120">針對系統管理員群組中，選取 [**允許**] 下的下列：</span><span class="sxs-lookup"><span data-stu-id="7cbb3-120">For the Administrator group, select the following under **Allow**:</span></span>
    
      - <span data-ttu-id="7cbb3-121">**完全控制**</span><span class="sxs-lookup"><span data-stu-id="7cbb3-121">**Full Control**</span></span>
    
      - <span data-ttu-id="7cbb3-122">**變更**</span><span class="sxs-lookup"><span data-stu-id="7cbb3-122">**Change**</span></span>
    
      - <span data-ttu-id="7cbb3-123">**讀取**</span><span class="sxs-lookup"><span data-stu-id="7cbb3-123">**Read**</span></span>

6.  <span data-ttu-id="7cbb3-124">在 [**撥號對應表 (電話內容)**] 方塊中，按一下 [**瀏覽**] 以尋找使用者的撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="7cbb3-124">Click **Apply**, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

