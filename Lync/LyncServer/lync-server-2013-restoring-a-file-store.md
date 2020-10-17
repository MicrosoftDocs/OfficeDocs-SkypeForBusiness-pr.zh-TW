---
title: Lync Server 2013：還原檔存放區
description: Lync Server 2013：還原檔存放區。
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
ms.openlocfilehash: 201c4b20f224fa3a25e931689e564410c60143e6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543829"
---
# <a name="restoring-a-file-store-in-lync-server-2013"></a>在 Lync Server 2013 中還原檔存放區

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-18_

Standard Edition 的檔案存放區通常位於 Standard Edition server 上。 Enterprise Edition 的檔案存放區一般位於檔案伺服器或叢集上。 下列程式說明如何還原檔存放區。

<div>

## <a name="to-restore-a-file-store"></a>還原檔案存放區

1.  如果檔案存放區失敗，請將適當的檔案存放區從 $Backup 複製 \\ 到檔案伺服器或 Standard Edition server 上的檔案存放區位置，然後再共用該資料夾。
    
    <div>
    

    > [!IMPORTANT]  
    > 還原的檔案存放區的路徑和檔案名應該與備份的檔案存放區完全相同，因此使用該檔案的元件可以存取這些檔。

    
    </div>

2.  如有必要，請設定檔案存放區 (ACLs) 的存取控制清單。 在命令列中輸入：
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > 只有在還原程式中未以其他方式執行拓撲產生器時，才需要執行此步驟。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

