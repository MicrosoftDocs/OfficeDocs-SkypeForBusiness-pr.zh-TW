---
title: 監視和疑難排解直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何監控和疑難排解直接路由組組，包括會話邊界控制器、直接路由元件和電信主幹。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 97bc8afb3645fca4e06b859b765dfbf1e3fe1859
ms.sourcegitcommit: 279ab5236431961c5181e2c01a69e5aa4290d381
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2021
ms.locfileid: "60462317"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>監視和疑難排解直接路由

本文將說明如何監控和疑難排解您的直接路由配置。 

使用直接路由撥打和接聽電話的能力涉及下列元件： 

- 會話邊界控制器 (SBC)  
- Microsoft Cloud 中的直接路由元件 
- 電信主幹 

如果您有疑難排解問題，您可以向 SBC 廠商或 Microsoft 開啟支援案例。 

Microsoft 正在努力提供更多疑難排解和監控工具。 請定期檢查檔以尋找更新。 

## <a name="direct-routing-diagnostic-tool"></a>直接路由診斷工具

如果您是系統管理員，您可以使用下列診斷工具來驗證使用者已正確為直接路由進行配置：

1. 選取 **下方的執行** 測試，以在 Microsoft 365 系統管理中填入診斷。 

   > [!div class="nextstepaction"]
   > [執行測試：直接路由](https://aka.ms/TeamsDirectRoutingDiag)

2. 在執行診斷窗格中，在使用者名稱或電子郵件欄位中輸入要測試的使用者電子郵件，然後選取執行 **測試**。

3. 測試會返回解決任何租使用者、使用者或策略組組的最佳下一個步驟，以驗證使用者已正確針對 Microsoft Teams 中的直接路由進行Microsoft Teams。

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>使用會話初始通訊協定監控會話邊界控制器的可用性 (SIP) 選項訊息

直接路由使用會話邊界控制器傳送的 SIP 選項來監控 SBC 健康情況。 租使用者系統管理員不需要執行任何動作來啟用 SIP 選項監控。 在做出路由決策時，會考慮收集的資訊。 

例如，如果針對特定使用者，有幾個 SBC 可以路由通話，則直接路由會考慮從每個 SBC 收到的 SIP 選項資訊，以決定路由。 

下圖顯示組組範例： 

![SIP 選項群組組範例。](media/sip-options-config-example.png)

當使用者撥打號碼 +1 425 \<any seven digits> 時，直接路由會評估路由。 路由中共有兩個 SBC：sbc1.contoso.com 和 sbc2.contoso.com。 這兩個 SBC 在路由中具有相等的優先順序。 挑選 SBC 之前，路由機制會根據 SBC 上次傳送 SIP 選項的時間，評估 SBC 的健康情況。 

如果傳送通話時的統計資料顯示 SBC 每分鐘傳送選項，則 SBC 會被視為健康狀態。  

進行通話時，會採用下列邏輯：

- SBC 在上午 11：00 配對。  
- SBC 會于上午 11：01、上午 11：02 等傳送選項。  
- 在 11：15，使用者進行通話，而路由機制會選取此 SBC。 

直接路由會採用三次一般間隔選項 (而一般間隔為一分鐘) 。 如果選項是在過去三分鐘內傳送，則 SBC 會視為健康狀態。

如果範例中的 SBC 在上午 11：12 到上午 11：15 (通話時間) 之間，會被視為健康狀態。 如果沒有，SBC 將會從路由降級。 

降級表示不會先試用 SBC。 例如，我們有一 sbc1.contoso.com sbc2.contoso.com 優先順序。  

如果 sbc1.contoso.com 未如先前所述定期傳送 SIP 選項，系統即會降級。 接下來，sbc2.contoso.com 通話。 如果 sbc2.contoso.con 無法傳遞通話，系統 sbc1.contoso.com (降級) ，然後再產生失敗。 

如果 (一個路由) 兩個或多個 SBC 視為健康且相等，Fisher-Yates隨機播放會用於在 SBCs 之間分配通話。

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>監控通話品質分析儀表板和 SBC 記錄 
 
在某些情況下，尤其是在初始配對期間，SBCs 或直接路由服務可能發生配置錯誤的問題。 

您可以使用下列工具來監控您的組組：  
 
- 通話品質儀表板 
- SBC 記錄 

直接路由服務有非常描述性的錯誤碼，會報告給通話分析或 SBC 記錄。 

通話品質儀表板提供有關通話品質和可靠性的資訊。 若要深入瞭解如何使用通話分析疑難排解問題，請參閱開啟並使用[Microsoft Teams](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard)和 商務用 Skype Online 的通話品質儀表板，以及使用通話分析來疑難排解通話品質不佳[的問題](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)。 

如果通話失敗，通話分析會提供標準 SIP 代碼，可協助進行疑難排解。 

![通話失敗範例 SIP 代碼。](media/failed-response-code.png)

不過，通話分析只有在通話到達直接路由的內部元件並失敗時，才能有所説明。 如果 SBC 配對發生問題，或 SIP"Invite" 遭到拒絕的問題 (例如，主幹 FQDN 的名稱未正確) ，通話分析將無法解決問題。 在此案例中，請參閱 SBC 記錄。 直接路由會傳送問題的詳細描述給 SBC;這些問題可以從 SBC 記錄中讀取。
