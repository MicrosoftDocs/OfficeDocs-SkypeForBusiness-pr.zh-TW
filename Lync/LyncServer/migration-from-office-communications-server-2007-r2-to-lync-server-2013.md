---
title: 從 Office Communications Server 2007 R2 移轉至 Lync Server 2013
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
ms.openlocfilehash: 39aef26271594ed57d113bed4c3bb3702df41fac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a>從 Office Communications Server 2007 R2 移轉至 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-19_

本節中的主題將引導您完成從 Office Communications Server 2007 R2 移轉至 Lync Server 2013 的程序

<div>


> [!IMPORTANT]  
> 本文件說明通常完成移轉的每個階段所需的步驟。 它並未涵蓋每個可能的舊版部署拓樸或每個可能的移轉案例。 因此，您可能不需要執行每個步驟所述，或您可能需要執行額外步驟，根據您的部署。 這份文件也提供驗證步驟的範例。 下列驗證步驟提供可協助您了解您要尋找以確保，每個階段成功完成為您的進行移轉。 調整您的特定移轉程序下列驗證步驟。



</div>

本指南提供將升級的現有部署的特定資訊。 它不會說明如何變更您現有的拓樸。 本指南並未涵蓋實作的新功能。 時的詳細程序會說明在其他地方，則本指南會引導您到適當的文件或文件] 區段中。

本文件定義字詞指定下列清單中。

  - *移轉*  
    將實際執行的部署從舊版 Office Communications Server 2007 R2 移至 Lync Server 2013。

<!-- end list -->

  - *升級*  
    伺服器或用戶端電腦上安裝較新版的軟體。

<!-- end list -->

  - *共存*  
    暫時環境，在移轉期間存在於，當某些功能會已移轉至 Lync Server 2013，以及其他功能則仍停留在前版的 Office Communications Server 2007 R2。

<!-- end list -->

  - *互通性*  
    共存期間順利運作您部署的能力。

<div>

## <a name="in-this-section"></a>本章節內容

  - [開始移轉之前](before-you-begin-the-migration_1.md)

  - [移轉階段](migration-phases_1.md)

  - [階段 1： 規劃從 Office Communications Server 2007 R2 移轉](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [階段 2： 準備移轉](phase-2-prepare-for-migration_1.md)

  - [階段 3： 部署 Lync Server 2013 試驗集區](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [階段 4： 合併拓撲](phase-4-merge-topologies.md)

  - [階段 5： 設定試驗集區](phase-5-configure-the-pilot-pool.md)

  - [階段 6： 將使用者移至試驗集區](phase-6-move-users-to-the-pilot-pool.md)

  - [階段 7： 將 Lync Server 2013 Edge Server 新增至試驗集區](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [階段 8： 從試驗部署移至實際執行環境](phase-8-move-from-pilot-deployment-into-production.md)

  - [階段 9： 完成移轉後工作](phase-9-complete-post-migration-tasks.md)

  - [階段 10： 解除委任舊版站台](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

