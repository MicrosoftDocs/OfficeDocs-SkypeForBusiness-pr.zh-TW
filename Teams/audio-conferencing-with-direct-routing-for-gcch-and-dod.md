---
title: 使用直接路由、GCCH 和 DoD 的音訊會議
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
ms.openlocfilehash: 577a9fe106cb5dae23049404b54433288e350b78
ms.sourcegitcommit: bd7847de9d1402476f8faaeae2ff97ec60d86a1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2021
ms.locfileid: "51262618"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>適用於 GCC High 和 DoD 的音訊會議搭配直接路由

使用直接路由GCC高和 DoD 的音訊會議可讓參與者Teams電話裝置GCC高或 DoD 組織中加入會議。 會議參與者可能偏好使用電話裝置加入 Teams 會議，例如網際網路連接受限或使用者在路上且無法存取Teams。 參與者可以加入宣告會議，撥入貴組織的撥入電話號碼，或讓會議撥出到其電話裝置。

透過具有 GCC High 和 DoD 直接路由的音訊會議，貴組織會使用自己的號碼做為撥入電話號碼，而所有電話裝置的會議撥出都透過直接路由路由。 若要啟用服務，組織必須設定直接路由，並設定可做為撥入電話號碼的電話號碼。 使用直接路由的需求與 Microsoft 提供撥入電話號碼的非 GCC High 和非 DoD 組織所提供的音訊會議服務不同。

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>使用直接路由部署音訊會議GCC高和 DoD

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>步驟 1：使用直接路由取得音訊會議GCC高或 DoD 授權 

若要在 GCC 或 DoD 中使用音訊會議，您的組織和貴組織的使用者必須指派具有直接路由授權的音訊會議。 以下是使用直接路由啟用音訊會議所需的授權，GCC高或 DoD。

- GCC高：音訊會議 - GCC高租使用者授權和音訊會議 - GCC使用者擁有高授權。

- DoD：音訊會議 - 貴組織的 DoD 租使用者授權和音訊會議 - 使用者用 DoD 授權。

啟用服務需要租使用者授權和至少一個使用者授權。 您無法僅使用租使用者授權或僅以使用者授權啟用服務。 若要取得租使用者和貴組織使用者的服務授權，請聯絡您的帳戶小組。

> [!IMPORTANT]
> 在設定撥入電話號碼之前，使用者無法啟用使用直接路由的音訊會議。 建議您在設定本文所述的撥入電話號碼之前，不要將 GCC High 或 DoD 授權的音訊會議指派給使用者。  若未遵循此指引，可能會導致撥號鍵台在用戶端Teams遺失。

### <a name="step-2-set-up-direct-routing"></a>步驟 2：設定直接路由

若要設定直接路由，請參閱下列文章：

- [規劃直接路由](direct-routing-plan.md)

- [設定直接路由](direct-routing-configure.md)

> [!NOTE]
> 當您設定直接路由時，請記得使用GCC文章所述之高或多維私人 FQDN 和埠。

### <a name="step-3-set-up-dial-in-phone-numbers"></a>步驟 3：設定撥入電話號碼

撥入電話號碼是與音訊會議橋接器相關聯的電話號碼。 參與者會使用這些號碼加入貴組織中使用者排程的會議。 這些號碼也會包含在組織中排程會議之使用者的會議邀請中，以及 「尋找當地號碼」頁面上。

#### <a name="define-service-phone-numbers-in-your-tenant"></a>在租使用者中定義服務電話號碼

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


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>步驟 4：定義全域語音路由策略，以啟用會議外接通話的路由

從貴組織中使用者組織的會議撥打到 PSTN 的外發通話路由，是由貴組織的全域語音路由策略所定義。 如果貴組織已定義全域語音路由策略，請確認全域語音路由策略允許從貴組織中使用者組織的會議發起的 PSTN 外接通話。 如果貴組織未定義全域語音路由策略，您必須定義一個策略，才能從貴組織中使用者組織的會議，將外線通話路由至 PSTN。 請注意，貴組織的全域語音路由原則也適用于貴組織中使用者對 PSTN 撥打的一對一通話。 如果貴組織的使用者已啟用一對一的 PSTN 通話，請確定全域語音路由策略符合貴組織在這兩種類型的通話需求。 

> [!NOTE]
> Location-Based高或 DoD 部署中Microsoft 365 政府社群雲端 (GCC) 路由。 啟用音訊會議時，請確認在高GCC或 DoD 環境中未啟用音訊會議使用者Location-Based路由。

#### <a name="defining-a-global-voice-routing-policy"></a>定義全域語音路由策略

您可以定義 PSTN 使用方式、語音路由、語音路由策略，並將新的語音路由策略指派為貴組織的全域語音路由策略，以定義全域語音路由策略。

下列步驟說明如何為沒有全域語音路由的組織定義新的全域語音路由策略。 如果貴組織已定義語音路由策略，請確認下列組態與貴組織現有的語音路由策略沒有衝突。

若要在線上遠端 PowerShell 會話中商務用 Skype PSTN 使用方式，請使用下列命令：

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

有關其他資訊，請參閱 [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage)。

若要建立新的語音路由，請使用下列命令：

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

定義貴組織的新語音路由時，請指定在直接路由組態期間為貴組織定義的一或多個 PSTN 線上 PSTN 閘道。 

號碼模式會根據通話的目的地電話號碼，指定哪些通話會透過指定的閘道清單路由。 在上例中，全球任何目的地的通話都會符合語音路由。 如果您想要限制可以從貴組織使用者會議撥打的電話號碼，您可以變更號碼模式，讓語音路由只符合目的地的號碼模式。 請注意，如果沒有任何語音路由符合所撥打之通話目的地電話號碼的號碼模式，將不會路由通話。

有關其他資訊，請參閱 [New-CsOnlineVoiceRoute](/powershell/module/skype/new-csonlinevoiceroute)。

若要建立新的語音路由策略，請使用下列命令：

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

如果在語音路由策略中定義多個 PSTN 使用方式，將會按照定義的順序進行評估。 建議根據與 PSTN 使用狀況相關聯的語音路由數模式，以較一般之最特定的順序定義 PSTN 使用量。 例如，如果 PSTN 使用量定義為將通話路由到美國，而另一個 PSTN 使用量已定義為將通話路由到全球任何其他位置，則 PSTN 通話到美國的 PSTN 使用量應列在 PSTN 使用量之前，再列在 PSTN 使用量之前，將通話路由到全球任何其他位置。

有關其他資訊，請參閱 [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy)。

若要將新的語音路由指派給貴組織的全域語音路由策略，請使用下列命令：

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

有關其他資訊，請參閱 [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。

定義全域語音路由策略後，貴組織中使用者組織的任何會議所撥打的任何外接電話，都會根據與全域語音路由策略 PSTN 使用關聯的語音路由進行評估。 撥出電話會依據符合撥號電話號碼號碼模式的第一個語音路由。

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>步驟 5：指派音訊會議與直接路由GCC高或 DoD 授權給使用者

若要將具有直接路由的音訊會議GCC高或 DoD 授權指派給使用者，請參閱[指派授權給使用者](/microsoft-365/admin/manage/assign-licenses-to-users)。

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>步驟 6： (選) 查看音訊會議號碼清單Teams

若要查看貴組織的音訊會議號碼清單，請前往 查看 Microsoft Teams 中的[音訊會議號碼Microsoft Teams。](see-a-list-of-audio-conferencing-numbers-in-teams.md)

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>步驟 7： (選) 為貴組織的音訊會議電話撥入號碼設定自動語音語音處理語言

若要變更貴組織音訊會議撥入號碼的語言，請參閱在 Microsoft Teams 中設定音訊會議[自動語音Microsoft Teams。](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>步驟 8： (選擇性) 變更貴組織音訊會議橋接器的設定

若要變更貴組織的音訊會議橋接器的設定，請參閱變更音訊會議橋接器 [的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>步驟 9： (選) 設定貴組織使用者會議邀請中包含的電話號碼

若要變更使用者會議邀請中包含的一組電話號碼，請參閱在 Microsoft Teams 中設定邀請[中Microsoft Teams。](set-the-phone-numbers-included-on-invites-in-teams.md)

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>音訊會議功能不支援音訊會議與直接路由GCC高和 DoD

以下是音訊會議功能，在音訊會議中不支援直接路由GCC高和 DoD：

- 使用名稱錄製來進入和離開通知。 對於使用直接路由的音訊會議，進入和離開通知會以鈴聲在會議中播放。

- 音訊會議的外發通話限制政策。 限制撥出通話的使用者層級控制項不適用於透過直接路由路由的會議撥出電話。

- 停用特定會議召集人免付費號碼的使用方式。 限制使用免付費號碼加入貴組織會議的使用者層級控制項不適用於透過直接路由路由的通話。

- 當使用者的設定變更時，傳送通知電子郵件給使用者。 音訊會議通知電子郵件不支援使用高和 doD GCC直接路由的音訊會議。