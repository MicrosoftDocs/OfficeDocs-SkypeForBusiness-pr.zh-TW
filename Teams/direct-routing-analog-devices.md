---
title: 直接路由 - 連接類比裝置
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
description: 請閱讀本文，瞭解如何在系統直接路由Microsoft 電話使用類比裝置。
ms.openlocfilehash: dc49c22dceffda6905d1f57652fd14d584d02cf6
ms.sourcegitcommit: 9d446485aa842abbdcd34d946b247166c2bf1610
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "52642093"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>如何使用類比裝置電話系統直接路由

本文將說明如何將類比裝置與直接路由電話系統使用。 若要將類比裝置連接到直接路由，您必須使用類比電話轉接器 (ATA) ，且此配接器必須受到認證會話邊界控制器 (SBC) 廠商的支援。 

當使用者從類比裝置進行通話時，訊號和媒體會透過 ATA (電話轉接器) SBC。  SBC 會根據內部路由Microsoft Teams，將電話傳送至 (網或公用交換電話網絡) PSTN。  當裝置進行通話時，其路由取決於為裝置所建立路由策略。

在下列圖表中，直接路由已進行配置，因此任何 Teams 之間與 +1425 4XX XX XX 和 +1425 5XX XX XX 之間的號碼，都必須使用紅色路由 (虛線) ， 與 +1425 4XX XX XX 和號碼範圍 +1425 5XX XX 以外的任何其他號碼之間的任何 PSTN 通話，都必須使用藍色 (實線) 。 

> [!div class="mx-imgBorder"]
> ![顯示直接路由配置的圖表](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>範例：如何設定使用直接路由的類比裝置

若要設定使用直接路由的類比裝置，您必須將類比電話轉接器連接到 SBC，並設定 SBC 以使用直接路由。 

此範例會逐步引導您完成下列步驟：

1. 連線 SBC 到直接路由。
2. 建立 PSTN 使用量。
3. 建立語音路由，並將其與 PSTN 使用量建立關聯。
4. 將語音路由指派給 PSTN 使用量。
5. 啟用線上使用者。
6. 指派語音路由策略給使用者。
7. 建立類比裝置的聲音路由。

若要瞭解如何將 ATA 連接到 SBC 並設定 SBC，請參閱您的 SBC 製造商設定指南：

- [AudioCodes 組組檔](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [功能區組組檔](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [Oracle 組組檔](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>步驟 1。  連線 SBC 到直接路由

下列命令會設定 SBC 連接，如下所示：

- FQDN sbc.contoso.com
- 訊號埠 5068
- 媒體旁路模式
- 已轉往 SBC 的通話記錄資訊-
- P-已確認身分識別 (PAI) 頁標題與通話一起轉轉 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>步驟 2：建立 PSTN 使用量 

下一個命令會建立一個空的 PSTN 使用量。 線上 PSTN 使用量是用於通話授權的字串值。 線上 PSTN 使用方式會連結線上語音策略至路由。 此範例會將字串「Interop」新加到目前的可用 PSTN 使用狀況清單中。 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>步驟 3：建立語音路由，並將其與 PSTN 使用量建立關聯：

此命令會為號碼範圍 +1425 XXX XX XX 建立身分識別 「類比交互操作」的新線上語音路由。  語音路由適用于線上閘道清單 sbc.contoso.com 將路由與線上 PSTN 使用方式「Interop」關聯。 語音路由包含一個正則運算式，用來識別哪些電話號碼會透過給定的語音路由路由：

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7})$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>步驟 4：將語音路由指派給 PSTN 使用量：

此命令會使用身分識別 「AadiInteropPolicy」建立新的線上每個使用者語音路由策略。 此政策會指派單一線上 PSTN 使用量：「Interop」。

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>步驟 5：啟用線上使用者

此命令會使用身分識別選項修改 exampleuser@contoso.com。 在這種情況下，帳戶會修改為啟用 企業語音 ，即 Microsoft VoIP 的實現，且已啟用語音信箱，並將號碼 +142550000000 指派給此使用者。  此命令應針對每個使用者執行Teams， (公司租使用者中的 ATA 裝置) 使用者除外。

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>步驟 6：將語音路由策略指派給使用者

此命令會指派每個使用者的線上語音路由策略AdisInteropPolicy給具有身分識別 exampleuser@contoso.com。  此命令應針對每個使用者執行Teams， (公司租使用者中的 ATA 裝置) 使用者除外。

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a>步驟 7：為類比裝置建立語音路由

此命令會針對適用于線上閘道清單的號碼範圍 +1425 4XX XX XX 建立身分識別 「類比交互操作」的線上語音路由 sbc.contoso.com 並關聯到線上 PSTN 使用方式「Interop」。  此命令應針對每個具有適當電話號碼模式的類比裝置執行。 或者，在前一個步驟中，在配置線上語音路由時，可以使用適當的類比裝置數位模式。

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6})$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>考量

- 除非另有說明，否則類比裝置是可傳送 DTMF 位數進行通話的任何裝置。 例如，類比電話、傳真機和高空傳呼機。

- 連接到 ATA 的類比電話無法從 Teams。 Teams使用者必須手動輸入與裝置相關聯的電話號碼，才能撥打該裝置。  
 

## <a name="see-also"></a>另請參閱

[規劃直接路由](direct-routing-plan.md)

[設定直接路由](direct-routing-configure.md)
