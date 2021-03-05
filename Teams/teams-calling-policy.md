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
description: 瞭解如何在 Microsoft Teams 中建立、修改及新增使用者至自訂通話政策，以及各種通話政策設定。
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
ms.openlocfilehash: 6cfa0043b4da6c3087c0e144bb0759ed5b87f01c
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "50465465"
---
<a name="calling-policies-in-microsoft-teams"></a>Microsoft Teams 中的通話政策
===================================

在 Microsoft Teams 中，通話政策可控制使用者可以使用哪些通話和呼叫轉呼叫功能。 通話政策會決定使用者是否可以撥打私人電話、使用呼叫轉寄或同時撥打給其他使用者或外部電話號碼、將通話路由到語音信箱、將通話傳送給通話群組、使用委派進行輸入和外送通話等等。

您可以使用自動建立 (全組織的預設) 或建立及指派自訂策略。

## <a name="create-a-custom-calling-policy"></a>建立自訂通話政策

請遵循下列步驟建立自訂通話政策。

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往 **語音**  >  **通話政策**。
2. 選取 [新增 **]**。
3. 開啟或關閉通話政策中想要使用的功能。
4. 若要控制使用者是否可以將輸入通話路由到語音信箱，**請選取啟用****或使用者控制**。 若要防止路由到語音信箱，請選取已 **停用**。
5. 選取 **儲存**。

## <a name="edit-a-calling-policy"></a>編輯通話政策

請遵循下列步驟來編輯現有的通話政策。

1. 在 Microsoft Teams 系統管理中心的左側流覽中，選取 **語音**  >  **通話政策**。
2. 按一下要修改之政策旁，然後選取 [ **編輯**。
3. 進行您想要的變更，然後按一下 **[儲存**。

## <a name="assign-a-custom-calling-policy-to-users"></a>指派自訂通話政策給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>通話政策設定

以下是您可以設定通話策略的設定。

### <a name="make-private-calls"></a>可進行私人通話

此設定會控制 Teams 中所有的通話功能。 關閉此功能以關閉 Teams 中所有的通話功能。

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>呼叫轉譯和同時撥打給貴組織人員

此設定會控制來電是否可以轉接給其他使用者，或同時撥打給其他人。 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>呼叫轉譯和同時撥打到外部電話號碼

此設定會控制來電是否可以轉接至外部號碼，或同時撥打外部號碼。

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>語音信箱可用於路由輸入通話

此設定可讓內送電話撥打到語音信箱。 有效的選項有：

- **已啟用** 語音信箱一直可用於來電。
- **已停用**  語音信箱不適用於來電。
- **使用者控制** 使用者可以決定是否要提供語音信箱。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>來電可以路由至通話群組 

此設定會控制來電是否可以轉接到通話群組。

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>允許委派電話的內線和外接電話

此設定可讓來電路由至代理人，允許代理人代表他們擁有委派許可權的使用者進行外線通話。 詳細資訊請參閱與代理人 [共用電話線](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>防止付費旁路，並透過 PSTN 傳送電話 

將這項設定設定為 **[開** 」 會透過 PSTN 傳送通話，並產生費用，而不是透過網路傳送電話並避開付費。

### <a name="busy-on-busy-is-available-while-in-a-call"></a>在通話中時，忙碌在忙碌中可以使用

忙碌中 (忙碌選項) 是一個新的設定，可讓您設定當使用者已經在通話或會議或保留通話時如何處理來電。 您可以使用忙碌訊號拒絕新的或來電。 您可以在租使用者層級或使用者層級啟用忙碌選項。 無論他們的忙碌選項是如何配置的，通話或會議中的使用者，或保留通話的使用者，都無法啟動新的通話或會議。 此設定預設為停用。

### <a name="allow-web-pstn-calling"></a>允許 Web PSTN 通話

此設定可讓使用者使用 Teams Web 用戶端撥打 PSTN 號碼。

### <a name="allow-music-on-hold"></a>允許等候音樂

這項設定可讓您在 PSTN 來電者處於保留狀態時開啟或關閉等候音樂。 它預設為開啟。 此設定不適用於通話公園和老闆代理人功能，目前僅能透過 PowerShell 使用。

## <a name="related-topics"></a>相關主題

[Set-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[在 Teams 中將原則指派給使用者](assign-policies.md)
