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
ms.openlocfilehash: 60c4a3e1563890d64394f3a99141523cb95add38
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a>還原 Lync Server 2013 中的檔案存放區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-18_

Standard Edition 的檔案存放區通常位於 Standard Edition server 上。 Enterprise Edition 的檔案存放區通常位於檔案伺服器或叢集。 下列程序說明如何還原檔案存放區。

<div>

## <a name="to-restore-a-file-store"></a>還原檔案存放區

1.  如果檔案存放區失敗，則將適當的檔案存放區複製 $Backup\\到檔案伺服器或 Standard Edition server]，然後共用資料夾的檔案存放區位置。
    
    <div>
    

    > [!IMPORTANT]  
    > 還原檔案存放區的路徑和檔案名稱應該是完全相同備份檔案存放區，以便使用檔案的元件可以存取它們。

    
    </div>

2.  如有必要，設定存取控制清單 (Acl) 檔案存放區。 在命令列中輸入：
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > 您需要執行此步驟中，只有當您未執行拓撲產生器的還原程序期間。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

