---
title: Lync Server 2013： 設定通話許可控制
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
ms.openlocfilehash: 8ebe3fbdd60409523755c865f4b4f34025acf15d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a>在 Lync Server 2013 中設定通話許可控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-21_

通話許可控制 (CAC) 是解決方案，可以決定是否可以建立的即時工作階段為基礎，協助防範擁塞網路上的使用者的音訊/視訊品質不佳的可用頻寬。 CAC 控制僅適用於音訊與視訊、 即時流量，並不會影響資料流量。 CAC 可能會將電話路由傳送到網際網路路徑時的預設 WAN 路徑沒有所需的頻寬。 如需詳細資訊，請參閱規劃文件中的[Planning for Lync Server 2013 中的通話許可控制](lync-server-2013-planning-for-call-admission-control.md)。

本章節提供一組範例程序，說明如何部署及管理 CAC 網路中。

<div>


> [!IMPORTANT]  
> 部署 CAC 之前，您必須先收集必要資訊的所有企業網路拓撲中, 所述<A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">範例： 收集您的 Lync Server 2013 中的通話許可控制需求</A>中規劃文件。 也請務必 CAC 的元件，已安裝並啟動中, 所述<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">定義和設定 Lync Server 2013 中的前端集區或 Standard Edition server</A>部署文件中。



</div>

<div>


> [!NOTE]  
> 所有本節中的 CAC 部署及管理範例是使用 Lync Server 管理命令介面來都執行。 或者，您也可以使用 Lync Server 控制台的 [<STRONG>網路設定</STRONG>] 區段來管理 CAC。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [設定 Lync Server 2013 中的 CAC 網路地區](lync-server-2013-configure-network-regions-for-cac.md)

  - [在 Lync Server 2013 中建立頻寬原則設定檔](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [設定 Lync Server 2013 中的 CAC 的網路網站](lync-server-2013-configure-network-sites-for-cac.md)

  - [將子網路與網站關聯的 Lync Server 2013 中的 CAC](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [在 Lync Server 2013 中建立網路地區連結](lync-server-2013-create-network-region-links.md)

  - [在 Lync Server 2013 中建立網路區間路由](lync-server-2013;-create-network-interregion-routes.md)

  - [Lync Server 2013 中建立網站間原則](lync-server-2013-create-network-intersite-policies.md)

  - [啟用 Lync Server 2013 中的通話許可控制](lync-server-2013-enable-call-admission-control.md)

  - [Lync Server 2013 的通話許可控制部署檢查清單](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

