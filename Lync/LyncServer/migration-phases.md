---
title: 遷移階段
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08379ec217cc684ae9b6bc11c44b89a3d642f6df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a>遷移階段

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-17_

在 Lync Server 2013 中，您可以定義網站包含 Lync Server 2013 元件您網路上。 網站是一組已妥善連接高速、 低延遲的網路，例如單一區域網路 (LAN) 或透過高速光纖並網路連線的兩個網路的電腦。

*前端集區*是一組相同的方式設定的前端伺服器和工時來提供服務給一般使用者群組。 集區可為您的使用者提供延展性及容錯移轉功能。 集區中的每部伺服器都必須執行一或多個相同的伺服器角色。 Standard Edition server，專用於小型組織，也會定義集區，並在單一伺服器上執行。 這可讓您有較少的成本，適用於 Lync Server 2013 功能，但並不提供，則為 true 的高可用性解決方案。

下列階段說明從 Lync Server 2010 集區移轉至 Lync Server 2013 的程序。 針對含有多個集區的多個站台，每一個集區都應該要遵循此階段式方法。

1.  [階段 1： 規劃從 Lync Server 2010 移轉](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [階段 2： 準備移轉](phase-2-prepare-for-migration.md)

3.  [階段 3： 部署 Lync Server 2013 試驗集區](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [階段 4： 將測試使用者移至試驗集區](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [階段 5： 將 Lync Server 2013 Edge Server 新增至試驗集區](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [階段 6： 從試驗部署移至實際執行環境](phase-6-move-from-pilot-deployment-into-production.md)

7.  [階段 7： 完成移轉後工作](phase-7-complete-post-migration-tasks.md)

8.  [第 8 階段： 解除委任舊版的集區](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

