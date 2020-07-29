---
title: 建立班級團隊的建議方法和最佳做法
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: lakuan
description: 了解如何為您的學校建立班級團隊的建議方法和最佳做法。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e85ef79247bdf35c3c116504af23728a0d268ca5
ms.sourcegitcommit: 682566e51a9e5f0fc65540535c7dcdcbd38e04c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/28/2020
ms.locfileid: "45429325"
---
# <a name="recommended-methods-and-best-practices-for-creating-class-teams"></a>建立班級團隊的建議方法和最佳做法

Microsoft Teams 教育版提供  [特定團隊類型](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67) 供教育使用。 [班級團隊類型](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)專為教室使用設計，並隨附支援教室需求的特定功能，包括：  

- 作業
- 成績
- OneNote 教室筆記本  
- [班級教材資料夾](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988) ，用於保護學生的唯讀內容
- [早期教師存取權](https://support.microsoft.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78)，以在新增學生之前設定班級 
- 能夠讓會干擾的學生靜音和其他特殊權限  

您可以利用幾個方式來建立班級團隊，而 Teams 教育版擁有一組獨特的部署工具，能讓您輕鬆完成。 我們將逐步執行各種選項，協助您選擇最符合您需求的正確部署路徑。  

## <a name="automatic-team-creation-using-sds"></a>使用 SDS 自動建立團隊

**此功能即將於 2020 年 7 月底之前推出。**

將團隊建立自動化能夠同時節省 IT 系統管理員和教師的時間。 這可確保在登入時教師已建立所有班級團隊，並準備好進行設定。 [學校資料同步 (SDS)](https://docs.microsoft.com/SchoolDataSync) 是免費的 Office 365 教育版工具，它會從教育機構的記錄系統 (例如，學生資訊系統 (SIS) 或學習管理系統 (LMS)) 中讀取資料。 SDS 會以許多方式使用該資料來強化 Office 365 設定，這些方式包括大量建立班級團隊，並與您的資訊系統保持同步，以讓講師和學生成員資格隨著註冊變更而更新。 SDS 可以從任何記錄系統匯入資料，並具有與世界各地許多現有 [SIS 廠商](https://docs.microsoft.com/schooldatasync/what-sis-and-mis-vendors-does-school-data-sync-support)的內建連接器。 我們強烈建議您使用 SDS，因為它提供下列優點。  

### <a name="benefits"></a>優點

- 自動建立及維護班級團隊，教師將能夠登入 Teams，並立即開始教學。
- 成員資格會與 SIS/LMS 同步，以維護學生成員資格變更。
- EDU 客戶成功團隊可提供免費部署協助。
- [早期教師存取權](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78)：授課者在准許學生之前，有時間可準備其團隊。  
- 選擇性地建立使用者並套用 Office 365 授權。
- 建立安全性群組，在各 Office 365 (包括 Teams 原則) 間使用。
- 建立系統管理單元，用於限定範圍的系統管理委派和[教師密碼重設](https://docs.microsoft.com/schooldatasync/how-to-enable-teacher-password-reset)。 
- 內建的錯誤和重試處理、節流輪詢，以及用於大規模處理的工作階段穩定性，以減少系統管理員的工作。  
- 內建的清理功能可在群組和團隊過期之後將其重新命名和封存。
- [成績同步](https://docs.microsoft.com/schooldatasync/grade-sync)：教師可在 Teams 中進行所有評分，並讓其自動將成績從 Teams 寫回到 SIS 成績表。 
- [學生資料保護](https://docs.microsoft.com/schooldatasync/protecting-student-personal-data)：防止學生使用非 Microsoft 應用程式，並追蹤及管理家長同意。 
- 匯入的資料可用來運用使用者角色、組織 (學校) 和其他重要資料以強化教育深入解析。  

### <a name="considerations"></a>考量

SDS 會透過兩個步驟建立團隊。 第一個步驟會在 Azure Active Directory (Azure AD) 中建立 Microsoft 365 群組，而第二個步驟會自動將該群組轉換成團隊。 建立團隊的第二個步驟在 SDS 中為選擇性。 取決於部署時間和可能造成的未使用團隊數量，系統管理員可能不想要自動建立團隊。 我們建議擁有 50 萬或更多個團隊的機構，在 SDS 中關閉自動團隊建立切換，並使用[由授課者引導的團隊建立方法](#educator-led-team-creation-from-office-365-class-groups)。  

### <a name="get-started"></a>入門

若要開始使用，請前往[學校資料同步 (SDS)](https://docs.microsoft.com/SchoolDataSync)，並連絡 [https://aka.ms/sdssupport](https://aka.ms/sdssupport) 部署協助。  

## <a name="educator-led-team-creation-from-office-365-class-groups"></a>來自 Office 365 班級群組之由授課者引導的團隊建立

**此功能即將於 2020 年 8 月中之前推出。**

如果想要讓教師更輕鬆、快速地建立其所需的班級，由授課者引導的團隊建立是絕佳的部署選項。 我們也建議擁有超過 50 萬個團隊的機構使用此方法來將外部建立的團隊數量最小化。  

此混合式方法可讓您使用 SDS 為每個班級建立群組 (建議)，或由您自己使用 [Graph API](https://docs.microsoft.com/graph/api/educationroot-post-classes) 為他們建立群組。 班級群組備妥之後，授課者就能使用 [建議的班級]**** 圖示，將其群組轉換成團隊。

:::image type="content" source="media/class-teams-edu-suggested-classes.png" alt-text="顯示建議的班級圖示的螢幕擷取畫面":::

### <a name="benefits"></a>優點

- [早期教師存取權](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78)：授課者在准許學生之前，有時間可準備其團隊。  
- 減少未使用和不必要的團隊數量。 班級已備妥並提出建議，但除非教師要使用它們，否則不會建立班級。 針對擁有超過 50 萬個團隊的大型機構，我們建議使用此選項，以減少雜亂。
- SDS
    - 成員資格會與 SIS/LMS 同步，以維護學生成員資格變更。
    - EDU 客戶成功團隊可提供免費部署協助。
    - 選擇性地建立使用者並套用 Office 365 授權。
    - 建立安全性群組，在各 Office 365 (包括 Teams 原則) 間使用。
    - 建立系統管理單元，用於限定範圍的系統管理委派和[教師密碼重設](https://docs.microsoft.com/schooldatasync/how-to-enable-teacher-password-reset)。
    - 內建的錯誤和重試處理、節流輪詢，以及用於大規模處理的工作階段穩定性，以減少系統管理員的工作。 
    - 內建的清理功能可在群組和團隊過期之後將其重新命名和封存。 
    - [成績同步](https://docs.microsoft.com/schooldatasync/grade-sync)：教師可在 Teams 中進行所有評分，並讓其自動將成績從 Teams 寫回到 SIS 成績表。 
    - [學生資料保護](https://docs.microsoft.com/schooldatasync/protecting-student-personal-data)：防止學生使用非 Microsoft 應用程式，並追蹤及管理家長同意。 
    - 匯入的資料可用來運用使用者角色、組織 (學校) 和其他重要資料以強化教育深入解析。
- Graph API
    - 額外的彈性和控制。
    - 不要求使用 SDS 整合。

### <a name="considerations"></a>考量

- 並非完全自動化，需要教師進行一些動作。
- 沒有建立團隊權限的教師仍可以從現有的群組建立團隊，如[此處](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)所示。
- Graph API 需要高階技術專業知識和時間來建立及執行指令碼，並修正建立班級群組時所發生的任何問題。

### <a name="get-started"></a>開始使用

若要使用 SDS 方法開始使用，請前往[學校資料同步 (SDS)](https://docs.microsoft.com/SchoolDataSync)，並連絡 [https://aka.ms/sdssupport](https://aka.ms/sdssupport) 部署協助。 

若要使用 Graph API 方法，請參閱 [Graph API](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-1.0&tabs=http) 和[建立班級團隊](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-beta&tabs=http)。  

> [!NOTE]
> 若要使用此方法搭配 SDS，您必須將 SDS 設定檔中的自動團隊切換關閉。 您也可以使用自動與由教育工作者引導的團隊建立組合，使用兩個 SDS 設定檔來建立必要和選用的班級團隊。

## <a name="powershell-script-using-graph-apis"></a>使用 Graph API 的 PowerShell 指令碼

利用 PowerShell，您可以編寫指令碼來建立團隊、頻道並自動進行設定。 這需要系統管理員先建立群組、新增教師和學生，然後建立團隊，如[此處](https://docs.microsoft.com/graph/teams-create-group-and-team)所示。 您也可以使用 Microsoft Graph API 來建立、設定、複製及封存團隊。 如需詳細資訊，請參閱[使用 Microsoft Graph API 來搭配使用 Microsoft Teams](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)、[Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams) 和[建立班級團隊](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta&tabs=http#example-6-create-a-team-with-a-non-standard-base-template-type)。 使用 Graph API 是獲得更多控制和彈性的絕佳方式，但它需要具備高階的技術專業知識，並且最初需要較多時間來設定。  

### <a name="benefits"></a>優點

- 額外的彈性和控制。
- 建立早期教師存取團隊或立即讓學生存取團隊的選項。  
- 如果您[從群組建立團隊](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta&tabs=http#example-4-create-a-team-from-group)，則教師會有早期存取權，並且會將學生成員資格變更同步至 Azure AD 群組。

### <a name="considerations"></a>考量

- 需要高階技術專業知識和時間來建立及執行指令碼，並修正建立班級群組時所發生的任何問題。
- 沒有內建的錯誤處理或重試邏輯。
- 成員資格變更不會與 SIS 同步。 

> [!NOTE]
> 班級團隊需要隱藏的群組成員資格，使得只有班級內的教師和學生會看到該班級的成員。 若要建立 Office 365 班級團隊，請參閱[建立班級團隊](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-beta&tabs=http)，以符合相同的隱私權需求。

## <a name="manual-team-creation"></a>手動建立團隊

當學生和授課者使用 Teams 時遇到的隔閡最小，並有彈性可量身訂做它來符合需求時，才能發揮其最大效用。 使用者可以量身訂做其 Teams 體驗的其中一個方式是能夠建立團隊。 授課者設定自己的班級類型團隊，並邀請學生，如[此處](https://support.microsoft.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b#ID0EADAAA=Create_a_team_from_scratch)所述。 授課者透過[將學生新增至團隊](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954)、[共用加入代碼](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)或[共用團隊的連結](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)來邀請學生。 若可能，最好是由授課者將學生新增至團隊，以確保學生取得存取權，並收到已將他們新增至團隊的通知。

### <a name="benefits"></a>優點

- 教師有額外的彈性。
- 立即建立團隊和存取。  

### <a name="considerations"></a>考量

- 需要教師執行動作和時間。
- 學生成員資格不會與 SIS 同步，且需要手動管理。
- 不會提供教師其團隊的早期存取權。 學生可以立即取得存取權。

## <a name="recommended-best-practices"></a>建議的最佳做法

- 盡早部署！ 盡早部署，以確保各個項目都能可靠運作，且備妥供學校的第一天使用。 如果您使用 SDS，則不需要完整的學生成員資格就能開始 SDS 部署。 當您的 SIS 中提供該資訊時，即會同步學生。
- 如果您有超過 50 萬個團隊，建議您使用[由授課者引導的團隊建立方法](#educator-led-team-creation-from-office-365-class-groups)。 透過只建立相關且需要的班級團隊，該方法能夠減少未使用的團隊和雜亂。  
- 如果 SDS 自動團隊建立發生任何問題 (例如班級遺失)，而教師立即需要這些團隊，則他們可以使用[由授課者引導的團隊建立方法](#educator-led-team-creation-from-office-365-class-groups)來重試。 [手動建立團隊](#manual-team-creation)是另一個解決方案，但是無法保持更新您的團隊成員資格。  
- 租用戶團隊的限制為 50 萬個團隊。 因此，系統管理員應積極嘗試減少未使用的團隊數量，以避免到達這些限制並延長其設定時間。 如需有關限制的詳細資訊，請參閱 [Microsoft Teams 的限制和規格](limits-specifications-teams.md)。  
