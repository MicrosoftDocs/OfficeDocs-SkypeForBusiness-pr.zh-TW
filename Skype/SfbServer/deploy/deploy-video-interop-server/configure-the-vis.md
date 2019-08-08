---
title: 在商務用 Skype Server 中設定視頻交互操作伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: '摘要: 在商務用 Skype Server 中設定視頻互通性伺服器 (VIS) 角色。'
ms.openlocfilehash: 9ac7b64b33c48bd4010c1431b5c0d658f223599a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235679"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>在商務用 Skype Server 中設定視頻交互操作伺服器
 
**摘要:** 在商務用 Skype Server 中設定影片互通性伺服器 (VIS) 角色。
  
 使用 Windows PowerShell 設定 VIS 將與視頻 trunks 相關聯的設定。 安裝 VIS 服務之後, 就會建立含全域作用中的影片幹線設定。 此視頻幹線設定會由 VIS 套用至所有沒有視頻幹線設定且具有更具體範圍的 trunks。 請注意, [影片主幹設定] 是適用于 [視頻 trunks] 的設定集合。
  
## <a name="configure-video-trunk-and-dial-plan"></a>設定影片幹線與撥號方案

使用下列 Windows PowerShell 命令來指定要與在 VIS 和所有視頻閘道之間的拓撲結構中定義的新定義幹線相關聯的影片幹線設定和撥號計畫。 所有這些設定都可以在 [全域]、[網站] 或 [服務] ([視頻閘道]) 層級設定。 
  
具有全域作用中的撥號方案會針對商務用 Skype Server 部署建立。 這個撥號方案是由 VIS 套用至所有不含特定範圍的撥號規劃的 trunks。 
  
### <a name="configure-the-vis-using-windows-powershell"></a>使用 Windows PowerShell 設定 VIS

1. 使用下列 Windows PowerShell Cmdlet, 建立新的影片幹線設定 (設定的集合), 以在 VIS 與 Cisco 整合通訊管理員 (CallManager 或 CUCM) 之間的主幹上使用:
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    如果有需要修改的現有影片主幹, 請使用下列 Windows PowerShell Cmdlet:
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    若要查看與特定的影片幹線設定相關聯的設定, 請使用下列 Windows PowerShell Cmdlet:
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    若要移除特定的視頻幹線設定, 請使用下列 Windows PowerShell Cmdlet (請注意, 如果特定幹線沒有更明確限制範圍的視頻幹線設定, 就會套用全域範圍的視頻幹線設定):
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. 使用下列 Windows PowerShell Cmdlet 建立要與主幹產生關聯的撥號方案:
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

若要覆寫會干擾預期 VIS 和 CUCM 互動的預設規則, 則需要**Remove-CsVoiceNormalizationRule**命令。
> [!NOTE]
> [移除-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps)可用來移除撥號方案。
  
對於來自視頻閘道的視頻 SIP 幹線呼叫, 其要求 URI 包含非 E. 164 個數字, VIS 將會讀取與關聯主幹相關聯的撥號方案名稱, 並將撥號計畫名稱包含在此 VI 中之邀請 URI 的電話內容部分中S 會傳送到前端。 前端的翻譯應用程式接著會解壓縮並將與撥號計畫相關聯的正常化規則套用至要求 URI。
## <a name="trunk-configuration-options"></a>幹線配置選項

先前所述的影片主幹設定的 Windows PowerShell Cmdlet 是商務用 Skype Server 2015 的新程式。 與影片幹線設定相關的設定需要簡短的說明。
  
 **GatewaySendsRtcpForActiveCalls**這個參數會判斷 RTCP 資料包是否從 VTC 傳送至 VIS, 以進行使用中的通話。 此處的目前通話指的是至少允許媒體流向一個方向的通話。 如果 GatewaySendsRtcpForActiveCalls 設定為 True, 則 VIS 可以在超過30秒的期限內收到 RTCP 資料包時終止通話。 預設值為**True**。
  
 **GatewaySendsRtcpForCallsOnHold**這個參數決定是否要在主幹中繼續傳送 RTCP 資料包, 以取得已保留的通話, 而且不會將任何媒體資料包流向任何方向。 如果通話處於保留狀態時, 如果沒有 RTCP 資料包從 VTC 流向 VIS, VIS 可以終止通話。 預設值為**True**。 當 SIPTransport 通訊協定設定為 TCP 時, 此設定會被忽略。
  
 **EnableMediaEncryptionForSipOverTls**此參數可在 SIPTransport 通訊協定設定為 TLS 時啟用或停用媒體的 SRTP。 預設值為**True**。 當 SIPTransport 通訊協定設定為 TCP 時, 此設定會被忽略。
  
 **EnableSessionTimer**這個參數可在 VIS 端針對與影片 SIP 幹線相關聯的每個 SIP 對話方塊, 啟用或停用會話計時器。 預設值為**False**。
  
 **ForwardErrorCorrectionType**這個參數是用來判斷視頻資料流程的轉寄糾錯 (FEC) 是否要套用在視頻互通性伺服器與視頻閘道之間的腿上。 將 ForwardErrorCorrectionType 設定為 [None], 就會關閉 VIS 與視頻閘道/VTC 之間的 FEC。 將 ForwardErrorCorrectionType 設定為「Cisco」可讓您透過 Cisco (例如 Cisco 整合通訊管理員 (CUCM) 等與視頻閘道相容的 FEC。 預設值為 [**無**]。
  
## <a name="see-also"></a>另請參閱

[設定 CUCM 以與商務用 Skype 伺服器進行交互操作](configure-cucm-for-interoperation.md)
