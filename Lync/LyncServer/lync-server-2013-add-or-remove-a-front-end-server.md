---
title: Lync Server 2013：新增或移除前端伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1fe1e81d3983b89d4f68111179c3adc7409bee2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a>在 Lync Server 2013 中新增或移除前端伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-01-21_

當您將前端伺服器新增到池中，或從池中移除前端伺服器時，您必須重新開機該池。 若要避免任何服務中斷給使用者，請在新增或移除前端伺服器時，請使用下列程式。

<div>


> [!NOTE]  
> 如果您要新增伺服器至池中，請將新的池伺服器更新為與池中現有伺服器相同的累加更新層級。



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a>新增或移除前端伺服器

1.  如果您要移除任何前端伺服器，請先停止與這些伺服器建立新連線。 若要這樣做，您可以使用下列 Cmdlet：
    
        Stop-CsWindowsServices -Graceful

2.  如果要移除的伺服器沒有目前的會話，請在這些伺服器上停止 Lync Server 服務。

3.  開啟拓撲建立器，然後新增或移除必要的伺服器。

4.  發佈拓撲。

5.  如果該池已超出兩個前端伺服器的數目，或從超過兩個伺服器，則必須輸入下列 Cmdlet：
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    如果該池有三個以上的伺服器，則在您輸入這個 Cmdlet 時，至少必須執行其中三個伺服器。

6.  一次重新開機一個池中的所有前端伺服器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

