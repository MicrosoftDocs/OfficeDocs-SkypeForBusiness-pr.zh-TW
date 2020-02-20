---
title: Lync Server 2013： 新增或移除前端伺服器
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
ms.openlocfilehash: 29c1b3800b05ac4318f853ece95b935c6e65c16c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a>新增或移除 Lync Server 2013 中的前端伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016年-01-21_

當您將前端伺服器新增至集區，或從集區移除前端伺服器時，您需要重新啟動集區。 若要避免服務中斷的使用者，請使用下列程序時新增或移除前端伺服器。

<div>


> [!NOTE]  
> 如果您正在加入新的伺服器集區，請更新您新的集區伺服器，以在相同的累計更新層級為現有的伺服器集區中。



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a>若要新增或移除前端伺服器

1.  如果您要移除任何前端伺服器，請先停止這些伺服器的新連線。 若要這麼做，您可以使用下列 cmdlet:
    
        Stop-CsWindowsServices -Graceful

2.  當正在移除的伺服器沒有目前的工作階段時，請在其上停止 Lync Server 服務。

3.  開啟拓撲產生器，並新增或移除必要的伺服器。

4.  發行拓撲。

5.  如果集區已從擁有兩個前端伺服器到兩個以上，或兩台變成實際上兩個以上的伺服器，您需要輸入下列 cmdlet:
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    如果集區中有三個或多個伺服器，然後至少三個這些伺服器必須執行當您輸入此 cmdlet。

6.  重新啟動所有前端伺服器集區，一次一個。

</div>

</div>

<span> </span>

</div>

</div>

</div>

