---
title: Microsoft Teams 中的通話政策
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中建立、修改及新增使用者至自訂通話策略，以及各種通話策略設定。
localization_priority: Normal
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
ms.openlocfilehash: 5e3cc466d855f55f63f34e798443fb285dc36c9e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162698"
---
<a name="calling-policies-in-microsoft-teams"></a>Microsoft Teams 中的通話政策
===================================

在 Microsoft Teams 中，通話政策會控制哪些通話和呼叫轉呼叫功能可供使用者使用。 通話政策會決定使用者是否可以撥打私人電話、使用呼叫轉寄或同時撥打給其他使用者或外部電話號碼、將通話路由至語音信箱、將通話傳送給通話群組、使用委派進行輸入和外寄通話等等。

您可以使用自動建立 (全組織的預設) ，或建立及指派自訂策略。

## <a name="create-a-custom-calling-policy"></a>建立自訂通話策略

請遵循下列步驟建立自訂通話策略。

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往 **語音**  >  **通話政策**。
2. 選取 [新增 **]**。
3. 開啟或關閉您想要在通話政策中使用的功能。
4. 若要控制使用者是否可以將輸入通話路由至語音信箱， **請選取** 啟用或 **使用者控制**。 若要防止路由至語音信箱，請選取 **已停用**。
5. 選取 **儲存**。

## <a name="edit-a-calling-policy"></a>編輯通話政策

請遵循這些步驟來編輯現有的通話政策。

1. 在 Microsoft Teams 系統管理中心的左側流覽中，選取 **語音**  >  **通話政策**。
2. 按一下要修改之政策旁的 ，然後選取 [ **編輯**。
3. 進行您想要的變更，然後按一下 [ **儲存**。

## <a name="assign-a-custom-calling-policy-to-users"></a>指派自訂通話策略給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>通話策略設定

以下是您可以針對通話策略所設定設定。

### <a name="make-private-calls"></a>可進行私人通話

此設定控制 Teams 中所有的通話功能。 關閉此功能以關閉 Teams 中所有的通話功能。

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>呼叫轉譯和同時撥打給貴組織人員

此設定可控制來電是否可以轉往其他使用者，或可以同時撥打給其他人。 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>呼叫轉轉和同時撥打到外部電話號碼

此設定可控制來電是否可以轉往外部號碼，或是否可以同時撥打外部號碼。

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>語音信箱可用於路由輸入通話

此設定可讓您將來電傳入語音信箱。 有效的選項為：

- **已啟用** 語音信箱隨時可供輸入通話使用。
- **已停用**  語音信箱不適用於來電。
- **使用者控制** 使用者可以決定是否想要語音信箱可用。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>可路由來電至通話群組 

此設定會控制是否可以將來電轉往通話群組。

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>允許委派傳入和外接通話

此設定可讓來電路由至代理人，允許代理人代表他們擁有委派許可權的使用者進行外接通話。 詳細資訊，請參閱 [與代理人共用電話線](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>防止免付費，並透過 PSTN 傳送通話 

將此選項設定為 **[開** 」 會透過 PSTN 傳送通話，並產生費用，而不是透過網路傳送電話並忽略付費。

### <a name="busy-on-busy-is-available-while-in-a-call"></a>通話時可在忙碌中忙碌

在忙碌 (忙碌選項) 是一個新的設定，可讓您設定當使用者已經在通話或會議或保留通話時如何處理來電。 新的或來電可能會以忙碌訊號拒絕。 您可以在租使用者層級或使用者層級啟用忙碌選項。 無論其忙碌選項的組組方式如何，通話或會議中的使用者或保留通話的使用者，都不得啟動新的通話或會議。 此設定預設為停用。

### <a name="allow-web-pstn-calling"></a>允許 Web PSTN 通話

此設定可讓使用者使用 Teams Web 用戶端撥打 PSTN 號碼。

### <a name="allow-music-on-hold"></a>允許等候音樂

這項設定可讓您在 PSTN 來電者處於保留狀態時開啟或關閉等候音樂。 預設為開啟。 此設定不適用於通話駐場和老闆代理人功能，目前僅能透過 PowerShell 使用。

## <a name="related-topics"></a>相關主題

[Set-CSTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[在 Teams 中將原則指派給使用者](assign-policies.md)