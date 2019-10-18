---
title: 在 Microsoft 團隊中呼叫原則
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 05/06/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中呼叫原則設定。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-voice
f1keywords:
- ms.teamsadmincenter.callingpolicies.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 788cc0e93b16585f1d3424d3bfa0a62693528740
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570267"
---
<a name="calling-policies-in-microsoft-teams"></a>在 Microsoft 團隊中呼叫原則
===================================

在 Microsoft 團隊中，通話原則控制使用者可以使用哪些通話和來電轉接功能。 通話原則決定使用者是否可以進行私人通話、使用來電轉接或同時撥打給其他使用者或外部電話號碼、將呼叫路由至語音信箱、傳送來電給通話群組、使用委派撥入和撥出通話等等。 預設的全域原則會自動建立，但系統管理員也可以建立並指派自訂通話原則。

## <a name="create-a-custom-calling-policy"></a>建立自訂通話原則

請依照這些步驟來建立自訂通話原則。

1. 在 Microsoft [團隊管理中心] 中，選取 [**語音** > **通話原則**]。
2. 選取 [**新增原則**]。
3. 開啟您想要在通話原則中使用的功能。 所有選取專案預設都是**關閉**的。
4. 若要控制使用者是否可以將來電路由到語音信箱，請選取 [**永遠啟用**] 或 [**使用者控制**]。 若要避免傳送語音信箱，請選取 [**永遠停用**]。
5. 選取 [**儲存**]。

## <a name="modify-an-existing-calling-policy"></a>修改現有的通話原則

請依照這些步驟來修改現有的通話原則。

1. 在 Microsoft [團隊管理中心] 中，選取 [**語音** > **通話原則**]。
2. 按一下您要修改的原則旁邊的，然後選取 [**編輯**]。
3. 開啟您想要在通話原則中使用的功能。 所有選取專案預設都是**關閉**的。
4. 若要控制使用者是否可以將來電路由到語音信箱，請選取 [**永遠啟用**] 或 [**使用者控制**]。 若要避免傳送語音信箱，請選取 [**永遠停用**]。
5. 選取 [**儲存**]。

## <a name="assign-a-calling-policy-to-a-user"></a>指派通話原則給使用者

請依照下列步驟，將自訂通話原則指派給使用者。

1. 在 Microsoft [團隊管理中心] 中，選取 [**語音** > **通話原則**]。
2. 按一下 [原則名稱] 旁的，選取它，然後選取 [**管理使用者**]。
3. 在 [**管理使用者**] 窗格中，搜尋使用者的名稱。 （您必須至少輸入三個字元。）
4. 選取使用者的名稱，然後選取 [**新增**]。
5. 選取 [**儲存**]。

## <a name="calling-policy-settings"></a>通話原則設定

使用下列設定來建立自訂通話原則。

### <a name="user-can-make-private-calls"></a>使用者可以撥打私人電話

此設定控制團隊中的所有通話功能。 關閉 [關閉] 以關閉小組中的所有通話功能。

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a>來電轉接及同時撥打給其他使用者

此設定控制是否可將來電轉寄給其他使用者，或是同時撥打其他人。 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>來電轉接及同時撥打至外部電話號碼

此設定控制是否可將來電轉移至外部號碼，或同時撥打外部號碼。

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a>[語音信箱] 可用於傳送來電給使用者

此設定可讓撥入呼叫傳送至語音信箱。 有效的選項包括：

   - **永遠啟用**來電時，語音信箱總是可以使用。 
   - **永遠停用** 來電無法使用語音信箱。 
   - **使用者控制**。 使用者可以決定是否要使用語音信箱。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>輸入通話可以傳送給通話群組 

> [!Include [feature preview](includes/preview-feature.md)]

此設定控制是否可以將來電轉移到通話群組。

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>允許委派撥入和撥出通話

> [!Include [feature preview](includes/preview-feature.md)]

此設定可讓撥入呼叫路由至代理人，允許代理人代表他們擁有委派許可權的使用者撥出電話。 如需詳細資訊，請參閱[與代理人共用電話線路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。


### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>透過 PSTN 避免付費旁路並傳送來電 

將此設定為 [**開啟**] 會透過 PSTN 傳送呼叫並產生費用，而不是透過網路傳送通話，而是避開 tolls。

### <a name="busy-on-busy-is-available-while-in-a-call"></a>通話時可使用 [忙碌] 功能

繁忙（忙選項））是小組通話原則中的新設定，可讓您設定當使用者已在通話或會議中，或有來電處於保留狀態時，處理來電的方式。 您可以使用占線信號拒絕新的或來電的通話。 您可以在租使用者層級或使用者層級啟用 busy 選項。 不論其忙碌選項的設定方式為何，通話或會議中的使用者，或使用保留通話的使用者，都不會阻止您開始新的通話或會議。 此設定預設為停用。

## <a name="see-also"></a>另請參閱

[Set-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)