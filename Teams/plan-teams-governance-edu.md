---
title: 適用於系統管理員的 Microsoft 教育版控管常見問題集
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Microsoft Education 群組管理員的常見問題解答，這些管理員會使用 Teams。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1859286fd14e3820a75615adc5da82fea863e74101e5a7911e888490e5799db3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54285802"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>適用於系統管理員的 Microsoft 教育版控管常見問題集

> [!Tip]
> 觀看下列會話以深入瞭解管理在 Microsoft Teams：管理、管理及生命週期[Microsoft Teams](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>如何控制團隊建立？ 我擔心學生會建立不當的團隊。

若要避免不當或誤導性的名稱，或只是提供團隊命名方式的更多結構，您可以使用目前預覽版中的 Microsoft 365 群組命名 (策略) ：

-   **首碼 -尾碼命名策略** 您可以使用首碼或尾碼來定義團隊的命名慣例 (群組) 例如 **，GRP_US_My Group_Engineering。** 首碼和尾碼可以是固定字串或使用者屬性 (例如 **[部門]**) ，根據建立團隊的使用者新增到名稱。
-   **自訂封鎖的字詞** 您可以上傳一組文字，禁止特定組織的使用者使用他們建立的團隊名稱。 例如，您可以封鎖 CEO、**薪資** 和 **人力資源** 等字詞，禁止在團隊名稱中用於他們不適用的群組名稱。 
-   **分類** 您可以建立組織中使用者在建立群組時可設定Microsoft 365分類。 

> [!IMPORTANT]
> 使用 Microsoft 365 組命名政策Azure Active Directory Premium P1一或多個群組成員之每個唯一使用者必須擁有 Azure Active Directory Premium P1 授權或 Azure AD Basic ED Microsoft 365 U 授權。

有關詳細指示，請參閱[Office組命名政策](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。

> [!Note]
> 如果團隊是使用另一個系統的輸入自動建立 (例如 學校資料同步處理) ，請確認輸入資料符合您配置的命名規則;如果沒有，團隊建立將會失敗。

## <a name="can-i-see-who-created-a-team"></a>我可以看到誰建立了團隊嗎？

若要找出誰建立了特定小組，請參閱搜尋稽核記錄中的[Microsoft Teams。](audit-log-events.md)

## <a name="can-i-control-who-can-create-teams"></a>我可以控制誰可以建立團隊嗎？

一般而言，建議您禁止任何人建立團隊。 如果每個人都可以建立團隊，Teams更容易被廣泛採用。 教職員、教師或學生可以使用Teams建立學習群組或特殊興趣群組。 這可Teams課堂內外接受。

根據我們的經驗，使用者教育可協助確保Teams使用方式。 一旦使用者瞭解建立團隊並非匿名，他們就會瞭解不小心建立團隊的含意，並往往會因誤用工具而感到塞塞。

如果您確定要控制誰可以建立團隊，請參閱管理誰可以建立[Microsoft 365群組](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>如何在學期或季開始時自動為每個課程建立團隊？

在每個學期或每季開始時，您需要一些新的團隊。 採取自動化方法自動建立這些團隊、填入正確的使用者，以及設定正確的許可權可能很合理：

-   學校資料同步處理可針對 Exchange Online 和 SharePoint Online 建立 Microsoft 365 群組、Microsoft Teams 和 OneNote 課程筆記本的班級團隊、Intune 教育版學校群組，以及名冊和單一登入 (SSO) 整合，適用于許多其他協力廠商應用程式。 如需深入瞭解，[請流覽 學校資料同步處理。](/schooldatasync/overview-of-school-data-sync)
-   您可以使用 PowerShell 建立團隊和頻道，並自動設定設定。 請參閱[Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps)以瞭解更多資訊。
-   您可以使用 Microsoft Graph API (Beta) 建立、設定、複製和存檔團隊。 請參閱[使用 Microsoft Graph API 處理Microsoft Teams](/graph/api/resources/teams-api-overview)以瞭解更多資訊。

> [!TIP]
> 學校資料同步處理會為每個Microsoft 365建立一個群組，並啟用隱藏的群組成員資格，讓班級中的[](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945)教師和學生可以看到該班級的成員。 如果使用不同的程式來建立班級群組，請使用 Cmdlet 的 HiddenGroupMembershipEnabled 參數New-UnifiedGroup Cmdlet 以滿足相同的隱私權需求。

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>當學期或季結束時，我要如何處理團隊？

建議您先考慮在學校學期或Teams結束後如何處理 Teams 資料：是否要刪除資料，或讓學生即使在完成課程後也能夠使用這些資料。 您一定會想要記住學校日曆，這樣您設定的任何政策都與假日不相衝突。 您可以使用下列工具來實施您的策略：

-   **保留政策：** 您可以使用此功能刪除您指定的年齡之前的所有資料，以確保所有或部分使用者與頻道 (聊天中移除舊資料) 資料。 您也可以設定Teams保留內容，以便無法刪除內容。 詳細資訊，請參閱適用于 Microsoft Teams[的保留Microsoft Teams。](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)
-   **到期政策：** 設定團隊在特定天數後到期。 在到期前 30 天，團隊的所有擁有者都會收到通知，告知其小組需要續約，否則團隊會被刪除 (但系統管理員可以在) 中復原已刪除的團隊。 這項設定對於確保未使用的團隊已日落非常實用。 如需深入瞭解，[請Microsoft 365到期政策](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)。

-   **檔案小組：** 此設定會將團隊置於唯讀模式。 他們仍然可以流覽和搜尋，但沒有人可以新增任何新文章。 [將團隊存檔或還原](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)說明團隊擁有者如何存檔團隊;團隊擁有者也可以使用 Beta Graph api ([來](/graph/api/resources/teams-api-overview)) 或還原團隊。
 
> [!IMPORTANT]
> 使用 Microsoft 365組到期Azure Active Directory Premium P1，每個唯一使用者必須擁有一或多個群組成員Microsoft 365授權。

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>建立團隊時，我的教職員成員可以使用團隊範本嗎？

是的。 使用者可以在建立新團隊時，從現有的範本選取建立團隊，Teams 擁有者也可以使用 Graph API [ (Beta) ](/graph/api/resources/teams-api-overview)從可用的範本建立新團隊。

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>我可以透過 PowerShell 或 Graph 自動化哪些Graph？

[Microsoft Graph API (Beta) ](/graph/api/resources/teams-api-overview)可以執行下列操作：

-   建立團隊。
-   新增成員和擁有者。
-   新增頻道。
-   新增應用程式。
-   複製現有團隊以快捷方式執行這些步驟，並取得其定位停駐點。
-   提供使用者您剛剛建立團隊的連結。
-   當您不再需要成員、擁有者、頻道和應用程式時，請移除它們。
-   當團隊不再使用中時，將其存檔。 
-   刪除團隊。
-   建立頻道執行緒

[PowerShell](/powershell/module/teams/?view=teams-ps) 可以執行下列操作：

-   建立團隊。
-   新增成員和擁有者。
-   新增頻道。
-   當您不再需要成員、擁有者和頻道時，請移除它們。
-   刪除團隊。

> [!TIP]
> Graph API 和 PowerShell Cmdlet 不斷新增功能。 請務必檢查 Microsoft Graph [API (和](/graph/api/resources/teams-api-overview) [PowerShell](/powershell/module/teams/?view=teams-ps)) 文章，瞭解功能增強功能。  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>我能否控制Teams教職員和學生可存取哪些功能？

是的。 您可以使用策略來控制使用者可存取的特定訊息、會議、通話和即時活動功能。 您可以使用整個租使用者設定來將相同的設定全部都適用，或如果需要，則適用使用者層級原則。 

如要進一步Teams，請參閱[管理Microsoft Teams的設定](enable-features-office-365.md)。
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>我可以控制教職員與學生共同合作的外部派對嗎？

您可以使用來賓存取來邀請租使用者以外的使用者，這很適合研究共同研究或來賓課程：

-   使用網域允許清單，根據來賓的網域允許或封鎖來賓。
-   開啟和關閉特定群組和Microsoft 365的來賓存取權，以控制哪些團隊可以 (，) 邀請來賓。
-   使用稽核記錄查看哪些通知已發送給受邀來賓。

詳細資訊請參閱群組中的[來賓Microsoft 365存取](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)。

## <a name="what-information-can-i-review-about-existing-teams"></a>我可以查看哪些現有團隊的資訊？

您可以檢查稽核記錄以查看：

-   神秘受邀為來賓加入哪個團隊。
-   神秘建立哪個團隊。

詳細資訊，請參閱在 Microsoft Teams 中[搜尋稽核Microsoft Teams。](audit-log-events.md)

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams變化如此快速。 如何保持最新狀態？

我們建議您使用下列資源取得最新Teams：

-   [新功能Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Microsoft Teams部落格](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)