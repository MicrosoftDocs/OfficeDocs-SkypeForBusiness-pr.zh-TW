---
title: Lync Server 2013： Lync Server 環境的最佳做法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00dbbf95990875b8366ce5a03f1d2d70e6652828
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-lync-server-2013-environments"></a>Lync Server 2013 環境的最佳做法

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-08-04_

下列一般原則適用于您系統的日常作業：

  - **瞭解並利用 MOF**   mof 是最佳做法、原則和模型的集合，這些方案提供組織有關 IT 資產管理的技術指導方針，例如每日 Lync Server 2013 作業。 下列 MOF 指導方針可協助您達到 Microsoft 產品的任務關鍵型生產系統可靠性、可用性、支援及可管理性。 如需詳細資訊，請參閱[Microsoft Operations Framework 4.0](http://go.microsoft.com/fwlink/p/?linkid=40939)。

  - **瞭解 Lync server 2013**   的最佳做法我們建議您執行實用且切實可行的程式來管理 Lync server 2013。 使用已嘗試、經過測試且已記錄的管理作業方法，可能會比開發自己的方法更有效率。

  - **將作業分為每日、每週及每月處理**   程式記錄您定期執行的工作所需的作業。 記錄您執行工作的方式，以協助確保當您的操作環境（例如部署新技術或員工變更）發生變更時，系統會保留您的資訊。 我們建議您將作業工作分成每天、每週及每月工作，以易於管理的工作負載進行。 每日工作都將重點放在系統的運作中，而且每月工作都將重點放在確保系統長期健康情況。
    
    這份檔可在僅部署立即訊息/目前狀態（IM/P）元件或使用企業語音的 IM/P 的環境中使用。 如果工作或檢查清單專案是企業語音所特有的，則會提及此情況，如果您的環境不包含企業語音，可能會略過該部分。

  - **部署操作 Lync Server 2013**   所需的工具有許多工具可協助您排查問題、自動化工作，以及協助監視及維護 Lync Server 2013 環境。 為您的組織定義一組標準的工具，讓由操作小組所執行的工作以正確、高效且一致的方式執行，並以可控的方式進行。 您也應該執行處理常式來追蹤事件和主要設定變更。

<div>

## <a name="reference"></a>參考

如需閱讀者對伺服器管理基礎知識的好處，我們提供伺服器管理做法的概覽。 讀者已熟悉伺服器管理，可能會選擇略過本節。

最佳做法是根據 IT 專業人員在許多環境中取得的知識和經驗來提供的建議。 它們提供您的 Lync Server 管理員每天必須執行之一般工作的標準程式，並列出他們應該用來管理 Lync Server 環境的工具。

Lync 系統管理員的一般工作包括下列專案：

  - **容量及可用性管理**   定義如何以及測量未來容量需求的方式，以及報告系統的容量、可靠性及可用性。 您必須確認執行 Lync Server 的伺服器已調整大小，以處理系統上的負載，而且未計畫的停機時間會保留在服務等級協定（SLA）中定義的等級底下。 此外，您必須升級硬體，才能繼續滿足已定義的需求。

  - **變更管理和設定管理**   控制對 IT 系統所做的變更。 這應該包括測試、應用程式意見反應與應急規劃、記錄所有變更，以及在問題發生時的管理核准。 記錄您的軟體和硬體資產及其設定。

  - **系統管理**   概述執行管理工作（例如資料庫管理和網站管理）的標準方法。

  - **安全性管理**   有一個詳細的原則和規劃，可保護 IT 基礎結構的資料機密性、資料完整性，以及資料的可用性。 這包括與維護和調整 IT 安全基礎結構相關的日常活動和工作。

  - **系統疑難排解**   大綱方法，以處理意外問題，包括避免未來的類似問題的步驟。

  - **服務層級協定**   針對 IT 系統效能維護一組目標，並定期針對這些目標評估效能。

  - **檔**   檔標準程式，例如配置資訊和吸取的經驗，並讓他們能供需要他們的員工成員使用。 變更設定之後，請據此更新檔。

</div>

<div>

## <a name="related-sections"></a>相關各節

繼續進行之前，請先複習下列有關系統操作的主題：

  - [Lync Server 2013 的容量及可用性管理](lync-server-2013-capacity-and-availability-management.md)

  - [Lync Server 2013 中的變更管理](lync-server-2013-change-management.md)

  - [Lync Server 2013 中的建構管理](lync-server-2013-configuration-management.md)

  - [Lync Server 2013 中的系統管理](lync-server-2013-system-administration.md)

  - [Lync Server 2013 中的服務等級協定](lync-server-2013-service-level-agreements.md)

  - [Lync Server 2013 中的檔](lync-server-2013-documentation.md)

  - [Lync Server 2013 中的標準程式](lync-server-2013-standard-procedures.md)

  - [Lync Server 2013 中的急診程式](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a>請參閱


[Microsoft Operations Framework 4。0](http://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

