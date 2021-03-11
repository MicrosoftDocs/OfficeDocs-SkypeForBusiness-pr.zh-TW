---
title: 具有直接路由、GCCH 和 DoD 的音訊會議
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
description: 系統管理員可以瞭解如何在 GCCH 和 DoD 環境中使用音訊會議與直接路由。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 84f2789c6d4f4e9c5446ad39d6f2d50d842b92a6
ms.sourcegitcommit: 0a7c1f52484452f66f678b0feca1455bade4fcf3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2021
ms.locfileid: "50716928"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>適用於 GCC High 和 DoD 的音訊會議搭配直接路由

具有 GCC High 和 DoD 直接路由的音訊會議可讓參與者使用電話裝置加入 GCC High 或 DoD 組織中 Teams 會議。 在網際網路連接受到限制或使用者在路上且無法存取 Teams 等情況下，會議參與者可能會想要使用電話裝置加入 Teams 會議。 參與者可以加入宣告會議，撥入組織的撥入電話號碼，或讓會議撥出到其電話裝置。

使用具有 GCC High 和 DoD 直接路由的音訊會議，貴組織會使用自己的號碼作為撥入電話號碼，而所有電話裝置的會議撥出都是透過直接路由路由。 若要啟用服務，組織必須設定直接路由，並設定可做為撥入電話號碼的電話號碼。 使用直接路由的需求與提供給非 GCC High 和非 DoD 組織的音訊會議服務不同，這些組織是 Microsoft 提供撥入電話號碼。

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>使用 GCC High 和 DoD 的直接路由部署音訊會議

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>步驟 1：取得具有 GCC High 或 DoD 授權直接路由的音訊會議 

若要在 GCC High 或 DoD 使用音訊會議，您的組織和貴組織的使用者必須擁有已指派直接路由授權的音訊會議。 以下是啟用 GCC High 或 DoD 直接路由音訊會議所需的授權。

- GCC High：音訊會議 - 貴組織的 GCC 高租使用者授權和音訊會議 - 適用于使用者的 GCC 高授權。

- DoD：音訊會議 - 貴組織的 DoD 租使用者授權和音訊會議 - 適用于使用者的 DoD 授權。

需要租使用者授權和至少一個使用者授權才能啟用服務。 您僅能使用租使用者授權或僅具有使用者授權來啟用服務。 若要取得租使用者和貴組織使用者的服務授權，請聯絡您的帳戶小組。

> [!IMPORTANT]
> 使用者必須設定撥入電話號碼，而且 Teams 用戶端有一個可以使用的撥號鍵台，才能使用直接路由進行音訊會議。 建議您在設定本文所述的撥入電話號碼之前，不要將具有 GCC High 直接路由的音訊會議或 DoD 授權指派給使用者。

### <a name="step-2-set-up-direct-routing"></a>步驟 2：設定直接路由

若要設定直接路由，請參閱下列文章：

- [規劃直接路由](direct-routing-plan.md)

- [設定直接路由](direct-routing-configure.md)

> [!NOTE]
> 設定直接路由時，請記得使用這兩篇文章中所述的 GCC High 或 DoD 私人 FQDN 和埠。

### <a name="step-3-set-up-dial-in-phone-numbers"></a>步驟 3：設定撥入電話號碼

撥入電話號碼是音訊會議橋接器相關聯的電話號碼。 這些號碼會由參與者用來加入貴組織中使用者排程的會議。 這些號碼也會包含在組織中排程會議之使用者的會議邀請中，以及 「尋找當地號碼」頁面。

#### <a name="define-service-phone-numbers-in-your-tenant"></a>定義租使用者中的服務電話號碼

您可以使用 New-csHybridTelephoneNumber PowerShell Cmdlet 定義租使用者中的服務電話號碼，以透過直接路由將通話路由至音訊會議服務。 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

例如：
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>將服務電話號碼指派給貴組織的音訊會議橋接器

您可以使用 Register-csOnlineDialInConferencingServiceNumber PowerShell Cmdlet，將服務電話號碼指派給貴組織的音訊會議橋接器。

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

您可以使用 Get-CsOnlineDialInConferencing Bridge 查看音訊會議橋接器的識別碼。 例如：

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>步驟 4：定義全域語音路由策略，以啟用會議外發通話的路由

從貴組織使用者組織的會議撥打到 PSTN 的外線通話路由，是由貴組織的全域語音路由策略所定義。 如果貴組織已定義全域語音路由策略，請確認全域語音路由策略允許從貴組織中使用者所組織之會議所啟動的 PSTN 外發通話。 如果貴組織未定義全域語音路由策略，您必須定義一個，才能從貴組織使用者組織的會議，將外線通話路由至 PSTN。 請注意，貴組織的全域語音路由原則也適用于貴組織使用者對 PSTN 撥打的一對一通話。 如果貴組織的使用者已啟用 PSTN 一對一通話，請確定全域語音路由策略符合貴組織在這兩種類型的通話需求。 

> [!NOTE]
> Location-Based高或 DoD 部署中的 Microsoft 365 政府社群雲端 (GCC) 路由。 啟用音訊會議時，請確認 GCC High 或 DoD 環境中未啟用音訊會議使用者進行Location-Based路由。

#### <a name="defining-a-global-voice-routing-policy"></a>定義全域語音路由策略

您可以定義 PSTN 使用量、語音路由、語音路由策略，並將新的語音路由策略指派為貴組織的全域語音路由策略，以定義全域語音路由策略。

下列步驟說明如何為沒有全域語音路由的組織定義新的全域語音路由策略。 如果貴組織已定義語音路由策略，請確認下列組態與貴組織現有的語音路由策略不衝突。

若要在商務用 Skype Online 的遠端 PowerShell 會話中建立新的 PSTN 使用方式，請使用下列命令：

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

其他資訊請參閱[Set-CsOnlinePstnUsage。](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage)

若要建立新語音路由，請使用下列命令：

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

為組織定義新的語音路由時，請指定在直接路由的組態期間為貴組織定義的一或多個 PSTN 線上 PSTN 閘道。 

號碼模式會根據通話的目的地電話號碼，指定哪些電話會透過指定的閘道清單路由。 在上例中，撥打到全世界任何目的地的通話都會符合語音路由。 如果您想要限制可以從貴組織使用者會議撥打的電話號碼，您可以變更號碼模式，讓語音路由只符合允許的目的地號碼模式。 請注意，如果沒有符合給定通話目的地電話號碼的號碼模式的語音路由，通話將不會路由。

其他資訊請參閱[New-CsOnlineVoiceRoute。](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute)

若要建立新的語音路由策略，請使用下列命令：

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

如果在語音路由策略中定義多個 PSTN 使用量，將會按照定義的順序進行評估。 建議 PSTN 使用量是按照與 PSTN 使用量相關聯的語音路由數量模式，以較一般之最特定的順序定義。 例如，如果將 PSTN 使用量定義為將通話路由到美國，而另一個 PSTN 使用量定義為將通話路由到世界上任何其他位置，則撥打到美國的 PSTN 使用量應會列在語音路由策略中，以在 PSTN 使用量之前將呼叫路由到全球任何其他位置。

其他資訊請參閱[New-CsOnlineVoiceRoutingPolicy。](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)

若要將新的語音路由指派給貴組織的全域語音路由策略，請使用下列命令：

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

其他資訊請參閱[Grant-CsOnlineVoiceRoutingPolicy。](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)

一旦定義全域語音路由策略後，貴組織中使用者所組織之會議所撥打的任何電話，都會根據與全域語音路由策略 PSTN 使用狀況相關聯的語音路由進行評估。 撥出電話會依據符合撥打電話號碼號碼模式的第一個語音路由進行路由。

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>步驟 5：使用 GCC High 或 DoD 授權直接路由指派音訊會議給使用者

若要將具有 GCC High 或 DoD 授權直接路由的音訊會議指派給使用者，請參閱指派 [授權給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>步驟 6： (選擇) 查看 Teams 中的音訊會議號碼清單

若要查看貴組織的音訊會議號碼清單，請前往 Microsoft Teams 中查看音訊會議 [號碼清單](see-a-list-of-audio-conferencing-numbers-in-teams.md)。

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>步驟 7： (選擇性) 為貴組織的音訊會議撥入號碼設定自動語音機語言

若要變更貴組織音訊會議撥入號碼的語言，請參閱 [在 Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)中設定音訊會議自動語音機語言。

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>步驟 8： (選擇) 變更貴組織音訊會議橋接器的設定

若要變更貴組織音訊會議橋接器的設定，請參閱變更音訊會議橋接器 [的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>步驟 9： (選) 設定貴組織使用者會議邀請中包含的電話號碼

若要變更使用者會議邀請中包含的一組電話號碼，貴組織請參閱設定 Microsoft Teams 中邀請中包含的 [電話號碼](set-the-phone-numbers-included-on-invites-in-teams.md)。

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>音訊會議不支援 GCC High 和 DoD 直接路由的音訊會議功能

下列是音訊會議在 GCC High 和 DoD 的直接路由中不支援的音訊會議功能：

- 使用名稱錄製進入和離開通知。 針對具有直接路由的音訊會議，進入和離開通知會以鈴聲在會議中播放。

- 音訊會議外線通話限制政策。 限制撥出電話的使用者層級控制項不適用於透過直接路由路由的會議撥出電話。

- 停用會議特定召集人免付費號碼的使用方式。 限制使用免付費電話號碼加入貴組織會議的使用者層級控制項不適用於透過直接路由路由的通話。

- 當使用者的設定變更時，傳送通知電子郵件給使用者。 音訊會議通知電子郵件不支援具有 GCC High 和 DoD 直接路由的音訊會議。
