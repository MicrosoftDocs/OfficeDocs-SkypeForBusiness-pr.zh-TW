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
ms.openlocfilehash: cd1984c6e51866b1ace707f305fb2a6cc356a132
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511610"
---
# <a name="restoring-a-file-store-in-lync-server-2013"></a><span data-ttu-id="85abe-102">在 Lync Server 2013 中還原檔存放區</span><span class="sxs-lookup"><span data-stu-id="85abe-102">Restoring a file store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85abe-103">_**主題上次修改日期：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="85abe-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="85abe-104">Standard Edition 的檔案存放區通常位於 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="85abe-104">File Stores for Standard Edition are typically located on the Standard Edition server.</span></span> <span data-ttu-id="85abe-105">Enterprise Edition 的檔案存放區一般位於檔案伺服器或叢集上。</span><span class="sxs-lookup"><span data-stu-id="85abe-105">File Stores for Enterprise Edition are typically located on a file server or cluster.</span></span> <span data-ttu-id="85abe-106">下列程式說明如何還原檔存放區。</span><span class="sxs-lookup"><span data-stu-id="85abe-106">The following procedure describes how to restore a File Store.</span></span>

<div>

## <a name="to-restore-a-file-store"></a><span data-ttu-id="85abe-107">還原檔案存放區</span><span class="sxs-lookup"><span data-stu-id="85abe-107">To restore a File Store</span></span>

1.  <span data-ttu-id="85abe-108">如果檔案存放區失敗，請將適當的檔案存放區從 $Backup 複製 \\ 到檔案伺服器或 Standard Edition server 上的檔案存放區位置，然後再共用該資料夾。</span><span class="sxs-lookup"><span data-stu-id="85abe-108">If a File Store fails, copy the appropriate File Store from $Backup\\ to the File Store location on the file server or Standard Edition server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="85abe-109">還原的檔案存放區的路徑和檔案名應該與備份的檔案存放區完全相同，因此使用該檔案的元件可以存取這些檔。</span><span class="sxs-lookup"><span data-stu-id="85abe-109">The path and file name for the restored File Store should be exactly the same as the backed up File Store, so that components that use the files can access them.</span></span>

    
    </div>

2.  <span data-ttu-id="85abe-110">如有必要，請設定檔案存放區 (ACLs) 的存取控制清單。</span><span class="sxs-lookup"><span data-stu-id="85abe-110">If necessary, set the access control lists (ACLs) for the File Store.</span></span> <span data-ttu-id="85abe-111">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="85abe-111">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="85abe-112">只有在還原程式中未以其他方式執行拓撲產生器時，才需要執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="85abe-112">You need to perform this step only if you have not otherwise run Topology Builder during your restoration process.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

