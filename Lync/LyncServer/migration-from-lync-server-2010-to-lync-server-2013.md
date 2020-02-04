---
title: 從 Lync Server 2010 移轉到 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c32d2679d4f31863e389735efb6660ea670b959
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a>從 Lync Server 2010 移轉到 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-17_

本節中的主題會引導您完成從 Lync Server 2010 遷移到 Lync Server 2013 的程式。

<div>


> [!IMPORTANT]  
> 本檔說明完成每個遷移階段通常需要執行的步驟。 它不會針對每個可能的舊版部署拓撲或每個可能的遷移案例進行處理。 因此，您可能不需要執行所述的每個步驟，或者您可能需要執行其他步驟（視您的部署而定）。 本檔也提供驗證步驟的範例。 提供這些驗證步驟是為了協助您瞭解所需尋找的專案，以確保每個階段都能在您完成遷移時順利完成。 將這些驗證步驟調整為您特定的遷移程式。



</div>

本指南提供升級現有部署的相關資訊。 它不會說明如何變更您現有的拓撲。 本指南並未涵蓋新功能的實現。 在其他地方記錄詳細的程式時，本指南會將您導向至適當的檔或檔區段。

此檔會根據下列清單中所指定的方式來定義字詞。

  - *移動*  
    將您的生產部署從舊版 Lync Server 2010 移至 Lync Server 2013。

<!-- end list -->

  - *更新*  
    在伺服器或用戶端電腦上安裝更新版本的軟體。

<!-- end list -->

  - *共存*  
    當某些功能已遷移至 Lync Server 2013 且其他功能仍保留在舊版 Lync Server 2010 中時，在遷移期間所存在的臨時環境。

<!-- end list -->

  - *互通性*  
    您的部署在共存期間成功運作的能力。

<div>

## <a name="in-this-section"></a>本節內容

  - [開始移轉之前](before-you-begin-the-migration.md)

  - [階段1：從 Lync Server 2010 規劃您的遷移](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [階段 2：準備移轉](phase-2-prepare-for-migration.md)

  - [階段3：部署 Lync Server 2013 試用版池](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [階段4：將測試使用者移至 [試驗] 池](phase-4-move-test-users-to-the-pilot-pool.md)

  - [階段5：將 Lync Server 2013 Edge 伺服器新增到 [試驗] 池](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [階段 6：從試驗部署移至生產](phase-6-move-from-pilot-deployment-into-production.md)

  - [階段 7：完成移轉後的工作](phase-7-complete-post-migration-tasks.md)

  - [階段 8：解除委任舊版集區](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

