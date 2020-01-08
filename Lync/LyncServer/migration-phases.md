---
title: 移轉階段
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa7226a442d8e41d4ab0e6e3511a35e020decb65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a>移轉階段

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-17_

在 Lync Server 2013 中，您會在網路上定義包含 Lync Server 2013 元件的網站。 網站是一組電腦，這些電腦是由高速、低延遲網路（例如單一局域網（LAN）或由高速光纖網路連接的兩個網路來連接。

[*前端] 池*是一組前端伺服器，其配置相同，且共同合作，為一組共同使用者提供服務。 [池] 可為您的使用者提供可伸縮性及容錯移轉功能。 池中的每個伺服器都必須執行相同的伺服器角色或角色。 專為小型組織設計的標準版伺服器也會定義一個池，並在單一伺服器上執行。 這可讓您將 Lync Server 2013 功能設為較低的成本，但不會提供真正的高可用性方案。

下列階段說明從 Lync Server 2010 到 Lync Server 2013 的池遷移過程。 針對包含多個池的多個網站，每個個別的池都應該遵循這個分階段的方法。

1.  [階段1：從 Lync Server 2010 規劃您的遷移](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [階段 2：準備移轉](phase-2-prepare-for-migration.md)

3.  [階段3：部署 Lync Server 2013 試用版池](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [階段4：將測試使用者移至 [試驗] 池](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [階段5：將 Lync Server 2013 Edge 伺服器新增到 [試驗] 池](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [階段 6：從試驗部署移至生產](phase-6-move-from-pilot-deployment-into-production.md)

7.  [階段 7：完成移轉後的工作](phase-7-complete-post-migration-tasks.md)

8.  [階段 8：解除委任舊版集區](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

