---
title: Lync Server 2013： 用於備份及還原的最佳作法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fc2aac99251c0b2e5bc950b3dc11e8e2044b440
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a>備份及還原 Lync Server 2013 的最佳作法

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

本節包含兩種類型的最佳作法：

  - 用於備份及還原的最佳作法。

  - 降低災害影響程度的最佳作法。

<div>

## <a name="best-practices-for-backup-and-restoration"></a>備份及還原的最佳作法

當您備份或還原您的資料，以利您備份和還原程序，套用下列最佳作法：

  - 在適當的時間間隔執行定期備份。 簡單且最常使用的備份類型和旋轉排程是完整、 夜間整個 SQL Server 資料庫的備份。 然後，如果需要還原，復原程序需要只有一個備份，並不超過一天的資料不會遺失。

  - 如果您使用 cmdlet 或 Lync Server Control Panel 以進行組態變更，使用**Export-csconfiguration** cmdlet 之後要採取的拓撲組態檔 (Xds.mdf) 快照備份進行的變更，使您不會遺失所做的變更，如果您需要還原資料庫。 請注意，此組態是以 XML 格式，備份壓縮的 ZIP 檔案。

  - 請確定您計劃要用於備份 Lync 伺服器之共用的資料夾有足夠的磁碟空間可容納所有備份的資料。

  - 排程備份 Lync Server 使用狀況通常較低，以改善伺服器效能及提升使用者經驗時。

  - 請確定備份資料的位置是安全 （建議使用遠端位置）。

  - 保留他們將可使用位置，以便在需要時還原資料的備份檔案。

  - 規劃及排程定期測試組織所支援的還原程序。

  - 驗證事先以確保其運作如預期般您備份和還原程序。

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a>降低災害影響程度的最佳作法

（例如電力中斷或突然硬體故障不事件所造成） 的慘服務中斷的處理的最佳策略是假設他們將會發生，並據此規劃。

如果 Lync 服務，最少的干擾及中斷，商務關鍵的組織，您應該考慮實作的前端伺服器，配對集區中[的高可用性和災害復原 Lync Server 2013 中的規劃](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)所述。 然後，如果其中一個這些集區有災害時，系統管理員可以切換至其他集區，最少的停機時間由該集區的使用者。

您開發以備份和還原策略的一部分的嚴重損壞管理計劃應包含下列：

  - 追蹤您的軟體媒體，以及軟體與韌體更新，隨時可用。

  - 維護硬體與軟體記錄。

  - 定期備份資料和監控備份的完整性。

  - 訓練人員相關的嚴重損壞修復、 記載的程序，以及實作災害復原模擬操演。

  - 預留備用硬體，或者，如果您有服務層級協議 (SLA)，與硬體廠商與供應商的提示取代訂立。

  - 分開保存交易記錄檔 （.ldf 檔案） 與資料庫檔案 （.mdf 檔案）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

