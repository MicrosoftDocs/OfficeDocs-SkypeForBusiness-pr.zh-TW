---
title: Lync Server 2013 Active Directory 支援
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
ms.openlocfilehash: 193ebaedd11c239ba380937da3051ec8336578a3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a>Lync Server 2013 中的 active Directory 支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-12-04_

Lync Server 2013 所支援的 Active Directory 網域服務的內部拓撲如下所示：

  - 具單一網域的單一樹系

  - 具單一樹狀結構和多個網域的單一樹系

  - 具多重樹狀結構和斷續命名空間的單一樹系

  - 中央樹系拓撲中的多重樹系

  - 資源樹系拓撲中的多重樹系

<div>


> [!NOTE]  
> Lync Server 2013 不支援單一標籤網域。 例如，名為<STRONG>contoso.local</STRONG>根網域與樹系支援，但是不支援名為<STRONG>本機</STRONG>的單一標籤根網域。 如需詳細資訊，請參閱 Microsoft 知識庫文章 300684，「 設定資訊視窗具有單一標籤 DNS 名稱的網域 」， <A href="https://go.microsoft.com/fwlink/p/?linkid=143752">https://go.microsoft.com/fwlink/p/?linkId=143752</A>。



</div>

<div>


> [!NOTE]  
> Lync Server 2013 不支援重新命名的網域。 如果您需要重新命名其中部署 Lync Server 的網域，您需要先解除安裝 Lync Server]，然後重新命名網域，並再重新安裝 Lync Server。



</div>

如需支援的拓撲與內部部署的需求的詳細資訊，請參閱規劃文件中的[Active Directory 網域服務需求、 支援和 Lync Server 2013 中的拓撲](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md)。

</div>

<span> </span>

</div>

</div>

</div>

