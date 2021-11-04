---
title: 商務用 Skype Server 中的詳細通話報告
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 38862e35-3fec-41b9-a035-0b301942d446
description: 摘要：瞭解商務用 Skype Server 中所用的通話詳細資料包告。
ms.openlocfilehash: 550c218d4799623359f68930286210116628b005
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767741"
---
# <a name="call-detail-report-in-skype-for-business-server"></a>商務用 Skype Server 中的詳細通話報告
 
**摘要：** 深入瞭解商務用 Skype Server 所用的通話詳細資料包告。
  
[通話詳細資料包告] 提供個別通話的詳細資訊，請參閱報告中包含幾乎所有的經驗品質統計資料，以及商務用 Skype Server 所收集的統計資料，劃分成下列報告區段：
  
- 通話資訊 
    
- 呼叫者裝置和訊號計量
    
- 被呼叫者裝置和訊號計量
    
- 呼叫者用戶端事件
    
- 被呼叫者用戶端事件
    
- 音訊資料流 (呼叫者至被呼叫者)
    
- 視訊資料流 (呼叫者至被呼叫者)
    
- 音訊資料流 (被呼叫者至呼叫者)
    
- 視訊資料流 (被呼叫者至呼叫者)
    
請注意，在指定報告上所見的類別及計量取決於兩個因素：工作階段類型，以及工作階段中所使用的端點類型。例如，純音訊通話不會報告視訊資料流計量，這是因為該通話沒有視訊資料流。同樣地，報告可能會只列出呼叫者統計資料，而沒有被呼叫者統計資料。這通常是因為被呼叫者並非使用 SIP 相容的裝置。端點會負責在通話結束時報告統計資料；不過行動電話 (對 SIP 或 SIP 統計資料一無所悉) 就無法報告該類資訊。如果您與某人通話，而他們使用行動電話接聽，則通話結束時將無法從該行動電話取得報告。
  
當您想確認指定通話為何發生媒體品質問題的確切原因時，[通話詳細資料報告] 最派得上用場。
  
## <a name="accessing-the-call-detail-report"></a>存取通話詳細資料報告

您可從下列報告中存取 [通話詳細資料報告]：
  
- 您可以按一下 [通話量] 或 [不良通話百分比] 計量，商務用 Skype Server (location-report.md 中的 [位置報告])  () 
    
- 商務用 Skype Server (summary.md 中的 [Media Quality Summary Report)  (，請按一下 [通話量] 或 [不良通話百分比] 度量值) 
    
- [商務用 Skype Server (中的媒體質量比較報表](comparison.md)，按一下[商務用 Skype Server 中的 [通話清單報告](call-list-report-0.md)]，然後按一下 [詳細資料度量) ]。
    
- [商務用 Skype Server (中的伺服器效能報告](server-performance.md)，請按一下 [通話量] 或 [不良通話百分比] 計量，) 
    
- [商務用 Skype Server (中的通話清單報告](call-list-report-0.md)，請按一下 [詳細資料] 度量) 
    
從 [通話詳細資料包告] 中，您可以按一下下列其中一個計量，[以在商務用 Skype Server 中存取裝置報告](device-report.md)：
  
- 擷取裝置
    
- 轉換裝置
    
按一下 [A/V Edge Server] 計量也可存取 [伺服器媒體品質趨勢報告]。
  
## <a name="making-the-best-use-of-the-call-detail-report"></a>發揮通話詳細資料報告的最大效用

[通話詳細資料報告] 通常涵蓋超過 250 個不同的計量，包括麥克風時間戳記漂移、低 SNR 時間及近端回音時間等項目。如果不記得這些計量實際上測量什麼，可嘗試將滑鼠移至計量標籤上，通常會顯示工具提示來說明該計量。
  
如果您找不到度量，請在搜尋方塊中輸入「度量」標籤的一部分，然後按一下 [ **尋找**]。 例如，如果您找不到 [低 SNR] 時間度量，請在搜尋方塊中輸入 SNR，然後按一下 [ **尋找**]。
  
請注意，報告只追蹤通話的相關資訊。 不會記錄通話本身。
  
## <a name="filters"></a>篩選

無。您無法篩選詳細通話報告。
  
## <a name="metrics"></a>度量

下表列出每個通話的詳細通話報告。
  
**詳細通話報告計量**

|**名稱**|**可以排序這個項目嗎？**|**描述**|
|:-----|:-----|:-----|
|**呼叫者 PAI** <br/> |否  <br/> |撥打通話之使用者的 P-Asserted-Identity。P-Asserted-Identity 可用來傳達信任網路中之使用者經驗證的身分識別。  <br/> |
|**呼叫者 URI** <br/> |否  <br/> |撥打通話之使用者的 SIP 位址。  <br/> |
|**呼叫者者端點** <br/> |否  <br/> |用來撥打通話的裝置。  <br/> |
|**呼叫者使用者代理程式** <br/> |否  <br/> |撥打通話之裝置上所使用的軟體。  <br/> |
|**通話開始** <br/> |否  <br/> |啟動通話的日期與時間。  <br/> |
|**中繼伺服器旁路通話** <br/> |否  <br/> |指出通話是連接至 PSTN 語音閘道或完整 IP-PBX，而未通過中繼伺服器。  <br/> |
|**呼叫者 OS** <br/> |否  <br/> |呼叫者電腦的作業系統。  <br/> |
|**呼叫者 CPU** <br/> |否  <br/> |安裝在啟動通話之使用者電腦上的 CPU。  <br/> |
|**呼叫者 CPU 核心編號** <br/> |否  <br/> |啟動通話者所使用電腦的處理器編號。  <br/> |
|**呼叫者 CPU 速度** <br/> |否  <br/> |啟動通話者所使用電腦的 CPU 時脈速度。  <br/> |
|**呼叫者 CPU 模擬** <br/> |否  <br/> |啟動通話者所使用電腦上的虛擬化 (若有的話)。  <br/> |
|**被呼叫者 PAI** <br/> |否  <br/> |受邀加入通話之使用者的 P-Asserted-Identity。P-Asserted-Identity 可用來傳達信任網路中之使用者經驗證的身分識別。  <br/> |
|**被呼叫者 URI** <br/> |否  <br/> |被呼叫使用者的 SIP 位址。  <br/> |
|**被呼叫者端點** <br/> |否  <br/> |用來接收通話的裝置。  <br/> |
|**被呼叫者使用者代理程式** <br/> |否  <br/> |接收通話之裝置上所使用的軟體。  <br/> |
|**Duration** <br/> |否  <br/> |通話時間長度。  <br/> |
|**媒體旁路警告旗標** <br/> |否  <br/> |略過中繼伺服器時發出的警告。  <br/> |
|**被呼叫者 OS** <br/> |否  <br/> |被呼叫使用者的電腦作業系統。  <br/> |
|**被呼叫者 CPU** <br/> |否  <br/> |安裝在被呼叫使用者電腦上的 CPU。  <br/> |
|**被呼叫者核心編號** <br/> |否  <br/> |被呼叫者所使用電腦中的處理器編號。  <br/> |
|**被呼叫者 CPU 速度** <br/> |否  <br/> |被呼叫者所使用電腦中的 CPU 時脈速度。  <br/> |
|**被呼叫者 CPU 虛擬** <br/> |否  <br/> |被呼叫者所使用電腦上的虛擬化 (若有的話)。  <br/> |
   

