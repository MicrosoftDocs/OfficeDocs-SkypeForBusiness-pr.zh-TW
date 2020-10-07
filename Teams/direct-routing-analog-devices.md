---
title: 直接路由-連接類比裝置
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 閱讀本文以瞭解如何將模擬裝置搭配 Microsoft Phone 系統 Direct 路由搭配使用。
ms.openlocfilehash: 0c6531a29e23e736a84db9bf8571abab2e13942a
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369188"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>如何將模擬裝置與電話系統直接路由搭配使用

本文說明如何將模擬裝置與電話系統 Direct 路由搭配使用。 若要將模擬裝置連線至直接路由，您必須使用模擬電話配接器 (的 ATA) ，且認證會話邊界控制器 (SBC) 供應商必須支援此配接器。 

當使用者從類比裝置撥打電話時，模擬程式和媒體會透過類比電話配接器 (ATA) 傳送給 SBC。  SBC 會根據內部路由資料表，將呼叫傳送至 Microsoft 團隊端點，或是傳送給公開的交換電話網絡 (PSTN) 。  當裝置撥打電話時，傳送的路線會視為裝置所建立的路由策略而定。

在下圖中，將 [直接路由] 設定為在 + 1425 4XX XX xx 和 + 1425)  (5XX （xx xx）中的數位之間撥打電話給，或從 + 1425 4XX （數位範圍 + 1425)  (5XX）到 + 4XX xx xx 及任何其他數位之間的任何一種，在 + 

> [!div class="mx-imgBorder"]
> ![顯示直接路由設定的圖表](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>範例：如何設定使用直接路由的類比裝置

若要設定直接路由的類比裝置的使用，您必須將類比電話配接器連線至 SBC，並設定 SBC 與直接路由搭配使用。 

這個範例會逐步引導您完成下列步驟：

1. 將 SBC 連接至直接路由。
2. 建立 PSTN 使用量。
3. 建立語音路由，並將它與 PSTN 使用狀況建立關聯。
4. 將語音路由指派給 PSTN 使用量。
5. 啟用線上使用者。
6. 將語音路線原則指派給使用者。
7. 建立類比裝置的語音路線。

如需如何將 ATA 連線至 SBC 並設定 SBC 的相關資訊，請參閱您的 SBC 製造商配置指南：

- [AudioCodes 設定檔](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [功能區設定檔](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>步驟1。  將 SBC 連接至直接路由

下列命令會設定 SBC 連接，如下所示：

- FQDN sbc.contoso.com
- 信號埠5068
- 媒體旁路模式
- 來電記錄資訊轉寄給 SBC-
- P-已斷言身分識別 (PAI) 標頭與通話一起轉寄 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>步驟2：建立 PSTN 使用量 

下一個命令會建立空白的 PSTN 用法。 線上 PSTN 用法是用來進行通話授權的字串值。 線上 PSTN 使用會將線上語音原則連結至路線。 這個範例會將字串「交互操作」新增到目前可用 PSTN 用法的清單中。 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>步驟3：建立語音路由，並將它與 PSTN 用法建立關聯：

這個命令會針對數位範圍 + 1425 XXX xx XX 的身分識別「類比-interop」建立新的線上語音路由。  語音路由適用于線上閘道 sbc.contoso.com 清單，並將路由與線上 PSTN 使用 "互通性" 關聯。 語音路由包含一個正則運算式，可識別將透過特定語音路線傳送哪些電話號碼：

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>步驟4：將語音路由指派給 PSTN 用法：

這個命令會針對 [AnalogInteropPolicy] 身分識別，建立新的每使用者語音路由策略。 此原則會指派單一線上 PSTN 使用量： "互通性"。

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>步驟5：啟用線上使用者

這個命令會使用身分識別 exampleuser@contoso.com 來修改使用者帳戶。 在這種情況下，會將帳戶修改為啟用企業語音、Microsoft VoIP 的 Microsoft 實現以及已啟用的語音信箱，並將數位 + 14255000000 指派給此使用者。  在公司租使用者中， (不包括 ATA 裝置使用者) 的每個小組使用者，都應該執行這個命令。

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>步驟6：將語音路線原則指派給使用者

這個命令會將每個使用者的線上語音路由策略 AnalogInteropPolicy 指派給具有身分識別 exampleuser@contoso.com 的使用者。  在公司租使用者中， (不包括 ATA 裝置使用者) 的每個小組使用者，都應該執行這個命令。

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a>步驟7：為類比裝置建立語音路線

這個命令會建立一個含有「類比-interop」的 [身分識別] 的線上語音路由，該號碼範圍 + 1425 4XX XX XX 適用于線上閘道 sbc.contoso.com 清單，並將其與線上 PSTN 使用 "互通性" 關聯。  針對每個具有適當電話號碼模式的類比裝置，都應該執行這個命令。 或者，當您在上述其中一個步驟中設定線上語音路由時，可以使用類比裝置的適當數位模式。

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>考量

- 除非另請注意，類比裝置就是任何可以傳送 DTMF 位數以進行呼叫的裝置。 例如，類比電話、傳真機和投影機呼機。

- 無法從團隊中搜尋連線至 ATA 的類比電話。 團隊使用者必須手動輸入與裝置相關聯的電話號碼，才能呼叫該裝置。  
 

## <a name="see-also"></a>另請參閱

[規劃直接路由](direct-routing-plan.md)

[設定直接路由](direct-routing-configure.md)
