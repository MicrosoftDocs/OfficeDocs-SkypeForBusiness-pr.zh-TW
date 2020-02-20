---
title: Lync Server 2013： 還原檔案存放區
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
ms.openlocfilehash: 409d22b6a0c2d762e39603a1c8eda5ce11cb5433
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a><span data-ttu-id="296c7-102">還原 Lync Server 2013 中的檔案存放區</span><span class="sxs-lookup"><span data-stu-id="296c7-102">Restoring a file store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="296c7-103">_**上次修改主題：** 2013年-02-18_</span><span class="sxs-lookup"><span data-stu-id="296c7-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="296c7-104">Standard Edition 的檔案存放區通常位於 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="296c7-104">File Stores for Standard Edition are typically located on the Standard Edition server.</span></span> <span data-ttu-id="296c7-105">Enterprise Edition 的檔案存放區通常位於檔案伺服器或叢集。</span><span class="sxs-lookup"><span data-stu-id="296c7-105">File Stores for Enterprise Edition are typically located on a file server or cluster.</span></span> <span data-ttu-id="296c7-106">下列程序說明如何還原檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="296c7-106">The following procedure describes how to restore a File Store.</span></span>

<div>

## <a name="to-restore-a-file-store"></a><span data-ttu-id="296c7-107">還原檔案存放區</span><span class="sxs-lookup"><span data-stu-id="296c7-107">To restore a File Store</span></span>

1.  <span data-ttu-id="296c7-108">如果檔案存放區失敗，則將適當的檔案存放區複製 $Backup\\到檔案伺服器或 Standard Edition server]，然後共用資料夾的檔案存放區位置。</span><span class="sxs-lookup"><span data-stu-id="296c7-108">If a File Store fails, copy the appropriate File Store from $Backup\\ to the File Store location on the file server or Standard Edition server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="296c7-109">還原檔案存放區的路徑和檔案名稱應該是完全相同備份檔案存放區，以便使用檔案的元件可以存取它們。</span><span class="sxs-lookup"><span data-stu-id="296c7-109">The path and file name for the restored File Store should be exactly the same as the backed up File Store, so that components that use the files can access them.</span></span>

    
    </div>

2.  <span data-ttu-id="296c7-110">如有必要，設定存取控制清單 (Acl) 檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="296c7-110">If necessary, set the access control lists (ACLs) for the File Store.</span></span> <span data-ttu-id="296c7-111">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="296c7-111">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="296c7-112">您需要執行此步驟中，只有當您未執行拓撲產生器的還原程序期間。</span><span class="sxs-lookup"><span data-stu-id="296c7-112">You need to perform this step only if you have not otherwise run Topology Builder during your restoration process.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

