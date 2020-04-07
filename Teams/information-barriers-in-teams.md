---
title: Microsoft 團隊中的資訊障礙
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: vikramju
f1.keywords:
- NOCSH
description: 瞭解資訊障礙及其對團隊有何影響。
appliesto:
- Microsoft Teams
ms.openlocfilehash: a666d89e78a9234144eb09173b713d1186410206
ms.sourcegitcommit: 25e70de7c943e22fe6ac6e8d6b4353ca68f81f83
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2020
ms.locfileid: "43157816"
---
# <a name="information-barriers-in-microsoft-teams"></a>Microsoft 團隊中的資訊障礙

資訊壁壘（IB）是系統管理員可以設定的原則，以避免個人或群組彼此通訊。 例如，如果某個部門處理的資訊不應與其他部門共用，或者必須防止或獨立地與該群組外的任何人通訊，這就很有用。

> [!NOTE]
> - 資訊屏障群組無法跨承租人建立。
> - 在版本1中不支援使用 bot 來新增使用者。
> - 專用通道符合您設定的資訊屏障原則。
> - [新增]：連線至團隊之 SharePoint 網站的資訊障礙支援現已成為私人預覽。 按一下[這裡](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR3-O9WDTKhhDtgWfphwS9YhUM0hJNklNRkZKMlhLNDRZNzlEQlVDSjdZVi4u)以參與私人預覽。

資訊屏障原則也會防止查閱和探索。 這表示如果您嘗試與您不應該與之通訊的人通訊，就不會在人員選擇器中找到該使用者。

## <a name="background"></a>背景

資訊障礙的主要驅動因素是來自金融服務行業。 財務行業監管機構（[FINRA]( http://www.finra.org)）會在成員公司內審查資訊的壁壘與利益衝突，並提供如何管理此類衝突（FINRA 2241、[債務研究規章注意事項 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)）的指導方針。  

不過，由於資訊障礙的推出，許多其他區域都會發現它們很有用。 其他常見的案例包括：

- 教育：一學校的學生無法查詢其他學校學生的連絡人詳細資料。
- 法律：維護一個用戶端的律師所取得之資料的機密性，不受代表不同用戶端之同一事務所的律師存取。
- 政府：資訊存取和控制限制在各個部門和群組中。
- [專業服務]：公司中的一組人員只能透過同盟或來賓存取權在客戶合作期間與用戶端或特定客戶進行交談。

例如，Enrico 屬於 [銀行] 區段，而 Pradeep 屬於 [財務顧問] 區段。 Enrico 和 Pradeep 無法彼此通訊，因為組織的 IB 原則會封鎖這兩個區段之間的通訊與共同作業。 不過，Enrico 和 Pradeep 可以與 HR 中的 [人力資源] 進行溝通。

![此範例顯示資訊障礙，避免在區段之間通訊](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>何時使用資訊障礙

在下列情況下，您可能會想要使用資訊障礙：

- 小組必須防止與特定其他團隊進行通訊或共用資料。
- 小組不能與團隊以外的任何人通訊或共用資料。

資訊屏障原則評估服務會判斷通訊是否符合資訊屏障原則。

## <a name="managing-information-barrier-policies"></a>管理資訊屏障原則

資訊屏障原則是在 Office 365 安全性 & 合規性中心（SCC）使用 PowerShell Cmdlet 來管理。 如需詳細資訊，請參閱[定義資訊屏障的原則](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)。

> [!IMPORTANT]
> 在您設定或定義原則之前，**您必須在 Microsoft 團隊中啟用範圍目錄搜尋**。 在您設定或定義資訊屏障的原則之前，請先在啟用範圍目錄搜尋後等候至少24小時。 [深入瞭解資訊障礙的先決條件](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites)。

## <a name="information-barriers-administrator-role"></a>資訊障礙管理員角色

IB 相容性管理角色負責管理資訊屏障原則。 如需有關此角色的詳細資訊，請參閱[Office 365 安全性 & 合規性中心的許可權](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center)。

## <a name="information-barrier-triggers"></a>資訊屏障觸發程式

資訊屏障原則會在下列團隊事件發生時啟用：

- **成員會新增至團隊**-每當您將使用者新增至團隊時，必須針對其他團隊成員的資訊屏障原則評估使用者的原則。 成功新增使用者之後，使用者就可以執行團隊中的所有職能，而不需要進一步檢查。 如果使用者的原則禁止將他們加入小組，使用者就不會顯示在搜尋中。

    ![顯示群組聊天的螢幕擷取畫面](media/information-barriers-add-members.png)

- **要求新的聊天**：每次在兩個或多個使用者之間要求新的交談時，就會評估聊天，以確保它不違反任何資訊屏障原則。 如果交談違反資訊屏障原則，就不會啟動交談。

    以下是1:1 聊天的範例。

     ![顯示1:1 聊天中封鎖通訊的螢幕擷取畫面](media/information-barriers-one-one-chat.png)

    以下是群組聊天的範例。

    ![顯示群組聊天的螢幕擷取畫面](media/information-barriers-group-chat.png)

- **使用者受邀加入會議**-當使用者受邀加入會議時，系統會針對其他團隊成員的原則評估使用者的原則，如果發生衝突，就不允許使用者加入會議。

    ![顯示使用者已封鎖會議的螢幕擷取畫面](media/information-barriers-meeting.png)

- **在兩個以上的使用者之間共用螢幕**-只要兩個或多個使用者共用畫面，就必須評估畫面共用，以確保它不會違反其他使用者的資訊屏障原則。 如果違反資訊屏障原則，就不允許使用螢幕共用。
- **使用者將電話撥打電話（VOIP）放在團隊中**，只要使用者向其他使用者或群組使用者啟動語音通話，就會評估通話，確定它不會違反其他小組成員的資訊屏障原則。 如果有任何侵犯，語音通話會遭到封鎖。
- **小組中的來賓使用者**也可以在小組中的來賓使用者也套用資訊屏障原則。 如果在貴組織的全域通訊清單中，來賓使用者需要可被探索，請參閱[管理 Office 365 群組中的來賓存取](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups?view=o365-worldwide#can-i-make-guest-objects-visible-in-the-global-address-list)。 一旦訪客使用者可被發現，您就可以[定義資訊屏障原則](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)。

## <a name="how-policy-changes-impact-existing-chats"></a>原則變更對現有聊天有何影響

當資訊屏障原則管理員對原則進行變更，或由於使用者的設定檔變更（例如作業變更或類似的原因），資訊屏障原則評估服務會自動搜尋成員，以確保小組成員不會違反任何原則的情況。

如果使用者之間已有聊天或其他通訊，且已設定新的原則，或是已變更現有的原則，此服務會評估現有的通訊，以確保仍允許進行通訊。

- **1:1 聊天**-如果已不再允許兩個使用者之間的通訊（如果原則封鎖通訊已套用至一或兩個使用者），系統會封鎖進一步通訊，聊天交談就會變成隻讀狀態。

- **群組聊天**-如果已不再允許來自某個使用者的通訊（例如，如果使用者變更了工作），則該使用者與違反該原則的其他使用者都可能會從群組聊天中移除，且不允許進一步與群組通訊。 使用者仍然可以看到舊的交談（這會是唯讀的），但無法看到或參與與群組的任何新交談。 如果新的或已變更的原則將通訊套用到多個使用者，則受該原則影響的使用者可能會從群組聊天中移除。 他們仍能看到舊的交談。

在這個範例中，Enrico 移至組織內的不同部門，並從群組聊天中移除。

  ![顯示群組聊天的螢幕擷取畫面](media/information-barriers-user-changes-job.png)

Enrico 無法再傳送訊息到群組聊天。

  ![顯示群組聊天的螢幕擷取畫面](media/information-barriers-user-changes-job-2.png)

- **小組**-已從群組中移除的任何使用者都會從小組中移除，而且將無法查看或參與現有或新的交談。

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>案例：現有聊天中的使用者遭到封鎖

目前，如果資訊屏障原則封鎖其他使用者，使用者就會遇到下列問題：

- [**人員]** 索引標籤-使用者無法在 [**人員**] 索引標籤上看到封鎖的使用者。
- **人員選擇器**-在 [人員選擇器] 中不會顯示封鎖的使用者。

    ![顯示群組聊天的螢幕擷取畫面](media/information-barriers-people-picker.png)
    
- [**活動]** 索引標籤-如果使用者要造訪封鎖使用者的 [**活動**] 索引標籤，就不會顯示任何文章。 （[**活動**] 索引標籤只會顯示頻道發佈，而在兩個使用者之間則不會有任何常見頻道。）
- **組織**結構-如果使用者存取的組織結構中出現封鎖的使用者，則封鎖的使用者不會出現在組織結構上，而是會顯示錯誤訊息。
- **連絡人卡片**-如果使用者參與交談，且隨後遭到封鎖，當使用者將游標移到封鎖的使用者名稱上時，其他使用者就會看到錯誤訊息，而不是連絡人卡片。 在卡片上所列的動作（例如 [通話與聊天]）將無法使用。
- [**建議的連絡人**]：封鎖的使用者不會出現在 [建議的連絡人] 清單中（針對新使用者顯示的初始連絡人清單）。
- [**聊天連絡人**]-使用者可以在聊天連絡人清單中看到封鎖的使用者，但會辨識封鎖的使用者，而使用者唯一可以執行的動作就是刪除它們。 使用者也可以按一下他們來查看其過去的交談。
- [**通話連絡人**]-使用者可以在通話連絡人清單中看到封鎖的使用者，但系統會辨識封鎖的使用者，而使用者唯一可以執行的動作就是刪除它們。
- **Skype 至團隊遷移**-在商務用 skype 中進行團隊遷移期間，所有使用者（即使是資訊屏障原則所封鎖），都會將它遷移至小組，然後將按照上述步驟進行處理。

## <a name="teams-policies-and-sharepoint-sites"></a>團隊原則與 SharePoint 網站

建立小組後，SharePoint 網站就會提供給小組，並與 [檔案體驗] 相關聯。 此 SharePoint 網站和檔案的存取權會採用組織的 IB，亦即，只有其針對每個 IB 原則的 IB 區段相符的使用者才能存取。 即使在檔案共用時，IB 原則也會生效。

例如：在 Contoso 銀行公司中，使用者「Sesha@contosobank.onmicrosoft.com」屬於投資銀行區段，而使用者 ' Nikita@contosobank.onmicrosoft.com ' 屬於區段建議。 組織的 IB 原則會封鎖這兩個區段之間的通訊與共同作業。
當使用者 Sesha 建立投資銀行區段的小組時，只有投資銀行區段使用者才能存取該小組和支援該小組的 SharePoint 網站。 即使她擁有 [網站] 連結，使用者 Nikita 還是無法存取該網站。

## <a name="required-licenses-and-permissions"></a>所需的授權和許可權

如需詳細資訊（包括方案和定價），請參閱[授權指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

## <a name="more-information"></a>詳細資訊

- 若要深入瞭解資訊障礙，請參閱[資訊障礙](https://docs.microsoft.com/office365/securitycompliance/information-barriers)。

- 若要設定資訊屏障原則，請參閱[定義資訊屏障的原則](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)。

- 若要編輯或移除資訊屏障原則，請參閱[編輯（或移除）資訊屏障原則](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies)。
