---
title: Lync Server 2013：設定呼叫許可控制
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
ms.openlocfilehash: 62f6858aa84309a268e8fc55af6cc0a63e6010a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a>在 Lync Server 2013 中設定通話許可控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

通話許可控制（CAC）是一個方案，可判斷是否可以根據可用頻寬建立即時會話，以協助避免使用者在擁擠的網路上發生的音訊/視頻品質不佳。 CAC 只會控制音訊和影片的即時流量，不會影響資料流量。 當預設 WAN 路徑沒有所需的頻寬時，CAC 可能會透過網際網路路徑傳送通話。 如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的 [通話許可控制](lync-server-2013-planning-for-call-admission-control.md)]。

本節提供一組範例程式，說明如何在您的網路中部署和管理 CAC。

<div>


> [!IMPORTANT]  
> 在您部署 CAC 前，您必須收集商業網路拓朴所需的所有必要資訊，如範例所述：在規劃檔中<A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">收集 Lync Server 2013 的通話許可控制需求</A>。 此外，請確定您已安裝並啟用 CAC 元件，如在部署檔中的<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 定義及設定前端池或標準版伺服器</A>中所述。



</div>

<div>


> [!NOTE]  
> 本節中的所有 CAC 部署與管理範例都是使用 Lync Server 管理命令介面來執行。 或者，您也可以使用 Lync Server [控制台] 的 [<STRONG>網路</STRONG>設定] 區段來管理 CAC。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中設定 CAC 的網路區域](lync-server-2013-configure-network-regions-for-cac.md)

  - [在 Lync Server 2013 中建立頻寬原則設定檔](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [在 Lync Server 2013 中設定 CAC 的網路網站](lync-server-2013-configure-network-sites-for-cac.md)

  - [在 Lync Server 2013 中，將子網與網路網站建立在 CAC 中](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [在 Lync Server 2013 中建立網路區域連結](lync-server-2013-create-network-region-links.md)

  - [在 Lync Server 2013 中建立網路 interregion 路由](lync-server-2013;-create-network-interregion-routes.md)

  - [在 Lync Server 2013 中建立網路站間原則](lync-server-2013-create-network-intersite-policies.md)

  - [在 Lync Server 2013 中啟用呼叫許可控制](lync-server-2013-enable-call-admission-control.md)

  - [Lync Server 2013 的呼叫許可控制部署檢查清單](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

