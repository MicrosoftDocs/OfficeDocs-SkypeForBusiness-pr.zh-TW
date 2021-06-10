---
title: 翻譯直接路由的電話號碼
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
description: 瞭解如何設定 Microsoft 電話直接路由。
ms.openlocfilehash: 03abeed954a7760c7c53142380a8ca558c5b3761
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096373"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>將電話號碼翻譯成替代格式

本文將說明如何將輸出和輸入通話的號碼轉換成替代格式。  這是下列步驟中的步驟 4，用於配置直接路由：

- 步驟 1。 [連線系統Microsoft 電話 SBC 並驗證連接](direct-routing-connect-the-sbc.md) 
- 步驟 2. [啟用使用者進行直接路由、語音和語音信箱](direct-routing-enable-users.md)   
- 步驟 3. [設定語音路由](direct-routing-voice-routing.md)
- **步驟 4.將數位轉換成替代格式 (**   本文) 

若要瞭解設定直接路由所需的所有步驟，請參閱 [設定直接路由](direct-routing-configure.md)。

有時候租使用者系統管理員可能會想要根據他們建立的模式來變更出站和/或來電的號碼，以確保與會話邊界控制器 (SBC) 。 本文將說明如何指定數位翻譯規則原則，將數位轉換成替代格式。 

您可以使用數位翻譯規則原則來翻譯下列數位：

- 來電：從 PSTN 端點 (來電) 呼叫Teams通話 (通話) 
- 外接電話：從Teams用戶端 (來電) 呼叫者 (PSTN 端點) 

原則會以 SBC 層級進行。 您可以將多個翻譯規則指派給 SBC，這些翻譯規則會以在 PowerShell 中列出規則時的順序進行。 您也可以變更原則中規則的順序。

若要建立、修改、查看及刪除數位操作規則，請使用 New-CsTeamsTranslationRule、Set-CsTeamsTranslationRule、Get-CsTeamsTranslationRule 和[Remove-CsTeamsTranslationRule](/powershell/module/skype/remove-csteamstranslationrule) Cmdlets。 [](/powershell/module/skype/new-csteamstranslationrule) [](/powershell/module/skype/set-csteamstranslationrule) [](/powershell/module/skype/get-csteamstranslationrule)

若要在 SBCs 上指派、設定及清單號碼操作規則，請使用 [New-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) 和 [Set-CSOnlinePSTNGateway Cmdlet](/powershell/module/skype/set-csonlinepstngateway) 與 InboundTeamsNumberTranslationRules， 輸入PSTNNumberTranslationRules，OutboundTeamsNumberTranslationRules， OutboundPSTNNumberTranslationRules， InboundTeamsNumberTranslationRules， InboundPSTNNumberTranslationRules， OutboundTeamsNumberTranslationRules， 和 OutboundPSTNNumberTranslationRules 參數。

> [!NOTE]
> 翻譯規則總數上限為 400 個、翻譯參數名稱長度上限為 100 個符號、最大翻譯參數模式長度為 1024 個符號，而翻譯參數翻譯長度上限為 256 個符號。


## <a name="example-sbc-configuration"></a>範例 SBC 組組

針對此案例，會執行 ```New-CsOnlinePSTNGateway``` Cmdlet 以建立下列 SBC 組組：

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

下表摘要列出指派給 SBC 的翻譯規則：

|名稱  |模式 |翻譯  |
|---------|---------|---------|
|AddPlus1     |^ (\d {10}) $          |+1$1          |
|AddE164SeattleAreaCode      |^ (\d {4}) $          | +1206555$1         |
|AddSeattleAreaCode    |^ (\d {4}) $          | 425555$1         |
|StripPlus1    |^+1 (\d {10}) $          | $1         |

在下列範例中，有兩個使用者，即艾莉和 Bob。 愛麗Teams使用者，其號碼是 +1 206 555 0100。 Bob 是 PSTN 使用者，其號碼是 +1 425 555 0100。

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>範例 1：輸入到十位數號碼的通話

Bob 使用非 E.164 的 10 位數號碼打電話給愛麗。 Bob 撥號 2065550100 以撥入艾斯達。
SBC 在 RequestURI 和 To 標頭中使用 2065550100，在 From 標頭中則使用 4255550100。


|頭  |來源語言 |翻譯的標題 |已應用參數和規則  |
|---------|---------|---------|---------|
|RequestURI  |邀請 sip:2065550100@sbc.contoso.com|邀請 sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|自    |自： \<sip:2065550100@sbc.contoso.com>|自： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|從   |從： \<sip:4255550100@sbc.contoso.com>|從： \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>範例 2：四位數號碼的輸入通話

Bob 使用四位數的號碼打電話給艾莉。 Bob 撥號 0100 以撥入艾斯達。
SBC 在 RequestURI 和 To 頁標題中使用 0100，而從標頭使用 4255550100。


|頭  |來源語言 |翻譯的標題 |已應用參數和規則  |
|---------|---------|---------|---------|
|RequestURI  |邀請 sip:0100@sbc.contoso.com          |邀請 sip:+12065550100@sbc.contoso.com           |輸入TeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|自    |自： \<sip:0100@sbc.contoso.com>|自： \<sip:+12065550100@sbc.contoso.com>|輸入TeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|從   |從： \<sip:4255550100@sbc.contoso.com>|從： \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>範例 3：使用十位數非 E.164 號碼的外發通話

艾莉使用十位數的號碼打電話給 Bob。 艾莉絲撥打 425 555 0100 來聯繫 Bob。
SBC 已針對使用者和 PSTN 使用者Teams非 E.164 十位數數位。

在此情境中，撥號方案會先轉換號碼，再將其傳送至直接路由介面。 當小紅在 Teams 用戶端輸入 425 555 0100 時，該號碼會根據國家/地區撥號方案轉換為 +14255550100。 產生的號碼是撥號方案規則的累加標準化，Teams翻譯規則。 翻譯Teams會移除撥號方案新增的「+1」。


|頭  |來源語言 |翻譯的標題 |已應用參數和規則  |
|---------|---------|---------|---------|
|RequestURI  |邀請 sip:+14255550100@sbc.contoso.com          |邀請 sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|自    |自： \<sip:+14255550100@sbc.contoso.com>|自： \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|從   |從： \<sip:+12065550100@sbc.contoso.com>|從： \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>範例 4：使用四位數非 E.164 號碼的外發通話

艾莉使用四位數的號碼打電話給 Bob。 艾莉使用 0100 從通話或使用連絡人與 Bob 聯繫。
SBC 已配置為針對 Teams 使用非 E.164 四位數數位，而 PSTN 使用者則使用十位數數位。 此案例不會使用撥號方案。


|頭  |來源語言 |翻譯的標題 |已應用參數和規則  |
|---------|---------|---------|---------|
|RequestURI  |邀請 sip:0100@sbc.contoso.com           |邀請 sip:4255550100@sbc.contoso.com       |輸入TeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|自    |自： \<sip:0100@sbc.contoso.com>|自： \<sip:4255555555@sbc.contoso.com>|輸入TeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|從   |從： \<sip:+12065550100@sbc.contoso.com>|從： \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>另請參閱

[規劃直接路由](direct-routing-plan.md)

[設定直接路由](direct-routing-configure.md)