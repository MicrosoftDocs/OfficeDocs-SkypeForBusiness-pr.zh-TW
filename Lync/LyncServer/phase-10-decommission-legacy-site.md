---
title: 階段 10： 解除委任舊版站台
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
ms.openlocfilehash: c306f79bf1e9f2d136472419b1c57465a2d71bf2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a>階段 10： 解除委任舊版站台

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012 年 10-16_

下列主題提供在解除委任集區]，並停用與舊版 Office Communications Server 2007 R2 部署中移除伺服器和集區中的指引。 本節所列的程序並非全為必要程序。 閱讀中每個這些主題，以決定要使用哪一個解除委任程序的資訊。

<div>


> [!WARNING]  
> 如果您匯入 Lync Server 2013 的電話撥入式會議的會議目錄，務必切換到 Lync Server 2013 會議目錄擁有權解除委任集區之前。 如果您解除委任集區，而第一個轉換的會議目錄擁有權，所有的移轉會議的撥號對應表中功能將不再有作用。 您必須執行轉換擁有權的步驟一次每個會議目錄舊版集區中。



</div>

<div>


> [!IMPORTANT]  
> 如需移轉與升級 Microsoft Unified Communications Managed API (UCMA) 應用程式]，再解除委任舊版環境，請參閱<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A>



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [移動會議目錄](move-conference-directories.md)

  - [更新 DNS SRV 記錄](update-dns-srv-records_1.md)

  - [解除委任伺服器和集區](decommissioning-servers-and-pools.md)

  - [移除 BackCompatSite](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

