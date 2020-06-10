---
title: 在組織中支援 Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.custom: seo-marvel-mar2020
ms.reviewer: marcl, billkau
audience: admin
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
description: 無論您是 Teams 系統管理員或服務支援工程師，都能使用這些資源在組織中支援 Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: cde06d104f6f61efd981bb87b1503e8f097c5c26
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637032"
---
# <a name="support-microsoft-teams-in-your-organization"></a>在組織中支援 Microsoft Teams

> [!NOTE]
> 本文取代 [Teams 的已知問題] 文章。 

使用本文中的資源，協助您在組織中支援 Teams。 

首先，請在以下文章複習最[常見問題與解決方法](#common-issues-and-resolutions)清單。

然後，如果您找不到所需的資訊，請移至 [Teams 疑難排解](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)，然後在目錄或 [依標題篩選]**** 方塊中搜尋您的問題。 
:::image type="content" source="media/known-issues1.png" alt-text="[Teams疑難排解] 頁面上的 [目錄] 和 [篩選] 方塊的螢幕擷取畫面":::

如果仍然無法解決問題，請與 [Microsoft 支援服務](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)聯繫。


## <a name="common-issues-and-resolutions"></a>常見問題和解決方案

> [!NOTE]
> 如需協助部署 Teams 以支援起因於 COVID-19 的遠端工作人員 (WFH)，請參閱[支援使用 Teams 的遠端工作者](support-remote-work-with-teams.md)。 此外，您可能符合 Microsoft 365 FastTrack 計畫的部署協助，請造訪 [[FastTrack 中心]](https://www.microsoft.com/fasttrack) 以提交要求。

### <a name="for-all-teams-customers"></a>適用於所有 Teams 客戶

| |  |
|---------|---------|
|**Teams 的新使用者嗎？**    |請參閱[開始使用 Microsoft Teams](get-started-with-teams-quick-start.md)。         |
|**啟用 Teams 來賓存取**     |參閱 [Teams 來賓存取檢查清單](guest-access-checklist.md)，並確定已完成所有步驟。 請參閱下列其他資源：<ul><li>[了解 Microsoft Teams 中的來賓存取](guest-access.md)</li>[來賓加入團隊的方式](guest-joins.md) <li>[設定 – Microsoft Teams 來賓存取檢查清單](guest-access-checklist.md)</li></ul>|
|**Teams 會議與撥入**    |需要在 Teams 中開啟或設定音訊會議的協助嗎？ 這名使用者是最近建立的嗎？ 如果是，您必須等待 2 至 24 小時**設定才會生效**。<br>若要驗證使用者已獲得音訊會議授權，並擁有預設付費電話號碼：<br><ol><li>在 Microsoft 365 系統管理中心，移至 **[作用中的使用者]**，然後選取有問題的使用者。</li><li> 視系統管理中心的版本而定，請選擇 **[授權和應用程式]**，或按一下 **[產品授權]** 上的 **[編輯]**。</li><li> 確認使用者已選取 [音訊會議]、[Microsoft Teams ] 和 [商務用 Skype Online (方案2)] 的授權。</li><li>在 **[系統管理中心]** 按一下 **[全部顯示]**，再按一下 **[Teams]**。</li><li>在 [Microsoft Teams 系統管理中心] 中，按一下 **[傳統入口網站]**。</li><li>在 [商務用 Skype 系統管理中心] 中，按一下 **[音訊會議]**，再按一下 **[使用者]**。</li><li>選取有問題的使用者，並確認使用者有 [預設付費電話號碼]。</li> </ol> 如需詳細資訊，請參閱[通話方案](calling-plans-for-office-365.md) (部分機器翻譯)，或撥打 Microsoft 商務帳單小組，取得授權相關問題的協助。 <br><br>其他資源：<ul><li>[Microsoft Teams 中的會議和召集會議](deploy-meetings-microsoft-teams-landing-page.md)</li><li>[音訊會議](audio-conferencing-in-office-365.md)</li></ul>       |
|**Teams Exploratory 授權**     |Microsoft Teams Exploratory 體驗可讓貴組織中擁有 Azure Active Directory (AAD) 和未取得 Teams 授權的使用者起始 Teams 探勘體驗。 系統管理員可以為其組織中的使用者開啟或關閉這項功能。 舊版 [Microsoft 商務雲端試用版](iw-trial-teams.md)現在已由 Teams Exploratory 體驗取代。 <br><br>其他資源：<ul><li>[使用者註冊 Teams Exploratory 體驗的方式](teams-exploratory.md#how-users-sign-up-for-the-teams-exploratory-experience)</li><li>[管理 Teams Exploratory 體驗](teams-exploratory.md#manage-the-teams-exploratory-experience)</li></ul>|
|**私人頻道**    |Microsoft Teams 中的私人頻道為小組內的共同作業建立了焦點空間。 只有小組中身為私人頻道的擁有者或成員的使用者，才可以存取頻道。 任何人 (包括來賓) 都可以新增為私人頻道的成員，只要他們已經是小組的成員即可。<br><br>如果要將共同作業限制為需要知道的人員，或是在不另外建立小組來管理已指派特定專案小組的情況下，促進小組人員之間的溝通，您可能會想要使用私人頻道。<br><br>其他資源：<ul><li>[使用者註冊 Teams Exploratory 體驗的方式](teams-exploratory.md#how-users-sign-up-for-the-teams-exploratory-experience)</li><li>[管理 Teams Exploratory 體驗](teams-exploratory.md#manage-the-teams-exploratory-experience)</li><ul>        |
|**會議原則**|[會議原則](meeting-policies-in-teams.md)是針對由您組織中的使用者所排程的會議，控制會議參與者可用於會議的功能。 建立原則並進行變更之後，您可以將使用者指派給該原則。         |
||**變更或建立會議原則**<br><br>若要變更或建立會議原則，請移至 [Microsoft Teams 系統管理中心] > **[會議] ** > ** [會議原則]**。 從清單中選取原則，或選取 **[新增]**。 如果您要建立新原則，請新增原則的名稱和描述。 名稱不能包含特殊字元，且長度不可超過 64 個字元。 選擇您的設定，然後按一下 [儲存]****。 例如，假設您有多位使用者，並且想要限制其會議所需的頻寬量。 您可以建立名為「有限頻寬」的新自訂原則，並停用下列設定：<br><br>在 [音訊與視訊]**** 下：<ul><li>關閉 [允許雲端錄製]。</li><li>關閉 [允許 IP 視訊]。</li></ul>在 [內容共用]**** 下：<ul><li>停用 [螢幕畫面分享模式]。</li><li>關閉 [允許白板]。</li><li>關閉 [允許共用記事]。</li></ul>然後，將原則指派給使用者。         |
| |**將會議原則指派給使用者**<br><br>若要指派會議原則給一位使用者：<ol><li>在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]****，然後按一下該使用者。</li><li>按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]****。</li><li>在 [會議原則]**** 下，選取要指派的原則，然後按一下 [套用]****。</li></ol> 若要一次將原則指派給多位使用者： <ol><li>在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]****，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。</li><li>在 [&#x2713;]**** (核取方塊) 欄中，選取使用者。 若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713;] (核取方塊)。</li><li>按一下 [編輯設定]****，進行所需的變更，然後按一下 [套用]****。</li></ol>或者，您可以執行下列內容︰<ol><li>在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [會議] > [會議原則]****。</li><li>按一下原則名稱的左側來選取原則。</li><li>選取 [管理使用者]****。</li><li>在 [管理使用者]**** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]****。 針對要新增的每一個使用者重複此步驟。</li><li>新增完使用者之後，按一下 **[儲存]**。</li></ol> ||**遺失撥號鍵台的疑難排解**     |請執行下列動作： <ul><li>請確認已指派使用者 [[Teams 授權]](teams-add-on-licensing/assign-teams-add-on-licenses.md)。</li><li>請確認已指派使用者 [[通話方案]](calling-plan-landing-page.md)。</li><li>為使用者啟用 [[企業語音]](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-enterprise-voice-online-and-phone-system-voicemail#to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail)。</li></ul>      ||**疑難排解 Teams 登入問題**   |首先，請確認 [Microsoft Teams 服務狀況良好](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/servicehealth)。 然後檢查是否有任何常見的錯誤碼，並參閱[為何我無法登入 Microsoft Teams？](https://support.office.com/article/a02f683b-61a3-4008-9447-ee60c5593b0f)  您可能還需要參閱 [Microsoft Teams 中的身分識別模型和驗證方式](identify-models-authentication.md) (部分機器翻譯)。         |

### <a name="for-education-customers"></a>適用於教育版客戶

|||
|---------|---------|
|您的使用者看到「您錯過了！」 的訊息。   |請確定要[為您的學校啟用 Microsoft Teams](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams)。 在 EDU 租用戶中不會預設啟用 Teams；您必須先將它開啟。 <br><br>接下來請參閱[遠端教學和學習](https://support.office.com/article/remote-teaching-and-learning-in-office-365-education-f651ccae-7b65-478b-8366-51bb884025c4)，以了解如何設定學校、課程規劃、虛擬會議，以及與學生共用內容的最新指導方針。<br><br>最後，請務必在 [Teams 的管理訓練](itadmin-readiness.md)中查看 Microsoft Teams IT 系統管理員訓練影片、投影集和許多其他資訊。        |


## <a name="related-topics"></a>相關主題

[Teams 疑難排解](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

[Teams 的支援資源](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
