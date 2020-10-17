---
title: Lync Server 2013：新增或移除前端伺服器
description: Lync Server 2013：新增或移除前端伺服器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 297bbf42dbba3d4f9926fd5ab9e0d7ed79349dc4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571999"
---
# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a>在 Lync Server 2013 中新增或移除前端伺服器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-01-21_

當您將前端伺服器新增至集區，或從集區中移除前端伺服器時，您必須重新開機集區。 若要避免任何服務中斷給使用者，請在新增或移除前端伺服器時使用下列程式。

<div>


> [!NOTE]  
> 若要將新伺服器新增至集區，請將新的集區伺服器更新成與集區中現有伺服器相同的累計更新層級。



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a>新增或移除前端伺服器

1.  如果您要移除任何前端伺服器，請先停止這些伺服器的新連線。 若要這麼做，您可以使用下列 Cmdlet：
    
        Stop-CsWindowsServices -Graceful

2.  當要移除的伺服器沒有目前的會話時，請停止其上的 Lync Server 服務。

3.  開啟拓撲產生器，並新增或移除必要的伺服器。

4.  發行拓撲。

5.  如果集區從兩部以上的伺服器到兩部以上，或從兩部以上的伺服器到兩部以上，您必須輸入下列 Cmdlet：
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    如果集區有三部以上的伺服器，當您輸入此 Cmdlet 時，至少必須執行三台伺服器。

6.  重新開機集區中的所有前端伺服器，一次一個。

</div>

</div>

<span> </span>

</div>

</div>

</div>

