---
title: 管理貴組織的清單應用程式
author: LanaChin
ms.author: v-lanac
ms.reviewer: anach,v-jasuk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何針對貴組織中的使用者管理團隊中的 [清單] 應用程式。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: d8225198a3d56c731193d72e98d4ebebe2954a2f
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766732"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft 團隊中管理貴組織的清單應用程式

## <a name="overview-of-lists"></a>清單概覽

Microsoft 團隊中的 [清單] 應用程式可協助組織中的使用者追蹤資訊、組織工作，以及管理工作流程。 使用者可以使用清單來追蹤問題、資產、常式、連絡人、庫存、事件、貸款、患者等資料，並使用可自訂的視圖、規則和通知來保持小組中的每個人都保持同步。

在團隊中，使用者會將清單作為頻道中的索引標籤存取。 按一下 **+** 以開啟索引標籤圖庫，然後新增 [清單] 應用程式索引標籤實例至頻道，即可開始使用。 

![索引標籤庫中 [清單] 應用程式的螢幕擷取畫面](media/lists-tab.png)

使用者可以從相同團隊或其他人有權存取的 SharePoint 網站建立新清單或釘選現有清單。 您可以從內建的範本、根據現有清單的結構或從 Excel 活頁簿匯入資料，從頭開始建立新的清單。 [清單] app 可在小組桌面、web 和行動用戶端中取得。

![如何在 [清單] 應用程式中建立清單的螢幕擷取畫面](media/lists-create-list.png)

## <a name="templates"></a>模版

清單中的範本是針對使用者的常見資訊追蹤案例量身定制的。 每個範本都有一個預先定義的清單結構、表單版面配置及格式設定選項（在 [清單] 視圖和 [詳細資料] 視圖層級）中，以協助使用者快速入門。 選取範本之後，使用者就會預覽清單的外觀，以及一些範例資料。 以下範例說明貴組織中的小組如何在清單中使用預先定義的範本：

- 使用 [問題追蹤器] 範本追蹤問題並讓他們關閉。
- 使用 [事件路線] 範本來整理您的所有活動詳細資料。
- 使用患者範本，在您的醫療保健組織中記錄患者在健康小組中的需求和狀態，以監控及協調護理。
- 使用貸款範本追蹤貸款申請的狀態。

## <a name="example-scenario"></a>範例案例

當地的郵局負責在他們的地區中排序並傳送郵件。 每早上，郵局都有一個小組 huddle 來審查日常目標、共用公告，並討論已知的事件。

Huddle 之後，郵件載體會拾取其郵件，並開始傳送傳送路線。 事件可能會沿著路線進行，例如交通意外、狗相關的問題，或社交 unrest 拒付。 當郵件運營商遇到事件時，他們會在行動裝置上使用團隊來記錄事件詳細資料，並在團隊頻道清單中追蹤這些活動。 小組中的每個人（包括欄位中的郵件載體）都可以看到這項資訊並保持及時瞭解。

在移至團隊之前，郵件運營商必須回到郵局，才能完成硬拷貝表單，以報告在 Excel 試算表中輸入的事件。 團隊首先為郵件運營商提供行動裝置，讓他們可以在其中使用清單來報告其在欄位中的事件、與小組成員共用事件詳細資料、在頻道中取得相關的交談，以及將事件放到解決方案中。

## <a name="what-you-need-to-know-about-lists"></a>清單所需注意的事項

### <a name="lists-is-available-in-every-team-and-channel"></a>清單在每個團隊和頻道中都有提供

清單是針對所有團隊使用者預先安裝的，可直接在每個團隊和頻道的索引標籤庫中取得。 這表示使用者不需要移至 [小組 app store] 就能安裝它。

### <a name="lists-and-sharepoint"></a>清單和 SharePoint

清單資料會儲存在 SharePoint Online 小組網站中。 若要深入瞭解 SharePoint Online 與團隊互動的方式，請參閱 [Sharepoint online 與商務用 OneDrive 與團隊互動的方式](SharePoint-OneDrive-interact.md)。

在 SharePoint 中設定的許可權會套用至 [清單] 應用程式中建立的清單。 根據預設，清單會繼承其所屬網站的許可權。 這些許可權會控制使用者可以執行的動作類型，例如是否可以建立或編輯清單。 若要深入瞭解，請參閱 [sharepoint 中的許可權等級](https://docs.microsoft.com/sharepoint/understanding-permission-levels) ，以及 [sharepoint Server 中的使用者許可權和許可權等級](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels)。

在某些情況下，您可能會想要限制使用者可以在清單中執行的動作。 例如，小組中的人員會編輯清單視圖，這會針對所有小組成員進行變更，而您想要只允許團隊擁有者或特定小組成員編輯清單視圖。 若要深入瞭解，請參閱 [自訂 SharePoint 清單或文件庫的許可權](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013)。

> [!NOTE]
> 此時，小組中的擁有者和成員許可權不會以任何方式連結至小組網站中的許可權，以控制清單或清單應用程式的行為。 不過，根據客戶的意見反應和使用量，我們會考慮未來的產品反覆運算。  

### <a name="limitations"></a>有限

透過清單，使用者可以取得桌面、網站和行動裝置體驗。 請務必知道，使用者無法使用小組行動用戶端上的清單來建立新的清單或釘選現有清單。 若要查看或編輯小組行動用戶端上的清單，必須先使用小組桌面或 web 用戶端上的清單來建立或新增清單。

來賓無法建立或刪除清單。 他們可以在現有清單中新增清單專案、開始建立清單專案的新交談，以及回復清單專案的現有交談。

### <a name="lists-and-the-sharepoint-app"></a>清單和 SharePoint 應用程式

如果貴組織中的使用者使用 SharePoint 應用程式建立清單，這些清單將會自動移至清單，而不需要使用者進行任何動作。 若要在小組中取得最佳最豐富的清單整合體驗，請使用清單 app 並釘選現有清單。

## <a name="set-up-lists"></a>設定清單

### <a name="enable-or-disable-lists-in-your-organization"></a>啟用或停用貴組織中的清單

預設會針對貴組織中的所有團隊使用者啟用清單。 您可以在 Microsoft 團隊系統管理中心的 [ [管理應用程式](manage-apps.md) ] 頁面上關閉或開啟組織階層的 app。

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [ **團隊 app**  >  **管理應用程式** ]。
2. 執行下列其中一項動作：

    - 若要關閉貴組織的清單，請搜尋 [清單] 應用程式，選取它，然後按一下 [ **封鎖** ]。
    - 若要開啟貴組織的清單，請搜尋 [清單] 應用程式，選取它，然後按一下 [ **允許** ]。

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a>啟用或停用貴組織中特定使用者的清單

若要允許或封鎖貴組織中的特定使用者使用清單，請確定您的組織已開啟 [ [管理應用程式](manage-apps.md) ] 頁面上的清單，然後建立自訂應用程式許可權原則，並將其指派給那些使用者。 若要深入瞭解，請參閱 [在團隊中管理 app 許可權原則](teams-app-permission-policies.md)。

## <a name="search-the-audit-log-for-list-events"></a>在審核記錄中搜尋清單事件

清單是以企業級審核啟用，因此您可以在安全性 & 合規性中心的 [審核] 記錄中搜尋清單及清單專案事件。 若要深入瞭解，請參閱 [在安全性 & 合規性中心搜尋審核記錄](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。

如需小組中與 [清單] 應用程式相關的審核事件清單，請參閱 [SharePoint 清單活動](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities)。

在您可以搜尋審核記錄之前，您必須先在 [安全性 & 合規性中心](https://protection.office.com)開啟審核。 請記住，審核資料只能從您開啟審核的位置取得。

## <a name="power-automate-power-apps-and-graph-api"></a>電源自動化、Power App 及圖形 API

清單支援工作流程的 [電源自動](https://preview.flow.microsoft.comconnectors/shared_sharepointonline/?slug=sharepoint) 作業及清單表單的 [power app](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form) 。 開發人員可以使用 [清單 API](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) ，將清單資料作為來源，透過 Microsoft Graph 連線。

## <a name="give-feedback-or-report-an-issue"></a>提供意見反應或報告問題
  
若要向我們傳送意見反應或報告問題， **請按一下 [** 團隊] 左側導覽底部附近的 [說明]，然後選取 [ **報告問題** ]。 選取 [ **清單** ]，然後輸入您的意見反應或您所遇到之問題的詳細資料。

## <a name="related-topics"></a>相關主題

- [清單說明文件](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Lists)
