---
title: 監控並疑難排解直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: 本文說明如何監視和疑難排解直接路由設定。
ms.openlocfilehash: b2afef2a8f02f6823be10d127c8efc7b4cd5d72d
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572165"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>監控並疑難排解直接路由

本文說明如何監視和疑難排解直接路由設定。 

使用直接路由撥打及接聽電話的功能，包括下列元件： 

- 會話邊界控制器（SBCs） 
- Microsoft 雲端中的直接路由元件 
- 電信 trunks 

如果您遇到疑難排解問題，您可以在您的 SBC 轉銷商或 Microsoft 開啟支援案例。 

Microsoft 正在努力提供更多工具以進行疑難排解及監視。 請定期查看檔以取得更新。 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>使用會話初始通訊協定（SIP）選項訊息監視會話邊界控制器的可用性

[直接路由]：使用由會話邊界控制器傳送的 SIP 選項來監視 SBC 健康情況。 租使用者管理員無需執行任何動作，即可啟用 SIP 選項監視。 建立路由決定時，會考慮收集的資訊。 

例如，如果您針對特定使用者提供數種可路由通話的 SBCs，直向路由會考慮從每個 SBC 接收的 SIP 選項資訊來判斷路由。 

下圖顯示配置範例： 

![SIP 選項配置範例](media/sip-options-config-example.png)

當使用者撥打電話給 number + 1 425 \<時，任何七位數>，直向路由會評估路由。 路由中有兩個 SBCs： sbc1.contoso.com 和 sbc2.contoso.com。 兩個 SBCs 在路由中都有相同的優先順序。 在挑選 SBC 前，路由機制會根據 SBC 每次傳送 SIP 選項的時間來評估 SBCs 的健康情況。 

如果傳送通話時的統計資料顯示 SBC 每分鐘傳送選項，則會被視為健康情況。  

撥打電話時，會套用下列邏輯：

- SBC 已成對 11:00 AM。  
- SBC 會在 11:01 AM、11:02 AM 等的時間傳送選項。  
- 在11:15，使用者撥打電話，而路由機制則會選取這個 SBC。 

[直接傳送] 會將週期性間隔選項分為三次（定期間隔為1分鐘）。 如果在過去三分鐘內傳送選項，則會認為 SBC 健康。

如果範例中的 SBC 在 11:12 AM 和 11:15 AM 之間（撥打的時間），則會被視為健康情況。 如果不是，則 SBC 將會從路由中降級。 

[降級] 表示不會先嘗試使用 SBC。 例如，我們有同等優先順序的 sbc1.contoso.com 和 sbc2.contoso.com。  

如果 sbc1.contoso.com 未依先前所述的定期間隔傳送 SIP 選項，則會將它降級。 接著，sbc2.contoso.com 通話的嘗試。 如果 sbc2 無法傳送通話，則會在產生失敗前再次嘗試 sbc1.contoso.com （降級）。 

如果在一個路線中有兩個（或多個） SBCs 是正常且相等的，則會套用 Fisher Yates 隨機播放，在 SBCs 間散佈通話。

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>監控通話品質分析儀表板和 SBC 記錄 
 
在某些情況下，特別是在初次配對期間，可能會發生有關 SBCs 或直接路由服務的錯誤配置問題。 

您可以使用下列工具來監視您的設定：  
 
- 通話品質儀表板 
- SBC 記錄 

直連路由服務會有一個描述為呼叫分析或 SBC 記錄的明顯的錯誤代碼。 

通話品質儀表板提供通話品質與可靠性的相關資訊。 若要進一步瞭解如何使用通話分析進行疑難排解，請參閱[開啟與使用 Microsoft 團隊和商務用 Skype Online 的通話品質儀表板](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard)，並[使用呼叫分析來排查不佳的通話品質](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)問題。 

如果通話失敗，通話分析提供標準 SIP 代碼，協助您進行疑難排解。 

![通話失敗的 SIP 代碼範例](media/failed-response-code.png)

不過，通話分析只會在來電到達直接路由的內部元件並失敗時加以協助。 如果 SBC 配對發生問題，或 SIP 「Invite」遭到拒絕的問題（例如，幹線 FQDN 的名稱未正確設定），通話分析將無法提供協助。 在這種情況下，請參閱 SBC 記錄。 直接路由會將問題的詳細描述傳送到 SBCs;您可以從 SBC 記錄中讀取這些問題。 
