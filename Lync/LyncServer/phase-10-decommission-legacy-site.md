---
title: 階段10：解除授權舊版網站
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8110d41e5f6436bfdbecc64fe07d514b5d0538ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a>階段10：解除授權舊版網站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-16_

下列主題提供解除授權的方式，以及從 Office 通訊伺服器 2007 R2 的舊版部署中停用及移除伺服器和池的指導方針。 並非本節所列的所有程式都是必要的。 閱讀其中每個主題中的資訊，以判斷要使用的解除授權程式。

<div>


> [!WARNING]  
> 如果您已將電話撥入式會議的會議目錄匯入到 Lync Server 2013，請務必先將會議目錄擁有權轉移至 Lync Server 2013，然後才能開始解除池的授權。 如果您在未事先轉移會議目錄擁有權的情況下停用池，所有已遷移會議的撥入功能將不再運作。 您必須針對舊版池中的每個會議目錄，執行一次轉移擁有權的步驟。



</div>

<div>


> [!IMPORTANT]  
> 如需遷移和升級 Microsoft 整合通訊管理 API （UCMA）應用程式的相關資訊，請參閱在解除舊版環境的授權之前，請參閱<A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A>



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [移動會議目錄](move-conference-directories.md)

  - [更新 DNS SRV 記錄](update-dns-srv-records_1.md)

  - [伺服器和池退役](decommissioning-servers-and-pools.md)

  - [移除 BackCompatSite](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

