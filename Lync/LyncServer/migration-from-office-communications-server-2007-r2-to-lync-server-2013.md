---
title: 從 Office 通訊伺服器 2007 R2 遷移至 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a71ac7e0e1291dedfa45e4e358b5b3495d8a623b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527250"
---
# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a>從 Office 通訊伺服器 2007 R2 遷移至 Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

本節中的主題將引導您完成從 Office 通訊伺服器 2007 R2 到 Lync Server 2013 的處理常式。

<div>


> [!IMPORTANT]  
> 本檔說明執行每個遷移階段時，通常需要執行的步驟。 它不會解決每一個可能的舊版部署拓撲或每一種可能的遷移案例。 因此，您可能不需要執行所述的每一個步驟，否則您可能需要執行其他步驟，視您的部署而定。 這份檔也提供驗證步驟的範例。 提供這些驗證步驟是為了協助您瞭解需要尋找哪些專案，以確保每個階段在您完成遷移時順利完成。 將這些驗證步驟調整為您特定的遷移程式。



</div>

本指南提供升級現有部署的相關資訊。 它不會說明如何變更現有的拓撲。 本指南並未涵蓋新功能的實施。 在其他地方記錄詳細的程式時，本指南會指引您使用適當的檔或檔區段。

這份檔會定義下列清單中所指定的字詞。

  - *遷移*  
    將實際執行部署從舊版 Office 通訊伺服器 2007 R2 移至 Lync Server 2013。

<!-- end list -->

  - *升級*  
    在伺服器或用戶端電腦上安裝較新版本的軟體。

<!-- end list -->

  - *共存*  
    當某些功能已遷移至 Lync Server 2013，而其他功能仍保留在先前版本的 Office 通訊伺服器 2007 R2 時，在遷移期間所存在的暫時環境。

<!-- end list -->

  - *互 操作 性*  
    您的部署在共存期間順利運作的能力。

<div>

## <a name="in-this-section"></a>本章節內容

  - [開始移轉之前](before-you-begin-the-migration_1.md)

  - [移轉階段](migration-phases_1.md)

  - [階段1：規劃從 Office 通訊伺服器 2007 R2 遷移](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [階段 2：準備移轉](phase-2-prepare-for-migration_1.md)

  - [階段3：部署 Lync Server 2013 試驗集區](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [階段4：合併拓撲](phase-4-merge-topologies.md)

  - [階段5：設定試驗集區](phase-5-configure-the-pilot-pool.md)

  - [階段6：將使用者移至試驗集區](phase-6-move-users-to-the-pilot-pool.md)

  - [第7階段：將 Lync Server 2013 Edge Server 新增至試驗集區](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [階段8：從試驗部署移至實際執行環境](phase-8-move-from-pilot-deployment-into-production.md)

  - [階段9：完成遷移後工作](phase-9-complete-post-migration-tasks.md)

  - [階段10：解除委任舊版網站](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

