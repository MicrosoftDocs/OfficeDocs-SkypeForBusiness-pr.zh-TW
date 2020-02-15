---
title: 'Lync Server 2013: Lync Server 環境的最佳作法'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d02d9ed669cf9404b1bf8d07db32c9d331769ec9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041112"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-lync-server-2013-environments"></a>Lync Server 2013 環境的最佳作法

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-08-04_

下列的一般原則應套用至系統的進行中作業：

  - **了解，並利用 MOF**   MOF 是一群最佳作法、 原則和模型，提供組織有關管理 IT 資產，例如每日的 Lync Server 2013 操作的技術指導。 遵循 MOF 指導方針，可協助您達成重要生產系統的可靠性、 可用性、 支援性和 Microsoft 產品的管理性。 如需詳細資訊，請參閱[Microsoft Operations Framework 4.0](http://go.microsoft.com/fwlink/p/?linkid=40939)。

  - **了解 Lync Server 2013 的最佳做法**   我們建議您實作實用及證實程序來管理 Lync Server 2013。 藉由使用企圖，可能會比自行開發方法更有效率的管理作業的測試，並記錄方法。

  - **分隔作業分成每日、 每週及每月處理程序**   您定期執行的必要作業工作的文件。 記載如何執行工作，可協助確定作業環境，例如當部署新的技術變更時，會保留您資訊或人員變更就會發生。 我們建議每週及每月的操作工作可分成易於管理的工作會每日、 執行的工作負載。 每日工作而著重於系統的運作的努力，並每月工作而更著重於確保長期系統的狀況。
    
    這份文件可用在環境中部署僅限立即訊息/目前狀態 (IM/P) 元件或 IM/P 與 Enterprise Voice。 Enterprise Voice 的特定工作或檢查清單項目時，這所述，如果您的環境不包括企業語音部分可能會略過。

  - **部署所需的操作 Lync Server 2013 的工具**   許多工具可協助疑難排解問題、 自動執行工作，以及協助監視及維護的 Lync Server 2013 環境。 定義一組標準工具為您的組織，因此精確、 有效、 一致地執行作業小組所執行的工作和受控制的方式。 您也應該實作用以追蹤事件及主要組態變更的程序。

<div>

## <a name="reference"></a>參考

造福讀者不熟悉伺服器管理的基本概念一般而言，我們提供伺服器管理作法的概觀。 已經熟悉伺服器管理的讀者可能會選擇略過本節。

最佳作法是根據知識，以及體驗的 IT 專業人員獲得了許多環境之間的建議。 它們提供標準程序的一般工作，您的 Lync Server 系統管理員必須執行每日、] 和 [清單工具他們應該用來管理 Lync Server 環境。

Lync 系統管理員的一般工作包括：

  - **容量和可用性管理**   定義如何該怎麼做以預測未來容量需求的量值和容量、 可靠性和您的系統的可用性相關的報告。 您必須驗證執行 Lync Server 的伺服器的大小，以處理系統上的負載，且該意外的停機時間會保留在服務層級協議 (SLA) 中所定義的層級下。 此外，您必須升級硬體，以繼續以符合已定義的需求。

  - **變更管理和組態管理**   控制如何與 IT 系統進行變更。 這應該包括測試、 應用程式的意見反應及緊急應變計劃、 文件的所有變更，並核准管理是否發生問題。 保留記錄的軟體和硬體資產和其組態。

  - **系統管理**   大綱標準方法來執行系統管理工作，例如資料庫管理與網站管理。

  - **安全性管理**   有詳細的原則及保護資料的機密性、 資料完整性和資料可用性的 IT 基礎結構的計劃。 這包括日常活動和與維護及調整 IT 安全性基礎結構相關的工作。

  - **系統疑難排解**   大綱方法來處理未預期的問題，包括可在未來防止類似的問題的步驟。

  - **服務等級協定**   維護一組的 IT 系統的效能目標並定期測量對這些目標的效能。

  - **文件**   記錄標準程序，例如設定資訊與經驗，並使其能需要這些人員成員。 進行組態變更時，請據此更新文件。

</div>

<div>

## <a name="related-sections"></a>相關各節

檢閱關於系統作業繼續進行之前的下列主題：

  - [Lync Server 2013 中的容量和可用性管理](lync-server-2013-capacity-and-availability-management.md)

  - [Lync Server 2013 中的變更管理](lync-server-2013-change-management.md)

  - [Lync Server 2013 中設定管理](lync-server-2013-configuration-management.md)

  - [Lync Server 2013 中的系統管理](lync-server-2013-system-administration.md)

  - [Lync Server 2013 中的服務等級協定](lync-server-2013-service-level-agreements.md)

  - [Lync Server 2013 中的文件](lync-server-2013-documentation.md)

  - [Lync Server 2013 中的標準程序](lync-server-2013-standard-procedures.md)

  - [Lync Server 2013 中的緊急程序](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[Microsoft Operations Framework 4.0](http://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

