---
title: 開始使用適用于醫療保健組織的團隊
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-overview
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 瞭解 Microsoft 團隊 telehealth、EHR 整合、第一線 worker 系統整合，以及患者 app 等健康護理功能。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: a5b8ea7cddba8def74a1f5b839710cf73bafc67e
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125766"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>開始使用適用于醫療保健組織的團隊

Microsoft 團隊提供許多適用于醫院和其他醫療保健組織的 telemedicine 功能。 團隊功能正處於開發階段，可協助醫院進行下列作業：

- 虛擬走訪與電子醫療保健記錄 (EHR) 整合
- 團隊原則套件
- 安全訊息
- 團隊範本
- 護理協調與共同作業

此功能是適用于醫療保健版 Microsoft 雲端的一部分。 進一步瞭解如何使用此方案，這會在 [Microsoft 雲端的醫療保健](https://docs.microsoft.com/industry/healthcare)版中從 Azure、Dynamics 365 和 microsoft 365 集中提供功能。

請觀看下列影片，瞭解如何使用「醫療保健集合」來加強 Microsoft 團隊中的健康小組共同作業。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> 本區段中的內容假設您已在組織中部署團隊。 如果您尚未推出小組，請先閱讀 [瞭解如何推出 Microsoft 團隊](../../How-to-roll-out-teams.md)。

下列案例適用于醫療保健組織：

| 案例 | 說明 | 需求 |
| -------- | -------- | -------- |
| [使用電子醫療保健記錄的虛擬造訪 (EHR) 整合](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | 使用患者排程、管理及進行虛擬走訪。 這個案例會連接 Microsoft 團隊與長篇故事平臺，以支援虛擬走訪。 | 適用于 Microsoft 雲端保健或訂閱 Microsoft 團隊 EHR 連接器獨立優惠的有效訂閱。 <br> 使用者必須具備適當的 Microsoft 365 或 Office 365 授權，包括 Microsoft 團隊會議 *。 <br> 組織必須具有長篇故事版本2018年11月或更新版本。 <br>[EHR 需求的詳細資料](ehr-admin.md#before-you-begin) |
| [使用 Microsoft 預訂和預定 app 進行虛擬走訪](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | 使用患者排程、管理及進行虛擬走訪。 這個案例依賴 Microsoft 預訂來支援虛擬走訪。 | 您必須為組織開啟 Microsoft 預訂。 <br> 預訂 app 的所有使用者和參與會議的所有人員都必須擁有支援小組會議排程的授權。 <br>[預訂需求的詳細資料](../../bookings-app-admin.md#prerequisites-for-using-the-bookings-app-in-teams)|
| [團隊原則套件](#teams-policy-packages)| 確保臨床工作者、資訊工作者和患者機房裝置具備適當的團隊功能存取權。| 使用者必須具備適當的授權 *。 |
| [安全訊息](#secure-messaging) | 讓您更容易注意到緊急郵件，並確信郵件已收到並閱讀。 | 使用者必須具備適當的授權 *。  |
| [團隊範本](#teams-templates-for-healthcare-organizations) | 建立小組，在 ward、pod 或部門中，或在醫院中的多個 wards、箱與部門之間，包含預先定義的設定範本、頻道及預先安裝的 app。 | 使用者必須具備適當的授權 *。  |
| [護理協調與共同作業](#care-coordination-and-collaboration) | 在排程、檔、工作等上，臨床醫師與教職員可以在內部共同作業。| 使用者必須具備適當的授權 *。 |

* 支援 Office 365 A3、A5、E3 和 E5，以及 Microsoft 365 商務標準、A3、A5、E3 和 E5。 如需有關一般團隊授權的詳細資訊，請參閱 [管理使用者對團隊的存取權](../../user-access.md)。

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>虛擬走訪與電子醫療保健記錄 (EHR) 整合

使用 Microsoft 團隊中的完整會議平臺，排程、管理及進行患者的虛擬走訪。

- 如果您的組織已經使用電子醫療記錄或 EHR，您可以整合 Microsoft 團隊以獲得更順暢的體驗。 Microsoft 團隊電子健康情況記錄 (EHR) 連接器可讓臨床醫師輕鬆地從 EHR 系統開始與其他團隊中的另一個提供者進行虛擬患者造訪或諮詢。 若要深入瞭解，請參閱 [使用團隊整合在 EHR 中的虛擬走訪](ehr-admin.md)。
- 如果您使用的不是受支援的 EHR，您可以在小組中使用 Microsoft 預訂和預定 app。 若要深入瞭解，請參閱 [Microsoft 團隊中的預訂 app 與虛擬走訪](../../bookings-app-admin.md)。

![與 Microsoft 團隊進行虛擬走訪](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>團隊原則套件

套用團隊原則套件，以定義不同角色可在團隊中進行的作業。 例如，指定以下專案的原則：

- 臨床工人（例如註冊的護士、電荷護理人員、醫生和社會員工），讓他們能夠擁有聊天、通話、班次管理和會議的完整存取權。
- 您的保健組織中的資訊工作者（例如 IT 人員、informatics 員工、財務人員及合規性監察官員）都可以擁有聊天、通話及會議的完整存取權。
- 患者會議室，用於控制患者會議室裝置的設定。

若要深入瞭解，請參閱 [醫療保健的團隊原則套件](../../policy-packages-healthcare.md)。

## <a name="secure-messaging"></a>安全訊息

安全訊息支援在健康團隊中共同作業，包括幾個新功能：

- 郵件寄件者可以為郵件設定特殊的優先順序，所以收件者會反復收到通知，直到他們閱讀郵件為止。
- 郵件寄件者可以要求讀信回條，當郵件收件者閱讀郵件時，就會收到通知。

總之，這些功能可讓您更快速地注意到緊急訊息，並確信郵件已被接收和讀取。 您可以在每個患者上建立使用這些功能的新健康情況團隊。 這些功能都是以原則為基礎，而且可以指派給個人或整個團隊。

若要深入瞭解，請參閱 [開始使用醫療保健組織的安全訊息原則](messaging-policies-hc.md)。

此外，與安全訊息相關的功能，也是由醫療保健組織聯盟的其他租使用者，允許更豐富的租使用者通訊。  (請參閱 [在 Microsoft 團隊) 中的 [管理外部存取 (同盟) ](../../manage-external-access.md) ]。

## <a name="teams-templates-for-healthcare-organizations"></a>醫療保健組織的團隊範本

我們已開發新的範本來建立小組，以套用至醫院設定。 如此一來，您就能更輕鬆地建立可讓醫療保健工人在不同部門或 wards 中與患者共同合作的小組。 若要深入瞭解，請參閱 [開始使用醫療保健組織的團隊範本](healthcare-templates.md)。 團隊可以針對內部部門（例如心臟病科）或 [護理 wards] 或 [開發中的其他範本] 進行啟動。

## <a name="care-coordination-and-collaboration"></a>護理協調與共同作業

讓您的健康小組共同作業，共同作業，並與 Microsoft 團隊共同作業。

![醫療保健：在團隊中與您的健康小組共同作業](../../media/teams-healthcare-collaborate-in-teams.png)

Microsoft 團隊可讓醫生、臨床醫師、護士及其他員工以 Microsoft 團隊中包含的共同作業功能來高效地共同作業，例如：

- 針對健康團隊與資訊工作者設定團隊和頻道。 在頻道中使用索引標籤來組織其工作，並提供可讓他們釘選資訊來源之索引標籤的其他協助。
- 聊天、張貼訊息及進行通訊。 您的小組可以持續進行與其他患者需要注意的交談。
- 與健康小組成員通話和會面。 您可以設定個別會議，或使用頻道會議來管理每日會議，兩者都有團隊的 [音訊]、[影片]、[螢幕共用]、[錄製] 和 [工具] 功能。
- 儲存及共用檔案和檔。 您的健康小組是單一虛擬小組的一部分，可在 Office 檔上運作及共同合作。

此外，您的小組可以使用團隊中的應用程式來執行下列作業：

- 使用 [清單] 應用程式共用清單及追蹤資訊
- 使用 [工作] app 追蹤及監視工作
- 使用 [核准] app 簡化核准
- 使用倒班 app 建立、管理及共用排程

### <a name="share-lists-and-track-information-with-the-lists-app"></a>使用 [清單] 應用程式共用清單及追蹤資訊

> [!NOTE]
> 2020年10月30日生效，患者 app 已停用，且已由小組中的 [清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 取代。 透過清單，您的醫療保健組織中的 [護理小組] 可建立案例的患者清單，包括從倒圓角和 interdisciplinary 小組會議到一般患者監視。

團隊中的 [清單] 應用程式可協助團隊追蹤資訊並組織工作。 App 是針對所有團隊使用者預先安裝的，而且在每個團隊和頻道中都可做為索引標籤。 清單可以從預先定義的範本中從頭開始建立，或是將資料匯入 Excel。

健康團隊可以使用患者範本來開始使用。 他們可以建立清單來追蹤患者的需求和狀態。 您可以在 Excel 試算表中加入現有的患者資料，在小組中建立清單。 這些清單可用來進行諸如舍入與患者監視等案例，以協助您共同處理護理。

例如，[充電護士] 會在包含所有健康小組成員的小組中建立一個患者清單。 在四捨五入期間，健康小組會在其行動裝置上存取小組，並更新清單中的患者資訊，讓小組中的每個人都可以查看，以保持同步處理。在舍入會話中，健康小組收集來討論及評估重要健康情況效能指標，以確保患者位於正確的 glide 路徑上以進行放電，他們可以使用大型顯示畫面上的小組共用此資訊。 不在網站上的健康小組成員可以遠端加入。

以下是為患者舍入設定的範例清單。

:::image type="content" source="../../media/lists-patients-example.png" alt-text="患者舍入範例清單的螢幕擷取畫面":::

若要深入瞭解，請參閱 [在團隊中管理貴組織的清單應用程式](../../manage-lists-app.md)。

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>使用 [工作] app 追蹤及監視工作

使用 [小組中的工作](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) 來追蹤您整個健康小組的專案。 您的健康團隊可以隨時從任何執行團隊的裝置建立、分派及排程工作、將任務分類，以及更新狀態。

若要深入瞭解，請參閱 [在 Microsoft 團隊中管理貴組織的任務應用程式](../../manage-tasks-app.md)

### <a name="streamline-approvals-with-the-approvals-app"></a>使用 [核准] app 簡化核准

使用 [核准](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) 來簡化您的小組所有要求和程式。 直接從您的中心建立、管理及共用核准，共同合作。 從您傳送聊天的相同位置開始、在頻道交談中，或從核准 app 本身開始核准流程。 只要選取核准類型，新增詳細資料，附加檔案，然後選擇 [核准者]。 提交之後，系統會通知核准者，並在要求時進行審查和操作。

您可以允許貴組織使用核准應用程式，並將其新增至您的小組。 若要深入瞭解如何管理應用程式，請參閱 [在 Microsoft 團隊系統管理中心管理您的應用程式](../../manage-apps.md)。

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>使用倒班 app 建立、管理及共用排程，並第一線工作人員整合

Microsoft 團隊會與倒班 app 和第一線工作者整合，這可以用來共同調整倒班人員的功能。 例如，在倒班中，護士經理可以為員工設定與協調排程，而護士可以檢查排程及調換班次。 團隊包含內建的第一線 Worker 應用程式設定原則，您可以將它指派給貴組織中的第一線工作人員。 根據預設，原則包含活動、班次、聊天及呼叫 app。 此原則會控制這些 app 的行為，例如，將倒班 app 釘選到應用程式行，讓團隊能快速存取。

若要深入瞭解，請參閱 [在 Microsoft 團隊中管理貴組織的倒班應用程式](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)。

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>協助您的臨床與資訊工作者參與團隊

有許多資源可協助貴組織中的所有使用者使用團隊感到舒適：

- 如果您只是開始與團隊進行歷程，或是將團隊擴大至更多組織範圍，請造訪 [團隊採用中心](https://adoption.microsoft.com/microsoft-teams/) ，以取得推出團隊的建議。
- 考慮為您的使用者設定自訂 [學習路徑](https://adoption.microsoft.com/microsoft-365-learning-pathways/) ，以涵蓋所需執行的工作。
- 針對您的使用者取得協助和訓練，瞭解如何在 [團隊支援網站](https://support.microsoft.com/teams)上的 Microsoft 團隊中執行基本工作，包括 [快速訓練](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)影片。 此網站也提供小組 app 的說明與訓練，包括 [清單](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) [、工作](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)、 [核准](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)、 [預訂](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b)及 [倒班](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)。
