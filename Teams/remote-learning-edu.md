---
title: 適用于教育系統管理員的 Microsoft 團隊資源
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: karsmith
ms.topic: reference
ms.service: msteams
audience: admin
description: 適用于 EDU 的 Microsoft 團隊的遠端學習啟動指導方針。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87d9e36578227c8f27acfdfd07abfa0cadbe69b7
ms.sourcegitcommit: f23c428043bb0b37c9a8600e64691bc2a1f2e874
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2020
ms.locfileid: "42403833"
---
# <a name="get-started-with-microsoft-teams-for-remote-learning"></a>開始使用 Microsoft 團隊進行遠端學習

Microsoft 團隊是一種將交談、內容、作業和應用程式集中在一個位置的平臺。 建立共同作業，並以專業學習社區連線，並與同事連線–全部都來自單一體驗。

您可以使用本文中的最佳做法開始使用 Microsoft 團隊，讓您的教學需求啟用遠端學習功能。 Microsoft 團隊可以用來啟用課程共同作業，讓學生參與交談、提供虛擬會議平臺，以及散佈作業。 學校管理員和人員可隨時掌握最新資訊，並使用通知與 topical 交談的小組共同作業。 使用專業的學習社區，教育者可以分享說明性的資料。

Microsoft 團隊擁有適用于桌面（Windows、Mac 和 Linux）、web 及行動裝置（Android 與 iOS）的[用戶端](get-clients.md)，以確保您所有的員工和學生都能保持連線。

深入瞭解[適用于教育網路研討會系列小組](https://aka.ms/TeamsEDUWebinars)的 Microsoft 團隊使用方式。

## <a name="user-accounts-licenses-and-identity-security"></a>使用者帳戶、授權及身分識別安全性

Microsoft 團隊利用 Microsoft 365 功能來驗證使用者並提供服務。 員工、教師和學生應該已建立身分識別，以協助共同作業。 如果身分識別尚不存在，請遵循此程式來建立。

您[必須先為使用者啟用團隊授權，](user-access.md)才能開始使用團隊功能。 團隊依賴其他 Microsoft 365 功能（例如[Office 365 群組](Office-365-groups.md)、 [Exchange](Exchange-Teams-interact.md)、 [SharePoint 和 OneDrive](SharePoint-OneDrive-interact.md) ）來啟用共同作業案例。 如果所有這些服務也都已啟用，使用者就會收到最佳的團隊體驗。 [小組支援由 Google 託管電子郵件的使用者使用](https://docs.microsoft.com/microsoft-365/education/deploy/enabling-teams-for-education-for-google-users)。

## <a name="easily-set-up-microsoft-teams"></a>輕鬆設定 Microsoft 團隊

以下是您必須執行的兩項動作，才能開始與團隊進行作業：

### <a name="1-allow-users-to-create-teams"></a>1. 允許使用者建立小組

學生與教育者將能在最小的障礙中使用小組，並能靈活地根據自己的需求加以調整。 使用者可以根據自己的需求建立小組，以調整其團隊體驗。 **根據預設，每個人都可以建立 Office 365 群組和團隊**。 有時這項功能可能不適用;例如，某些客戶可能想要限制主要副學生建立小組。 如有需要，您可以將 Office 365 群組和小組建立限制在您環境中的[特定安全性群組](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups)。

當您讓所有人（包括學生）建立課程、研究、群組專案，以及學習群組時，高等教育客戶可獲得較高的教育成績。 主要-副學校可能會想要限制學生建立小組，以確保在包含成人的論壇中進行所有學生對學生通訊。 在此案例中，您可以將 Office 365 群組和小組建立限制在所有的教育者與員工。

### <a name="2-configure-user-experiences-using-policies"></a>2. 使用原則設定使用者體驗

[團隊原則](teams-policies.md)提供控制特定使用者或使用者群組可用選項的功能。 您可以套用原則，以定義應該允許誰使用私人聊天、私人通話、會議排程、可共用的內容類型等。

使用預設（全域）原則所含的功能 **，高等教育員工、教育者和學生**都能受益。 您可以啟用一些其他原則設定，為 Microsoft 團隊新增更多功能，包括[啟用訊息原則中的翻譯功能](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings)，以及允許自動會議在會議原則中進行。

**主要-副學校學生**可能需要提供受限制的許可權給學生。 原則設定學生可以進行的動作界限。 因為學生人數通常是最大的一組使用者，而且通常會收到限制性最強的設定，所以建議您變更「全域（組織範圍預設值）」策略的學生原則。

以下是一組常用的非預設原則設定，這些設定會指派給主要副學生，以限制學生間的 unmoderated 通訊：

#### <a name="messaging-policy"></a>訊息原則

- 變更設為 [關閉]
- Giphy 的內容評等設定為「strict」
- [翻譯郵件] 已設定為 [開啟]
- 使用 [優先順序通知] 設定為 [關閉] 來傳送緊急郵件
- 從群組聊天中移除使用者設定為 [關閉]

#### <a name="meeting-policy"></a>會議原則

- 允許將頻道中的 [立即開會] 設定為 [關閉]
- 允許將 Outlook 增益集設為 [關閉]
- 允許將 [頻道會議排程] 設定為 [關閉]
- 允許將私人會議的排程設定為 [關閉]
- [允許在私人會議中立即開會] 設定為 [關閉]

#### <a name="live-events-policy"></a>即時事件原則

- [允許排程] 設定為 [關閉]

#### <a name="calling-policy"></a>通話原則

- 將私人通話設定為 [off] （關閉）

#### <a name="teams-policy"></a>團隊原則

- 建立專用頻道設定為 [關閉]

**主要學校員工和教育**者應該指派提供受限於學生限制之核心功能的原則。 建立可讓您進行私人聊天與會議排程的新原則（新原則的預設設定）。 透過[安全性群組成員資格將這些原則指派給您的員工並進行教育](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)。

## <a name="start-using-teams"></a>開始使用團隊

### <a name="create-class-teams-for-secure-classroom-use"></a>建立課程小組以進行安全的教室使用

Microsoft 教育版團隊提供[特定的小組類型](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)供教學使用。 「[課程小組類型](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)」是針對具有特定功能的教室而設計的，包括：作業、OneNote 教室筆記本、[課程材料資料夾](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988)（用於保護學生的唯讀內容），以及讓中斷式學生靜音的功能。 有幾種方法可讓您部署班級團隊：

1. 您可以**設定**[學校資料同步](https://sds.microsoft.com/)處理（SDS），讓所有課程都能根據學校資訊系統中的資訊來建立課程小組。 這個程式會為每個區段設定小組，並讓教師與學生 rosters 同步處理。在 admitting 學生之前，[教育者將能準備好其小組](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78)。 或者，如果教師不使用小組，學生就不會被獲准加入小組，因為教師永遠不需要按一下 [啟動]。 SDS[支援超過](https://aka.ms/SDSSupport)80 個不同的學校資訊系統（SIS 系統），可協助您規劃及設定。
1. **教育**者自行設定班級類型小組，並邀請學生。 教育者可以透過[將學生新增給小組](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954)、[共用加入代碼](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)，或[共用團隊連結來](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)執行此動作。 如果可能的話，建議您將學生新增給小組，以確保學生取得存取權，並通知他們已新增至小組。

在小組設定之後，小組擁有者可以[自訂小組的設定](https://support.office.com/article/find-your-class-team-s-settings-in-microsoft-teams-2592d4de-581d-4952-9028-02317880c158)，包括新增[小組圖片](https://support.office.com/article/change-your-team-picture-02ea2af6-b49d-4de8-9551-1a5e472993c0)、建立課程主題或群組共同作業區域的[頻道](https://support.office.com/article/create-student-project-groups-channels-in-microsoft-teams-f85b3c07-fb87-4b94-883b-9be55f4b1e45?ui=en-US&rs=en-US&ad=US)、新增像是 Quizlet/Flipgrid/kahoot 之類的[應用程式](https://support.office.com/article/add-an-app-to-teams-b2217706-f7ed-4e64-8e96-c413afd02f77)，以呈現現有的教學內容，並[提及其小組的第一篇文章](https://support.office.com/article/using-the-conversation-tab-in-microsoft-teams-53d1c530-3797-4a6f-9892-6760f8763df2)來通知每個人並開始交談。

### <a name="create-staff-teams-for-staff-communication-and-collaboration"></a>建立員工小組以進行人員溝通與共同作業

[教職員工類型小組](https://support.office.com/article/create-a-staff-team-in-microsoft-teams-314ac9d5-36a9-408e-8ae4-7ef20e9f1ddf)專為學校管理員與員工設計，輕鬆共用資訊，並在學校的方案中共同作業，包括製作宣告、設定會議、共用內容，以及引入外部 app，就像是[任務追蹤的 Planner](https://support.office.com/article/create-a-plan-with-planner-d000976a-7490-4ddf-b9af-09ee764891e2)。 學校管理員可以透過小組建立嚮導將學校員工成員新增至小組，[並在建立小組之後新增成員](https://support.office.com/article/add-members-to-a-team-in-teams-aff2249d-b456-4bc3-81e7-52327b6b38e9)，或是[共用加入程式碼或連結至小組](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)。 [建立通道](https://support.office.com/article/create-a-channel-in-teams-fda0b75e-5b90-4fb8-8857-7e102b014525)是依工作流或主旨組織交談和檔案的絕佳方式。 [小組擁有者的入門指南](https://support.office.com/article/go-to-guide-for-team-owners-75f9669b-bd8f-457d-b60b-ac2ac9c8ead4?ui=en-US&rs=en-US&ad=US)是瞭解團隊擁有者職責和功能的絕佳位置。

## <a name="teams-meeting-scenarios"></a>團隊會議案例

### <a name="collaborative-meetings-for-virtual-classes"></a>虛擬班級的合作會議

[Microsoft 團隊會議](https://docs.microsoft.com/MicrosoftTeams/tutorial-meetings-in-teams)支援最多250個併發的出席者，包括音訊、影片、[內容共用](https://support.office.com/article/show-your-screen-during-a-meeting-90c84e5a-b6fe-4ed4-9687-5923d230d3a7)、白板和共用筆記等功能。 您可以在 Microsoft 團隊用戶端中排程會議，以便在[私人空間或團隊頻道](https://docs.microsoft.com/MicrosoftTeams/tutorial-meetings-in-teams)內進行會議，讓所有小組成員都知道這一點。 您可以錄製並儲存會議，供出席者日後查看。 您也可以 transcribed 這些錄製[，輕鬆地找到](https://support.office.com/article/Microsoft-Stream-automatically-creates-closed-captions-for-videos-8d6ac353-9ff2-4e2b-bca1-329499455308)已討論的內容。 可擕式電腦或行動電話網路攝像頭、麥克風和喇叭可用於會議，您可以從[Microsoft 團隊優化的裝置](https://products.office.com/microsoft-teams/across-devices/devices)取得優質音訊/視頻品質。

### <a name="districtuniversity-events-or-updates"></a>地區/大學活動或更新

有些指示需要更多的物件和其他的生產功能。 這些會議通常已定義簡報者、製造商及&A 的審查 Q。 Microsoft 團隊會使用[Microsoft 團隊即時事件](teams-live-events/what-are-teams-live-events.md)來支援這些會議。 即時事件可用於案例，例如地區或大學範圍的更新、領導位址，以及適用于大型課程或學生群組的指示，或延伸至您的群組。 深入瞭解如何進行即時會話：[規劃及排程即時](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502)事件、[產生即時](https://support.office.com/article/video-produce-a-live-event-34c89e79-ffd4-4a6a-baf6-77055e0709cb)事件、[參與即時事件](https://support.office.com/article/video-attend-a-live-event-d837ad8d-ce34-44d0-9744-9beb50e943ac)，以及[moderating Q&a](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76)。

## <a name="recommended-tips--tricks"></a>& 墩的建議秘訣

您可以深入瞭解 Microsoft 團隊在教育版中的使用方式，請參閱[Microsoft 團隊教育](https://support.office.com/article/Teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114)版。

> [!NOTE]
> 某些主要的 Microsoft 團隊功能並非適用于教育版。 核心團隊功能的秘訣和訣竅可在以下網址找到： [Microsoft 團隊說明與學習](https://support.office.com/teams)。

## <a name="adoption-content"></a>採用內容

Microsoft 已開發適用于部署 Microsoft 團隊的[採納內容](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76)與策略指導方針。 [Microsoft [團隊採用指南](https://teamworktools.azurewebsites.net/tft/index.html)] 提供了可供團隊感知使用的許多範本，並提供更好的可用內容與[團隊客戶成功案例](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip)。 Microsoft 教師中心提供教育特定訓練，說明如何在教室中使用[Microsoft 團隊](https://education.microsoft.com/learningPath/18793af1)和[OneNote](https://education.microsoft.com/learningPath/b6e3b5f2) 。

其他採用資源包括：

- ["您可以在： 90" 快速提示影片中](https://www.youtube.com/playlist?list=PLiluTszfwwMKx-yVe7ekBX6gsLIHf1Z8k)
- [Microsoft 團隊教育版影片播放清單](https://www.youtube.com/playlist?list=PLiluTszfwwMKicAo6agloFALEB5WvYNYs)
- [博客：請參閱此學校如何使用團隊進行距離學習](https://www.wellingtoncollege.cn/tianjin-international/teaching-and-learning-update/)

## <a name="support-readiness"></a>支援就緒性

IT 專業人員和支援人員可以利用 Microsoft 團隊 IT 架構海報與系統管理技術訓練，協助您快速掌握團隊架構及 Microsoft 365 功能的基本用途。

其他支援資源包括：

- [疑難排解 Microsoft 團隊安裝與更新問題](troubleshoot-installation.md)
- [監控及管理通話品質](monitor-call-quality-qos.md)
- [驗證 Teams 的服務健康情況](service-health.md)
- [Teams 的支援資源](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [監控及管理通話品質](monitor-call-quality-qos.md)
- [驗證 Teams 的服務健康情況](service-health.md)
- [Teams 的支援資源](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [Microsoft 團隊說明中心](https://support.office.com/en-us/teams)
