---
title: Lync Server 2013：設定 DFS 檔存放區
description: Lync Server 2013：設定 DFS 檔存放區。
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
ms.openlocfilehash: d70ae93db188ec51d04dd33d6c3cb5659db5a2c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564379"
---
# <a name="configure-dfs-file-storage-for-lync-server-2013"></a><span data-ttu-id="17409-103">設定 Lync Server 2013 的 DFS 檔存放區</span><span class="sxs-lookup"><span data-stu-id="17409-103">Configure DFS file storage for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17409-104">_**主題上次修改日期：** 2016-05-23_</span><span class="sxs-lookup"><span data-stu-id="17409-104">_**Topic Last Modified:** 2016-05-23_</span></span>

<span data-ttu-id="17409-105">Lync Server 2013 支援在分散式檔案系統 (DFS) 上使用檔案共用。</span><span class="sxs-lookup"><span data-stu-id="17409-105">Lync Server 2013 supports using file shares on a Distributed File System (DFS).</span></span> <span data-ttu-id="17409-106">如需有關 Windows Server 2008 DFS 的詳細資訊，請參閱 Windows Server 2008 的 DFS 逐步指南 [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835) 。若要使用 DFS，Lync Server 2013 需要下列專案：</span><span class="sxs-lookup"><span data-stu-id="17409-106">For details about DFS for Windows Server 2008, see the DFS Step-by-Step Guide for Windows Server 2008 at [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835).To use a DFS, Lync Server 2013 requires the following:</span></span>

  - <span data-ttu-id="17409-107">命名空間是以網域為基礎的</span><span class="sxs-lookup"><span data-stu-id="17409-107">Namespaces are domain based</span></span>

  - <span data-ttu-id="17409-108">所有命名空間伺服器都執行最低 Windows 2008</span><span class="sxs-lookup"><span data-stu-id="17409-108">All namespace servers are running a minimum of Windows 2008</span></span>

<span data-ttu-id="17409-109">Lync Server 2013 安裝程式要求共用資料夾的許可權允許系統管理員的完整存取權。</span><span class="sxs-lookup"><span data-stu-id="17409-109">Lync Server 2013 setup requires that permissions on shared folder allow full access to Administrator.</span></span> <span data-ttu-id="17409-110">然後，Lync Server 2013 會使用 NTFS 檔案許可權來做為資料夾的 ACL。</span><span class="sxs-lookup"><span data-stu-id="17409-110">Lync Server 2013 will then use NTFS file permissions to ACL the folders.</span></span> <span data-ttu-id="17409-111">繼承的 DFS 共用許可權將不會用來限制存取。</span><span class="sxs-lookup"><span data-stu-id="17409-111">Inherited DFS share permissions will not be used to restrict access.</span></span>

<span data-ttu-id="17409-112">如需檔案共用需求的詳細資訊，請參閱支援檔中的 [storage storage support In Lync Server 2013](lync-server-2013-file-storage-support.md) 。</span><span class="sxs-lookup"><span data-stu-id="17409-112">For more details about File Share requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="17409-113">您可能正在尋找設定非 DFS 共用的資訊。</span><span class="sxs-lookup"><span data-stu-id="17409-113">You may be looking for information on configuring a non-DFS share.</span></span> <span data-ttu-id="17409-114">如果是的話，請參閱 <A href="lync-server-2013-hardware-setup.md">Lync Server 2013 的硬體設定</A>。</span><span class="sxs-lookup"><span data-stu-id="17409-114">If so, check out <A href="lync-server-2013-hardware-setup.md">Hardware setup for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="17409-115">下列程式說明如何使用 DFS 命名空間嚮導正確設定共用資料夾許可權，如《 DFS 安裝指南) 所述 (。</span><span class="sxs-lookup"><span data-stu-id="17409-115">The following procedure describes how to correctly configure shared folder permissions using the DFS Namespace Wizard (as described in DFS setup guide).</span></span>

<div>

## <a name="to-configure-shared-folder-permissions"></a><span data-ttu-id="17409-116">設定共用資料夾許可權</span><span class="sxs-lookup"><span data-stu-id="17409-116">To configure shared folder permissions</span></span>

1.  <span data-ttu-id="17409-117">按一下 [ **開始**]，指向 [ **所有程式**]，指向 [系統 **管理工具**]，然後按一下 [ **DFS 管理**]。</span><span class="sxs-lookup"><span data-stu-id="17409-117">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **DFS Management**.</span></span>

2.  <span data-ttu-id="17409-118">在 [DFS 管理] 嵌入式管理單元的主控台樹中，以滑鼠右鍵按一下命名空間伺服器 (例如 filesrv1.contoso.com) ]，然後按一下 [ **編輯設定**]。</span><span class="sxs-lookup"><span data-stu-id="17409-118">In the console tree of the DFS Management snap-in, right-click the namespace server (for example filesrv1.contoso.com), and then click **Edit Settings**.</span></span>

3.  <span data-ttu-id="17409-119">選取 [ **共用資料夾許可權**]。</span><span class="sxs-lookup"><span data-stu-id="17409-119">Select **Shared Folder Permissions**.</span></span>

4.  <span data-ttu-id="17409-120">選取 [ **使用自訂許可權**]。</span><span class="sxs-lookup"><span data-stu-id="17409-120">Select **Use Custom Permissions**.</span></span>

5.  <span data-ttu-id="17409-121">針對系統管理員群組，選取 [ **允許**] 底下的下列專案：</span><span class="sxs-lookup"><span data-stu-id="17409-121">For the Administrator group, select the following under **Allow**:</span></span>
    
      - <span data-ttu-id="17409-122">**完全控制**</span><span class="sxs-lookup"><span data-stu-id="17409-122">**Full Control**</span></span>
    
      - <span data-ttu-id="17409-123">**Change**</span><span class="sxs-lookup"><span data-stu-id="17409-123">**Change**</span></span>
    
      - <span data-ttu-id="17409-124">**Read**</span><span class="sxs-lookup"><span data-stu-id="17409-124">**Read**</span></span>

6.  <span data-ttu-id="17409-125">在 [**撥號對應表 (電話內容)**] 方塊中，按一下 [**瀏覽**] 以尋找使用者的撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="17409-125">Click **Apply**, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

