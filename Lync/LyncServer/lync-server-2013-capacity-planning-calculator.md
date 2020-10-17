---
title: Lync Server 2013 容量規劃計算機
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 230b731bf7b63a1ce86b5652d9e3d3b2956c94a3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512820"
---
# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a>使用 Lync Server 2013 的容量規劃計算機

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-21_

Microsoft® Lync™ Server 2013 容量規劃計算機可于下載 <https://www.microsoft.com/download/details.aspx?id=36828> 。 其設計目的是為了協助您根據組織中啟用的使用者數目和通訊形式來判斷伺服器需求。 您可以輸入組織的設定檔，而計算機會提供建議，以協助您規劃拓撲。

計算機所建立的建議只用于規劃目的。 需要實際的負載模擬，以確保已適當布建 Lync Server 2013。 若要在模擬負載下執行壓力測試，請使用 [Lync Server 2013 壓力和效能工具](https://go.microsoft.com/fwlink/?linkid=282724)。

在您決定要為使用者啟用的使用者設定檔和形式之後，就可以使用計算機來規劃所需的伺服器、記憶體及頻寬數目。 此版本的計算機不會提供磁片 I/O 需求的指導方針。

此計算機會對 [Microsoft Lync server](https://go.microsoft.com/fwlink/?linkid=282725) 和 [microsoft lync server](lync-server-2013-planning.md)進行補充。 在您複習指南並使用規劃工具建立建議的拓撲之後，使用計算機。

如果您有特定使用者設定檔的確切詳細資訊，您可以從計算機獲得最大益處。 例如，啟用語音功能的使用者數目、每位使用者每小時平均通話量、通話持續時間，以及會議中並行使用者的百分比，都可能會對伺服器的需求造成極大的影響。 計算機所建立之建議的準確性取決於您提供的資訊準確性。

<div>

## <a name="using-the-capacity-calculator"></a>使用容量計算機

計算機是 Microsoft Excel®試算表。 橙色-彩色儲存格供您輸入。 預設值是在具有十二部前端伺服器的一個集區中輸入 (80000 使用者) ，但是您可以根據組織的需求變更這些值。

使用模型包含下列章節。 若要計算您的容量需求，請輸入資料，如下所述：

**立即訊息與顯示狀態**

  - 在 [使用者數目] 底下，輸入將同時登入的使用者數目。 此數位通常是布建使用者總數的80%。 在大多數情況下，會為您的並行使用者啟用100% 的 IM 和目前狀態。 預設值為80000。

  - 連絡人清單中的連絡人數目平均會指出我們所用的連絡人數目，以驗證您的系統需求。 此數位不會改變。

**企業語音**

  - 在 [已啟用企業語音的使用者] 中，輸入已啟用 Enterprise Voice 的使用者百分比。 預設值為60%。

  - 在 [每位使用者每小時平均通話數目] (峰值) 中，輸入您預期平均使用者在高峰時負載的期間內每小時所要加入的通話數目。 預設值為4。

  - 在使用媒體旁路的通話百分比中，輸入您的使用者所撥打的呼叫百分比，將會略過轉送伺服器。 預設值為65%。

  - 在 UC-PSTN 通話的語音使用者百分比中，輸入您組織通話的百分比 UC-PSTN 電話。 預設值為60%

  - 在 UC-UC 通話的語音使用者百分比中，會顯示已啟用 Enterprise Voice 之使用者的百分比，只適用于 UC-UC 通話。 這個數位是根據您為 UC-PSTN 通話啟用之語音使用者百分比所輸入的專案而計算。

**會議**

  - 在 [同時會議的使用者百分比] 中，輸入將同時參與會議的使用者百分比。 預設值為5%。

  - 在 [僅限群組 IM 的會議百分比 (無語音) ] 中，輸入其會議只會涉及立即訊息的會議百分比;也就是說，不包含音訊元件。 預設值為10%

  - 在使用電話撥入式會議的使用者百分比中，輸入要使用電話撥入式會議的會議中，同時參與者所占的百分比。 預設值為15%。

  - 在 [使用語音的會議百分比] 中，輸入要包含音訊元件的會議百分比。
    
      - 如果20% 的語音會議也會包含一般影片，請選取 [包含影片 (沒有多重查看) ] 核取方塊。
    
      - 如果20% 的會議也會包含多個 View 影片，請選取 [包含多重查看] 核取方塊。
    
      - 如果50% 的語音會議也會包含應用程式共用，請選取 [包括應用程式共用] 核取方塊。
    
      - 如果20% 的語音會議包含資料上傳，例如 Microsoft PowerPoint®簡報，請選取 [包含 web 會議] 核取方塊。

**行動性**

  - 在 [啟用行動的使用者百分比] 中，輸入使用行動裝置啟用以連線至 Lync Server 之使用者的百分比。 預設值為40%。

當您輸入所有必要資訊之後，容量計算機會估計您的需求。 黃色儲存格會根據 Lync Server 2013 效能實驗室中所執行的測試，顯示 CPU、記憶體及頻寬需求的計算值。 這些數位是以指導方針提供，並非每個單一變化都會經過測試及驗證。 計算下列值：

  - 前端 CPU：如果整個負載都是由一個前端伺服器處理，而不是與 Microsoft 測試中所用伺服器的規格相同，則為 CPU 使用量的百分比。

  - 網路（以 Mbps 為單位）：相對於工作負載 (Mbps) 的頻寬需求（以 mb 為單位）。

  - 記憶體單位為 GB：在對應工作量的 gb (GB) 中需要的記憶體。

綠色儲存格會顯示您輸入的使用模式建議。

  - 前端伺服器總數：所需的物理伺服器數目是以執行 Lync Server 2013 的專用伺服器為基礎，具有雙處理器，hex 核心，含2260兆周期。

  - 請注意，建議啟用超執行緒，並已驗證，以提升支援音訊/視頻之伺服器的效能。

  - Edge Server：所需的 Edge Server 數目，取決於所有同時使用者透過 Edge Server 進行通訊的使用者的30%。 計算機中無法變更此百分比。

  - 封存/通話詳細資料記錄/經驗品質服務存放區：封存或監控功能所需的儲存區數目（如果在您的組織中已啟用）。

  - 需要 (集區所需的後端資料庫伺服器) ：支援所選工作負載所需的後端資料庫伺服器數目。

此外，在前端伺服器總數的最後一列中，會提供更多關於伺服器和網路上的負載的資訊，以結合所有計劃的工作負載。

  - 平均 CPU 負載：每個前端伺服器的平均 CPU 使用量。

  - 網路（以 Mbps 為單位）：支援您輸入的使用模式所需的頻寬配置。

  - 記憶體單位為 GB：每一部前端伺服器所需的記憶體（gb）。

</div>

<div>

## <a name="adjusting-for-your-processors"></a>調整您的處理器

試算表中的所有 CPU 使用量圖假設每一部伺服器都有雙處理器、hex 核心和 2.26 GHz，至少 32 GB 的記憶體，以及8個或更多的 10000 RPM 硬碟，至少有 72 GB 的可用磁碟空間。

如果您的伺服器具有不同的處理器，您可以調整這些圖形，使其符合您的硬體。

</div>

</div>

<span> </span>

</div>

</div>

</div>

