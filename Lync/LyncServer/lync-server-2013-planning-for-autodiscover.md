---
title: Lync Server 2013：規劃自動探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 709b27059e1908a45b4b473f5380215bbd499d27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a>規劃 Lync Server 2013 中的自動探索

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-16_

在 Lync server 2010 （2011年11月）累計更新中，會針對 Lync Server 推出自動探索功能。 此初始的自動探索實現的主要用途是提供 Lync Mobile 的一種方法來找出行動服務（Mcx）。 Lync Server 2013 中的自動探索服務現已成為所有用戶端用來尋找伺服器和使用者服務的服務。 Microsoft Lync Server 2013 自動探索服務會在控制器和前端伺服器上執行。

<div>


> [!TIP]  
> 如需深入瞭解自動探索以及傳送給用戶端的內容，請參閱<A href="lync-server-2013-understanding-autodiscover.md">瞭解 Lync Server 2013 中的自動</A>探索。<BR>行動性仍是一個獨特的案例，行動服務仍需要一些特殊規劃。 如需其他詳細資料，請參閱<A href="lync-server-2013-planning-for-mobility.md">在 Lync Server 2013 中規劃行動</A>。



</div>

當 [Lync Server 2010] 中推出 [自動探索] 時，需要進行一些折衷，才能實現需要對現有伺服器部署有潛在證書變更的服務。 自動探索可用於 HTTPS 的埠 TCP 443，或經由埠 TCP 80 （針對 HTTP）使用。 如果決定使用 HTTPS，必須重新頒發反向代理、控制器和前端伺服器上的憑證，才能容納必要`lyncdiscover.<domain>`的`lyncdiscoverinternal.<domain>` DNS 記錄。 如果決定要使用 HTTP，您可以使用 DNS CNAME （或別名）記錄來避免重新頒發憑證，以使用憑證上現有的名稱。 使用 HTTP 是指未加密初始通訊。

由於 Lync Server 2013 使用所有用戶端的自動探索功能，因此主要案例是使用 HTTPS，並以 lyncdiscover 建立證書。\<[\>網域] 做為反向代理、控制器和前端伺服器的設定的一部分。 如果您要從 Lync Server 2010 將自動探索實現到升級後的部署，您可能會想要使用 HTTP 來避免重新頒發憑證。 下列各節提供這兩個案例的指導方針。

<div>


> [!IMPORTANT]  
> 外部 web 服務發佈規則所使用的憑證上的 [subject 替換名稱] 清單必須包含<EM>lyncdiscover&lt; 。針對&gt; </EM>貴組織內的每個 SIP 網域 sipdomain 專案。 如需董事、前端伺服器及反向 proxy 所需的主題替換名稱專案的詳細資料，請參閱<A href="lync-server-2013-certificate-summary-autodiscover.md">在 Lync Server 2013 中</A>的 [自動探索]。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [憑證摘要-Lync Server 2013 中的自動探索](lync-server-2013-certificate-summary-autodiscover.md)

  - [埠摘要-Lync Server 2013 中的自動探索](lync-server-2013-port-summary-autodiscover.md)

  - [DNS 摘要-Lync Server 2013 中的自動探索](lync-server-2013-dns-summary-autodiscover.md)

  - [Lync Server 2013 中的混合式和剝離網域自動探索](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

