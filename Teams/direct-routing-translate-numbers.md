---
title: 翻譯直接路由的電話號碼
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
description: 瞭解如何設定 Microsoft Phone System Direct Routing。
ms.openlocfilehash: ac6dbd46d525232235d957b7d47f1fe108e3e4a3
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727765"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>將電話號碼翻譯成替代格式

本文將說明如何將撥出和輸入通話的號碼轉換為替代格式。 這是設定直接路由的下列步驟 4 步驟：

- 步驟 1. [將 SBC 與 Microsoft Phone System 連線並驗證連線](direct-routing-connect-the-sbc.md) 
- 步驟 2. [啟用使用者的直接路由、語音和語音信箱](direct-routing-enable-users.md)   
- 步驟 3. [設定語音路由](direct-routing-voice-routing.md)
- **步驟 4.將數位翻譯成替代格式**   (本文) 

如需設定直接路由所需所有步驟的相關資訊，請參閱 [設定直接路由](direct-routing-configure.md)。

有時候租使用者系統管理員可能會想要根據他們建立的模式來變更撥出和/或輸入通話的號碼，以確保與會話框線控制器 (SBC) 的互通性。 本文說明如何指定數位翻譯規則原則，將數位翻譯成替代格式。 

您可以使用數位翻譯規則原則來翻譯下列數位：

- 撥入電話：從 PSTN 端點 (來電者) 至 Teams 用戶端 (來電者) 
- 撥出電話：從 Teams 用戶端 (來電者) 到 PSTN 端點 (來電者) 

原則會套用至 SBC 層級。 您可以將多個翻譯規則指派給 SBC，這些規則會依照您在 PowerShell 中列出的順序來套用。 您也可以變更原則中規則的順序。

若要建立、修改、檢視及刪除數位操作規則，請使用 [New-CsTeamsTranslationRule](/powershell/module/skype/new-csteamstranslationrule)、 [Set-CsTeamsTranslationRule](/powershell/module/skype/set-csteamstranslationrule)、 [Get-CsTeamsTranslationRule](/powershell/module/skype/get-csteamstranslationrule)和 [Remove-CsTeamsTranslationRule](/powershell/module/skype/remove-csteamstranslationrule) Cmdlet。

若要在 SBC 上指派、設定及清單編號操作規則，請搭配 InboundTeamsNumberTranslationRules、InboundPSTNNumberTranslationRules、OutboundTeamsNumberTranslationRules、OutboundTeamsNumberTranslationRules 和 OutboundPSTNMberTranslationRules 參數使用[New-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) Cmdlet。[ ](/powershell/module/skype/new-csonlinepstngateway)

> [!NOTE]
> 翻譯規則的總數上限為 400 個，翻譯參數名稱長度上限為 100 個符號，翻譯參數圖樣長度上限為 1024 個符號，翻譯參數翻譯長度上限為 256 個符號。


## <a name="example-sbc-configuration"></a>SBC 設定範例

針對此案例，系統會執行New-CsOnlinePSTNGateway Cmdlet 以建立下列 SBC 設定：

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,‘StripPlus1’  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

指派給 SBC 的翻譯規則摘要如下表：

|名稱  |模式 |翻譯  |
|---------|---------|---------|
|AddPlus1     |^ (\d {10}) $          |+1$1          |
|AddE164SeattleAreaCode      |^ (\d {4}) $          | +1206555$1         |
|AddSeattleAreaCode    |^ (\d {4}) $          | 425555$1         |
|StripPlus1    |^\+1 (\d {10}) $          | $1         |

在下列範例中，有兩個使用者：[寄件者] 和 [百勝]。 加碼是 Teams 使用者，其號碼為 +1 206 555 0100。 Bob 是 PSTN 使用者，其號碼為 +1 425 555 0100。

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>範例 1：輸入電話到十位數號碼

百勝使用非 E.164 的十位數號碼來稱呼「特性」。 Bob 撥號2065550100以連線到 [天元]。
SBC 會在 [寄件者] 標頭的 [RequestURI] 和 [到] 標題和 [4255550100] 中使用2065550100。


|頭  |來源語言 |翻譯的頁首 |參數和規則已套用  |
|---------|---------|---------|---------|
|RequestURI  |邀請 sip:2065550100@sbc.contoso.com|邀請 sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|自    |自： \<sip:2065550100@sbc.contoso.com>|自： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|從   |從： \<sip:4255550100@sbc.contoso.com>|從： \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>範例 2：輸入電話到四位數號碼

Bob 會使用四位數號碼來稱呼[正在使用]。 Bob 撥號 0100 以連線到[劉德標]。
SBC 會在 [要求] 標題中使用 0100，在 [寄件者] 標頭中使用 [到] 標頭和4255550100。


|頭  |來源語言 |翻譯的頁首 |參數和規則已套用  |
|---------|---------|---------|---------|
|RequestURI  |邀請 sip:0100@sbc.contoso.com          |邀請 sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|自    |自： \<sip:0100@sbc.contoso.com>|自： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|從   |從： \<sip:4255550100@sbc.contoso.com>|從： \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>範例 3：使用十位數非 E.164 號碼的撥出通話

使用十位數號碼撥打 Bob。 將電話撥號 425 555 0100 連線到 Bob。
SBC 設定為同時為 Teams 和 PSTN 使用者使用非 E.164 的十位數數位。

在此案例中，撥號對應表會先將號碼轉譯，再傳送到直接路由介面。 當[加力] 在 Teams 用戶端中輸入 425 555 0100 時，該號碼會由國家/地區撥號對應表轉換為 +14255550100。 產生的號碼是撥號對應表規則和 Teams 翻譯規則的累積正規化。 Teams 翻譯規則會移除撥號對應表新增的 「+1」。


|頭  |來源語言 |翻譯的頁首 |參數和規則已套用  |
|---------|---------|---------|---------|
|RequestURI  |邀請 sip:+14255550100@sbc.contoso.com          |邀請 sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|自    |自： \<sip:+14255550100@sbc.contoso.com>|自： \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|從   |從： \<sip:+12065550100@sbc.contoso.com>|從： \<sip:2065550100@sbc.contoso.com>|輸出TeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>範例 4：使用四位數非 E.164 號碼的撥出通話

使用四位數號碼撥打 Bob。 方格使用 0100 從通話或使用連絡人連絡 Bob。
SBC 設定為使用 Teams 使用者的非 E.164 四位數數位，以及 PSTN 使用者的十位數數位。 此案例中未套用撥號對應表。


|頭  |來源語言 |翻譯的頁首 |參數和規則已套用  |
|---------|---------|---------|---------|
|RequestURI  |邀請 sip:0100@sbc.contoso.com           |邀請 sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|自    |自： \<sip:0100@sbc.contoso.com>|自： \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|從   |從： \<sip:+12065550100@sbc.contoso.com>|從： \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>另請參閱

[規劃直接路由](direct-routing-plan.md)

[設定直接路由](direct-routing-configure.md)
