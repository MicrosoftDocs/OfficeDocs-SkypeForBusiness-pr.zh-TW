---
title: Lync Server 2013：還原檔存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c013159de83d258273e381dd54556bcceec056f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a><span data-ttu-id="d3a6a-102">在 Lync Server 2013 中還原檔案存放區</span><span class="sxs-lookup"><span data-stu-id="d3a6a-102">Restoring a file store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3a6a-103">_**主題上次修改日期：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="d3a6a-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="d3a6a-104">標準版的檔案存放區通常位於標準版伺服器上。</span><span class="sxs-lookup"><span data-stu-id="d3a6a-104">File Stores for Standard Edition are typically located on the Standard Edition server.</span></span> <span data-ttu-id="d3a6a-105">企業版的檔案存放區通常位於檔案伺服器或群集上。</span><span class="sxs-lookup"><span data-stu-id="d3a6a-105">File Stores for Enterprise Edition are typically located on a file server or cluster.</span></span> <span data-ttu-id="d3a6a-106">下列程式說明如何還原檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="d3a6a-106">The following procedure describes how to restore a File Store.</span></span>

<div>

## <a name="to-restore-a-file-store"></a><span data-ttu-id="d3a6a-107">還原檔案存放區</span><span class="sxs-lookup"><span data-stu-id="d3a6a-107">To restore a File Store</span></span>

1.  <span data-ttu-id="d3a6a-108">如果檔案儲存失敗，請將適當的檔案存放區從\\ $Backup 複製到檔案伺服器或標準版伺服器上的檔案存放位置，然後共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="d3a6a-108">If a File Store fails, copy the appropriate File Store from $Backup\\ to the File Store location on the file server or Standard Edition server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d3a6a-109">已還原之檔案存放區的路徑和檔案名應該與已備份的檔案存放區完全相同，因此使用檔案的元件可以存取它們。</span><span class="sxs-lookup"><span data-stu-id="d3a6a-109">The path and file name for the restored File Store should be exactly the same as the backed up File Store, so that components that use the files can access them.</span></span>

    
    </div>

2.  <span data-ttu-id="d3a6a-110">如有需要，請設定檔案存放區的存取控制清單（Acl）。</span><span class="sxs-lookup"><span data-stu-id="d3a6a-110">If necessary, set the access control lists (ACLs) for the File Store.</span></span> <span data-ttu-id="d3a6a-111">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="d3a6a-111">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d3a6a-112">您必須執行此步驟，才能讓您在還原程式期間未執行拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="d3a6a-112">You need to perform this step only if you have not otherwise run Topology Builder during your restoration process.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

