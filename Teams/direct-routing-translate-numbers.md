---
title: 翻譯直接傳送的電話號碼
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何設定 Microsoft Phone 系統 Direct 路由。
ms.openlocfilehash: 2b675948153589c73fa545a95ac785b716b55265
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157950"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>將電話號碼轉譯成替換格式

本文說明如何將輸出和撥入通話的號碼轉譯成替代格式。  以下是設定直接路由的步驟4：

- 步驟1。 [將 SBC 與 Microsoft Phone 系統連接並驗證連接](direct-routing-connect-the-sbc.md) 
- 步驟2。 [允許使用者使用直接路由、語音及語音信箱](direct-routing-enable-users.md)   
- 步驟3。 [設定語音路由](direct-routing-voice-routing.md)
- **步驟4。將數位轉換成替代格式**（本文）

如需設定直接路由所需的所有步驟的詳細資訊，請參閱設定[直接路由](direct-routing-configure.md)。

有時候，租使用者管理員可能會根據其建立的模式，變更輸出與/或撥入通話的號碼，以確保與會話邊界控制器（SBCs）的互通性。 本文說明如何指定數位翻譯規則原則，以將數位轉換成替代格式。 

您可以使用 [數位翻譯規則] 原則來轉譯下列各項的數位：

- 入站通話：從 PSTN 端點（來電者）到團隊用戶端的呼叫（被叫方）
- [呼出通話]：從團隊用戶端（來電者）到 PSTN 端點的呼叫（被叫方）

原則會套用到 SBC 層級。 您可以將多個翻譯規則指派給 SBC，這些規則會依您在 PowerShell 中列出它們時的出現順序來套用。 您也可以在原則中變更規則的順序。

若要建立、修改、查看及刪除數位處理規則，請使用[新的 CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule)、 [CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule)、 [CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule)及[Remove-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule) Cmdlet。

若要在 SBCs 上指派、設定及列出數位操作規則，請使用[新的 CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway)和[CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) Cmdlet 以及 InboundTeamsNumberTranslationRules、InboundPSTNNumberTranslationRules、OutboundTeamsNumberTranslationRules、OutboundPSTNNumberTranslationRules、InboundTeamsNumberTranslationRulesList、InboundPSTNNumberTranslationRulesList、OutboundTeamsNumberTranslationRulesList、OutboundPSTNNumberTranslationRulesList、、、參數.


## <a name="example-sbc-configuration"></a>SBC 範例配置

在```New-CsOnlinePSTNGateway```這種情況下，會執行此 Cmdlet 來建立下列 SBC 配置：

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

指派給 SBC 的翻譯規則摘要如下表所示：

|名稱  |模式 |翻譯  |
|---------|---------|---------|
|AddPlus1     |^ （\d{10}） $          |+ 1 $ 1          |
|AddE164SeattleAreaCode      |^ （\d{4}） $          | + 1206555 $ 1         |
|AddSeattleAreaCode    |^ （\d{4}） $          | 425555 $ 1         |
|StripPlus1    |^ + 1 （\d{10}） $          | $1         |

在下列範例中，有兩個使用者： Alice 和 Bob。 劉愛琳是一個編號為 + 1 206 555 0100 的團隊使用者。 Bob 是一個數位為 + 1 425 555 0100 的 PSTN 使用者。

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>範例1：撥入至十位數的電話

Bob 使用非 E. 164 10 位數的數位呼叫 Alice。 王俊元會撥打2065550100，以達到 Alice。
SBC 在 RequestURI 中使用2065550100，並在 [寄件者] 標題中使用 [標題] 和 [4255550100]。


|資料  |來源語言 |已翻譯的頁首 |已套用參數及規則  |
|---------|---------|---------|---------|
|RequestURI  |邀請 sip:2065550100@sbc.contoso.com|邀請 sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRulesList 'AddPlus1'|
|自    |至： \<sip:2065550100@sbc.contoso.com>|至： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddPlus1'|
|從   |發件\<人： sip:4255550100@sbc.contoso.com>|發件\<人： sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRulesList 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>範例2：撥入至四位數的電話號碼

Bob 使用四位數的數位撥打 Alice。 王俊元會撥打0100，以達到 Alice。
SBC 在 RequestURI 中使用0100，並在 [寄件者] 標題中使用 [標題] 和 [4255550100]。


|資料  |來源語言 |已翻譯的頁首 |已套用參數及規則  |
|---------|---------|---------|---------|
|RequestURI  |邀請 sip:0100@sbc.contoso.com          |邀請 sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'        |
|自    |至： \<sip:0100@sbc.contoso.com>|至： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'         |
|從   |發件\<人： sip:4255550100@sbc.contoso.com>|發件\<人： sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRulesList 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>範例3：使用10位數的非 E. 164 號碼撥出通話

劉愛琳會使用十位數的數位呼叫 Bob。 劉愛琳會撥打 425 555 0100 來取得 Bob 的聯繫。
SBC 針對團隊和 PSTN 使用者設定為使用非 E. 164 10 位數的數位。

在這種情況下，撥號方案會在傳送數位至直接路由介面之前先轉換號碼。 當 Alice 在 [團隊用戶端] 中輸入 425 555 0100 時，該數位會依國家/地區撥號方案轉譯為 [+ 14255550100]。 產生的數位是撥號方案規則與團隊翻譯規則的累計正常化。 團隊翻譯規則會移除撥號方案新增的 "+ 1"。


|資料  |來源語言 |已翻譯的頁首 |已套用參數及規則  |
|---------|---------|---------|---------|
|RequestURI  |邀請 sip:+14255550100@sbc.contoso.com          |邀請 sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRulesList 'StripPlus1'         |
|自    |至： \<sip:+14255550100@sbc.contoso.com>|至： \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRulesList 'StripPlus1'       |
|從   |發件\<人： sip:+12065550100@sbc.contoso.com>|發件\<人： sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRulesList 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>範例4：使用四位數的非 E. 164 號碼撥出通話

劉愛琳會使用四位數的數位呼叫 Bob。 Alice 使用0100來從來電到 Bob 或使用連絡人。
SBC 設定為使用非 E. 164 個4位數的團隊使用者，以及十位數的 PSTN 使用者數位。 在這種情況下，不會套用撥號方案。


|資料  |來源語言 |已翻譯的頁首 |已套用參數及規則  |
|---------|---------|---------|---------|
|RequestURI  |邀請 sip:0100@sbc.contoso.com           |邀請 sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'         |
|自    |至： \<sip:0100@sbc.contoso.com>|至： \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|從   |發件\<人： sip:+12065550100@sbc.contoso.com>|發件\<人： sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRulesList 'StripPlus1' |

## <a name="see-also"></a>另請參閱

[規劃直接路由](direct-routing-plan.md)

[設定直接路由](direct-routing-configure.md)
