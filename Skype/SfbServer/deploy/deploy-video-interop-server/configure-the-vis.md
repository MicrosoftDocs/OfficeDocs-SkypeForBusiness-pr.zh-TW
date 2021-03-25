---
title: 在商務用 Skype Server 中設定視頻 Interop 伺服器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 摘要：在商務用 Skype Server 中設定 (VIS) 角色的視頻 Interop 伺服器。
ms.openlocfilehash: 8d5da36d07583cc1c20407d842b94531062947ba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120302"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>在商務用 Skype Server 中設定視頻 Interop 伺服器
 
**摘要：** 在商務用 Skype Server 中設定 (VIS) 角色的視頻 Interop 伺服器。
  
 使用 Windows PowerShell，設定 VIS 將與影片主幹關聯的設定。 安裝 VIS 服務後，就會建立具有全域範圍的影片主幹設定。 此影片主幹設定會由 VIS 套用至所有未具有較特定範圍的「影片主幹」設定的主幹。 請注意，「影片主幹」設定是適用于影片主幹的設定集合。
  
## <a name="configure-video-trunk-and-dial-plan"></a>設定影片主幹及撥號對應表

使用下列 Windows PowerShell 命令，指定要與新定義主幹 (關聯的影片主幹設定和撥號對應表，) 在 VIS 和所有的視頻閘道之間的拓撲檔中所定義。 您可以在全域、網站或服務 (的視頻閘道) 層級設定所有這些設定。 
  
具有全域範圍的撥號對應表是針對商務用 Skype Server 部署而建立的。 此撥號對應表是由 VIS 套用至所有沒有具有更特定範圍的撥號對應表的主幹。 
  
### <a name="configure-the-vis-using-windows-powershell"></a>使用 Windows PowerShell 設定 VIS

1. 使用下列 Windows PowerShell Cmdlet，建立新的影片主幹設定 (，以在 VIS 和 Cisco 整合通訊管理員 (CallManager 或 CUCM) 之間的主幹上使用的設定) ：
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    如果有需要修改的現有影片主幹，請使用下列 Windows PowerShell Cmdlet：
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    若要查看與特定影片主幹設定相關聯的設定，請使用下列 Windows PowerShell Cmdlet：
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    若要移除特定的「影片主幹」設定，請使用下列 Windows PowerShell Cmdlet (請注意，如果特定主幹) 上沒有特殊範圍的影片主幹設定，則會套用全域範圍的視頻主幹設定：
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. 使用下列 Windows PowerShell Cmdlet，建立與主幹相關聯的撥號對應表：
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

需要使用 **Remove-get-csvoicenormalizationrule** 命令來覆寫會干擾預期 VIS 和 CUCM 互動的預設規則。
> [!NOTE]
> 可以使用[get-csdialplan](/powershell/module/skype/remove-csdialplan?view=skype-ps)移除撥號對應表。
  
針對來自視頻閘道（要求 URI 包含非 e.164 號碼）的影片 SIP 主幹呼叫，VIS 會讀取與關聯主幹相關聯的撥號對應表名稱，並將撥號對應表名稱包含在 VIS 傳送至前端之邀請中之要求 URI 的電話內容部分中。 前端的翻譯應用程式接著會解壓縮並套用與撥號對應表相關聯的正規化規則到要求 URI。
## <a name="trunk-configuration-options"></a>主幹設定選項

先前提及之影片主幹設定的 Windows PowerShell Cmdlet 是商務用 Skype Server 2015 的新 Cmdlet。 與影片主幹設定相關聯的設定需要簡短的說明。
  
 **GatewaySendsRtcpForActiveCalls** 此參數會決定是否要將 RTCP 的封包從 VTC 傳送至 VIS 以進行使用中通話。 此處的目前通話指的是至少允許媒體流向一個方向的通話。 如果 GatewaySendsRtcpForActiveCalls 設定為 True，VIS 可以在超過30秒的期限內收到 RTCP 封包時結束通話。 預設值為 **True** 。
  
 **GatewaySendsRtcpForCallsOnHold** 此參數會決定是否要針對暫止的通話繼續在主幹中傳送 RTCP 封包，而且沒有預期任何媒體封包流向任何方向。 若通話處於保留狀態，VIS 可以終止通話（如果沒有 RTCP 封包從 VTC 流向 VIS）。 預設值為 **True** 。 SIPTransport 通訊協定設定為 TCP 時，會忽略此設定。
  
 **EnableMediaEncryptionForSipOverTls** 當 SIPTransport 通訊協定設定為 TLS 時，此參數會啟用或停用媒體的 SRTP。 預設值為 **True** 。 SIPTransport 通訊協定設定為 TCP 時，會忽略此設定。
  
 **EnableSessionTimer** 此參數會針對與影片 SIP 主幹相關聯的每個 SIP 對話方塊，啟用或停用 VIS 端的會話計時器。 預設值為 **False** 。
  
 **ForwardErrorCorrectionType** 此參數是用來判斷是否要將影片的 [轉寄錯誤修正] (FEC) 套用到視頻 Interop 伺服器和視頻閘道之間的腿。 將 ForwardErrorCorrectionType 設定為 "None" 會關閉 VIS 和 Video Gateway/VTC 之間的 FEC。 將 ForwardErrorCorrectionType 設定為 "Cisco" 可使 FEC 與透過 Cisco 的視頻閘道相容，例如 Cisco 整合通訊管理員 (CUCM) 。 預設值為 **None**。
  
## <a name="see-also"></a>另請參閱

[設定 CUCM 以搭配商務用 Skype 伺服器進行交互操作](configure-cucm-for-interoperation.md)