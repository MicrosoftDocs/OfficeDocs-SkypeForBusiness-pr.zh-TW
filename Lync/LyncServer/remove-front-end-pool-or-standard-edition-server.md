---
title: 移除前端集區或 Standard Edition Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5a3b08d6e8b4f0b792063b19a47889de11283c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-front-end-pool-or-standard-edition-server"></a>移除前端集區或 Standard Edition Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

本主題將引導您完成移除前端池或標準版前端伺服器的程式。 當您移除 [前端] 池時，您會將屬於該池的每個前端伺服器移除為 [池移除] 程式的一部分。 當您移除標準版前端伺服器時，必須從拓撲建立器移除 SQL Store 定義。

<div>

## <a name="to-remove-a-front-end-server-pool"></a>移除前端伺服器池

1.  開啟拓撲建立器。

2.  流覽至 Lync Server 2010 節點。

3.  展開 [**企業版前端] 池**、展開 [前端] 池、以滑鼠右鍵按一下您要移除的 [前端] 池，然後按一下 [**刪除**]。

4.  發佈拓撲，檢查 [複製狀態]，然後視需要執行 Lync Server 部署嚮導。

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a>移除標準版前端伺服器

1.  開啟拓撲建立器。

2.  流覽至 Lync Server 2010 節點。

3.  展開 [**標準版前端伺服器**]，以滑鼠右鍵按一下您要移除的前端伺服器，然後按一下 [**刪除**]。

4.  展開 **[SQL] 商店**，以滑鼠右鍵按一下與標準版前端伺服器相關聯的 SQL Server 資料庫，然後按一下 [**刪除**]。
    
    <div>
    

    > [!IMPORTANT]  
    > 您必須從標準版前端伺服器移除 collocated SQL Server 資料庫的定義。

    
    </div>

5.  發佈拓撲，檢查 [複製狀態]，然後視需要執行 Lync Server 部署嚮導。

</div>

</div>

<span> </span>

</div>

</div>

</div>

