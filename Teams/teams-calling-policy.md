---
title: 通話 Microsoft Teams 中的原則：呼叫和來電轉接功能
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中建立、修改及新增自訂呼叫原則，以及各種通話原則設定。
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
ms.openlocfilehash: e38a566e025c711a9b17a050137e67af7507e63d5c5e829ba4448ee4a1577790
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309242"
---
#  <a name="calling-and-call-forwarding-in-teams"></a>Teams 中的呼叫及來電轉接

在 Microsoft Teams 中，通話原則可控制使用者可使用哪些通話和通話轉接功能。 呼叫原則決定使用者是否可以撥打私人電話、使用來電轉接或同時撥打至其他使用者或外部電話號碼、將來電路由傳送至語音信箱、傳送呼叫至通話群組，以及使用委派進行內送和撥出電話等等。

您可以使用全域 (組織內預設建立的預設) 原則，或建立及指派自訂原則。

## <a name="create-a-custom-calling-policy"></a>建立自訂通話原則

請遵循下列步驟來建立自訂呼叫原則。

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 **語音**  >  **通話原則**。
2. 選取 ****[新增]。
3. 開啟或關閉您想要在通話原則中使用的功能。
4. 若要控制使用者是否可以將來電路由到語音信箱，請選取 ****[已啟用] 或 ****[使用者控制]。 若要防止路由至語音信箱，請選取 ****[已停用]。
5. 選取 ****[儲存]。

## <a name="edit-a-calling-policy"></a>編輯通話原則

請遵循下列步驟來編輯現有的呼叫原則。

1. 在 Microsoft Teams 系統管理中心的左側導覽中，選取 [**語音**  >  **通話原則**]。
2. 按一下您要修改之原則旁的 [下一步]，然後選取 [ **編輯**]。
3. 進行所需的變更，然後按一下 [ **儲存**]。

## <a name="assign-a-custom-calling-policy-to-users"></a>指派自訂通話原則給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>通話原則設定

以下是您可以針對通話原則進行設定的設定。

### <a name="make-private-calls"></a>進行私人通話

此設定會控制 Teams 中的所有呼叫功能。 關閉此功能可關閉 Teams 中的所有通話功能。

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>通話轉接和同步鈴響給組織中的人員

此設定會控制是否可以轉寄來電給其他使用者，或同時撥打另一位人員。 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>通話轉接和同步鈴響給外部電話號碼

此設定會控制是否可將來電轉送到外部號碼，或同時撥打外部號碼。

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>可使用語音信箱路由來電

此設定可讓輸入呼叫傳送至語音信箱。 有效的選項包括：

- **已啟用** 語音信箱永遠可用於撥入電話。
- **停用**  語音信箱無法用於撥出電話。
- **使用者控制** 使用者可以決定是否要使用語音信箱。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>接入通話可以被路由到通話群組

此設定控制是否可將來電轉接至通話群組。

### <a name="delegation-for-inbound-and-outbound-calls"></a>撥入和撥出電話的委派

此設定可讓輸入呼叫路由傳送至代理人，讓代理人代表其委派許可權的使用者撥出電話。 如需詳細資訊，請參閱 [與代理人共用電話線](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>禁止透過 PSTN 進行來電任意轉接與傳送通話 

設定為 [ **開啟] 時** ，會透過 PSTN 傳送來電，而不是透過網路傳送來電，而是略過電話費。

### <a name="busy-on-busy-is-available-when-in-a-call"></a>通話中有空閒的占線

忙碌忙碌 (繁忙選項) 可讓您設定使用者已在通話或會議中，或具有暫止通話時處理來電的方式。 您可以使用繁忙的信號拒絕新的或來電，也可以據此傳送使用者未應答的設定。 您可以在租使用者層級或在使用者層級啟用忙碌選項。 不論其忙碌選項的設定方式，通話或會議中的使用者或是具有「保留」通話的使用者，都不會妨礙他們發起新的通話或會議。 預設會停用此設定。

### <a name="web-pstn-calling"></a>Web PSTN 通話

此設定可讓使用者使用 Teams 網頁用戶端呼叫 PSTN 號碼。

### <a name="incoming-meeting-invites-are-automatically-answered"></a>自動回應傳入的會議邀請

此設定會控制是否自動回應傳入會議邀請。 它預設為關閉狀態。 請記住，此設定只適用于傳入會議邀請。 這不適用於其他類型的來電。

### <a name="allow-music-on-hold"></a>允許等候音樂

當 PSTN 來電者處於暫止狀態時，此設定可讓您開啟或關閉等候的音樂。 預設為開啟。 此設定不適用於通話駐留和上司委派功能，而且目前僅可透過 PowerShell 取得。

## <a name="related-articles"></a>相關文章

[CSTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[將原則指派給 Teams 中的使用者](assign-policies.md)
