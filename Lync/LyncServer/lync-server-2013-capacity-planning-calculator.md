---
title: Lync Server 2013 容量規劃小算盤
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
ms.openlocfilehash: 0caac7e07d83658fd1b39192a6d9792ae6b17c0e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a>使用 Lync Server 2013 的容量規劃 [小算盤]

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-11-21_

Microsoft® Lync™ Server 2013 容量規劃小算盤] 位於可供下載在<https://www.microsoft.com/download/details.aspx?id=36828>。 它被設計來協助您判斷伺服器的需求，根據使用者和組織已啟用的溝通形式的數字。 您輸入您的組織設定檔]，和 [小算盤] 提供的建議，協助您規劃您的拓撲。

進行規劃時只是由 [小算盤] 所建立的建議。 實際的負載模擬，才能確保已適當地佈建 Lync Server 2013。 若要執行壓力測試模擬的負載下，使用[Lync Server 2013 壓力及效能工具](https://go.microsoft.com/fwlink/?linkid=282724)。

您已決定您的使用者設定檔，並且想要啟用您的使用者形式之後，就可以使用 [小算盤] 可規劃伺服器、 記憶體及您所需要的頻寬的數目。 此版本的計算機不提供指引磁碟 I/O 的需求。

此計算機補充[Microsoft Lync Server](https://go.microsoft.com/fwlink/?linkid=282725)和[Microsoft Lync Server](lync-server-2013-planning.md)。 您已檢閱快顯功能表，並使用規劃工具所建立的建議的拓撲之後，請使用 [小算盤]。

您可以享有最 [小算盤] 如果您有關於您的特定使用者設定檔的精確、 詳細資訊。 例如，已啟用語音的使用者，每位使用者每小時、 通話持續期間，並在會議中並行使用者的百分比的平均通話的百分比可以讓伺服器需求極大差異。 [小算盤] 所建立的建議的準確性取決於您所提供的資訊的正確性。

<div>

## <a name="using-the-capacity-calculator"></a>使用容量的小算盤

小算盤] 位於 Microsoft Excel® 試算表。 橙色無儲存格都是從您的輸入。 預設值為輸入 (80000 位使用者在與十二個前端伺服器集區中的），但您可以變更這些值，根據貴組織的需求。

使用模型包含下列各節。 若要計算容量需求，請輸入資料，如所述：

**立即訊息和目前狀態**

  - [數字的使用者] 下方輸入會同時登入的使用者數目。 此數字通常為 80%的佈建的使用者總數。 在大部分情況下，100%的並行使用者將會啟用 IM 和目前狀態。 預設值為 80000。

  - 在連絡人清單中的連絡人的平均數目表示我們正在用來驗證您的系統需求的連絡人數目。 此數字不是可變更。

**企業語音**

  - 在啟用 Enterprise Voice 的使用者，請輸入您的使用者啟用 Enterprise voice 的百分比。 預設值為 60%。

  - 在每位使用者每小時 （尖峰時） 通話的平均數目，輸入您預期一般使用者參與的尖峰負載時段每小時來電數目。 預設值為 4。

  - 在使用媒體的通話百分比略過，輸入您將會略過中繼伺服器的使用者所撥出通話的百分比。 預設值是 65%。

  - 在語音使用者參與 UC-PSTN 通話的百分比，輸入也就是 UC-PSTN 通話貴組織的通話百分比。 預設值為 60%

  - 在語音使用者參與 UC-UC 通話的百分比顯示的使用者啟用 Enterprise Voice 會啟用僅適用於 UC-UC 通話的百分比。 此數字是根據計算您輸入的語音使用者啟用 UC-PSTN 通話百分比。

**會議**

  - 並行會議中的使用者百分比，輸入將會同時參與會議的使用者百分比。 預設值為 5%。

  - 在 [群組只 （沒有語音） IM 與會議的百分比，輸入的會議的會議，包括立即訊息僅限主動百分比亦即，不包含音訊的元件。 預設值為 10%

  - 使用電話撥入式會議的使用者百分比，請輸入並行參與者在會議中將會使用電話撥入式會議的百分比。 預設值為 15%。

  - 在使用語音會議的百分比，輸入將會包含音訊元件的會議的百分比。
    
      - 如果 20%的語音會議也會包括一般的影片，選取 [包含視訊 （沒有多檢視） 核取方塊。
    
      - 如果 20%的會議也會包括多重檢視視訊，選取 [包括多檢視] 核取方塊。
    
      - 如果您的語音會議的 50%，也會包括應用程式共用，選取包含應用程式共用] 核取方塊。
    
      - 如果語音會議中的 20%包含的資料上傳，例如 Microsoft PowerPoint® 簡報中，選取包含 web 會議] 核取方塊。

**行動性**

  - 在啟用行動使用者的百分比，輸入您將會連線至 Lync Server 使用行動裝置啟用的使用者百分比。 預設值為 40%。

當您輸入的所有必要資訊時，容量小算盤估計您的需求。 黃色的儲存格顯示 CPU、 記憶體和執行 Lync Server 2013 效能實驗室中測試為基礎的頻寬需求的計算的值。 數字所提供的指導方針，為不是每個單一的變化測試及驗證。 計算下列值：

  - Front End CPU： 如果整個負載正在處理一個前端伺服器的規格相同的伺服器所用的 CPU 使用率百分比 Microsoft 測試。

  - 網路以 Mbps： 在 [秒 mb (Mbps 的相對應的工作負載) 的頻寬需求。

  - 在 [GB 的記憶體： 在 (gb) 的相對應的工作負載所需的記憶體。

綠色的儲存格會顯示您所輸入的使用狀況模型的建議。

  - 前端伺服器總數： 所需的實體伺服器的數目取決於雙處理器，以執行 Lync Server 2013 的專用伺服器十六進位雙核心，2,260 兆週。

  - 請注意，啟用超執行緒，建議證明的伺服器支援音訊/視訊提升效能。

  - Edge Server: Edge Server 數目有需要，根據 30%的所有同時連線的使用者透過 Edge Server 進行通訊。 在 [小算盤] 中，無法變更此百分比。

  - 封存/通話詳細記錄/經驗品質 services 儲存區： 所需的封存或監控功能，如果他們已啟用組織中的儲存區的數目。

  - 後端資料庫伺服器所需 （集區所需）： 的後端資料庫支援的所選的工作負載所需的伺服器。

此外，總前端伺服器] 旁的列，提供詳細資訊是關於您的伺服器和網路上的負載結合的所有計劃工作負載。

  - 平均 CPU 負載： 平均 CPU 使用率每部前端伺服器。

  - 網路以 Mbps： 所需的頻寬配置，以支援您所輸入的使用狀況模型。

  - 在 [GB 的記憶體： 以 gb 為單位，每一部前端伺服器所需的記憶體。

</div>

<div>

## <a name="adjusting-for-your-processors"></a>調整您的處理器

所有在試算表中的 CPU 使用量圖表假設每部伺服器具有雙處理器、 十六進位-核心 2.26 GHz，至少要有 32 GB 記憶體，與，而 8 或更多個 10000 RPM 硬碟磁碟機，每個至少 72 GB 可用磁碟空間。

如果您的伺服器有不同的處理器，您可以調整數據以符合您的硬體。

</div>

</div>

<span> </span>

</div>

</div>

</div>

