---
title: 使用 azure 監視器Microsoft Teams 會議室監控裝置
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
description: 本文討論如何使用 Azure 監視器Microsoft Teams 會議室整合的方式監控裝置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a19a6be8f48bedca228457f7e5c2c85be1ef8374
ms.sourcegitcommit: b878c57b8e822913b7aac8c105f476bc4ebfcd7d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2022
ms.locfileid: "63761897"
---
# <a name="monitor-microsoft-teams-rooms-devices-with-azure-monitor"></a>使用 azure 監視器Microsoft Teams 會議室監控裝置

本文討論如何使用 Azure 監視器Microsoft Teams 會議室以整合方式監控資料。

您可以將 Azure 監視器設定為提供基本遙測，以Microsoft Teams會議室裝置。 請參閱[規劃Microsoft Teams 會議室 Azure 監視器](azure-monitor-plan.md)進行管理，以及使用[Azure 監視器Microsoft Teams 會議室部署管理](azure-monitor-deploy.md)，以瞭解詳細資料。 隨著監控解決方案的成熟，您可以使用額外的資料和監控功能，建立更詳細的裝置績效視圖。

## <a name="understand-the-log-entries"></a>瞭解記錄專案

下列事件描述會每隔五分鐘插入事件記錄描述欄位，當 Microsoft Teams 會議室 應用程式在 Windows記錄中記錄對應資訊時。 系統Microsoft Monitoring Agent這些記錄至 Azure 監視器中的記錄分析，將記錄剖析到您使用 Azure 監視器部署Microsoft Teams 會議室[監控所建立儀表板](azure-monitor-deploy.md)。 有了儀表板，您可以查看個別的記錄專案，以判斷動作路線 。如果需要的話。

事件 ID 2000 和 3000 表示Teams 會議室如預期工作。 事件 2001 和 3001 表示找到問題。 如果事件識別碼 4000 比您設定比較基準或組織中其他已部署裝置看到的結果超過預期，可能需要採取動作。

瞭解這些事件描述可快速提醒您問題，並提供進一步疑難排解的起點。

| EventIDlevel &nbsp; &nbsp;|Eventbehavior &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|EventDescription &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> 資訊 | 這是正常的心跳事件。 每隔 5 分鐘，Microsoft Teams 會議室檢查是否已Microsoft Teams或商務用 Skype網路Exchange連接。 <br> 如果所有 3 個要素都成立，它會每隔 5 分鐘將事件識別碼 2000 寫入事件記錄，直到裝置離線或一或多個條件不再符合。 | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> 在此範例中，所有心跳條件都符合，Microsoft Teams 會議室裝置標示為正常。 如果發生錯誤，應用程式會改為記錄事件識別碼 2001。 |
| 2001  <br> 錯誤 | 這是應用程式錯誤事件。 每隔 5 分鐘，Microsoft Teams 會議室檢查是否以網路Microsoft Teams或商務用 Skype網路Exchange登錄。 如果一或多個因素不成立，它會每隔 5 分鐘將 EventID 2001 寫入事件記錄，直到裝置離線或再次符合所有條件。  | `{"Description":"Network status : Healthy. Exchange status : Connected. Signin status: Unhealthy. Teams Signin status: Healthy.", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  在此範例中，Microsoft Teams 會議室確定網路連接正常，且應用程式已連接到 Exchange，但粗體部分表示 App 未連接。 這可能是裝置或主機上的組組問題。  <br> <br> 網路狀態會顯示為健康狀態或不正常狀態。 如果狀態不健康，表示您可能有網路問題，或裝置可能已經拔除 (但您也可能有 Exchange Microsoft Teams 或 商務用 Skype 錯誤) 。  <br><br> Exchange狀態會顯示為已連接或下列其中一項：已中斷連接、正在連接、自動探索Error (最常見的錯誤) 、GeneralError 或 ServerVersionNotSupported。 如果狀態為正在連接，請等到下一個健康情況訊息被送出，因為其他錯誤會將問題參照到具有解決問題經驗的系統管理員Exchange問題。  <br><br>  表示 _應用程式已_ / Teams狀態 (登錄狀態) 顯示為健康狀態或不 _健康_ 狀態。__  如果狀態不健康，請傳送技術人員進一步調查。 |
| 3000  <br> 資訊 | 此事件會驗證已執行硬體檢查，併發現狀態正常。 每隔 5 分鐘Microsoft Teams 會議室檢查會議室顯示器、麥克風、喇叭和相機等已配置的硬體元件是否已連接及運作。 如果所有元件都正常，它會將 EventID 3000 寫入事件記錄。 除非已連接裝置發生問題，否則此事件會每 5 分鐘撰寫一次。  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> 在此範例中，所有硬體檢查都通過。 如果發生錯誤，應用程式會改為記錄事件識別碼 3001。 |
| 3001  <br> 錯誤事件  | 這是硬體錯誤事件。 Microsoft Teams 會議室應用程式有一個程式，每 5 分鐘檢查 (、麥克風、喇叭、相機) 連接硬體元件的健康狀態。 如果一或多個元件不健康，它會將 EventID 3001 寫入事件記錄。 此事件會每隔 5 分鐘撰寫一次，直到裝置問題修正。   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>  硬體周邊設備會顯示為健康或不健康。 <br> 在此範例中，會議室前方有兩個已配置的顯示器，目前兩者均無法使用。 會議 _麥克風狀態_ 不正常 _，_ 可能有幾個可能的原因。 由於至少有一個資源未通過檢查，因此 ResourceState 會列為不健康狀態。 傳送技術人員進一步調查。 |
| 4000  <br> 資訊  <br> | 這是 App 重新開機事件。 每次重新開機應用程式時，它會將此事件記錄到 Windows記錄中。  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> 應用程式可能會因為各種原因重新開機。 比較同一棟大樓和不同建築物中的裝置重新開機頻率。 請記住電源波動和失敗等已知問題，因為這可能提供基礎結構問題的線索。|

## <a name="related-topics"></a>相關主題
 

[使用 azure 監視器Microsoft Teams 會議室監控](azure-monitor-plan.md)

[使用 azure 監視器Microsoft Teams 會議室部署監控](azure-monitor-deploy.md)
