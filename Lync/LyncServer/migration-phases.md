---
title: 遷移階段
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63f789abee1949f7fae5a7a3d7dcdc03c86dc352
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527220"
---
# <a name="migration-phases"></a>遷移階段

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-17_

在 Lync Server 2013 中，您可以在網路上定義包含 Lync Server 2013 元件的網站。 網站是以高速度、低延遲網路連接的一組電腦，例如單一區域網路 (LAN) 或由高速光纖網路連接的兩個網路。

*前端集*區是一組前端伺服器，其設定方式相同，並且共同運作，為一般使用者群組提供服務。 集區可為您的使用者提供延展性及容錯移轉功能。 集區中的每部伺服器都必須執行一或多個相同的伺服器角色。 專為小型組織設計的 Standard Edition 伺服器也會定義集區，並在單一伺服器上執行。 這可讓您將 Lync Server 2013 功能設為較低的成本，但不會提供真正的高可用性解決方案。

下列階段說明從 Lync Server 2010 到 Lync Server 2013 的集區遷移過程。 針對含有多個集區的多個站台，每一個集區都應該要遵循此階段式方法。

1.  [階段1：規劃從 Lync Server 2010 進行遷移](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [階段 2：準備移轉](phase-2-prepare-for-migration.md)

3.  [階段3：部署 Lync Server 2013 試驗集區](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [階段4：將測試使用者移至試驗集區](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [第5階段：將 Lync Server 2013 Edge Server 新增至試驗集區](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [階段 6：從試驗部署移至生產](phase-6-move-from-pilot-deployment-into-production.md)

7.  [階段 7：完成移轉後的工作](phase-7-complete-post-migration-tasks.md)

8.  [階段 8：解除委任舊版集區](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

