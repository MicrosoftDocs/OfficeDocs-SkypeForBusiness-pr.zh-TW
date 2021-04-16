---
title: 開始使用適用於醫療保健組織的 Teams
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
description: 瞭解 Microsoft Teams 遠距健康、電子健康記錄 (EHR) 整合、第一線員工系統整合和病患應用程式等醫療保健功能。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: f6048d2413ea92e377358af43c7348abbbe00be1
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760596"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>開始使用適用於醫療保健組織的 Teams

Microsoft Teams 提供許多對醫院和其他健康照護組織實用的遠距醫療功能。 開發中的 Teams 功能可協助醫院下列事項：

- 虛擬看診與電子健康記錄 (EHR) 整合
- Teams 原則套件
- 安全傳訊
- Teams 範本
- 協調照護與共同合作

此功能是 Microsoft Cloud for Healthcare 的一部分。 深入瞭解使用此解決方案，此解決方案將 Azure、Dynamics 365 和 Microsoft 365 的功能彙集在 [Microsoft Cloud for Healthcare](/industry/healthcare)。

請觀看下列影片，深入瞭解使用醫療保健資料集以增強 Microsoft Teams 中的健康小組共同作業。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> 本章節內容假設您已在貴組織中部署 Teams。 如果您尚未推出 Teams，請先閱讀 [如何推出 Microsoft Teams](../../deploy-overview.md)。

下列案例為醫療保健組織可用的案例：

| 案例 | 說明 | 需求 |
| -------- | -------- | -------- |
| [虛擬看診及電子健康記錄 (EHR) 整合](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | 與病患排程、管理及與患者進行虛擬看診。 此案例會連接 Microsoft Teams 和 Epic 平臺，以支援虛擬看診。 | 適用於醫療保健的 Microsoft Cloud 作用中訂閱或 Microsoft Teams EHR 連接器獨立供應項目訂閱。 <br> 使用者必須擁有包含 Microsoft Teams 會議的適當 Microsoft 365 或 Office 365 授權。 <br> 組織必須有 Epic 2018 年 11 月版本或更新版本。 <br>[EHR 要求的詳細資料](ehr-admin.md#before-you-begin) |
| [使用 Microsoft Bookings 和 Bookings 應用程式進行的虛擬看診](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | 與病患排程、管理及與患者進行虛擬看診。 此案例依賴 Microsoft Bookings 來支援虛擬看診。 | 必須為組織開啟 Microsoft Bookings。 <br> Bookings 應用程式的所有使用者，以及所有參與會議的員工都必須擁有支援 Teams 會議排程授權*。 <br>[Bookings 要求的詳細資料](../../bookings-app-admin.md#prerequisites-for-using-the-bookings-app-in-teams)|
| [Teams 原則套件](#teams-policy-packages)| 確保臨床工作者、資訊工作者和病房裝置具有 Teams 功能的適當存取權。| 使用者必須擁有適當的授權*。 |
| [安全傳訊](#secure-messaging) | 更快速地注意緊急訊息，並確信已收到並讀取訊息。 | 使用者必須擁有適當的授權*。  |
| [Teams 範本](#teams-templates-for-healthcare-organizations) | 建立團隊，其中包括預先定義設定和頻道範本及預先安裝的應用程式，以適用於在病房、Pod 或部門間或院內的多個病房、Pod 和各部門間的通訊和共同作業。 | 使用者必須擁有適當的授權*。  |
| [協調照護與共同作業](#care-coordination-and-collaboration) | 臨床醫生和教職員可以內部協作排程、文件和工作等等。| 使用者必須擁有適當的授權*。 |

*支援 Office 365 A3、A5、E3 和 E5，以及 Microsoft 365 商務標準版、A3、A5、E3 和 E5。 如需一般 Teams 授權的詳細資訊，請參閱 [管理使用者對 Teams 的存取權](../../user-access.md)。

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>虛擬看診與電子健康記錄 (EHR) 整合

使用 Microsoft Teams 中的完整會議平臺進行排程、管理及與病患的虛擬看診。

- 如果貴組織已經使用電子健康記錄或 EHR，您可以整合 Microsoft Teams 以獲得更順暢的體驗。 Microsoft Teams 電子健康記錄 (EHR) 連接器讓臨床醫生可以直接從 EHR 系統，在 Teams 中啟動虛擬病患就診或諮詢。 若要深入瞭解，請參閱 [Teams 的虛擬看診 - 整合至 EHR](ehr-admin.md)。
- 如果您未使用受支援的 EHR，您可以使用 Microsoft Bookings 和 Teams 中的 Bookings 應用程式。 若要深入瞭解，請參閱 [Microsoft Teams 中的 Bookings 應用程式和虛擬看診](../../bookings-app-admin.md)。

![使用 Microsoft Teams 進行虛擬看診](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Teams 原則套件

套用 Teams 原則套件以定義不同的角色在 Teams 中的作用。 例如，指定適用原則：

- 臨床工作者 (例如註冊的護士、護士長、醫生和社會工作者) 能完整存取聊天、通話、班次管理和會議。
- 貴醫療保健組織的資訊工作者 (例如 IT 人員、資訊人員、財務人員和法務人員) 可以完整存取聊天、通話和會議的完整存取權。
- 病房，以控制病房裝置的設定。

若要深入瞭解，請參閱 [適用於醫療保健的 Teams 原則套件](../../policy-packages-healthcare.md)。

## <a name="secure-messaging"></a>安全傳訊

安全傳訊支援健康小組內的共同作業，包括一些新功能：

- 郵件寄件者可以設定其訊息的特殊優先順序，在收件者在讀取訊息之前，收件者會重複收到通知。
- 郵件寄件者可以要求讀取通知，當訊息收件者讀取他們寄出的郵件時，寄件者就會收到通知。

當這些功能結合一起時，可以對緊急訊息更快速地注意，並確信可以收到和讀取訊息。 可以使用這些功能依照每位患者的情況建立新健康小組。 這些功能是原則式功能，而且可以指派給個人或整個 Teams。

若要深入瞭解，請參閱 [開始使用適用於醫療保健組織的安全傳訊原則](messaging-policies-hc.md)。

與安全傳訊相關的是讓其他租用戶透過醫療保健組織聯盟的能力，允許更豐富的租用戶間通訊。 ( [參閱 在 Microsoft Teams 中管理外部存取 (同盟)](../../manage-external-access.md))。

## <a name="teams-templates-for-healthcare-organizations"></a>適用於醫療保健組織的 Teams 範本

建立 Teams 的新範本已開發並套用至醫院環境，預計很快就會推出更多範本。 這可更輕鬆地建立醫療保健工作者用於各科或各病房間的患者共同照護團隊。 若要深入了解，請參閱 [開始使用適用於醫療保健組織的 Teams 範本](./healthcare-templates-admin-console.md)。 Teams 可以針對內部部門 (例如心臟科或照護病房) 啟用，而且正在開發其他更多範本。

## <a name="care-coordination-and-collaboration"></a>協調照護與共同合作

讓您的健康小組一起協調照護，並與 Microsoft Teams 共同作業。

![醫療保健：在 Teams 中與您的健康小組共同作業](../../media/teams-healthcare-collaborate-in-teams.png)

Microsoft Teams 可讓醫生、臨床醫生、護士和其他員工更有效率的共同作業，藉由 Microsoft Teams 中包含的協同作業功能，例如：

- 設定適用於健康小組和資訊工作者的團隊和頻道。 使用具索引標籤的頻道並視之為組織工作的方式，透過索引標籤的其它協助以釘選其資訊來源。
- 聊天、張貼訊息和聊天。 您的團隊可以持續討論需要留意的不同病患。
- 與健康小組成員通話並開會。 設定個別會議，或使用頻道會議以管理每日會議，同時提供 Teams 音訊、影片、螢幕畫面分享、錄製和轉譯功能。
- 儲存及共用檔案和文件。 您的健康小組是單一虛擬化小組的一部分，可在 Office 文件上運作並共同作業。

此外，您的小組可以使用 Teams 中的應用程式進行：

- 使用清單應用程式共用清單和追蹤資訊
- 使用工作應用程式追蹤和監控工作
- 使用核准應用程式簡化核准
- 使用 [班次] 應用程式建立、管理及共用排程

### <a name="share-lists-and-track-information-with-the-lists-app"></a>使用清單應用程式共用清單和追蹤資訊

> [!NOTE]
> 自 2020 年 10 月 30 日起，病患應用程式已淘汰並且由 Teams 中的[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)取代。 使用清單，您的醫療保健組織照護小組可以針對各種案例建立病患清單，範圍從會診和跨學科小組會議到一般病患監視。

Microsoft Teams 中的 [清單] 應用程式可協助追蹤資訊和整理工作。 此應用程式已為所有 Teams 使用者預先安裝完成，可供每個團隊和頻道作為索引標籤使用。 建立清單的方式可以從頭開始、從預先定義的範本開始，或將資料匯出至 Excel。

健康小組可以使用病患範本開始使用。 他們可以建立清單以追蹤病患的需求和狀態。 可以帶入 Excel 試算表上的現有病患資料以在 Teams 中建立清單。 這些清單可用於輪次和病患監視等案例，以協調照護。

例如，護士長會在包含所有健康小組成員的小組中建立病患清單。 在輪次期間，健康小組會在其行動裝置上存取 Teams，並更新清單中的病患資訊，小組中的每個人都可檢視這些資訊以保持資訊同步。在健康小組開會討論及評估關鍵健康效能指標的輪班工作階段中，確保病患處於正確的出院途徑，並可在大型顯示畫面上使用 Teams 共用此資訊。 不在現場的健康小組成員可以遠端加入會議。

以下是針對病患輪班設定的範例清單。

:::image type="content" source="../../media/lists-patients-example.png" alt-text="病患輪班訪視的範例清單螢幕擷取畫面":::

若要深入了解，請參閱 [在 Teams 中管理貴組織的清單應用程式](../../manage-lists-app.md)。

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>使用工作應用程式追蹤和監控工作

在 Teams 中使用 [工作](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) 以追蹤整個健康小組的 To Do 項目。 您的健康小組隨時都可以在執行 Teams 的任何裝置上建立、指派及排程工作、分類工作及更新狀態。 IT 專業人員和系統管理員也可以發佈工作給貴組織的特定小組。 例如，您可以發佈一組新安全通訊協定或新進給步驟的工作，以在整個醫院使用。

若要深入了解，請參閱 [在 Microsoft Teams 中管理貴組織的 [工作] 應用程式](../../manage-tasks-app.md)

### <a name="streamline-approvals-with-the-approvals-app"></a>使用核准應用程式簡化核准

使用 [核准](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) 以簡化您與小組的所有要求與程序。 直接從您的團隊合作中心建立、管理及共用核准。 從您傳送聊天、使用頻道交談或在核准應用程式本身的相同位置開始核准流程。 只要選取核准類型、新增詳細資料、附加檔案，然後選擇核准者。 一旦提交，核准者會收到通知，而且可以對要求進行檢視並採取行動。

您可以允許貴組織的核准應用程式，並新增到您的小組。 若要深入瞭解，請參閱 [Teams 核准應用程式可用性](../../approval-admin.md)。

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>使用 [班次] 應用程式和 [第一線員工整合] 以建立、管理及共用排程

Microsoft Teams 與 [班次] 應用程式和 [第一線員工] 整合，可用於協調班次員工功能等。 例如，在班次中，護士長可以設定及協調員工的排程，而護士可以檢查排程和調班。 Teams 包含內建的 [第一線員工] 應用程式設定原則，您可以指派給貴組織的第一線員工。 根據預設，此原則包含活動、班次、聊天和通話應用程式。 此原則可控制這些應用程式的行為，例如，將 [班次] 應用程式釘選到應用程式工作列，讓小組可以快速存取它。

若要深入了解，請參閱 [在 Microsoft Teams 中管理貴組織的 [班次] 應用程式](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)。

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>協助臨床和資訊工作者使用 Teams

有許多資源可協助貴組織的所有使用者熟悉並使用 Teams：

- 如果您只是剛開始使用貴組織的 Teams 或將 Teams 擴充到貴組織的更多領域，請瀏覽 [Teams 採用中心](https://adoption.microsoft.com/microsoft-teams/)，以獲得有關推出 Teams 的建議。
- 請考慮為使用者設定自訂 [學習路徑](https://adoption.microsoft.com/microsoft-365-learning-pathways/)，以僅涵蓋他們所需要執行的工作。
- 取得有關如何在 [Teams 支援網站](https://support.microsoft.com/teams) 上執行 Microsoft Teams 基本工作之使用者說明與訓練，包括 [快速訓練影片](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)。 此網站也提供 Teams 應用程式的協助和訓練，包括 [清單](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)、 [工作](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)、 [核准](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)、 [Bookings](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b)和 [Shifts](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)。
