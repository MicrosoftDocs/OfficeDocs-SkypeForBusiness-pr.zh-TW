---
title: 從商務用 Skype 內部部署（Microsoft 團隊）升級至團隊
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從商務用 Skype 升級至 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11252c916224393c19ebc11c4c40faceab02342c
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940666"
---
# <a name="coexistence-with-teams-and-skype-for-business"></a>與團隊和商務用 Skype 共存

本文將說明當您在同一個組織中執行兩個小組和商務用 Skype 用戶端時可能遇到的行為，無論使用何種模式和要使用哪種升級方法：

- [會議](#meetings)
- [互通性](#interoperability)
- [團隊交談-互通性與原生執行緒](#teams-conversations---interop-versus-native-threads)
- [目前狀態](#presence)
- [同盟](#federation)
- [連絡人](#contacts)



## <a name="meetings"></a>會議

無論其模式為何，使用者都可以加入受邀者（無論是商務用 Skype 或團隊）所邀請的任何類型的會議。  不過，使用者必須以符合會議類型的對應用戶端加入會議：

- 如果會議是「團隊」會議，所有參與者都 (他們是 TeamsOnly、孤島或商務用 Skype 使用者) 使用團隊用戶端加入會議。 如果未安裝團隊，則在試圖加入會議時，該使用者會被導向網頁。

- 如果會議是商務用 Skype 會議，所有參與者都 (他們是 TeamsOnly、孤島或商務用 Skype 使用者) 使用商務用 Skype 用戶端加入會議。 如果未安裝商務用 Skype 用戶端，使用者將會透過 Skype 會議應用程式導向網頁進行加入。

組織會議時，排程的會議類型是以召集人的模式為基礎，如下表所示：

| 召集人模式    |      行為 |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    安排在團隊中的所有會議。 Outlook 中無法使用商務用 Skype 增益集。 | 
| SfbWithTeamsCollab, SfbOnly   | 在商務用 Skype 中排程的所有會議。 Outlook 中無法使用 [團隊] 增益集。 | 
| 離島 | 根據預設，可以在商務用 Skype 或團隊中排程會議。 您可以在 Outlook 中使用這兩個增益集。 不過，您可以選擇性地要求在 Islands 中的使用者使用 PreferredMeetingProviderForIslandsMode = 團隊指派 TeamsMeetingPolicy 的實例，在小組中隨時排程會議。| 


## <a name="interoperability"></a>互通性

在某些情況下，小組支援與商務用 Skype ) 的互通性 ( 「交互操作」。 互通性通訊指的是商務用 Skype 使用者與團隊使用者之間的交談或通話。  交互操作通訊只可以在兩個使用者之間取得;不支援多方聊天/通話或新增其他使用者。

當下列各項都成立時，就會建立兩個使用者之間的互通性聊天或通話：

- 一位使用者使用的是 [商務用 Skype]。

- 初始通訊的收件者模式不是孤島 (否則，如果兩個使用者都在同一個組織中，通訊就會在相同的用戶端) 中土地。 在聯盟案例中，傳送使用者使用的是 [小組]，而收件者則不是 TeamsOnly 模式。 

- 團隊使用者也不會將商務用 Skype 帳戶駐留在內部部署中。 

在交互操作通訊中，聊天只是純文字。 此外，在 *交互操作聊天本身中*不可能進行檔案共用和螢幕共用。 不過，交互操作交談中的使用者可以從互通性聊天中建立點播會議，輕鬆地達到檔案和/或螢幕共用，如下所述：

- 如果小組使用者嘗試共用其畫面，系統會自動建立一個點播團隊會議，而該會議的邀請連結會傳送到商務用 Skype 使用者的用戶端。 按一下連結時，商務用 Skype 使用者將會開啟團隊並加入會議。 兩個使用者現在都在團隊會議中，而且可以視需要共用。

- 如果商務用 Skype 使用者使用的是2018或更新版本的用戶端，且試圖共用任何內容，則會自動建立點播商務用 Skype 會議，而該會議的邀請連結會傳送給團隊使用者的用戶端。 當您按一下連結時，小組使用者會嘗試加入商務用 Skype 會議。 如果團隊使用者已安裝商務用 Skype 用戶端，則會開啟並提示使用者登入 (（如果尚未登入) ）。  如果團隊使用者沒有安裝商務用 Skype 用戶端，系統會提示使用者使用 web 版本。 這兩個使用者登入之後，他們就在商務用 Skype 會議中，而且可以視需要共用。

## <a name="teams-conversations---interop-versus-native-threads"></a>團隊交談-互通性與原生執行緒

因為互通性通訊不支援原生團隊交談的所有功能，所以團隊用戶端會為小組對團隊以及商務用 Skype 通訊提供獨立的交談執行緒。 這些交談在使用者介面中會以不同的方式呈現：互通性執行緒可以與一般原生團隊執行緒區別：

- 不需要豐富的文字、檔案/螢幕共用、無法新增使用者的控制項。
- 針對目標使用者的圖示所做的修改，顯示商務用 Skype 的「S」。

下列螢幕擷取畫面顯示這些差異：

與使用者 G3 測試的原生團隊與團隊交談

![顯示原生團隊與團隊交談的圖表](media/teams-upgrade-native-thread.png)

具有相同使用者 G3 測試的互通性交談

![顯示互通性團隊與團隊交談的圖表](media/teams-upgrade-interop-thread.png)

建立交談執行緒之後，其類型就不會變更。 建立後，小組中的互通性執行緒將永遠會傳送給目標使用者的商務用 Skype 用戶端。 原生執行緒永遠會傳送給目標使用者的團隊用戶端。  如果收件者使用者的模式變更，現有的團隊執行緒將無法正常運作，而且會在該聊天上顯示一則筆記，其中包含開始新的原生交談的連結，如下列螢幕擷取畫面所示。


![顯示已升級的商務用 Skype 使用者聊天的圖表](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

## <a name="presence"></a>目前狀態

指定使用者的「目前狀態」是依據客戶在服務中的活動。 隨後便會發佈目前狀態，供其他使用者查看。  商務用 Skype 與團隊是獨立用戶端的個別服務，所以每個服務都有自己的狀態供使用者使用。   在團隊與商務用 Skype Online 中的目前狀態服務之間也有同步處理。  這可讓一個服務視需要從其他服務發佈使用者的目前狀態。 

目前狀態發佈行為是以使用者的模式為基礎。 以下是三種基本案例：

- 如果使用者處於 TeamsOnly 模式，則所有其他使用者都會看到該使用者的小組目前狀態，不論他們使用的是哪一個用戶端。

- 如果使用者是在任何商務用 Skype 模式中，所有其他使用者都會看到該使用者的商務用 Skype 目前狀態，不論他們使用的是哪一種用戶端。

- 如果使用者使用的是孤島模式，在商務用 Skype 中發佈的目前狀態就是獨立的，因此同一個組織中的使用者所顯示的目前狀態將視其他使用者的用戶端而定。 同盟組織中的使用者會根據商務用 Skype 活動查看該使用者的目前狀態，因為在商務用 Skype 中，來自孤島模式使用者的聯盟流量。

例如，假設使用者 A 處於孤島模式。 如果使用者 A 在小組中使用中，但尚未登入商務用 Skype，其他使用者就會看到使用者 A 從其小組用戶端使用，但在其商務用 Skype 用戶端中，他們會看到使用者 A 為離線狀態。 這是由於設計，因為使用者 A 不在執行用戶端，所以無法到達。 


## <a name="federation"></a>同盟

從小組聯盟到另一個使用商務用 Skype 的使用者，必須讓團隊使用者在商務用 Skype 中駐留在線上。 TeamsUpgradePolicy 會控制傳入的同盟聊天和通話的路由。 同盟路由行為與與相同租使用者案例相同，但在孤島模式除外。 當收件者處於孤島模式時：

- 如果收件者是聯盟租使用者，則會從商務用 Skype 中的 [小組] 土地開始聊天和通話。
- 如果收件者在相同的租使用者中，就會從團隊中的團隊土地開始聊天和通話。
- 從商務用 Skype 發起的聊天和通話，在商務用 Skype 中永遠不間斷。

聯盟聊天可以是本機執行緒或交互操作執行緒。 請參閱 [小組交談---互通性與本機執行緒](#teams-conversations---interop-versus-native-threads)。

- 如果收件者和寄件者都在 TeamsOnly 升級模式中，則交談將是一個固有的聊天體驗，包括所有豐富的訊息和呼叫功能。 若要深入瞭解，請閱讀 [團隊中的外部 (聯盟) 使用者的原生聊天體驗](native-chat-for-external-users.md)。 

- 如果其中一個交談參與者不在 TeamsOnly 升級模式中，則交談仍會有純文字訊息的交互操作體驗。 使用者介面會以與同一個租使用者交互操作執行緒相似的方式公開同盟聊天，但有一個指示使用者是外部的筆記。

如需更多詳細資料，請參閱在團隊中管理[外部 (聯盟) 使用者](native-chat-for-external-users.md)的[Microsoft 團隊中的外部存取](manage-external-access.md)及原生聊天體驗。

## <a name="contacts"></a>連絡人

[小組] 和 [商務用 Skype] 有不同的連絡人清單。 這表示在單一系統中所做的連絡人新增、移除及修改，不會與其他系統同步處理。 不過，當兩個特定事件發生時，商務用 Skype 的連絡人會自動複製到小組中： 

- 針對任何商務用 Skype Online 使用者，第一次登入小組時，商務用 Skype 的連絡人將會複製到小組。  在商務用 Skype Server 中擁有內部部署帳戶的使用者無法使用此行為。  

- 在使用者升級至 TeamsOnly (之後，您可以透過指派 TeamsUpgradePolicy 或移動 Move-csuser-MoveToTeams) ，下次使用者登入小組時，商務用 Skype 中現有的連絡人將會與已存在於團隊中的現有連絡人合併。 不論使用者的商務用 Skype 帳戶是駐留在內部部署還是線上，都會發生此行為。 

在這兩種情況下，從商務用 Skype 將連絡人轉移至團隊是非同步，因此可能需要幾分鐘的時間，才會在團隊中顯示連絡人。 上述兩個事件會觸發複本。  

## <a name="related-links"></a>相關連結

[與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南](migration-interop-guidance-for-teams-with-skype.md) 

[在商務用 Skype Server 與 Microsoft 365 或 Office 365 之間設定混合式連接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存與升級設定](setting-your-coexistence-and-upgrade-settings.md)

[授與 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議遷移服務 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

