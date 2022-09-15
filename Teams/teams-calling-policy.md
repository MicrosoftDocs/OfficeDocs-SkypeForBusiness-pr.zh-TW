---
title: Microsoft Teams 中的通話原則：通話和來電轉接功能
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中建立、修改及新增使用者至自訂通話原則，以及各種通話原則設定。
ms.localizationpriority: medium
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6c785a6860c1ea45200253e9d2530a80e9dd28f6
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2022
ms.locfileid: "67708263"
---
# <a name="calling-and-call-forwarding-in-teams"></a>Teams 中的通話和來電轉接

在 Microsoft Teams 中，通話原則可控制哪些呼叫和來電轉接功能可供使用者使用。 通話原則決定使用者是否可以撥打私人電話、使用來電轉接或同時撥打給其他使用者或外部電話號碼、將通話路由至語音信箱、將電話傳送給通話群組、使用委派進行輸入和撥出電話等等。

您可以使用全域 (組織的預設) 自動建立的原則，或建立及指派自訂原則。

## <a name="create-a-custom-calling-policy"></a>建立自訂通話原則

請依照下列步驟建立自訂通話原則。

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 **語音**  >  **通話原則**。
2. 選取 [新增 **]**。
3. 開啟或關閉通話原則中要使用的功能。
4. 若要控制使用者是否可以將撥入電話路由至語音信箱，請選 **取 [已啟用** ] 或 [ **使用者控制]**。 若要防止路由到語音信箱，請選取 [ **已停用]**。
5. 選取 [儲存 **]**。

## <a name="edit-a-calling-policy"></a>編輯通話原則

請依照下列步驟編輯現有的通話原則。

1. 在 Microsoft Teams 系統管理中心的左側導覽中，選取 **[語音**  >  **通話原則]**。
2. 按一下您要修改的原則旁邊，然後選取 [ **編輯]**。
3. 進行您要的變更，然後按一下 [ **儲存]**。

## <a name="assign-a-custom-calling-policy-to-users"></a>指派自訂通話原則給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>通話原則設定

以下是您可以針對通話原則設定的設定。

### <a name="make-private-calls"></a>可進行私人通話

此設定會控制 Teams 中的所有通話功能。 關閉此功能可關閉 Teams 中的所有通話功能。

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>來電轉接和同時撥打給組織中的人員

此設定可控制是否可以將來電轉接給其他使用者，或同時撥打給其他人。

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>來電轉接和同時撥打到外部電話號碼

此設定會控制來電是否可以轉接至外部號碼，或同時撥打外部號碼。

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>語音信箱可用於路由輸入通話

此設定可讓輸入電話傳送至語音信箱。 有效的選項有：

- **啟用** 語音信箱一律可供輸入通話使用。
- **禁用**  語音信箱不適用於輸入通話。
- **使用者控制** 使用者可以判斷是否要使用語音信箱。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>撥入電話可以路由至通話群組

此設定會控制是否可以將來電轉接至通話群組。

### <a name="delegation-for-inbound-and-outbound-calls"></a>委派輸入和撥出電話

此設定可將撥入電話路由至代理人，讓代理人代表其具有委派許可權的使用者撥打撥出電話。 如需詳細資訊，請參閱 [與代理人共用電話線](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>防止略過付費並透過 PSTN 傳送電話

將此設定設為 [ **開** 啟] 會透過 PSTN 傳送電話並產生費用，而不是透過網路傳送電話並略過付費。

### <a name="busy-on-busy-is-available-when-in-a-call"></a>在通話中忙碌時可以使用忙碌

在 [忙碌] ([忙碌選項] 中忙碌) 可讓您設定當使用者已在電話或電話會議中，或是電話處於保留狀態時，來電的處理方式。 新來電或來電可能會因訊號忙碌而遭拒，也可以路由至使用者的未接聽設定。 您可以在租使用者層級或使用者層級啟用忙碌選項。 無論他們的忙碌選項設定方式為何，通話或會議中的使用者或保留通話的使用者都無法發起新的通話或會議。 此設定預設為停用。

### <a name="web-pstn-calling"></a>Web PSTN 通話

此設定可讓使用者使用 Teams Web 用戶端撥打 PSTN 號碼。

### <a name="automatically-answer-incoming-meeting-invites"></a>自動回答傳入的會議邀請

此設定會控制是否自動回復傳入的會議邀請。 預設為關閉。 請記住，此設定僅適用于傳入的會議邀請。 不適用於其他類型的通話。

### <a name="allow-music-on-hold"></a>允許等候音樂

此設定可讓您在 PSTN 來電者處於保留狀態時，開啟或關閉等候音樂。 預設會開啟此功能。 此設定不適用於通話公園和老闆代理人功能。

### <a name="allow-sip-devices-calling"></a>允許 SIP 裝置通話

此設定可讓使用者使用 SIP 裝置撥打和接聽電話。

### <a name="spam-filtering"></a>垃圾郵件篩選

此設定可讓您控制來電中可用的垃圾郵件篩選類型。

### <a name="call-recording-live-captions-and-transcription"></a>通話錄製、即時輔助字幕和轉譯

這些設定可讓您控制使用者是否可以使用通話錄製、即時輔助字幕和轉譯功能。

## <a name="related-articles"></a>相關文章

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

[Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy)

[Remove-CsTeamsCallingPolicy](/powershell/module/skype/remove-csteamscallingpolicy)

[在 Teams 中將原則指派給使用者](policy-assignment-overview.md)
