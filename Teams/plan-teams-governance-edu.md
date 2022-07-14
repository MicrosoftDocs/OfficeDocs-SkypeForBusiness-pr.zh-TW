---
title: 適用於系統管理員的 Microsoft 教育版控管常見問題集
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 使用 Teams 之 Microsoft 教育版群組系統管理員的常見問題解答。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fe9c0b19e5ba586ac8bfe430295de459c3d836d2
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790178"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>適用於系統管理員的 Microsoft 教育版控管常見問題集

> [!Tip]
> 請觀看下列會話以深入瞭解 Microsoft Teams 中的管理： [Microsoft Teams 中的管理、管理和生命週期](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>如何?控制團隊建立？ 我擔心學生會建立不適當的團隊。

為了避免不當或誤導性的名稱，或只是為團隊的命名方式提供更多結構，您可以使用目前預覽) 中的Microsoft 365 群組命名原則 (：

-   **首碼尾碼命名原則** 您可以使用首碼或尾碼來定義團隊 (群組) 的命名慣例，例如 **GRP_US_My Group_Engineering**。 首碼和後稱謂可以是固定字串或使用者屬性， (例如 **[部門]**) ，根據建立團隊的使用者新增至名稱。
-   **自訂封鎖的單字** 您可以上傳一組字詞，讓特定組織的使用者無法使用他們所建立之團隊的名稱。 例如，您可以針對不適用的群組，封鎖「 **執行員**」、 **「薪資**」和 **「人力資源** 」這兩個字詞，禁止他們使用在團隊名稱中。
-   **分類** 您可以建立組織中的使用者建立 Microsoft 365 群組時可以設定的分類。 

> [!IMPORTANT]
> 若使用Microsoft 365 群組命名原則，每個屬於一或多個 Microsoft 365 群組成員的唯一使用者都需要Azure Active Directory Premium P1授權或 Azure AD Basic EDU 授權。

如需詳細指示，請參閱 [Office 群組命名原則](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。

> [!Note]
> 如果團隊是使用來自其他系統 (，例如學校資料同步處理) 自動建立，請確認輸入資料符合您已設定的命名原則;如果沒有，團隊建立將會失敗。

## <a name="can-i-see-who-created-a-team"></a>我可以查看誰建立了團隊嗎？

若要瞭解建立特定團隊的人員，請參閱 [搜尋 Microsoft Teams 中事件的稽核記錄](audit-log-events.md)。

## <a name="can-i-control-who-can-create-teams"></a>我可以控制誰可以建立團隊嗎？

一般建議您不要讓任何人建立團隊。 如果每個人都能建立團隊，Teams 就更可能受到廣泛採用。 教職員、教師或學生可以使用 Teams 來建立研究群組或特殊興趣群組。 這可協助在教室內外接受 Teams。

在我們的體驗中，使用者教育可協助確保負責的 Teams 使用量。 只要使用者瞭解建立團隊並非匿名團隊，他們就會瞭解不小心建立團隊所帶來的影響，並往往會讓您遠離不當使用工具。

如果您確定要控制誰可以建立團隊，請參閱[管理誰可以建立Microsoft 365 群組](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>如何?在學期開始或每季時自動為每個課程建立團隊嗎？

在每一個學期或每季的開頭，您需要一些新的團隊。 採用自動化方法自動建立這些團隊、向正確的使用者填入團隊，以及設定正確的許可權可能是合理的：

-   學校資料同步處理可以建立Exchange Online和 SharePoint Online 的Microsoft 365 群組、Microsoft Teams 和 OneNote 課程筆記本的班級團隊、教育用 Intune 的學校群組，以及針對許多其他協力廠商應用程式 (SSO) 整合的名冊和單一登入。 若要深入瞭解 [，請參閱學校資料同步處理概觀](/schooldatasync/overview-of-school-data-sync)。
-   使用 PowerShell，您可以建立團隊和頻道，並自動設定設定。 如需詳細資訊，請參閱 [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) 。
-   您可以使用 Beta 版中的 Microsoft 圖形 API () 來建立、設定、複製及封存團隊。 如需詳細資訊，請參閱[使用 Microsoft 圖形 API與 Microsoft Teams](/graph/api/resources/teams-api-overview)合作。

> [!TIP]
> 學校資料同步處理會為每個已同步處理的班級建立 Microsoft 365 [群組，並啟用隱藏的群組成員資格](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) ，讓班級內的教師和學生可以看到該班級的成員。 如果使用不同的程式建立類別群組，請使用 New-UnifiedGroup Cmdlet 的 HiddenGroupMembershipEnabled 參數來符合相同的隱私權需求。

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>如何?在學期或季度結束時處理團隊？

我們建議您先思考在學校學期或季度結束後，要如何處理 Teams 資料：是否要刪除 Teams 資料，或是在學生完成課程後仍可繼續使用。 您會想要記住學校行事曆，這樣您設定的原則就不會與假日發生衝突。 您可以使用下列工具來實作策略：

-   **保留原則：** 使用此功能刪除所有超過您指定年齡的資料，以確保已移除聊天 (中所有或部分使用者) 和頻道的舊資料。 您也可以將 Teams 設定為保留內容，使其無法刪除。 如需詳細資訊，請參閱 [Microsoft Teams 的保留原則](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)。
-   **到期原則：** 將團隊設定為在特定天數之後到期。 在到期前 30 天，團隊的所有擁有者都會收到續約通知，否則系統會 (系統管理員可以在另外 30 天內復原刪除的團隊) 。 此設定對於確保未使用的團隊日落非常有用。 如需詳細資訊，請參閱 [Microsoft 365 群組到期原則](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)。

-   **封存小組：** 此設定會讓團隊進入唯讀模式。 他們仍然可以流覽和搜尋，但沒有人可以新增任何文章。 [封存或還原團隊](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)說明團隊擁有者如何封存團隊;團隊擁有者也可以使用[圖形 API (Beta 版) ](/graph/api/resources/teams-api-overview)來封存或還原團隊。
 
> [!IMPORTANT]
> 使用Microsoft 365 群組到期原則需要為屬於一或多個 Microsoft 365 群組成員的每個唯一使用者Azure Active Directory Premium P1授權。

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>建立團隊時，是否有可供教職員使用的團隊範本？

是的。 建立新團隊時，使用者可以 **從現有範本** 選取 [建立團隊]，而 Teams 擁有者也可以使用 [圖形 API (Beta 版)](/graph/api/resources/teams-api-overview)從可用的範本建立新團隊。

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>我可以透過 PowerShell 或 Graph 自動化哪些工作？

[Microsoft 圖形 API (Beta 版) ](/graph/api/resources/teams-api-overview)可以執行下列動作：

-   建立團隊。
-   新增成員和擁有者。
-   新增頻道。
-   [新增應用程式]。
-   藉由複製現有團隊來快捷方式執行這些步驟，並取得其索引標籤。
-   為使用者提供您剛建立之團隊的連結。
-   當您不再需要成員、擁有者、頻道和應用程式時，請移除他們。
-   當團隊不再為使用中狀態時封存團隊。 
-   刪除團隊。
-   建立頻道對話

[PowerShell](/powershell/module/teams/?view=teams-ps) 可以執行下列動作：

-   建立團隊。
-   新增成員和擁有者。
-   新增頻道。
-   當您不再需要成員、擁有者和頻道時，請移除他們。
-   刪除團隊。

> [!TIP]
> 圖形 API和 PowerShell Cmdlet 會不斷新增功能。 請務必經常查看[Microsoft 圖形 API (Beta 版) ](/graph/api/resources/teams-api-overview)和[PowerShell](/powershell/module/teams/?view=teams-ps)文章，以取得功能增強功能。  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>我可以控制教職員和學生可以存取哪些 Teams 功能嗎？

是的。 您可以使用原則來控制使用者有權存取的特定訊息、會議、通話和即時活動功能。 您可以使用全租使用者設定將相同的設定套用至所有設定，或視需要套用使用者層級原則。 

如需 Teams 原則的詳細資訊，請參閱 [管理組織的 Microsoft Teams 設定](enable-features-office-365.md)。
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>我可以控制教職員和學生共同作業的外部派對嗎？

您可以使用來賓存取來邀請租使用者外部的使用者，這對進行研究共同作業或來賓授課很有用：

-   使用網域允許清單，根據來賓的網域允許或封鎖來賓。
-   開啟和關閉特定Microsoft 365 群組和團隊的來賓存取權，以控制哪些團隊可以 (，而且無法) 邀請來賓。
-   使用稽核記錄來查看哪些警示已傳送給受邀的來賓。

如需詳細資訊，請參閱[Microsoft 365 群組中的來賓存取](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)權。

## <a name="what-information-can-i-review-about-existing-teams"></a>我可以檢閱哪些關於現有團隊的資訊？

您可以檢查稽核記錄以查看：

-   受邀為團隊訪客的人員。
-   建立哪一個團隊的人員。

如需詳細資訊，請參閱 [搜尋 Microsoft Teams 中事件的稽核記錄](audit-log-events.md)。

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams 的演進速度如此之快。 如何保持在最新狀態？

建議您使用下列資源來取得 Teams 上的最新更新：

-   [Microsoft Teams 的新增功能](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Microsoft Teams 部落格](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)