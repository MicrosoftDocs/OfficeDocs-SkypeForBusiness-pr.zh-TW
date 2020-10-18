---
title: 在 Microsoft 團隊中呼叫原則
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中建立、修改及新增使用者至自訂通話原則，以及各種通話原則設定。
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
ms.openlocfilehash: 03ec48de66bc5b179b3a1d8cfe006b1789d09a33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48581097"
---
<a name="calling-policies-in-microsoft-teams"></a>在 Microsoft 團隊中呼叫原則
===================================

在 Microsoft 團隊中，通話原則控制使用者可以使用哪些通話和來電轉接功能。 通話原則決定使用者是否可以進行私人通話、使用來電轉接或同時撥打給其他使用者或外部電話號碼、將呼叫路由至語音信箱、傳送來電給通話群組、使用委派撥入和撥出通話等等。

您可以使用全域 (組織範圍的預設) 原則，此原則會自動建立，或建立並指派自訂原則。

## <a name="create-a-custom-calling-policy"></a>建立自訂通話原則

請依照這些步驟來建立自訂通話原則。

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至**語音**  >  **通話原則**。
2. 選取 [ **新增**]。
3. 開啟或關閉您想要在通話原則中使用的功能。
4. 若要控制使用者是否可以將來電路由到語音信箱，請選取 [ **已啟用** ] 或 [ **使用者控制**]。 若要避免傳送語音信箱，請選取 [ **停用**]。
5. 選取 [ **儲存**]。

## <a name="edit-a-calling-policy"></a>編輯通話原則

請依照下列步驟編輯現有的通話原則。

1. 在 Microsoft [團隊管理中心] 的左導覽中，選取 [**語音**  >  **通話原則**]。
2. 按一下您要修改的原則旁邊的，然後選取 [ **編輯**]。
3. 進行您想要的變更，然後按一下 [ **儲存**]。

## <a name="assign-a-custom-calling-policy-to-users"></a>將自訂通話原則指派給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>通話原則設定

以下是您可以針對通話原則設定的設定。

### <a name="make-private-calls"></a>可進行私人通話

此設定控制團隊中的所有通話功能。 關閉 [關閉] 以關閉小組中的所有通話功能。

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>來電轉接及同時撥打給組織中的人員

此設定控制是否可將來電轉寄給其他使用者，或是同時撥打其他人。 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>來電轉接及同時撥打至外部電話號碼

此設定控制是否可將來電轉移至外部號碼，或同時撥打外部號碼。

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>可傳送來電的語音信箱

此設定可讓撥入呼叫傳送至語音信箱。 有效的選項包括：

- **已啟用** 來電時，語音信箱總是可以使用。
- **停用**  來電無法使用語音信箱。
- **使用者控制** 使用者可以決定是否要使用語音信箱。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>輸入通話可以傳送給通話群組 

> [!Include [feature preview](includes/preview-feature.md)]

此設定控制是否可以將來電轉移到通話群組。

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>允許委派撥入和撥出通話

> [!Include [feature preview](includes/preview-feature.md)]

此設定可讓撥入呼叫路由至代理人，允許代理人代表他們擁有委派許可權的使用者撥出電話。 如需詳細資訊，請參閱 [與代理人共用電話線路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>透過 PSTN 避免付費旁路並傳送來電 

將此設定為 [ **開啟** ] 會透過 PSTN 傳送呼叫並產生費用，而不是透過網路傳送通話，而是避開 tolls。

### <a name="busy-on-busy-is-available-while-in-a-call"></a>通話時可使用 [忙碌] 功能

[忙碌] (的 [忙碌] 選項) 是一種新設定，可讓您設定當使用者已在通話或會議中，或有來電處於保留狀態時，處理來電的方式。 您可以使用占線信號拒絕新的或來電的通話。 您可以在租使用者層級或使用者層級啟用 busy 選項。 不論其忙碌選項的設定方式為何，通話或會議中的使用者，或使用保留通話的使用者，都不會阻止您開始新的通話或會議。 此設定預設為停用。

### <a name="allow-web-pstn-calling"></a>允許網路 PSTN 通話

此設定可讓使用者使用團隊網頁用戶端呼叫 PSTN 號碼。

### <a name="allow-music-on-hold"></a>允許暫停音樂

此設定可讓您在保留 PSTN 呼叫者時，開啟或關閉 [等候音樂]。 預設為開啟。 此設定不適用於通話駐留和上司委派功能，目前僅可透過 PowerShell 取得。

## <a name="related-topics"></a>相關主題

[Set-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[指派策略給小組中的使用者](assign-policies.md)
