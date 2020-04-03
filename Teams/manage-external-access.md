---
title: 在 Microsoft Teams 中管理外部存取 (同盟)
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
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
description: 您的 Teams 或 IT 系統管理員可以設定其他網域的外部存取 (同盟)，讓這些網域的使用者參與 Teams。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: b354172e5a60e3c6f9df5d74c5d16731fdac0bf8
ms.sourcegitcommit: 4ee9835282e1440d03abc6dbcd172bc20c5b3015
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2020
ms.locfileid: "43096858"
---
<a name="manage-external-access-in-microsoft-teams"></a>在 Microsoft Teams 中管理外部存取
======================================================

外部存取是一種讓整個外部網域的 Teams 使用者可以在 Teams 中尋找、通話、聊天以及與您進行會議的方式。 您也可以使用外部存取，與仍在使用商務用 Skype (線上或內部部署) 或 Skype (預覽版) 的外部使用者通訊。

如果您想讓外部使用者存取小組和頻道，「來賓存取」可能是更好的做法。 如需外部存取和來賓存取之間差異的詳細資訊，請參閱[比較外部和來賓存取](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。 

使用外部存取的時機：
  
- 您的使用者位於不同網域，且需要共同作業。 例如，Rob@contoso.com 和 Ann@northwindtraders.com 正與 contoso.com 和 northwindtraders.com 網域中的其他人一起共同合作一個專案。

- 您希望組織中的人員能夠使用 Teams 與組織外部特定公司的人員連絡。

- 您希望全球的任何其他 Teams 使用者能夠利用您的電子郵件地址找到您並與您連絡。 

> [!IMPORTANT]
> 目前，要在 Microsoft Teams 應用程式中與不是 Azure Active Directory (Azure AD) 來賓或租用戶的組織外部使用者同盟，您必須正確設定混合式部署並移到商務用 Skype Online。 自 2019 年 2 月 25 日起，如果 SIP 設定檔的使用者不在商務用 Skype Online 中，Teams 將不再支援原生同盟。 如需有關設定混合式部署並移至 Teams 的詳細資訊，請參閱[將商務用 Skype 混合式部署升級至 Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)。

## <a name="plan-for-external-access"></a>規劃外部存取

Teams 預設會開啟外部存取，這表示您的組織可以與所有外部網域通訊。 如果您新增封鎖網域，將允許所有其他網域；如果您新增允許網域，所有其他網域都會遭到封鎖。 在 Teams 系統管理中心設定外部存取有三種案例 ([全組織設定]****  >  [外部存取]****)：

- **開放式同盟**：這是 Teams 的預設設定，可讓您組織中的人員尋找、通話、聊天、以及設定與任何網域中的組織外部人員進行會議。

    在此案例中，您的使用者可以與執行 Teams 或商務用 Skype 的所有外部網域通訊，「前提」是這些外部網域使用開放式同盟或是已將您的網域新增到允許清單。

- **允許特定網域**：透過將網域新增至 [允許]**** 清單中，可限制外部存取只能存取允許的網域。 一旦您設定了允許網域的清單，所有其他網域都會遭到封鎖。 若要允許特定網域，按一下 [新增網域]****，新增網域的名稱，按一下 [對這個網域採取的動作]****，然後選取 [允許]****。

- **封鎖特定網域** - 透過將網域新增至 [封鎖]**** 清單，您可以與封鎖網域「以外」** 的所有外部網域通訊。 若要封鎖特定網域，按一下 [新增網域]****，新增網域的名稱，按一下 [對這個網域採取的動作]****，然後選取 [封鎖]****。 一旦您設定了封鎖網域的清單，就會允許所有其他網域。

## <a name="allow-or-block-domains"></a>允許或封鎖網域

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a>步驟 1 - 讓您的組織與其他 Teams 組織通訊

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，移至 [全組織設定]****  >  [外部存取]****。

2. 開啟 [使用者可以與其他商務用 Skype 和 Teams 使用者通訊]**** 設定。

     ![螢幕擷取畫面：開啟 [使用者可以與其他商務用 Skype 與 Teams 使用者通訊] 設定](media/manage-external-access-2.png)。

3. 如果您想要讓所有 Teams 組織都能與貴組織中的使用者通訊，請直接跳至步驟 5。

4. 如果您想要限制能夠與貴組織使用者通訊的組織，可以允許部分網域以外的所有網域，或只允許特定網域。 

    - 若要允許部分網域以外的所有網域，按一下 [新增網域]****，新增您要封鎖的網域。 在 [新增網域]**** 窗格中，輸入網域的名稱，按一下 [封鎖]****，然後按一下 [完成]****。 
    - 若要限制特定組織的通訊，將這些網域新增至 [允許]**** 狀態的清單中。 一旦在 [允許] 清單中新增任何網域，與其他組織的通訊將限於只能與其網域在 [允許] 清單中的組織通訊。 

5. 按一下 [儲存]****。

6. 確定其他 Teams 組織的系統管理員也完成這些步驟。 例如，如果系統管理員要限制可與其使用者通訊的組織，則必須在其 [允許的網域]**** 清單中輸入您的企業網域。

### <a name="step-2---test-it"></a>步驟 2 - 測試

若要測試您的設定，您需要不在防火牆後面的 Teams 使用者。
  
1. 當您和其他組織的系統管理員皆已變更 [外部存取]**** 設定後，您應該已準備就緒。

2. 在 Teams 應用程式中，依電子郵件地址搜尋人員，然後傳送聊天要求。

3. 請您的 Teams  連絡人傳送聊天要求給您。 如果您沒有收到其要求，就表示您的防火牆設定有問題 (假設他們已確認其防火牆設定正確)。

4. 另一個測試問題是否為您的防火牆的方法，是前往不在您的防火牆後的 WiFi 地點。 例如咖啡店，然後使用 Teams 傳送聊天要求給您的連絡人。 如果在該 WiFi 地點要求可以成功送到，但在公司不行，您就知道問題是您的防火牆。

> [!NOTE]
> 如果您和另一位使用者都開啟外部存取並允許彼此的網域，應該就可以外部存取。 如果行不通，另一位使用者應確定其設定沒有封鎖您的網域。

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>與商務用 Skype Online 組織中的使用者通訊

如果您要設定外部存取，讓您的 Teams 使用者可以尋找及聯繫商務用 Skype 組織的使用者，但對方組織限制誰可以與他們的使用者聯繫，請按照下列步驟設定從您的網域到對方組織網域的外部存取。 然後要求對方組織的系統管理員按照下列步驟設定商務用 Skype Online 的外部存取。

如需常見商務用 Skype Online 案例的特定指導方針，請參閱下方的[常見的外部存取案例](#common-external-access-scenarios)。

![商務用 Skype 標誌圖示](media/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**

請對方組織的系統管理員執行下列步驟：

1. 在 Microsoft 365 系統管理中心，移至 [系統管理中心]****  >  [Teams & Skype]****  >  [舊版入口網站]****。
  
2. 在 [商務用 Skype 系統管理中心]****，選擇 [組織]****  >  [外部通訊]****。

3. 若要設定與特定公司或其他網域中的使用者進行通訊，請在下拉式方塊中選擇 [僅對允許的網域開啟]****。

    或者，如果他們想要與世界各地有開啟商務用 Skype 原則的其他人通訊，請選擇 [對封鎖網域以外的網域開啟]****。 這是預設設定。

4. 在 [封鎖或允許的網域]**** 底下，選擇 **+**，然後新增您要允許的網域名稱。

## <a name="communicate-with-skype-users-in-preview"></a>與 Skype 使用者通訊 (預覽)

請按照這些步驟，讓貴組織的 Teams 使用者可以和 Skype 使用者聊天和通話。 Teams 使用者便可以搜尋 Skype 使用者，並開始一對一的純文字交談或進行音訊/視訊通話，反之亦然。

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，移至 [全組織設定]****  >  [外部存取]****。

2. 開啟 [使用者可以與 Skype 使用者通訊]**** 設定。

    ![螢幕擷取畫面：開啟 [使用者可以與 Skype 使用者通訊] 設定](media/manage-external-access-5.png)。

若要深入瞭解 Teams 使用者和 Skype 使用者的通訊方式 (包括通訊的限制)，請參閱 [Teams 和 Skype 的互通性](teams-skype-interop.md)。

## <a name="common-external-access-scenarios"></a>常見的外部存取案例

|**如果您想要...**  |**請這麼做**  |
|---------|-----------------------|
|讓組織中的 **Teams 使用者**能夠與其他 (外部) 組織中的 **Teams 使用者**通訊。|在 [外部存取] 中，將外部網域新增到 [允許清單] 或使用開放式同盟。 然後請其他 Teams 組織的系統管理員執行相同的動作。      |
|讓組織中的 **Teams 使用者**能夠與相同組織中的**商務用 Skype Online 使用者**通訊。  |啟用「共存」模式，或選擇 Islands 升級模式來支援貴組織中商務用 Skype 使用者。   |
|讓組織中的 **Teams 使用者**能夠與其他 (外部) 組織中的**商務用 Skype Online 使用者**通訊。      |在 [外部存取] 中，將外部網域新增到 [允許清單] 或使用開放式同盟。 <br><br>開啟 [外部存取] 中的 [使用者可以與其他商務用 Skype 和 Teams 使用者通訊]**** 設定。 然後請其他 Teams 組織的系統管理員執行相同的動作。 <br><br>**注意**：商務用 Skype 使用者所屬的外部網域必須啟用「共存」模式，或選擇 Islands 升級模式來支援該組織中的商務用 Skype 使用者。|
|讓組織中的 **Teams 使用者**能夠與 **Skype** 使用者通訊。<br> (預覽)  |開啟 [外部存取] 中的 [使用者可以與 Skype 使用者通訊]**** 設定。 |
|讓您的**商務用 Skype Online 使用者**與其他 Office 365 組織中的 **Teams 使用者**通訊。| 如果您的使用者屬於下列其中一種升級模式，且其他組織的 Teams 使用者是在 TeamsOnly 模式，您的商務用 Skype Online 使用者就可以與其他組織中的 Teams 使用者通訊：Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings。 <br><br>開啟 [外部存取] 中的 [使用者可以與其他商務用 Skype 和 Teams 使用者通訊]**** 設定。 然後請其他 Teams 組織的系統管理員執行相同的動作。|
|讓您的**商務用 Skype Online 使用者**與其他 Office 365 組織的**商務用 Skype Online 使用者**通訊。    | 如果您的商務用 Skype Online 使用者屬於下列其中一種升級模式：Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings，且其他組織的商務用 Skype Online 使用者屬於下列其中一種升級模式：Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings，您的商務用 Skype Online 使用者就可以與其他組織中的商務用 Skype Online 使用者通訊。<br><br>開啟 [外部存取] 中的 [使用者可以與其他商務用 Skype 和 Teams 使用者通訊]**** 設定。 然後請其他 Teams 組織的系統管理員執行相同的動作。|
|讓您的**商務用 Skype Online 使用者**與其他內部部署組織的**商務用 Skype 使用者**通訊。     |如果您的商務用 Skype Online 使用者屬於下列其中一種升級模式：Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings，且其他組織的商務用 Skype Online 使用者屬於下列其中一種升級模式：Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings，您的商務用 Skype Online 使用者就可以與內部部署組織中的商務用 Skype 使用者通訊。<br><br>開啟 [外部存取] 中的 [使用者可以與其他商務用 Skype 和 Teams 使用者通訊]**** 設定。 然後請其他 Teams 組織的系統管理員執行相同的動作。|
|讓您的**商務用 Skype Online 使用者**與貴組織內部或外部的 **Skype 使用者**通訊。   |開啟 [外部存取] 中的 [使用者可以與 Skype 使用者通訊]**** 設定。|

> [!IMPORTANT]
> 您不需要將任何 ** Skype 網域**新增為允許網域，就能讓 Teams 或商務用 Skype Online 的使用者與組織內部或外部的 Skype 使用者通訊。 所有 **Skype 網域**皆為核准清單，這表示所有這些網域都被視為允許。

## <a name="how-does-external-access-compare-with-guest-access"></a>外部存取與來賓存取的比較？

若要瞭解外部存取和來賓存取之間的差異，請參閱[與其他組織的使用者通訊](communicate-with-users-from-other-organizations.md)。

## <a name="related-topics"></a>相關主題

- [外部 (同盟) 使用者的原生聊天體驗](native-chat-for-external-users.md)
