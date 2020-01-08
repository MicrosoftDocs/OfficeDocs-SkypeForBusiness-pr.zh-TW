---
title: Lync Server 2013：備份和還原的最佳做法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fc7a926bd8fd5c61f87d5e8252c30f40e5a6a69
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a>Lync Server 2013 備份和還原的最佳做法

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

本節包含兩種類型的最佳做法：

  - 備份與還原的最佳做法。

  - 將災難影響降至最低的最佳做法。

<div>

## <a name="best-practices-for-backup-and-restoration"></a>備份與還原的最佳做法

若要協助您的備份和還原程式，請在備份或還原資料時，套用下列最佳做法：

  - 以適當的間隔執行定期備份。 最簡單且最常使用的備份類型和輪換排程是完整、晚上備份整個 SQL Server 資料庫。 然後，如果需要還原，還原程式只需要一個備份，而且一天的資料就不會遺失。

  - 如果您使用 [Cmdlet] 或 [Lync Server 控制台] 進行設定變更，請在進行變更之後，使用**Export CsConfiguration** Cmdlet 來製作拓撲設定檔案（Xds）的快照備份，以免您需要還原資料庫時才遺失所做的變更。 請注意，此設定是以 XML 格式來備份，並壓縮為 ZIP 檔案。

  - 請確定您打算用來備份 Lync Server 的共用資料夾有足夠的磁碟空間來容納所有備份的資料。

  - 在 Lync 伺服器使用量通常較低時排程備份，以提升伺服器效能和使用者體驗。

  - 確定備份資料的位置是安全的（我們建議遠端位置）。

  - 將備份檔案保留在其中，以備您需要還原資料時使用。

  - 規劃並排程您組織所支援之還原處理程式的定期測試。

  - 事先驗證您的備份和還原程式，以確保它們能如期運作。

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a>將災難影響降至最低的最佳做法

處理災難性服務中斷的最佳策略（由無法管理的事件（例如電源中斷或突然硬體故障）所造成）是假設它們將會發生，並據此規劃。

如果 Lync 服務的中斷和停機時間最低，對於您的組織而言是至關重要的，您應該考慮實現前端伺服器的成對池，如在[Lync Server 2013 規劃高可用性和災難](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)復原中所述。 然後，如果其中一個池有災難，系統管理員可以將該池的使用者切換為由其他池提供，但停機時間最低。

您在備份和還原策略中開發的災難管理方案應包括下列各項：

  - 讓您的軟體媒體和軟體及固件更新保持在隨時可用。

  - 維護硬體和軟體記錄。

  - 定期備份您的資料，並監控備份的完整性。

  - 在災難復原中訓練您的員工、記錄程式，以及實施災害復原類比訓練。

  - 讓備用硬體保持可用，或如果您有服務等級協定（SLA），請與硬體廠商和供應商進行提示取代。

  - 分隔事務日誌檔（.ldf 檔案）和資料庫檔案（.mdf 檔案）的位置。

</div>

</div>

<span> </span>

</div>

</div>

</div>

