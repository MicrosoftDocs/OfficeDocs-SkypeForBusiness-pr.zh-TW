---
title: Lync Server 2013：備份及還原的最佳作法
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
ms.openlocfilehash: ca14913d063a8691d0477af912e70e72b91143fa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535200"
---
# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a>Lync Server 2013 備份及還原的最佳作法

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

本節包含兩種最佳作法類型：

  - 備份及還原的最佳作法。

  - 使災難影響降至最低的最佳作法。

<div>

## <a name="best-practices-for-backup-and-restoration"></a>備份及還原的最佳作法

若要協助您的備份與還原程式，請在備份或還原資料時套用下列最佳作法：

  - 以適當的間隔執行定期備份。 最簡單且最常使用的備份類型和輪替排程是完整、晚上備份整個 SQL Server 資料庫的完整備份。 這樣一來，如果需要還原，還原程式只需要一個備份，而且不會有超過一天的資料遺失。

  - 如果您使用 Cmdlet 或 Lync Server 控制台進行設定變更，請在進行變更之後，使用 **Export-CsConfiguration** 指令程式對拓撲設定檔進行快照備份，以 () Xds，這樣就不會在您需要還原資料庫時丟失變更。 請注意，這項設定會以 XML 格式備份，並壓縮成 ZIP 檔案。

  - 確定您計畫用於備份 Lync 伺服器的共用資料夾具有足夠的磁碟空間，可容納所有備份的資料。

  - 當 Lync Server 的使用量一般很低時，排程備份，以提升伺服器效能和使用者經驗。

  - 請確定備份資料的位置是否安全 (建議) 遠端位置。

  - 保留可供使用的備份檔案，以備您需要還原資料時使用。

  - 規劃及排程定期測試組織所支援的還原程式。

  - 請事先驗證備份與還原程式，以確定其運作如預期。

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a>最小化災難影響的最佳作法

處理災難性服務中斷的最佳策略， (因無法管理事件（例如電源中斷或突然硬體失敗）所造成，請) 假設會發生這些事件，並據此進行規劃。

如果 Lync 服務具有最低中斷和停機時間，對您的組織而言是至關重要的，您應該考慮實施前端伺服器的配對集區（如在 [Lync Server 2013 中規劃高可用性和嚴重損壞修復中](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)所述）。 然後，如果其中一個集區發生災難，系統管理員可以將該集區的使用者切換為由其他集區所提供，至少停機時間。

您在備份與還原策略中所制定的災難管理計畫應包含下列專案：

  - 讓您的軟體媒體和您的軟體和固件更新，都能隨時使用。

  - 維護硬體和軟體記錄。

  - 定期備份資料，並監視備份的完整性。

  - 訓練您的員工在嚴重損壞修復、記錄程式及實施嚴重損壞修復類比訓練。

  - 讓備用硬體可用，或者，如果您有服務層級協定 (SLA) ，請與硬體廠商和廠商簽定，以進行提示取代。

  - 將交易記錄檔的位置分開 ( .ldf 檔案中) 和資料庫檔案)  ( .mdf 檔案。

</div>

</div>

<span> </span>

</div>

</div>

</div>

