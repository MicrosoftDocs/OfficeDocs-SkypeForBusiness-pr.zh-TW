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
ms.openlocfilehash: a478e203ed973ff2199b4ad500de0441e200918d
ms.sourcegitcommit: 387141880842c93ecf4a936aaa26342a3f996259
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2023
ms.locfileid: "69781438"
---
# <a name="calling-policies-calling-and-call-forwarding-features-in-teams"></a>通話原則：Teams 中的通話和來電轉接功能

在 Microsoft Teams 中，通話原則可控制哪些呼叫和來電轉接功能可供使用者使用。 通話原則決定使用者是否可以撥打私人電話、使用來電轉接或同時撥打給其他使用者或外部電話號碼、將通話路由至語音信箱、將電話傳送給通話群組、使用委派進行輸入和撥出電話等等。

您可以使用全域 (組織的預設) 自動建立的原則，或建立及指派自訂原則。

## <a name="create-a-custom-calling-policy"></a>建立自訂通話原則

請依照下列步驟建立自訂通話原則。

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 **語音**  >  **通話原則**。
2. 選取 [新增 **]**。
3. 開啟或關閉通話原則中要使用的功能。
    - 例如，若要控制使用者是否可以將撥入電話路由至語音信箱，請選 **取 [已啟用** ] 或 [ **使用者控制]**。 若要防止路由到語音信箱，請選取 **[未啟用]**。
4. 選取 [儲存 **]**。

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

此設定會控制 Teams 中的所有通話功能。 關閉此設定可關閉 Teams 中的所有通話功能。

### <a name="cloud-recording-for-calling"></a>用於通話的雲端錄製

此設定會控制使用者是否可以錄製通話。 此設定預設為關閉。

### <a name="transcription"></a>轉錄

此設定會控制使用者是否可以使用轉接來電。 此設定預設為關閉。

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>來電轉接和同時撥打給組織中的人員

此設定會控制是否可以將來電轉接給其他使用者，或同時撥打您組織中的另一個人。 此設定預設為開啟。

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>來電轉接和同時撥打到外部電話號碼

此設定會控制來電是否可以轉接至外部號碼，或同時撥打外部號碼。 此設定預設為開啟。

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>語音信箱可用於路由輸入通話

此設定可讓輸入電話傳送至語音信箱。 預設設定是由 **使用者控制**。 有效的選項有：

- **啟用** 語音信箱一律可供輸入通話使用。
- **未啟用**  語音信箱不適用於輸入通話。
- **使用者控制** 使用者可以判斷是否要使用語音信箱。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>撥入電話可以路由至通話群組

此設定會控制是否可以將來電轉接至通話群組。 此設定預設為開啟。

### <a name="delegation-for-inbound-and-outbound-calls"></a>委派輸入和撥出電話

此設定可將撥入電話路由至代理人，讓代理人代表其具有委派許可權的使用者撥打撥出電話。 此設定預設為開啟。 如需詳細資訊，請參閱 [與代理人共用電話線](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>防止略過付費並透過 PSTN 傳送電話

開啟此設定將會透過 PSTN 傳送電話並產生費用，而不是透過網路傳送電話並略過付費。 此設定預設為關閉。

### <a name="music-on-hold-for-pstn-calls"></a>PSTN 通話音樂保留

此設定可讓您在 PSTN 來電者處於保留狀態時，開啟或關閉等候音樂。 預設會開啟此功能。 此設定不適用於通話公園和老闆代理人功能。 深入瞭解如何 [設定自訂音樂](music-on-hold.md)。

### <a name="busy-on-busy-when-in-a-call"></a>在通話中忙碌

在通話中忙碌， (也稱為「忙碌選項」) 可讓您設定當使用者已在電話或會議中，或是電話已被保留時，來電的處理方式。 新來電或來電可能會因訊號忙碌而遭拒，也可以路由至使用者的未接聽設定。 無論他們的忙碌選項設定方式為何，通話或會議中的使用者或保留通話的使用者都無法發起新的通話或會議。 此設定預設為 **[未啟用** ]。

- **未啟用** 未啟用忙碌選項，當使用者已在通話中時，新的或來電仍可傳送給使用者。
- **啟用** 新來電或來電會以忙碌訊號拒絕。
- **懸而未決** 使用者的未回答設定將會被使用，例如路由到語音信箱或轉寄給另一個使用者。
- **使用者控制** 此選項目前無法運作;如果設定的話，系統會將此值讀取為 **[未啟用]**。

### <a name="web-pstn-calling"></a>Web PSTN 通話

此設定可讓使用者使用 Teams Web 用戶端撥打 PSTN 號碼。 此設定預設為開啟。

### <a name="real-time-captions-in-teams-calls"></a>Teams 通話中的即時輔助字幕

此設定會控制 Teams 通話中的即時輔助字幕是否可供使用者使用。 此設定預設為開啟。

### <a name="automatically-answer-incoming-meeting-invites"></a>自動回答傳入的會議邀請

此設定會控制是否自動回復傳入的會議邀請。 預設為關閉。 請記住，此設定僅適用于傳入的會議邀請。 不適用於其他類型的通話。

### <a name="spam-filtering"></a>垃圾郵件篩選

此設定可讓您控制來電中可用的垃圾郵件篩選類型。 基本和 Captcha 互動式語音 (IVR) 檢查都可以執行。 此設定預設為開啟。

### <a name="sip-devices-can-be-used-for-calls"></a>SIP 裝置可用於通話

此設定可讓使用者使用 SIP 裝置撥打和接聽電話。 此設定預設為關閉。

### <a name="open-apps-in-browser-for-incoming-pstn-calls"></a>在瀏覽器中開啟應用程式以進行 PSTN 來電

此設定會控制應用程式是否自動在瀏覽器中開啟，以進行傳入 PSTN 來電給使用者。 這可以用來將輸入來電者的電話號碼傳遞至應用程式，以便在通話進行時尋找相關聯的客戶記錄。 此設定預設為關閉。

如果已開啟，必須在 URL 中提供應用程式連結， **才能在瀏覽器中開啟 PSTN 來電方塊中的應用程式** 。 您可以使用 {phone} 預留位置，將 E.164 格式的電話號碼 () 傳遞至提供的 URL。 或者，您可以提供不含任何預留位置的一般 URL。 這只會啟動列出的 URL。

![針對傳入 PSTN 通話原則設定的 [在瀏覽器中開啟應用程式] 的螢幕擷取畫面。](media/teams-open-apps-in-browser-pstn.png)

## <a name="related-articles"></a>相關文章

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[在 Teams 中將原則指派給使用者](policy-assignment-overview.md)

[PSTN 連線選項](pstn-connectivity.md)

[為您的使用者設定通話設定](user-call-settings.md)
