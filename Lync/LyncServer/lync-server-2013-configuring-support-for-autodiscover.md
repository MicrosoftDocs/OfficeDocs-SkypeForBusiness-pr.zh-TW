---
title: Lync Server 2013：設定自動探索的支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 779929d270fa4ae2f8eec59a954c2273ff61b44f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a>在 Lync Server 2013 中設定自動探索的支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-21_

Lync Server web services**自動探索服務**會先出現在 lync Server 2010 累計更新：2011年11月。 此更新隨附于 Lync 行動用戶端的初始版本。 自動探索服務公開了行動服務，稱為 Mcx 服務。

自動探索服務會充當單一位置，讓所有用戶端要求提供哪些服務和功能的相關資訊，以及如何與 sevices 取得聯繫，只要是完全合格的功能變數名稱或網頁統一資源定位器參照即可。 自動探索會公開許多功能，而每個用戶端都會根據用戶端可以使用的功能來提出要求。 例如，桌面 Lync 2013 用戶端會使用 autodiscvoer 來判斷外部 web 服務，但不會使用行動（Mcx）服務。 若要正確定義並讓您的用戶端使用提供的功能，您必須定義允許用戶端有效尋找及使用自動探索專案的案例。 若要使用 autodoscover，您的部署需要反向 proxy 發佈 Lync Server web 服務、DNS 記錄已設定為解析 Lync Server 自動探索服務和 Lync Server web 服務的 DNS 查詢，以及該憑證服務針對您的特定案例正確地設定。

<div>


> [!TIP]  
> 如需有關自動探索要求/回應中的元素的技術詳細資料，請參閱<A href="lync-server-2013-understanding-autodiscover.md">瞭解 Lync Server 2013 中的自動</A>探索。



</div>

下列資訊與表格會根據案例所定義的設定（如果有的話）來提供自動探索服務的完整和有效使用。 下列主題中的資訊僅適用于 Microsoft Lync Server 2013。 如果您正在尋找如何規劃 Lync Server 2010 行動性的指導方針，請參閱[http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113)。 若要部署 Lync Server 2010 的行動性，請參閱[http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中針對自動探索設定 DNS](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [在 Lync Server 2013 中設定自動探索的憑證](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [在 Lync Server 2013 中針對自動探索設定反向 proxy](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [在 Lync Server 2013 中設定自動探索以進行混合式部署](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

