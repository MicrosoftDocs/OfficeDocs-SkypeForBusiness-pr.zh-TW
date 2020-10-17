---
title: Lync Server 2013：設定通話許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1edac7fe7b3b56cdaa5324f1c6e976bfb0b746fe
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517660"
---
# <a name="configure-call-admission-control-in-lync-server-2013"></a>在 Lync Server 2013 中設定通話許可控制

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

通話許可控制 (CAC) 是一種方案，可判斷即時會話是否可以根據可用的頻寬建立，以協助避免網路擁塞之使用者的音訊/視頻品質不良。 CAC 只會控制音訊和影片的即時流量，而且不會影響資料流量。 當預設 WAN 路徑不具備必要的頻寬時，CAC 可能會透過網際網路路徑路由傳送通話。 如需詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的通話許可控制](lync-server-2013-planning-for-call-admission-control.md) 。

本節提供一組範例程式，說明如何在網路中部署及管理 CAC。

<div>


> [!IMPORTANT]  
> 在您部署 CAC 之前，您必須收集商業網路拓撲的所有必要資訊，如範例所述：在規劃檔中 <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">收集 Lync Server 2013 的通話許可控制需求</A> 。 此外，請確定已安裝並啟動 CAC 元件，如在部署檔中的 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">定義和設定前端集區或 Standard Edition 2013 server</A> 中所述。



</div>

<div>


> [!NOTE]  
> 本節中的所有 CAC 部署和管理範例都是使用 Lync Server 管理命令介面來執行。 或者，您也可以使用 Lync Server 控制台的 [ <STRONG>網路</STRONG> 設定] 區段來管理 CAC。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中設定 CAC 的網路地區](lync-server-2013-configure-network-regions-for-cac.md)

  - [在 Lync Server 2013 中建立頻寬原則設定檔](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [在 Lync Server 2013 中設定 CAC 的網路網站](lync-server-2013-configure-network-sites-for-cac.md)

  - [在 Lync Server 2013 中將子網與 CAC 的網路網站產生關聯](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [在 Lync Server 2013 中建立網路地區連結](lync-server-2013-create-network-region-links.md)

  - [在 Lync Server 2013 中建立網路區間路由](lync-server-2013;-create-network-interregion-routes.md)

  - [在 Lync Server 2013 中建立網路站間原則](lync-server-2013-create-network-intersite-policies.md)

  - [在 Lync Server 2013 中啟用通話許可控制](lync-server-2013-enable-call-admission-control.md)

  - [Lync Server 2013 的通話許可控制部署檢查清單](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

