---
title: Skype for Business 伺服器容量規劃小算盤
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 摘要： 如何使用容量計算器工具。
ms.openlocfilehash: 1bb1c9cde82c1f2d6e487c3bc28520b630d59210
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031077"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Skype for Business 伺服器容量規劃小算盤
 
**摘要：** 如何使用容量計算器工具。

> [!NOTE]
> 本文的參考用 Skype Server 2015 下載項目，但它適用於：
> - Skype for Business Server 2019。
> - Skype for Business Server 2015。
  
[Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196)與[Skype for Business Server 2019 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=57509)增強[Skype for Business 規劃工具](https://www.microsoft.com/download/details.aspx?id=50357)和部署文件 ([您用 Skype Server 2015 部署規劃](../plan-your-deployment/plan-your-deployment.md)及[規劃您 Skype for Business Server 2019 部署](../../SfBServer2019/plan/plan-your-deployment-2019.md)分別)。 您已檢閱快顯功能表，並使用規劃工具所建立的建議的拓撲之後，請使用 [小算盤]。
  
Skype for Business 伺服器容量計算器可協助您決定使用者數目和您的組織使用的通訊工具為基礎的伺服器需求。 您已決定您的使用者設定檔，並且想要啟用使用者的功能之後，使用 [小算盤] 來判斷伺服器、 記憶體及您需要的頻寬的數目。 此版本的計算機不提供指引磁碟 I/O 的需求。
  
您可以享有最 [小算盤] 如果您有關於您的特定使用者設定檔的精確、 詳細資訊。 例如，已啟用語音的使用者，每位使用者每小時、 通話持續期間，並在會議中並行使用者的百分比的平均通話的百分比可以讓伺服器需求極大差異。 [小算盤] 所建立的建議的準確性取決於您所提供的資訊的正確性。
  
一旦您已使用規劃工具和容量規劃小算盤，您應該模擬您建議與計劃的負載，以確保，Skype for Business Server 適當地佈建。 若要執行壓力測試模擬的負載下，使用記載在[Skype for Business Server 壓力及效能工具](https://technet.microsoft.com/library/mt631400.aspx) [Skype for Business Server 壓力及效能工具](https://www.microsoft.com/download/details.aspx?id=50367)。
  
## <a name="using-the-capacity-calculator"></a>使用容量的小算盤

小算盤] 位於 Microsoft Excel 試算表。 您輸入的儲存格被彩色橙色。 預設值輸入中的儲存格 (如商務用 Skype Server 2015，與十二個前端伺服器，如 Skype for Business Server 2019，106,000 使用者十六個前端伺服器與一個集區中的一個集區中的 80000 位使用者)，但您應該變更這些值，以符合貴組織的需求。
  
使用模型包含下列各節。 若要計算容量需求，請輸入資料所述的工作表從頂端開始，並開始向下逐列： 
  
 **立即訊息和目前狀態**
  
- [**使用者數量**] 下方輸入會一次登入的使用者數目。 此數字通常為 80%的佈建的使用者總數。 在大部分情況下，100%的並行使用者將會啟用 IM 和目前狀態。 預設值為 80000 商務用 Skype Server 2015，與 Skype for Business Server 2019 的 106,000 使用者。
    
- **在連絡人清單中的連絡人的平均數目**表示我們正在用來驗證您的系統需求的連絡人數目。 此數字固定，並不是您應該變更。
    
  **企業語音**
  
- 在**使用者啟用 Enterprise Voice**，輸入您的使用者啟用 Enterprise Voice 的百分比。 預設值為 60%。 
    
- 在**每位使用者每小時 （尖峰時） 通話的平均數目**，輸入您預期一般使用者參與的尖峰負載時段每小時來電數目。 預設值為 4。 
    
- **使用媒體旁路的通話百分比**，請輸入您將會略過中繼伺服器的使用者所撥出通話的百分比。 預設值是 65%，但無法為較低，如果您改變會展現地理位置，或具有高百分比的使用者在家工作。
    
- **語音使用者參與 UC-PSTN 通話的百分比**，請輸入貴組織的呼叫，也就是 UC-PSTN 通話的百分比。 預設值為 60%。
    
- **語音使用者參與 UC-UC 通話的百分比**顯示的使用者啟用 Enterprise Voice 會啟用僅適用於 UC-UC 通話的百分比。 此數字是根據計算您輸入**的語音使用者啟用 UC-PSTN 通話**百分比。 
    
  **會議**
  
- **並行會議中使用者的百分比**，請輸入使用者將參與會議在同一時間的百分比。 預設值為 5%。 
    
- 在**群組只 （沒有語音） IM 與會議的百分比**，輸入的立即訊息只會牽涉到，且不包含音訊會議的百分比。 預設值為 10%
    
- 在**百分比的使用者使用電話撥入式會議**，請輸入在會議中將會使用電話撥入式會議，一次的與會者百分比。 預設值為 15%。
    
- **使用語音會議的百分比**，請輸入內含音訊會議的百分比。 
    
  - 如果 20%的語音會議也會包括一般的影片，請選取 [**包括視訊 （沒有多檢視表）** ] 核取方塊。
    
  - 如果 20%的會議也會包括多重檢視視訊，選取 [**包括多檢視**] 核取方塊。
    
  - 如果您的語音會議的 50%，也會包括應用程式共用，選取 [**包括應用程式共用**] 核取方塊。
    
  - 如果語音會議中的 20%包含的資料上傳 PowerPoint 簡報，例如選取 [**包括 web 會議**] 核取方塊。
    
  **行動性**
  
- 在**啟用行動使用者的百分比**，輸入您將會連線到 Skype for Business Server 使用行動裝置啟用的使用者百分比。 預設值為 40%。 
    
當您輸入的所有必要資訊時，容量小算盤估計您的需求。 黃色的儲存格顯示 CPU、 記憶體及根據 skype for Business Server 效能實驗室執行測試的頻寬需求的計算的值。 數字所提供的指導方針，為不是每個單一的變化測試及驗證。 計算下列值： 
  
- **Front End CPU**： 如果一部前端伺服器的規格相同的伺服器，用於測試 （請參閱本文結尾處的描述） 會被處理整個負載的百分比的 CPU 使用量。
    
- **網路以 Mbps**： 在 [秒 mb (Mbps 的相對應的工作負載) 的頻寬需求。
    
- **在 [GB 的記憶體**： 在 (gb) 的相對應的工作負載所需的記憶體。
    
綠色的儲存格會顯示您所輸入的使用狀況模型的建議。 
  
- **總前端伺服器**： 所需的實體伺服器的數目取決於執行用 Skype Server 2015 與雙處理器，專用伺服器十六進位核心、 2,260 兆週，或 Skype for Business Server 2019 與 Intel Xeon E5 2673 v3、 雙處理器、 十六進位核心。
    
    請注意，啟用超執行緒，建議證明的伺服器支援音訊/視訊提升效能。
    
- **Edge Server**： 邊際伺服器的數目，根據 30%的所有同時連線的使用者透過 Edge Server 通訊所需。 在 [小算盤] 中，無法變更此百分比。 
    
- **封存/通話詳細資料錄製/品質的體驗 services 儲存區**： 所需的封存或監控功能，如果他們已啟用組織中的儲存區的數目。
    
- **後端資料庫伺服器必要 （集區所需）**： 支援的所選的工作負載所需的後端資料庫伺服器的數目。
    
此外，總前端伺服器] 旁的列，提供詳細資訊是關於您的伺服器和網路上的負載結合的所有計劃工作負載。
  
- **平均 CPU 負載**： 每個前端伺服器的平均 CPU 使用率。
    
- **網路以 Mbps**： 所需的頻寬配置，以支援您所輸入的使用狀況模型。
    
- **在 [GB 的記憶體**： 以 gb 為單位，每一部前端伺服器所需的記憶體。
    
### <a name="adjusting-for-your-processors"></a>調整您的處理器

所有在試算表中的 CPU 使用量圖表假設每個商務用 Skype Server 2015 伺服器具有雙處理器、 十六進位-核心 2.26 GHz，至少要有 32 GB 記憶體，與，而 8 或更多個 10000 RPM 硬碟磁碟機，每個至少 72 GB 可用磁碟空間。 針對每個 Skype for Business Server 2019 伺服器中，所有在試算表中的 CPU 使用量圖表假設每個伺服器有雙處理器、 十六進位雙核心 Intel Xeon E5 2673 v3，至少 64 GB 的記憶體，與，而 8 或更多個 10000 RPM 硬碟磁碟機，每個至少 72 GB 可用磁碟 s速度。
  
如果您的伺服器有不同的處理器，您可以調整數據以符合您的硬體。
  
