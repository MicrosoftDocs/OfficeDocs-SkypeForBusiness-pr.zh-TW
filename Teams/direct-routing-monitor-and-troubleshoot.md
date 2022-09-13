---
title: 監視器直接路由
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
description: 瞭解如何監視和疑難排解直接路由設定，包括會話框線控制器、直接路由元件和 Telecom 主幹。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47a86e8dd98cdb86cd698b187b21453daa003b07
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657243"
---
# <a name="monitor-direct-routing"></a>監視器直接路由

本文說明如何監視和疑難排解您的直接路由設定。 

使用直接路由撥打和接聽電話的功能包含下列元件： 

- 會話框線控制器 (SBC)  
- Microsoft Cloud 中的直接路由元件 
- 電信主幹 

如果疑難排解問題有問題，您可以向 SBC 廠商或 Microsoft 開啟支援案例。 

Microsoft 正在努力提供更多工具來進行疑難排解和監視。 定期檢查檔以取得更新。 

## <a name="troubleshoot-direct-routing"></a>直接路由疑難排解

若要疑難排解直接路由，請參閱 [診斷直接路由的問題](/MicrosoftTeams/troubleshoot/phone-system/direct-routing/diagnose-direct-routing-issues)。

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>使用會話初始通訊協定 (SIP) 選項訊息監控會話框線控制器的可用性

直接路由使用會話框線控制器傳送的 SIP 選項來監控 SBC 健康情況。 租使用者系統管理員不需要採取任何動作，即可啟用 SIP 選項監控。 進行路由決策時，會將收集的資訊納入考慮。 

例如，如果特定使用者有數個可用來路由通話的 SB，直接路由會考慮從每個 SBC 收到的 SIP 選項資訊來判斷路由。 

下圖顯示設定範例： 

![SIP 選項設定範例。](media/sip-options-config-example.png)

當使用者撥打電話 +1 425 \<any seven digits> 時，直接路由會評估路由。 路線中有兩個 SBC：sbc1.contoso.com 和 sbc2.contoso.com。 這兩個 SBC 在路線上都有相同的優先順序。 挑選 SBC 之前，路由機制會根據 SBC 上次傳送 SIP 選項的時間來評估 SBC 的健康情況。 

如果傳送電話時的統計資料顯示 SBC 每分鐘傳送一次選項，則 SBC 視為健康情況。  

撥打電話時，適用下列邏輯：

- SBC 已于上午 11：00 配對。  
- SBC 會在上午 11：01、上午 11：02 等選項傳送選項。  
- 在 11：15 時，使用者撥打電話，而路由機制會選取此 SBC。 

直接路由會採用定期間隔選項三次， (定期間隔為一分鐘) 。 如果在最後三分鐘內傳送了選項，SBC 會被視為健康情況。

如果範例中的 SBC 在上午 11：12 到上午 11：15 之間的任何期間傳送選項， (撥打電話) ，則視為健康情況。 如果沒有，SBC 會從路由降級。 

降級表示不會先嘗試 SBC。 例如，我們有 sbc1.contoso.com 和 sbc2.contoso.com 具有相同的優先順序。  

如果 sbc1.contoso.com 未如先前所述定期傳送 SIP 選項，則會降級。 接下來，sbc2.contoso.com 嘗試通話。 如果 sbc2.contoso.con 無法接聽電話，系統會在產生失敗之前，再次嘗試 sbc1.contoso.com (降級) 。 

如果一條路 (由有兩個或兩個以上的) SB 會被視為健康且相等，則會套用Fisher-Yates隨機，以便在 SBC 之間散佈通話。

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>監控通話品質分析儀表板和 SBC 記錄 
 
在某些情況下，尤其是在初始配對期間，可能與 SBC 或直接路由服務設定錯誤相關的問題。 

您可以使用下列工具來監控您的設定：  
 
- 通話品質儀表板 
- SBC 記錄檔 

直接路由服務已向通話分析或 SBC 記錄報告描述性錯誤碼。

通話品質儀表板提供通話品質和可靠性的相關資訊。 若要深入瞭解如何疑難排解使用「通話分析」的問題，請參閱[開啟和使用 Microsoft Teams 的通話品質儀表板和商務用 Skype Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard)和[使用通話分析來疑難排解不佳的通話品質](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)。 

如果通話失敗，通話分析會提供標準 SIP 代碼，協助您進行疑難排解。 

![通話失敗時的 SIP 代碼範例。](media/failed-response-code.png)

不過，撥號分析功能只能在來電到達直接路由的內部元件並失敗時提供協助。 例如，如果 SBC 配對有問題，或是 SIP「邀請」遭到拒絕 (，FQDN 主幹的名稱設定錯誤) ，通話分析就無法解決問題。 在此情況下，請參閱 SBC 記錄檔。 直接路由會將問題的詳細描述傳送到 SBC;您可以從 SBC 記錄閱讀這些問題。
