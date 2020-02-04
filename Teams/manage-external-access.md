---
title: 在 Microsoft 團隊中管理外部存取（同盟）
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- ms.teamsadmincenter.externalaccess.overview
description: 您的小組或 IT 系統管理員可以為其他網域設定外部存取（同盟），讓來自這些網域的使用者參與團隊。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: a04a5547e13b8b93864b1b23dc598b08877c745a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707288"
---
<a name="manage-external-access-in-microsoft-teams"></a>在 Microsoft 團隊中管理外部存取
======================================================

外部存取是從整個網域中的外部團隊使用者尋找、通話、聊天，以及在團隊中設定會議的一種方式。 您也可以使用外部存取來與仍在使用商務用 Skype （線上和內部部署）及 Skype （即將2020）的外部使用者進行通訊。

如果您想讓外部使用者存取團隊和頻道，來賓存取可能是更好的作法。 如需外部存取與來賓存取之間差異的詳細資訊，請參閱[比較外部與來賓存取](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。 

在下列情況中使用外部存取：
  
- 您在不同網域中擁有需要共同作業的使用者。 例如，Rob@contoso.com 和 Ann@northwindtraders.com 是與其他人一起與 contoso.com 和 northwindtraders.com 網域中的部分專案共同作業。

- 您希望貴組織中的人員可以使用團隊與組織外部的特定企業中的人員聯繫。

- 您希望世界各地的其他人都能使用您的電子郵件地址，找出並與您聯繫。 




> [!IMPORTANT]
> 目前，若要將 Microsoft 團隊應用程式內的外部使用者聯盟到您組織外部的外部使用者（目前不是 Azure Active Directory （Azure AD）或租使用者的來賓），您必須正確地設定混合式並移至商務用 Skype Online。 從2019年2月25日起，小組不支援原生同盟，且不需要 SIP 設定檔的使用者駐留在商務用 Skype Online 中。 如需進一步瞭解如何將您的帳戶設定成混合式，然後移至小組，請參閱將[商務用 Skype 混合式部署升級至團隊](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)。






## <a name="plan-for-external-access"></a>規劃外部存取

根據預設，會開啟 [小組] 中的外部存取，這表示您的組織可以與所有外部網域進行通訊。 如果您新增封鎖的網域，則允許所有其他網域;而且如果您新增 [允許的網域]，所有其他網域都會遭到封鎖。 在 [小組管理中心] 中設定外部存取的情況有三種（**全組織設定** > **外部存取**）：

- **開啟同盟**：這是團隊中的預設設定，可讓組織中的人員找出、通話、聊天，以及在任何網域中與組織外部的人員進行會議。

    在此案例中，您的使用者可以與執行團隊或商務用 Skype 的所有外部網域進行通訊，並使用開啟的同盟，或已將您的網域新增至其允許清單。

- [**允許特定網域**]：若要將網域新增至 [**允許**] 清單，您只需將外部存取許可權制為 [允許的網域]。 一旦您設定了允許的網域清單，所有其他網域都會遭到封鎖。 若要允許特定網域，按一下 [**新增網域**]，新增功能變數名稱，按一下 [**動作] 以在這個網域上執行**，然後選取 [**允許**]。

- **封鎖特定網域**-只要將網域新增至**封鎖**清單，您就可以與所有外部網域通訊，*除了*您封鎖的以外。 若要封鎖特定網域，按一下 [**新增網域**]，新增功能變數名稱，按一下 [**動作] 以在這個網域上執行**，然後選取 [**封鎖**]。 一旦您設定封鎖網域的清單，所有其他網域都會被允許。

## <a name="allow-or-block-domains"></a>允許或封鎖網域

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a>步驟 1-讓您的組織與其他小組組織溝通

![](media/teams-logo-30x30.png)**使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示  

1. 在左側導覽中，移至 [**全組織性設定** > **外部存取**]。

2. 切換**使用者可以與商務用 Skype 通訊，並將小組使用者**切換到 [**開啟**]。

     ![開啟外部訪問切換開關的螢幕擷取畫面](media/manage-external-access-2.png).

3. 如果您想要讓所有團隊組織都與您組織中的使用者通訊，請跳至步驟5。

4. 如果您想要限制可與您組織中的使用者通訊的組織，您可以允許除部分網域以外全部，或只允許特定的網域。 

    - 若要允許除部分網域以外的所有網域，請按一下 [**新增網域**]，新增您要封鎖的網域。 在 [**新增網域**] 窗格中，輸入功能變數名稱，按一下 [**封鎖**]，然後按一下 [**完成**]。 
    - 若要限制特定組織的通訊，請將這些網域新增至狀態為 [**允許**] 的清單中。 一旦您將任何網域新增至 [允許] 清單，與其他組織的通訊就會受到限制，僅限那些網域位於 [允許] 清單中的組織。 

5. 按一下 [**儲存**]。

6. 確定其他小組組織中的系統管理員完成這些相同的步驟。 例如，在他們的 [**允許的網域**] 清單中，他們的系統管理員必須在限制可與使用者通訊的組織時，才能為您的企業輸入網域。

### <a name="step-2---test-it"></a>步驟 2-測試

若要測試您的設定，您需要不在防火牆後的小組使用者。
  
1. 在您與組織的管理員變更**外部存取**設定之後，您就應該可以開始使用。

2. 在 [團隊] 應用程式中，搜尋人員的電子郵件地址，然後傳送要求到聊天。

3. 請您的小組連絡人向您傳送聊天的要求。 如果您沒有收到他們的要求，問題就是您的防火牆設定（假設他們已確認其防火牆設定正確）。

4. 測試問題是否為您防火牆的另一種方法，就是移至不在防火牆背後的 WiFi 位置。 例如咖啡廳，然後使用小組將要求傳送給您的連絡人進行聊天。 如果郵件是在 WiFi 位置進行，但不在您工作時，您知道問題是您的防火牆。

> [!NOTE]
> 如果您與另一位使用者同時開啟外部存取並允許其他人的網域，這將會運作。 如果沒有作用，則其他使用者必須確定其設定沒有封鎖您的網域。

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>在商務用 Skype Online 組織中與使用者通訊

如果您要設定 [外部存取]，讓您的小組使用者在商務用 Skype 組織中找到並與使用者聯繫，以限制誰可以與其使用者聯繫，請依照步驟將您的網域中的外部存取權設定為其他組織的網域。 然後要求其他組織中的系統管理員，按照下列步驟來設定商務用 Skype Online 的外部存取。 

如需一般的商務用 Skype Online 案例的相關指導，請參閱以下[常見的外部存取案例](#common-external-access-scenarios)。

![](media/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示

讓該組織中的系統管理員執行下列步驟：

1. 在 Microsoft 365 系統管理中心，移至 [系統**管理中心** > ]**團隊 & Skype** > **舊版入口網站**。
  
2. 在**商務用 Skype 系統管理中心**中，選擇 [**組織** > **外部通訊**]。

3. 若要設定與特定企業或其他網域中的使用者通訊，請在下拉式方塊中，選擇 [**只對允許的網域開啟**]。

    或者，如果他們想要啟用與世界上已開啟商務用 Skype 原則的其他人通訊，請選擇 [**封鎖的網域除外**]。 這是預設設定。

4. 在 [**封鎖或允許**的網域**+**] 下，選擇 []，然後新增您想要允許的功能變數名稱。

## <a name="common-external-access-scenarios"></a>常見的外部存取案例

|**如果您想要 .。。**  |**執行此動作**  |
|---------|-----------------------|
|讓您組織中的**小組使用者**與另一個（外部）組織中的**小組使用者**通訊。|在 [外部存取] 中，將外部網域新增至 [允許] 清單或使用 [開啟同盟]。 然後讓其他團隊組織中的系統管理員執行相同的動作。      |
|讓您組織中的**小組使用者**與同一個組織中的**商務用 Skype Online 使用者**通訊。  |啟用共存模式，或選擇孤島升級模式，以支援貴組織中的商務用 Skype 使用者。   |
|讓您組織中的**小組使用者**與另一個（外部）組織中的**商務用 Skype Online 使用者**通訊。      |在 [外部存取] 中，將外部網域新增至 [允許] 清單或使用 [開啟同盟]。 <br><br>開啟 [**使用者可以與商務用 Skype 和小組使用者通訊]，並**在外部存取中設定。 然後讓其他團隊組織中的系統管理員執行相同的動作。 <br><br>**注意**：與商務用 skype 使用者的外部網域必須啟用共存模式，或選擇孤島升級模式，以支援該組織中的商務用 skype 使用者。|
|讓您組織中的**小組使用者**與您組織內部或外部的**Skype**使用者進行通訊。   | 此案例即將推出。 <br><br>**重要**：您的小組使用者還無法與 Skype 使用者通訊，但您的商務用 skype 使用者可以繼續與貴組織內部或外部的 skype 使用者進行通訊。 開啟**使用者可以使用商務用 Skype 與團隊使用者**，以及**商務用 skype 使用者可以**與外部存取中的 skype 使用者設定進行通訊。 |
|讓您的**商務用 Skype Online 使用者**與另一個 Office 365 組織中的**小組使用者**進行通訊。| 如果您的使用者是下列其中一種升級模式，您的商務用 Skype Online 使用者就可以與其他組織中的小組使用者通訊： Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings;其他組織的團隊使用者都在 TeamsOnly 模式中。 <br><br>開啟 [**使用者可以與商務用 Skype 和小組使用者通訊**] 的 [外部存取] 中的 [設定]。 然後讓其他團隊組織中的系統管理員執行相同的操作。|
|讓您的**商務用 Skype online 使用者**與其他 Office 365 組織中的**商務用 skype online 使用者**進行通訊。    | 如果您的使用者是下列其中一種升級模式，您的商務用 Skype Online 使用者可以與其他組織中的商務用 Skype Online 使用者通訊： Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings;其他組織的商務用 Skype Online 使用者是下列其中一種升級模式： Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings。<br><br>開啟 [**使用者可以與商務用 Skype 和小組使用者通訊**] 的 [外部存取] 中的 [設定]。 然後讓其他團隊組織中的系統管理員執行相同的操作。|
|讓您的**商務用 Skype Online 使用者**與內部部署組織中的**商務用 skype 使用者**進行通訊。     |如果您的使用者是下列其中一種升級模式，您的商務用 Skype Online 使用者可以與商務用 Skype 使用者進行通訊：孤島、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings;其他組織的商務用 Skype Online 使用者是下列其中一種升級模式： Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings。<br><br>開啟 [**使用者可以與商務用 Skype 和小組使用者通訊**] 的 [外部存取] 中的 [設定]。 然後讓其他團隊組織中的系統管理員執行相同的操作。|
|讓您的**商務用 Skype Online 使用者**與**skype 使用者**通訊（在您的組織內部或外部）。   |開啟 [**商務用 skype] 使用者可以與**[外部存取] 中的 [skype 使用者通訊] 設定。|

> [!IMPORTANT]
> 您不需要將任何**Skype 網域**新增為 [允許的網域]，就能讓小組或商務用 Skype Online 使用者與貴組織內部或外部的 skype 使用者通訊。 所有**Skype 網域**都是白名單，這表示所有這些網域都被視為允許。



## <a name="how-does-external-access-compare-with-guest-access"></a>外部存取與來賓存取有何不同？

若要瞭解外部存取與來賓存取權之間的差異，請閱讀[與其他組織的使用者進行通訊](communicate-with-users-from-other-organizations.md)。

## <a name="related-topics"></a>相關主題

[外部（同盟）使用者的原生聊天體驗](native-chat-for-external-users.md)
