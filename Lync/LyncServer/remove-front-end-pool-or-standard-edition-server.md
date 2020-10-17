---
title: 移除前端集區或 Standard Edition Server
description: 移除前端集區或 Standard Edition server。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c878d56b073558f4f4b50f31b6742fd581c80241
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570239"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>移除前端集區或 Standard Edition Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

本主題將引導您完成移除前端集區或 Standard Edition 前端伺服器的程式。 當您移除前端集區時，會移除屬於集區的所有前端伺服器，作為集區移除程式的一部分。 當您移除 Standard Edition 前端伺服器時，必須從拓撲產生器移除 SQL 存放區定義。

<div>

## <a name="to-remove-a-front-end-server-pool"></a>移除前端伺服器集區

1.  開啟拓撲產生器。

2.  流覽至 [Lync Server 2010] 節點。

3.  展開 [ **Enterprise Edition 前端**集區]，展開前端集區，以滑鼠右鍵按一下您要移除的前端集區，然後按一下 [ **刪除**]。

4.  發佈拓撲，檢查複寫狀態，然後視需要執行 Lync Server 部署嚮導。

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a>移除 Standard Edition 前端伺服器

1.  開啟拓撲產生器。

2.  流覽至 [Lync Server 2010] 節點。

3.  展開 [ **Standard Edition 前端伺服器**]，以滑鼠右鍵按一下您要移除的前端伺服器，然後按一下 [ **刪除**]。

4.  展開 **[SQL 存放區**]，以滑鼠右鍵按一下與 Standard Edition 前端伺服器相關聯的 SQL Server 資料庫，然後按一下 [ **刪除**]。
    
    <div>
    

    > [!IMPORTANT]  
    > 您必須從 Standard Edition 前端伺服器移除組合 SQL Server 資料庫的定義。

    
    </div>

5.  發佈拓撲，檢查複寫狀態，然後視需要執行 Lync Server 部署嚮導。

</div>

</div>

<span> </span>

</div>

</div>

</div>

