---
title: Lync Server 2013 Active Directory 支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9be3bda71e44d0e739fce3a8d01db9cb84e2b9e3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a>Lync Server 2013 中的 Active Directory 支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-04_

Lync Server 2013 支援的 Active Directory 網域服務內部部署拓撲如下所示：

  - 單一目錄林與單一網域

  - 具有單一樹狀結構和多個網域的單一目錄林

  - 具有多個樹和不連續命名空間的單一目錄林

  - 中央目錄林拓撲中的多個林

  - 資原始目錄林拓朴中的多個目錄林

<div>


> [!NOTE]  
> Lync Server 2013 不支援單標籤網域。 例如，支援名為<STRONG>contoso. local</STRONG>的根網域的林，但不支援名為<STRONG>local</STRONG>的單一標籤根網域。 如需詳細資訊，請參閱 Microsoft 知識庫文章300684：「使用單標籤 DNS 名稱設定 Windows 網域的相關資訊」 <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>。



</div>

<div>


> [!NOTE]  
> Lync Server 2013 不支援重新命名網域。 如果您需要重新命名部署 Lync Server 的網域，您必須先卸載 Lync Server，然後重新命名網域，然後重新安裝 Lync Server。



</div>

如需支援的拓撲及內部部署部署需求的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的 Active Directory 網域服務需求、支援及拓撲](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md)。

</div>

<span> </span>

</div>

</div>

</div>

