---
title: Lync Server 2013 Active Directory 支援
description: Lync Server 2013 Active Directory 支援。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 349862b2f541ef3033c9a725a6ff04c6a4e219f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567929"
---
# <a name="active-directory-support-in-lync-server-2013"></a>Lync Server 2013 中的 Active Directory 支援

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-04_

Lync Server 2013 支援的 Active Directory 網域服務內部部署拓撲如下：

  - 具單一網域的單一樹系

  - 具單一樹狀結構和多個網域的單一樹系

  - 具多重樹狀結構和斷續命名空間的單一樹系

  - 中央樹系拓撲中的多重樹系

  - 資源樹系拓撲中的多重樹系

<div>


> [!NOTE]  
> Lync Server 2013 不支援單一標籤網域。 例如，支援具有名為 <STRONG>contoso</STRONG> 的根功能變數名稱的樹系，但不支援名為 <STRONG>local</STRONG> 的單一標籤根功能變數名稱。 如需詳細資訊，請參閱 Microsoft 知識庫文章300684：「如何針對具有單一標籤 DNS 名稱的網域設定 Windows」的相關資訊」 <A href="https://go.microsoft.com/fwlink/p/?linkid=143752">https://go.microsoft.com/fwlink/p/?linkId=143752</A> 。



</div>

<div>


> [!NOTE]  
> Lync Server 2013 不支援重新命名網域。 如果您需要重新命名已部署 Lync Server 的網域，您必須先卸載 Lync Server，然後重新命名網域，然後重新安裝 Lync Server。



</div>

如需內部部署部署支援的拓撲和需求的詳細資訊，請參閱規劃檔中的 [Active Directory 網域服務需求、支援和拓撲中的 Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) 。

</div>

<span> </span>

</div>

</div>

</div>

