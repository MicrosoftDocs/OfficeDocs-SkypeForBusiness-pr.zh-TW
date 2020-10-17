---
title: 階段10：解除委任舊版網站
description: 階段10：解除委任舊版網站。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9692301a1da38cfd69780ce2524f00dd428454e5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571199"
---
# <a name="phase-10-decommission-legacy-site"></a>階段10：解除委任舊版網站

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-16_

下列主題提供解除委任集區的指導，以及從 Office 通訊伺服器 2007 R2 的舊版部署停用和移除伺服器及集區的指導方針。 本節所列的程序並非全為必要程序。 請閱讀下列各主題中的資訊，以判斷要使用的解除委任程式。

<div>


> [!WARNING]  
> 如果您已將電話撥入式會議的會議目錄匯入 Lync Server 2013，請務必先將會議目錄擁有權轉移至 Lync Server 2013，再開始解除委任集區。 如果您解除委任集區，但沒有第一次轉換會議目錄擁有權，所有已遷移會議的撥入功能將不再運作。 您必須執行此步驟，針對舊版集區中的每個會議目錄，將擁有權轉移一次。



</div>

<div>


> [!IMPORTANT]  
> 如需遷移和升級 Microsoft 整合通訊 Managed API (UCMA) 應用程式的資訊，在解除委任舊版環境之前，請參閱 <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A>



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [移動會議目錄](move-conference-directories.md)

  - [更新 DNS SRV 記錄](update-dns-srv-records.md)

  - [解除委任伺服器與集區](decommissioning-servers-and-pools.md)

  - [移除 BackCompatSite](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

