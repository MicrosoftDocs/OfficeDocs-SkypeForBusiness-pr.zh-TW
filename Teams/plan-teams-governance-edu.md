---
title: 適用於系統管理員的 Microsoft 教育版控管常見問題集
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 針對使用團隊之 Microsoft 教育小組之系統管理員的常見問題的解答。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 79b6e33c6434a1242b7d30322aff77b62f1b42fd
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780212"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>適用於系統管理員的 Microsoft 教育版控管常見問題集

> [!Tip]
> 請觀看下列會話，以深入瞭解 Microsoft 團隊中的管理： microsoft 團隊中的管理[、管理與生命週期](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>如何控制小組建立？ 我擔心學生會建立不適當的小組。

若要避免不適當或令人誤解的名稱，或只是為了提供更多有關團隊命名方式的結構，您可以使用 Microsoft 365 群組命名原則（目前在預覽中）：

-   **前置詞尾碼命名原則**您可以使用 [首碼] 或 [尾碼] 定義小組（群組）的命名慣例，例如**GRP_US_My Group_Engineering**]。 首碼和尾碼可以是固定字串或使用者屬性（例如 **[部門]**），根據建立小組的使用者，新增到名稱中。
-   **自訂封鎖的單字**您可以上傳特定組織中的使用者在其建立的小組名稱中封鎖的一組字。 例如，您可以封鎖條款**CEO**、**工資**與**HR**在小組名稱中用於不適用的群組。
-   **分類**您可以建立組織中的使用者在建立 Office 365 群組時可以設定的分類。 

> [!IMPORTANT]
> 使用 Microsoft 365 群組命名原則時，必須具備 Azure Active Directory Premium P1 授權或 Azure AD 基本 EDU 授權，才能針對一或多個 Microsoft 365 群組成員的每個唯一使用者。

如需詳細指示，請參閱[Office 群組命名原則](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。

> [!Note]
> 如果您是使用來自另一個系統的輸入（例如學校資料同步處理）自動建立團隊，請確認輸入資料符合您所設定的命名原則;如果不是，小組建立就會失敗。

## <a name="can-i-see-who-created-a-team"></a>我可以看到誰建立了團隊嗎？

若要瞭解建立特定團隊的人員，請參閱在[[審核記錄] 中搜尋 Microsoft 團隊中的事件](audit-log-events.md)。

## <a name="can-i-control-who-can-create-teams"></a>我可以控制誰可以建立團隊嗎？

一般來說，建議您不要從任何人都能建立小組。 如果每個人都能建立小組，就很可能會廣泛採用團隊。 教職員、教師或學生可以使用團隊來建立研究群組或特殊的興趣小組。 這將協助在教室內和外部接受團隊。

在我們的經驗中，使用者教育有助於確保責任團隊的使用。 只要使用者瞭解建立團隊不是匿名的，他們就能瞭解 carelessly 建立小組的意義，並傾向于 shy 離開工具。

如果您確定要控制誰可以建立團隊，請參閱[管理可建立 Microsoft 365 群組的人員](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>如何在學期或季開始時為每個課程自動建立小組？

在每個學期或季的開始，您需要有許多新團隊。 您可以採取自動化方法來自動建立這些團隊、使用正確的使用者進行填充，並設定正確的許可權：

-   學校資料同步處理可建立適用于 Exchange Online 和 SharePoint Online 的 Microsoft 365 群組、Microsoft 團隊的課程小組以及 OneNote 課程筆記本、適用于 Intune 的學校小組，以及針對許多其他協力廠商應用程式的 rostering 及單一登入（SSO）整合。 深入瞭解[學校資料同步處理的概覽](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync)。
-   您可以使用 PowerShell 建立團隊和頻道，並自動設定設定。 如需詳細資訊，請參閱[Microsoft 團隊 PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 。
-   您可以使用 Microsoft Graph API （目前在 Beta 版）來建立、設定、克隆及封存小組。 如需詳細資訊，請參閱[使用 Microsoft GRAPH API 與 Microsoft 團隊共同作業](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)。

> [!TIP]
> 學校資料同步處理會針對同步處理的每個類別建立 Office 365 群組，並[啟用隱藏的群組成員資格](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945)，因此只有班級中的教師與學生才能看到該類別的成員。 如果您使用不同的程式來建立班級群組，請使用新的-UnifiedGroup Cmdlet 的 HiddenGroupMembershipEnabled 參數，以符合相同的隱私權需求。

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>如何在學期或季結束時處理團隊？

我們建議您先思考，在學校學期或季結束時，您想要如何處理團隊資料：不論是要刪除，還是在學生完成課程後仍可供學生使用。 您可能會想要保留學校行事曆，因此您設定的任何原則都不會與假日發生衝突。 您可以使用下列工具來實施您的戰略：

-   **保留原則：** 使用此功能刪除您指定之期限之前的所有資料，以確定舊資料已從聊天中移除（適用于所有或部分使用者）和頻道。 您也可以設定團隊保留內容，使其無法刪除。 如需詳細資訊，請參閱[Microsoft 團隊的保留原則](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)。
-   **到期原則：** 將團隊設定為在特定天數後到期。 到期前三十天之前，小組的所有擁有者都會收到通知，指出他們的小組需要更新，否則將會被刪除（即使系統管理員可以在30天內復原已刪除的小組）。 這個設定對確定未使用的團隊有 sunsetted 是非常實用的。 若要深入瞭解，請參閱[Office 365 群組過期原則](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)。

-   封存**團隊：** 此設定會將團隊放入唯讀模式。 他們仍然可以流覽和搜尋，但沒有人可以新增任何新的文章。 封存[或還原團隊](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)說明團隊擁有者如何封存團隊;小組擁有者也可以使用[圖形 API （Beta）](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)來封存或還原團隊。
 
> [!IMPORTANT]
> 使用 Microsoft 365 群組過期原則，對於屬於一或多個 Microsoft 365 群組成員的每個唯一使用者，都需要 Azure Active Directory Premium P1 授權。

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>在建立小組時，是否有供教職員成員使用的小組範本？

是。 使用者可以在建立新的小組時，選取 [**從現有的範本建立小組**]，而團隊擁有者也可以使用[圖形 API （Beta）](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)從可用的範本建立新的小組。

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>我可以透過 PowerShell 或圖形自動執行哪些任務？

[Microsoft GRAPH API （Beta 版）](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)可以執行下列動作：

-   建立小組。
-   新增成員和擁有者。
-   新增頻道。
-   新增應用程式。
-   您可以將現有的團隊克隆並取得索引標籤，以快捷方式執行這些步驟。
-   為使用者提供您剛建立之小組的連結。
-   當您不再需要成員、擁有者、頻道和應用程式時，可以將它們移除。
-   封存團隊不再使用中的時間。 
-   刪除小組。
-   建立通道執行緒

[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)可以執行下列動作：

-   建立小組。
-   新增成員和擁有者。
-   新增頻道。
-   當您不再需要成員、擁有者和頻道時，可以將它們移除。
-   刪除小組。

> [!TIP]
> 圖形 API 和 PowerShell Cmdlet 會持續新增功能。 請務必檢查[Microsoft GRAPH API （Beta）](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)和[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)文章，以瞭解功能增強功能。  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>我可以控制教職員和學生能存取的小組功能嗎？

是。 您可以使用原則來控制使用者可以存取的特定訊息、會議、通話及即時事件功能。 您可以使用整個租使用者的設定，將相同的設定套用至全部，或在必要時套用使用者層級原則。 

如需團隊原則的詳細資訊，請參閱[管理貴組織的 Microsoft 團隊設定](enable-features-office-365.md)。
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>我可以控制教職員和學生共同作業的外部參與方嗎？

您可以使用來賓存取來邀請來自您租使用者以外的使用者，這對於研究共同作業或訪客講座很有用：

-   使用網域 whitelisting 根據其網域來允許或封鎖來賓。
-   針對特定 Microsoft 365 群組和團隊開啟和關閉來賓存取權，以控制哪些團隊可以（且不能）邀請來賓。
-   使用審核記錄來查看哪些通知已傳送給受邀的來賓。

如需詳細資訊，請參閱[Microsoft 365 群組中的來賓存取權](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)。

## <a name="what-information-can-i-review-about-existing-teams"></a>我可以查看現有團隊的哪些資訊？

您可以查看 [審核記錄]，查看：

-   受邀者成為哪個團隊的來賓。
-   建立哪個團隊。

如需詳細資訊，請參閱在[[審核記錄] 中搜尋 Microsoft 團隊中的事件](audit-log-events.md)。

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>小組會快速演變成如此。 我要如何掌握最新資訊？

我們建議您在下列資源中取得小組的最新更新：

-   [Microsoft 團隊的新功能](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Microsoft 團隊博客](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
