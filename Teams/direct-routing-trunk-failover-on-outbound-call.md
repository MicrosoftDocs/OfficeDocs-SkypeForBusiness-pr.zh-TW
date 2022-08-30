---
title: 輸出呼叫上的主幹容錯移轉
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 請閱讀本主題，瞭解如何在從 Teams 到會話框線控制器 (SBC) 的撥出電話上處理主機容錯移轉。
ms.openlocfilehash: 0fa0d452a2611874be570f4e80a746bb07da0163
ms.sourcegitcommit: d7a86b3a72005764c18acb60eedf5163523ffae3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2022
ms.locfileid: "67457133"
---
# <a name="trunk-failover-on-outbound-calls"></a>輸出呼叫上的主幹容錯移轉

本主題說明如何避免撥出電話上的主幹容錯移轉，從 Teams 到會話框線控制器 (SBC) 。

## <a name="failover-on-network-errors"></a>網路錯誤的容錯移轉

如果因任何原因無法連接樹幹，則會嘗試從不同的 Microsoft 資料中心連線到同一個主幹。 資料中心可能位於您目前地理區域以外的其他地理區域。 如果拒絕連線、TLS 逾時，或有任何其他網路層級的問題，則可能無法連接主幹。

例如，如果系統管理員僅限制從已知 IP 位址存取 SBC，但卻忘記將所有 Microsoft 直接路由資料中心的 IP 位址放在 SBC 存取控制清單 (ACL) 上，連線可能會失敗。 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>從會話框線控制器 (SBC) 接收的特定 SIP 代碼容錯移轉

如果直接路由在回應外寄邀請時收到任何 4xx 或 6xx SIP 錯誤碼，則預設會將通話視為已完成。 撥出表示從 Teams 用戶端到公用交換電話網路 (PSTN) 的通話，流量如下：Teams 用戶端 ->直接路由 -> SBC ->電話語音網路。

SIP 代碼清單可在 [會話初始通訊協定 (SIP) RFC 中](https://tools.ietf.org/html/rfc3261)找到。

假設 SBC 在傳入邀請上回複了代碼「408 要求逾時：伺服器無法在適當時間內產生回應，例如，如果伺服器無法及時判斷使用者的位置。」 用戶端可能會隨時重複要求而不修改。」

這個特定的 SBC 可能因為網路設定錯誤或其他錯誤，而無法連線到來電者。 不過，路由中還有一個 SBC 可以連絡來電者。

在下列圖表中，當使用者撥打電話號碼時，路由中有兩個 SB 可以接通此通話。 一開始會選取 SBC1.contoso.com 來進行通話，但 SBC1.contoso.com 因為網路問題而無法連線到 PTSN 網路。
根據預設，此時會完成通話。 
 
![顯示 SBC 因網路問題而無法連線 PSTN 的圖表。](media/direct-routing-failover-response-codes1.png)

路由中還有一個可能傳遞通話的 SBC。
如果您設定參數 `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"` ，將會在下列圖表中嘗試 (SBC2.contoso.com 第二個 SBC) ：

![顯示路由到第二個 SBC 的圖表。](media/direct-routing-failover-response-codes2.png)

設定參數 -FailoverResponseCodes 並指定程式碼可協助您微調路由，並避免當 SBC 因網路或其他問題而無法撥打電話時可能發生的問題。

預設值：408、503、504

