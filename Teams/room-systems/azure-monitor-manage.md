---
title: 使用 Azure 監視器管理 Microsoft 團隊聊天室裝置
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection: M365-voice
description: 本文將說明如何使用 Azure 監視器, 以整合、端到端的方式來管理 Microsoft 團隊聊天室裝置。
ms.openlocfilehash: 3a317796a4fe79dfec70d2c8c33c59ddccba6a05
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36182487"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a>使用 Azure 監視器管理 Microsoft 團隊聊天室裝置

本文將說明如何使用 Azure 監視器, 以整合、端到端的方式來管理 Microsoft 團隊聊天室裝置。

您可以設定 [Azure 監視器], 以提供可協助您管理 Skype 會議室裝置的基本遙測 (請參閱[使用 Azure 監視器規劃 Microsoft 團隊聊天室管理](azure-monitor-plan.md), 並[使用 Azure 監視器部署 microsoft 團隊聊天室管理]((azure-monitor-deploy.md) for details))。 隨著您的管理解決方案逐漸成熟, 您可以使用其他資料和管理功能來建立更詳細的裝置效能視圖。

## <a name="understand-the-log-entries"></a>瞭解記錄專案

當 Microsoft 團隊聊天室應用程式在 Windows 事件記錄檔中記錄對應的資訊時, 每隔五分鐘, 就會將下列事件描述插入到 [事件記錄檔描述] 欄位中。 Microsoft Monitoring Agent 會將這些記錄傳遞到 Azure 監視器中的記錄分析, 這會將這些記錄解析成您在[使用 Azure 監視器部署 Microsoft 團隊聊天室管理](azure-monitor-deploy.md)中所建立的儀表板。 使用儀表板, 您可以查看個別記錄專案, 視需要決定動作的課程。 

事件識別碼2000和3000指出問題的裝置正常運作。 事件識別碼2001和3001指出發現問題。 與您所設定的比較基準或貴組織中其他部署的裝置相比, 事件 ID 4000 可能需要採取動作。

瞭解這些事件描述會立即提醒您問題, 並為進一步的疑難排解提供起點。

| 事件&nbsp;識別碼&nbsp;層級|事件&nbsp;行為&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|事件&nbsp;描述&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> 錯誤資訊 | 這是正常的心跳事件。 每5分鐘, Microsoft [小組聊天室] 都會檢查其是否已登入 Microsoft 團隊或商務用 Skype, 且具有網路和 Exchange 連線能力。 <br> 如果所有3個要素皆為 true, 則會將事件 ID 2000 在事件日誌中每隔5分鐘寫入一次, 直到裝置離線或已不再滿足一或多個條件為止。 | {"描述": "心跳為健康情況。", "ResourceState": "健康情況", "OperationResult": "Pass", "10.0.14393.693", "別名": "Alias @contoso .com", "DisplayName": "Alias<span></span>.com", "DisplayName": "name:" 顯示名稱"," AppVersion ":" 1.0.38.0 "," IPv4Address ":" 10.10.10.10 "," IPv6Address ":" IP v6 address "} <br><br> 在這個範例中, 已滿足所有的心跳條件, 且 Microsoft 團隊聊天室裝置標示為正常狀態。 如果發生錯誤, 應用程式會改為記錄事件 ID 2001。 |
| 2001  <br> 出錯 | 這是應用程式錯誤事件。 Microsoft 球隊聊天室會每隔5分鐘檢查其是否已登入 Microsoft 團隊或使用網路和 Exchange 連線的商務用 Skype。 如果有一個或多個因素不是 true, 則會將 EventID 2001 在事件日誌中的每5分鐘寫入一次, 直到裝置離線, 或所有條件都能再次符合為止。  | {「描述」:」網路狀態: 健康。 Exchange 狀態: 已連線。 **登出狀態: 不正常。** "," ResourceState ":" 不健康 "," OperationName ":" 心跳 "," OperationResult ":" 失敗 "," OS ":" Windows 10 "," OSVersion ":" 10.0.14393.693 "," 別名 ":" "," DisplayName ":" [顯示名稱], "1.0.38.0": "IPv4Address", "IPv6Address ":" ip v6 位址 "} <br><br>  在這個範例中, Microsoft 球隊聊天室決定網路連線正常運作, 且 app 已連線到 Exchange, 但粗體部分指示該 app 未連線至商務用 Skype。 這可能是裝置或主機上的配置問題。  <br> <br> 網路狀態將會顯示為 [健康] 或 [不正常]。 如果狀態不正常, 可能是網路問題或裝置已被拔出 (但您可能還需要 Exchange 與 Microsoft 團隊或商務用 Skype 錯誤)。  <br><br> Exchange 狀態會顯示為 [已連接] 或下列其中一個: [已中斷連線]、[連線]、[AutodiscoveryError] (最常見的錯誤)、[GeneralError] 或 [ServerVersionNotSupported]。 如果狀態是 [連線], 請等到傳送下一個健康情況訊息為止, 否則其他錯誤, 請參閱解決 Exchange 問題之系統管理員的問題。  <br><br>  登入狀態 (指出 app 已登入商務用 Skype) 會顯示為 [健康] 或 [不健康]。 如果狀態不正常, 請傳送一個技術人員來進一步調查。 |
| 3000  <br> 錯誤資訊 | 這個事件會驗證硬體檢查是否已執行併發現正常。 Microsoft 團隊聊天室會每隔5分鐘檢查已設定的硬體元件 (例如會議室顯示、麥克風、喇叭及攝影機), 並已連接並運作。 如果所有元件都健康, 它會將 EventID 3000 寫入事件記錄檔。 除非連線的裝置出現問題, 否則這個事件將會繼續每5分鐘寫入一次。  <br> | {"描述": "HardwareCheckEngine 是健全的功能。", "ResourceState": "", "OperationName": "HardwareCheckEngine", "OperationResult": "Pass", "OS": "Windows 10", "OSVersion": "10.0.14393.693", "別名":<span></span>"alias @contoso .com", "DisplayName ":" 顯示名稱 "," AppVersion ":" 1.0.38.0 "," IPv4Address ":" 10.10.10.10 "," IPv6Address ":" ip v6 address "}  <br><br> 在這個範例中, 所有硬體檢查都已過。 如果發生錯誤, 應用程式會改為記錄事件 ID 3001。 |
| 3001  <br> 錯誤事件  | 這是硬體錯誤事件。 Microsoft [小組聊天室] app 有一個程式, 可檢查已連接之硬體元件 (房間、麥克風、喇叭、相機) 的健康情況 (每隔5分鐘)。 如果一或多個元件不健全, 它會將 EventID 3001 寫入事件記錄檔。 這個事件將在5分鐘後持續寫入, 直到修正裝置問題為止。   | {「描述」:」**會議室的正面顯示狀態: 不正常。** 已設定顯示計數為2。 實際顯示數目為0。 **會議麥克風狀態: 不正常。** 會議演講者狀態: 健康情況。 預設演講者狀態: 健康情況。 相機狀態: [完好]。 "," ResourceState ":" 不健康 "," OperationName ":" HardwareCheckEngine "," OperationResult ":" 失敗 "," OS ":" Windows 10 "," OSVersion ":" 10.0.14393.1198 "," "Alias<span></span>": "alias @contoso .com", "DisplayName": "Yosemite會議室 "," AppVersion ":" 2.0.58.0 "," IPv4Address ":" 10.10.10.10 "," IPv6Address ":" IPv6Address "," IPv4Address2 ":" 10.10.10.10 "," ":" "} <br><br>  硬體外設顯示為 [健康] 或 [不健康]。 <br> 在這個範例中, 有兩個房間的會議室顯示為已設定, 目前都不提供。 會議麥克風狀態不健康, 可能有許多可能的原因。 因為至少有一個資源沒有通過檢查, 所以 ResourceState 會列為不正常。 傳送技術人員來進一步調查。 |
| 4000  <br> 錯誤資訊  <br> | 這是應用程式重新開機事件。 每次重新開機應用程式時, 都會將這個事件記錄到 Windows 事件記錄檔。  <br> | {"描述": "應用程式重新開機.", "ResourceState": "Restart", "OperationResult": "Pass", "OS": "Windows 10", "OSVersion": "10.0.14393.693", "別名": "Alias<span></span>@domain .com", "DisplayName": "顯示名稱", "AppVersion ":" 1.0.38.0 "," IPv4Address ":" 10.10.10.10 "," IPv6Address ":" ip v6 address "} <br><br> 應用程式可能會因各種原因重新開機。 比較同一建築物和不同建築物中裝置的重啟頻率, 請記住諸如電源波動與失敗等已知問題, 因為這可能會提供基礎結構問題的線索。|

## <a name="see-also"></a>另請參閱
 

[使用 Azure 監視器規劃 Microsoft 團隊聊天室管理](azure-monitor-plan.md)

[使用 Azure 監視器部署 Microsoft 團隊聊天室管理](azure-monitor-deploy.md)
