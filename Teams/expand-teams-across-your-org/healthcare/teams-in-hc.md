---
title: 開始使用醫療保健組織的 Teams
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
description: 瞭解 Microsoft Teams 遠端健康、EHR 整合、第一線員工系統整合和病患應用程式等醫療保健功能。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 1bf890c7ffb6fa13730870cb1f4eabecb5df7c85
ms.sourcegitcommit: e29e38bf00536400e5826fc55bc86dfd6ed761f3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/08/2021
ms.locfileid: "50558382"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>開始使用醫療保健組織的 Teams

Microsoft Teams 提供許多適用于醫療保健和其他醫療保健組織的遠端醫療功能。 Teams 功能正在開發中，可協助他們使用：

- EHR 整合的虛擬 (電子) 記錄
- Teams 政策套件
- 安全傳訊
- Teams 範本
- 照護協調與共同合作

此功能是 Microsoft Cloud 醫療保健的一部分。 深入瞭解使用此解決方案，此解決方案將 Azure、Dynamics 365 和 Microsoft 365 在 [Microsoft Cloud 的醫療保健功能結合在一起](https://docs.microsoft.com/industry/healthcare)。

請觀看下列影片，進一步瞭解如何在 Microsoft Teams 中使用醫療保健集合加強健康小組共同合作。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> 本節內容假設您已在組織中部署 Teams。 如果您尚未推出 Teams，請從閱讀如何推出 [Microsoft Teams 開始](../../How-to-roll-out-teams.md)。

下列案例適用于醫療保健組織：

| 案例 | 說明 | 需求 |
| -------- | -------- | -------- |
| [使用電子醫療保健記錄與 EHR (整合) 虛擬訪問](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | 排程、管理及與病患進行虛擬看診。 此案例將 Microsoft Teams 和一般平臺連接在一起，以支援虛擬訪問。 | 使用中的 Microsoft Cloud 醫療保健訂閱或 Microsoft Teams EHR Connector 獨立方案訂閱。 <br> 使用者必須擁有包含 Microsoft Teams 會議*的適當 Microsoft 365 或 Office 365 授權。 <br> 組織必須擁有 2018 年 11 月或更新的版本。 <br>[EHR 需求詳細資料](ehr-admin.md#before-you-begin) |
| [使用 Microsoft Bookings 和 Bookings 應用程式進行虛擬訪問](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | 排程、管理及與病患進行虛擬看診。 此案例仰賴 Microsoft Bookings 支援虛擬訪問。 | 必須針對組織開啟 Microsoft Bookings。 <br> Bookings App 的所有使用者以及所有參與會議的員工都必須擁有支援 Teams 會議排程*授權。 <br>[Bookings 需求詳細資料](../../bookings-app-admin.md#prerequisites-for-using-the-bookings-app-in-teams)|
| [Teams 政策套件](#teams-policy-packages)| 確保醫療工作者、資訊工作者和病患室裝置能夠適當存取 Teams 功能。| 使用者必須擁有適當的授權*。 |
| [安全傳訊](#secure-messaging) | 更快速地注意緊急郵件，並信賴郵件已接收並讀取。 | 使用者必須擁有適當的授權*。  |
| [Teams 範本](#teams-templates-for-healthcare-organizations) | 建立團隊，包含預先定義的設定、頻道和預先安裝應用程式範本，以在一個團隊、容器或部門內，或在醫院內多個容器、容器和科系之間進行通訊和共同合作。 | 使用者必須擁有適當的授權*。  |
| [照護協調與共同合作](#care-coordination-and-collaboration) | 醫師和教職員可以在排程、檔、工作等專案上進行內部共同作業。| 使用者必須擁有適當的授權*。 |

*支援 Office 365 A3、A5、E3 和 E5，以及 Microsoft 365 商務標準版、A3、A5、E3 和 E5。 有關一般 Teams 授權的資訊，請參閱管理 Teams [的使用者存取權](../../user-access.md)。

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>EHR 整合的虛擬 (電子) 記錄

在 Microsoft Teams 中使用完整的會議平臺來排程、管理及虛擬看診病患。

- 如果貴組織已經使用電子健康記錄或 EHR，您可以整合 Microsoft Teams，獲得更流暢的體驗。 Microsoft Teams 電子健康記錄 (EHR) Connector 讓醫生可以直接從 EHR 系統，在 Teams 中啟動虛擬病患看診或諮詢。 若要深入瞭解，請參閱使用 Teams 進行 [虛擬訪問 - 與 EHR 整合](ehr-admin.md)。
- 如果您不是使用支援的 EHR，您可以使用 Microsoft Bookings 和 Teams 中的 Bookings 應用程式。 若要深入瞭解，請參閱 [Bookings App 和 Microsoft Teams 中的虛擬訪問](../../bookings-app-admin.md)。

![使用 Microsoft Teams 進行虛擬訪問](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Teams 政策套件

套用 Teams 原則套件，以定義在 Teams 中可以執行的不同角色。 例如，指定用於：

- 醫療工作者 ，例如註冊的護士、主管護士、醫師和社交工作者，以便完全存取聊天、通話、輪班管理和會議。
- 您醫療保健組織的資訊工作者 ，例如 IT 人員、資訊人員、財務人員和合規性人員，可以擁有聊天、通話和會議的完整存取權。
- 病患室，以控制病患室裝置設定。

若要深入瞭解，請參閱 [適用于醫療保健的 Teams 政策套件](../../policy-packages-healthcare.md)。

## <a name="secure-messaging"></a>安全傳訊

安全訊息支援健康小組內的共同合作，包括數項新功能：

- 郵件寄件者可以設定其郵件的特殊優先順序，讓收件者重複收到通知，直到他們讀取郵件。
- 郵件寄件者可以要求讀信回條，因此當郵件收件者讀取所送出的郵件時，會收到通知。

這些功能可同時更快速地注意緊急郵件，並讓您對郵件的接收和讀取更有信心。 您可以使用這些功能建立每個病患的新健康小組。 這些功能是以策略為基礎，可以指派給個人或整個 Teams。

若要深入瞭解，請參閱 [開始使用醫療保健組織的安全訊息策略](messaging-policies-hc.md)。

安全訊息的另外一個相關功能是讓其他租使用者由醫療保健組織建立聯盟，允許更豐富的租使用者間通訊。  (Microsoft Teams ([管理) 外部存取) 。](../../manage-external-access.md)

## <a name="teams-templates-for-healthcare-organizations"></a>醫療保健組織的 Teams 範本

建立 Teams 的新範本已開發為適用于醫院設定，預計近期將推出更多範本。 這可更輕鬆地建立讓醫療保健工作者用於協調不同科系或醫院病患照護的團隊。 若要深入瞭解，請參閱開始使用 [醫療保健](healthcare-templates.md)組織的 Teams 範本。 團隊可以針對內部部門啟動，例如心律科或照護科，且開發中的範本更多。

## <a name="care-coordination-and-collaboration"></a>照護協調與共同合作

將您的健康小組彙集在一起，以與 Microsoft Teams 協調照護及共同合作。

![醫療保健：在 Teams 中與您的健康小組共同合作](../../media/teams-healthcare-collaborate-in-teams.png)

Microsoft Teams 可讓醫師、醫師、護士和其他員工使用 Microsoft Teams 中包含的共同合作功能，有效率地共同合作，例如：

- 為健康小組和資訊工作者設定團隊和頻道。 使用具有定位字元的頻道來建立工作結構，並額外提供來自可釘上資訊來源之資料標籤的協助。
- 聊天、張貼訊息和溝通。 您的小組可以持續討論需要注意的不同病患。
- 與健康小組的成員通話和開會。 設定個別會議，或使用頻道會議來管理每日會議，兩者均提供 Teams 音訊、視視、螢幕共用、錄製和抄寫功能。
- 儲存及共用檔案和檔。 您的健康小組是單一虛擬小組的一員，可處理 Office 檔並共同處理。

此外，您的小組可以使用 Teams 中的應用程式：

- 使用清單應用程式共用清單和追蹤資訊
- 使用工作應用程式追蹤及監控工作
- 使用核准應用程式簡化核准
- 使用 Shifts 應用程式建立、管理及共用排程

### <a name="share-lists-and-track-information-with-the-lists-app"></a>使用清單應用程式共用清單和追蹤資訊

> [!NOTE]
> 自 2020 年 10 月 30 日起，病患應用程式已[](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)停用，並取代為 Teams 中的清單應用程式。 使用清單，您醫療保健組織的照護小組可以針對各種情況建立病患清單，從四輪和多行小組會議到一般病患監控。

Teams 中的清單應用程式可協助團隊追蹤資訊並整理工作。 此應用程式已預先安裝供所有 Teams 使用者使用，並可在每個團隊和頻道中做為一個選項卡使用。 清單可以從頭建立、從預先定義的範本建立，或將資料導入 Excel。

健康小組可以使用病患範本開始使用。 他們可以建立清單來追蹤病患的需求和狀態。 您可以輸入 Excel 試算表上現有的病患資料，以在 Teams 中建立清單。 這些清單可用於圓形和病患監控等案例，以協調照護。

例如，付費護士在包含所有健康小組成員的小組中建立病患清單。 在四輪期間，健康小組會以行動裝置存取 Teams，並更新清單中的病患資訊，讓團隊中的每個人都可以查看這些資訊，以便保持同步。在健康小組會聚在一起討論及評估關鍵健康表現計量的四周會議，以確保病患處于正確卸貨路徑，他們可以使用大型顯示畫面上的 Teams 來共用這項資訊。 不在網站的健康小組成員可以遠端加入。

以下是針對病患四分位所設定之範例清單。

:::image type="content" source="../../media/lists-patients-example.png" alt-text="病患四分位的範例清單螢幕擷取畫面":::

若要深入瞭解，請參閱在 Teams 中管理 [貴組織的清單應用程式](../../manage-lists-app.md)。

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>使用工作應用程式追蹤及監控工作

使用 [Teams](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) 中的工作來追蹤，以針對整個健康小組執行專案。 您的健康小組可以從執行 Teams 的任何裝置隨時建立、指派及排程工作、分類工作及更新狀態。

若要深入瞭解，請參閱在 Microsoft Teams 中為貴組織 [管理工作應用程式](../../manage-tasks-app.md)

### <a name="streamline-approvals-with-the-approvals-app"></a>使用核准應用程式簡化核准

使用 [核准](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) 來簡化您與小組的所有要求與程式。 直接從您的中心建立、管理及共用核准，以用於團隊合作。 從傳送聊天的同一個地方、頻道交談中，或從核准應用程式本身開始核准流程。 只要選取核准類型、新增詳細資料、附加檔案，然後選擇核准者。 提交後，核准者會收到通知，並可以審查要求並採取行動。

您可以允許貴組織的核准應用程式，並新增到您的小組。 若要深入瞭解，請參閱 [Teams 核准應用程式可用性](../../approval-admin.md)。

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>使用 Shifts 應用程式與前線工作人員整合來建立、管理及共用排程

Microsoft Teams 與 Shifts App 和前線員工整合，可用來協調班次教職員功能等。 例如，在 Shifts 中，護士經理可以設定及協調其教職員的排程，而護士可以檢查排程及調班。 Teams 包含內建的 Frontline Worker 應用程式設定政策，您可以指派給貴組織的前線工作人員。 根據預設，該政策包含活動、班次、聊天和通話應用程式。 這個策略會控制這些應用程式的行為，例如將 Shifts 應用程式釘到應用程式行，讓小組可以快速存取。

若要深入瞭解，請參閱在 Microsoft Teams 中管理貴組織的 [Shifts 應用程式](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)。

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>協助您的醫療與資訊工作者使用 Teams

有許多資源可協助貴組織的所有使用者習慣使用 Teams：

- 如果您才 [剛開始](https://adoption.microsoft.com/microsoft-teams/) 使用 Teams 組織，或將 Teams 擴充到組織的更多領域，請流覽 Teams 採用中心以尋求有關推出 Teams 的建議。
- 請考慮 [為使用者設定](https://adoption.microsoft.com/microsoft-365-learning-pathways/) 自訂學習路徑，只涵蓋他們需要執行的工作。
- 取得有關如何在 Teams 支援網站上執行 Microsoft Teams 基本工作之使用者[](https://support.microsoft.com/teams)說明與訓練，包括[快速訓練影片](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)。 這個網站也有 Teams 應用程式的協助與訓練，包括清單、[](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)工作、[](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)[核准](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)[、Bookings](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b)和[Shifts。](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
