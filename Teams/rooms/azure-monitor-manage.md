---
title: 使用 Azure 監視器監視Microsoft Teams 會議室裝置
ms.author: dstrome
author: dstrome
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
description: 本文探討如何使用 Azure 監視器，以整合的方式監視Microsoft Teams 會議室裝置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 38238d4b1d0bc33182f002e7dcf6389028315c48
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880207"
---
# <a name="monitor-microsoft-teams-rooms-devices-with-azure-monitor"></a>使用 Azure 監視器監視Microsoft Teams 會議室裝置

本文探討如何使用 Azure 監視器，以整合的方式監視Microsoft Teams 會議室。

您可以設定 Azure 監視器以提供基本遙測，協助您監控 Microsoft Teams 會議室裝置。 如需詳細資料，請參閱[使用 Azure 監視器規劃](azure-monitor-plan.md)[Microsoft Teams 會議室管理以及使用 Azure 監視器部署Microsoft Teams 會議室管理](azure-monitor-deploy.md)。 隨著監控解決方案的成熟，您可以使用其他資料和監控功能來建立更詳細的裝置效能檢視。

## <a name="understand-the-log-entries"></a>瞭解記錄專案

當Microsoft Teams 會議室應用程式記錄 Windows 事件記錄檔中的對應資訊時，下列事件描述每五分鐘會插入事件記錄檔描述欄位。 Microsoft 監控專員將這些記錄傳遞給 Azure 監視器中的記錄分析，將它們剖析為您在[使用 Azure 監視器部署Microsoft Teams 會議室監視](azure-monitor-deploy.md)中建立的儀表板。 您可以使用儀表板查看個別的記錄專案，以視需要判斷動作的課程。

事件識別碼 2000 和 3000 表示Teams 會議室如預期般運作。 事件識別碼 2001 和 3001 表示已找到問題。 相較于您設定的比較基準或組織中其他已部署的裝置，事件識別碼 4000 可能會需要比預期更頻繁的顯示方式採取動作。

瞭解這些事件描述會快速提醒您問題，並提供進一步疑難排解的起點。

| 事件 &nbsp; 識別碼 &nbsp; 層級|事件 &nbsp; 行為&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|事件 &nbsp; 描述&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> 資訊 | 這是健康心跳事件。 每隔 5 分鐘，Microsoft Teams 會議室檢查登入 Microsoft Teams 或 商務用 Skype，並具有網路和 Exchange 連線能力。 <br> 如果這三個因素皆為 True，它會每隔 5 分鐘將事件識別碼 2000 寫入事件記錄檔，直到裝置離線或無法再符合一或多個條件為止。 | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> 在此範例中，已符合所有心跳條件，且Microsoft Teams 會議室裝置標示為健康。 如果發生錯誤，應用程式會改為錄製事件識別碼 2001。 |
| 2001  <br> 錯誤 | 這是應用程式錯誤事件。 每隔 5 分鐘，Microsoft Teams 會議室檢查已登入 Microsoft Teams 或商務用 Skype網路和 Exchange 連線能力。 如果一或多個因素不正確，它會每隔 5 分鐘將 EventID 2001 寫入事件記錄檔，直到裝置離線或再次符合所有條件為止。  | `{"Description":"Network status : Healthy. Exchange status : Connected. Sign in status: Unhealthy. Teams sign in status: Healthy.", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  在此範例中，Microsoft Teams 會議室判斷網路連線狀況良好，且應用程式已連線到 Exchange，但粗體部分表示該應用程式未連線。 這可能是裝置或主機的設定問題。  <br> <br> 網路狀態會顯示為健康或不健康。 如果狀態不健康，您可能有網路問題，或裝置可能已 (撅取，但您可能也會有 Exchange 和 Microsoft Teams，或商務用 Skype錯誤) 。  <br><br> Exchange 狀態會顯示為 [已連線] 或下列其中一項：[中斷連線]、[連線]、[自動探索] (最常見的錯誤) 、GeneralError 或 ServerVersionNotSupported。 如果狀態為 [連線]，請等到下一封健康訊息傳送出去，否則其他錯誤會將此問題提交給有解決 Exchange 問題經驗的系統管理員。  <br><br>  表示應用程式已登入商務用 Skype或 Teams 登入 _狀態_ 的 Teams 登入 _狀態_ /)  (顯示為 _健康_ 或 _不健康_。 如果狀態不健康，請傳送技術人員進一步調查。 |
| 3000  <br> 資訊 | 此事件驗證硬體檢查已執行，且發現狀況良好。 每隔 5 分鐘Microsoft Teams 會議室檢查會議室前方顯示器、麥克風、喇叭和相機等硬體元件是否已連線並運作。 如果所有元件都健康，它會將 EventID 3000 寫入事件記錄檔。 除非連線的裝置發生問題，否則此事件每 5 分鐘撰寫一次。  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> 在此範例中，已通過所有硬體檢查。 如果發生錯誤，應用程式會改為錄製事件識別碼 3001。 |
| 3001  <br> 錯誤事件  | 這是硬體錯誤事件。 Microsoft Teams 會議室應用程式有一個程式，可檢查連接硬體元件 (房間前方、麥克風、喇叭、相機) 每 5 分鐘一次的健康情況。 如果一或多個元件不健康，它會將 EventID 3001 寫入事件記錄檔。 此事件每隔 5 分鐘撰寫一次，直到裝置問題修正為止。   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>  硬體介面設備會顯示為健康或不健康。 <br> 在此範例中，已設定兩 _個前方房間_ 顯示器，目前兩個都無法使用。 _會議麥克風狀態__不健康_，可能有幾個可能的原因。 由於至少有一個資源未通過檢查，因此 ResourceState 列為「不健康」。 請派技術人員進一步調查。 |
| 4000  <br> 資訊  <br> | 這是應用程式重新開機事件。 每次重新開機應用程式時，它會將此事件記錄在 Windows 事件記錄檔中。  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> 應用程式可能會因為各種原因重新開機。 比較同一棟大樓和不同建築物中裝置的重新開機頻率。 請記住電源波動和失敗等已知問題，因為這可能會為基礎結構問題提供線索。|

## <a name="related-topics"></a>相關主題
 

[使用 Azure 監視器規劃Microsoft Teams 會議室監控](azure-monitor-plan.md)

[使用 Azure 監視器部署Microsoft Teams 會議室監視](azure-monitor-deploy.md)
