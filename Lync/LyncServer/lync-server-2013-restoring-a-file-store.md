---
title: Lync Server 2013：還原檔存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc9f1bae4e1a9a84815e576267a15155bec227da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a>在 Lync Server 2013 中還原檔案存放區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-18_

標準版的檔案存放區通常位於標準版伺服器上。 企業版的檔案存放區通常位於檔案伺服器或群集上。 下列程式說明如何還原檔案存放區。

<div>

## <a name="to-restore-a-file-store"></a>還原檔案存放區

1.  如果檔案儲存失敗，請將適當的檔案存放區從\\ $Backup 複製到檔案伺服器或標準版伺服器上的檔案存放位置，然後共用資料夾。
    
    <div>
    

    > [!IMPORTANT]  
    > 已還原之檔案存放區的路徑和檔案名應該與已備份的檔案存放區完全相同，因此使用檔案的元件可以存取它們。

    
    </div>

2.  如有需要，請設定檔案存放區的存取控制清單（Acl）。 在命令列中，輸入：
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > 您必須執行此步驟，才能讓您在還原程式期間未執行拓撲產生器。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

