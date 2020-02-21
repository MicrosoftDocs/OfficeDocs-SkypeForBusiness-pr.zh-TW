---
title: 從 Lync Server 2010 移轉至 Lync Server 2013
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
ms.openlocfilehash: 7ea588abf4018ab06a415d4aa5ef7decf5f93996
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a>從 Lync Server 2010 移轉至 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-17_

本節中的主題會引導您完成從 Lync Server 2010 移轉至 Lync Server 2013 的程序。

<div>


> [!IMPORTANT]  
> 本文件說明通常完成移轉的每個階段所需的步驟。 它並未涵蓋每個可能的舊版部署拓樸或每個可能的移轉案例。 因此，您可能不需要執行每個步驟所述，或您可能需要執行額外步驟，根據您的部署。 這份文件也提供驗證步驟的範例。 下列驗證步驟提供可協助您了解您要尋找以確保，每個階段成功完成為您的進行移轉。 調整您的特定移轉程序下列驗證步驟。



</div>

本指南提供將升級的現有部署的特定資訊。 它不會說明如何變更您現有的拓樸。 本指南並未涵蓋實作的新功能。 時的詳細程序會說明在其他地方，則本指南會引導您到適當的文件或文件] 區段中。

本文件定義字詞指定下列清單中。

  - *移轉*  
    將實際執行的部署從舊版 Lync Server 2010 移至 Lync Server 2013。

<!-- end list -->

  - *升級*  
    伺服器或用戶端電腦上安裝較新版的軟體。

<!-- end list -->

  - *共存*  
    暫時環境，在移轉期間存在於，當某些功能會已移轉至 Lync Server 2013，以及其他功能則仍停留在前版的 Lync Server 2010。

<!-- end list -->

  - *互通性*  
    共存期間順利運作您部署的能力。

<div>

## <a name="in-this-section"></a>本章節內容

  - [開始移轉之前](before-you-begin-the-migration.md)

  - [階段 1： 規劃從 Lync Server 2010 移轉](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [階段 2： 準備移轉](phase-2-prepare-for-migration.md)

  - [階段 3： 部署 Lync Server 2013 試驗集區](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [階段 4： 將測試使用者移至試驗集區](phase-4-move-test-users-to-the-pilot-pool.md)

  - [階段 5： 將 Lync Server 2013 Edge Server 新增至試驗集區](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [階段 6： 從試驗部署移至實際執行環境](phase-6-move-from-pilot-deployment-into-production.md)

  - [階段 7： 完成移轉後工作](phase-7-complete-post-migration-tasks.md)

  - [第 8 階段： 解除委任舊版的集區](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

