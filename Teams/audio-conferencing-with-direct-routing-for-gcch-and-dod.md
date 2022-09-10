---
title: 含直接路由、GCCH 和 DoD 的音訊會議
author: MicrosoftHeidi
ms.author: heidip
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
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 管理員可以瞭解如何在 GCCH 和 DoD 環境中搭配直接路由使用音訊會議。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd467b9da8d296c21d4a0405d651bbaa6b001fd3
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641774"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>適用於 GCC High 和 DoD 的音訊會議搭配直接路由

具有 GCC High 和 DoD 直接路由的音訊會議可讓參與者使用電話裝置加入 GCC High 或 DoD 組織中的 Teams 會議。 會議參與者可能會偏好使用電話裝置加入 Teams 會議，例如網際網路連線有限或使用者在外且無法存取 Teams 的情況。 參與者可以選擇透過撥入貴組織的撥入電話號碼或讓會議撥出到其電話裝置來加入會議。

透過 GCC High 和 DoD 直接路由的音訊會議，貴組織會使用自己的號碼作為撥入電話號碼，而所有會議撥出到電話裝置的號碼都是透過直接路由路由傳送。 若要啟用服務，組織需要設定直接路由，並設定可以用來作為撥入電話號碼的電話號碼。 使用直接路由的需求與 Microsoft 提供撥入電話號碼的非 GCC High 和非 DoD 組織所提供的音訊會議服務不同。

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>使用 GCC High 和 DoD 的直接路由部署音訊會議

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>步驟 1：使用 GCC High 或 DoD 授權的直接路由取得音訊會議

若要在 GCC High 或 DoD 中使用音訊會議，貴組織和貴組織中的使用者必須擁有指派直接路由授權的音訊會議。 以下是啟用具有 GCC High 或 DoD 直接路由之音訊會議所需的授權。

- GCC High：音訊會議 - 貴組織的 GCC 高租使用者授權和音訊會議 - GCC High 授權供使用者使用。

- DoD：音訊會議 - 貴組織的 DoD 租使用者授權和音訊會議 - 使用者的 DoD 授權。

必須有租使用者授權和至少一個使用者授權才能啟用服務。 您無法只使用租使用者授權或只使用使用者授權來啟用服務。 若要取得租使用者和組織中使用者的服務授權，請連絡您的帳戶小組。

> [!IMPORTANT]
> 在設定撥入電話號碼之前，使用者無法使用具有直接路由的音訊會議。 建議您不要將 GCC High 直接路由的音訊會議或 DoD 授權指派給使用者，直到您設定撥入電話號碼為止，如本文所述。  若未遵循此指引，可能會導致 Teams 用戶端中的撥號鍵台完全遺失。

### <a name="step-2-set-up-direct-routing"></a>步驟 2：設定直接路由

若要設定直接路由，請參閱下列文章：

- [規劃直接路由](direct-routing-plan.md)

- [設定直接路由](direct-routing-configure.md)

> [!NOTE]
> 設定直接路由時，請記得使用這兩篇文章中所述的 GCC High 或 DoD 特定 FQDN 和埠。

### <a name="step-3-set-up-dial-in-phone-numbers"></a>步驟 3：設定撥入電話號碼

撥入電話號碼是與音訊會議橋接器相關聯的電話號碼。 參與者會使用這些數位加入組織中使用者排定的會議。 這些號碼也會包含在貴組織中排程會議之使用者的會議邀請和 [尋找當地號碼] 頁面中。

#### <a name="define-service-phone-numbers-in-your-tenant"></a>定義租使用者中的服務電話號碼

您可以使用 New-csHybridTelephoneNumber PowerShell Cmdlet 來定義租使用者中可用來透過直接路由將通話路由到音訊會議服務的服務電話號碼。

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

例如：

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>將服務電話號碼指派給貴組織的音訊會議橋接器

您可以使用 Register-csOnlineDialInConferencingServiceNumber PowerShell Cmdlet，將服務電話號碼指派給組織的音訊會議橋接器。

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

您可以使用 Get-CsOnlineDialInConferencingBridge 查看音訊會議橋接器的識別碼。 例如：

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>步驟 4：定義全域語音路由原則，以啟用從會議傳送的撥出電話

從組織中使用者召集的會議撥打到 PSTN 的撥出電話，是由貴組織的全域語音路由原則所定義。 如果貴組織定義了全域語音路由原則，請確認全域語音路由原則允許撥出電話至 PSTN，而該 PSTN 預期是由貴組織中的使用者召集的會議發起。 如果貴組織並未定義全域語音路由原則，您必須定義一個，以便從組織中使用者召集的會議中，將撥出電話傳送到 PSTN。 請注意，貴組織的全域語音路由原則也適用于組織中使用者對 PSTN 進行的一對一通話。 如果貴組織中的使用者已啟用一對一電話到 PSTN，請確定全域語音路由原則符合貴組織在這兩種通話類型的需求。

> [!NOTE]
> Location-Based路由無法在 Microsoft 365 政府社群雲端 (GCC) High 或 DoD 部署中使用。 啟用音訊會議時，請確認 GCC High 或 DoD 環境中的音訊會議使用者未啟用Location-Based路由。

#### <a name="defining-a-global-voice-routing-policy"></a>定義全域語音路由原則

定義 PSTN 使用量、語音路由、語音路由原則，以及將新的語音路由原則指派為貴組織的全域語音路由原則，即可定義全域語音路由原則。

下列步驟說明如何為沒有全域語音路由原則的組織定義新的全域語音路由原則。 如果貴組織已定義語音路由原則，請確認下列設定與貴組織現有的語音路由原則不衝突。

若要在 Teams 的遠端 PowerShell 會話中建立新的 PSTN 使用方式，請使用下列命令：

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

如需詳細資訊，請參閱 [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage)。

若要建立新的語音路由，請使用下列命令：

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

為貴組織定義新的語音路由時，請指定在設定直接路由期間為貴組織定義的一或多個 PSTN 線上 PSTN 閘道。

號碼模式會根據通話的目的地電話號碼，指定要透過指定的閘道清單路由哪些電話。 在上述範例中，呼叫全球任何目的地都會符合語音路由。 如果您想要限制可從貴組織使用者的會議撥打的電話號碼，您可以變更號碼模式，讓語音路由只符合允許的目的地號碼模式。 請注意，如果沒有符合指定通話目的地電話號碼之號碼模式的語音路由，則不會路由通話。

如需詳細資訊，請參閱 [New-CsOnlineVoiceRoute](/powershell/module/skype/new-csonlinevoiceroute)。

若要建立新的語音路由原則，請使用下列命令：

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

如果語音路由原則中定義了多個 PSTN 使用量，則會依定義順序評估。 建議您根據 PSTN 使用量相關之語音路由的數值模式，以較一般最特定的順序來定義 PSTN 使用量。 例如，如果 PSTN 使用量已定義為將呼叫路由至美國，並且已定義另一個 PSTN 使用量以將通話路由至世界任何其他位置，則傳送到美國的 PSTN 使用量應該列在 PSTN 使用率之前之語音路由原則中，將呼叫路由到世界任何其他位置。

如需詳細資訊，請參閱 [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy)。

若要將新的語音路由指派給貴組織的全域語音路由原則，請使用下列命令：

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

如需詳細資訊，請參閱 [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。

定義全域語音路由原則後，會根據與全域語音路由原則的 PSTN 使用方式相關聯的語音路由，評估組織中使用者所召集的任何撥出通話。 撥出電話會根據第一個符合撥號電話號碼模式的語音路由路由。

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>步驟 5：使用 GCC High 或 DoD 授權的直接路由指派音訊會議給使用者

若要使用 GCC High 的直接路由或 DoD 授權指派音訊會議給使用者，請參閱 [指派授權給使用者](/microsoft-365/admin/manage/assign-licenses-to-users)。

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>步驟 6： (選擇性) 查看 Teams 中的音訊會議號碼清單

若要查看貴組織的音訊會議號碼清單，請移至 [查看 Microsoft Teams 中的音訊會議號碼清單](see-a-list-of-audio-conferencing-numbers-in-teams.md)。

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>步驟 7： (選擇性) 為組織的音訊會議撥入號碼設定自動語音應答語言

若要變更貴組織音訊會議撥入號碼的語言，請參閱 [在 Microsoft Teams 中設定音訊會議的自動語音應答語言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)。

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>步驟 8： (選擇性) 變更貴組織音訊會議橋接器的設定

若要變更貴組織的音訊會議橋接器設定，請參閱 [變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>步驟 9： (選擇性) 設定組織中使用者會議邀請中包含的電話號碼

若要變更使用者會議邀請中包含的電話號碼組，請參閱 [在 Microsoft Teams 中設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites-in-teams.md)。

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>音訊會議不支援音訊會議功能，且 GCC High 和 DoD 的直接路由

下列是音訊會議不支援的音訊會議功能，以及 GCC High 和 DoD 的直接路由：

- 使用名稱錄製進入和結束通知。 針對具有直接路由的音訊會議，進入和離開通知會在會議中以音調的方式播放。

- 停用會議特定召集人免付費電話號碼的使用。 限制使用免付費電話號碼加入貴組織會議的使用者層級控制項不適用於透過直接路由路由傳送的通話。

- 當使用者的設定變更時，傳送通知電子郵件給使用者。 音訊會議通知電子郵件不支援具有 GCC High 和 DoD 直接路由的音訊會議。
