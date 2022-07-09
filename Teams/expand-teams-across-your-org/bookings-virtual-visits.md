---
title: 使用 Microsoft Teams 和 Bookings 應用程式進行虛擬約會
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: 瞭解如何使用 Teams 中的 Bookings 應用程式來排程、管理及進行虛擬約會。
ms.openlocfilehash: 245b9fdf8cd619ea68d2d20097f1aee4bdbbf20d
ms.sourcegitcommit: 15ec17eff4ad4c962d00b8683513f9b269d82917
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2022
ms.locfileid: "66695126"
---
# <a name="virtual-appointments-with-microsoft-teams-and-the-bookings-app"></a>使用 Microsoft Teams 和 Bookings 應用程式進行虛擬約會

## <a name="overview"></a>概觀

Microsoft Teams 中的 [Bookings 應用程式](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5) 為組織提供了一個簡單的方式來排程和管理教職員和出席者的虛擬約會。 使用它來排程約會，例如醫療探訪、財務諮詢、面談、客戶支援、虛擬配件與諮詢、教育辦公室時間等。

Bookings 應用程式可讓您輕鬆管理任何組織的複雜排程需求。 排程器可以從單一體驗管理多個部門與員工行事曆，以及與內部和外部出席者之間的通訊。

虛擬約會是透過 Microsoft Teams 會議進行，可提供強大的視訊會議功能。 例如，醫生可以與病患共用螢幕並檢閱測試結果。 或者，銀行顧問可以在檔上要求電子簽章，以便從遠端關閉交易。

每個虛擬約會都包含一個 Teams 會議連結，該連結會以電子郵件傳送給出席者，讓他們可以從網頁瀏覽器或任何裝置上的 Teams 中輕鬆加入。 自動電子郵件提醒有助於減少無放映時間，並加強客戶和客戶的參與度。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4TQop]

使用 Bookings，您可以獲得專為您的產業量身打造的體驗。 以下是一些您可以在組織中使用此功能的範例：

|行業 | 範例 |
|---------|---------|
|金融服務    |  遠端銷售與服務的虛擬約會<br/>排程和管理銀行關係經理、財務顧問和索賠調整者的約會，僅舉幾例，為客戶提供更高效且方便的服務。  |
|零售   | 虛擬試裝和諮詢 <br/>排程和管理銷售人員、產品專家和設計顧問的約會，以便與客戶進行虛擬配件和諮詢。   |
|醫療   |  病患照護的虛擬預約 <br/>為您的護理小組成員排程和管理約會，以便與病患或其他醫療保健提供者開會討論醫療。   |

本文提供有關如何使用 Teams 中的 Bookings 應用程式來排程、管理及進行虛擬約會的概觀。

## <a name="before-you-get-started"></a>開始之前

如果您是系統管理員，請參閱 [管理 Teams 中的 Bookings 應用程式](../bookings-app-admin.md) ，以瞭解在 Teams 中使用 Bookings 應用程式的先決條件、如何控制組織中 Bookings 的存取權，以及建議的原則和系統管理員設定。

請記住，只有貴組織中的排程器需要在 Teams 中安裝 Bookings 應用程式。 進行虛擬約會或參與虛擬約會的員工不需要應用程式。 他們可以從 Teams 或 Outlook 行事曆加入約會，或是使用預約確認電子郵件中的會議連結。

## <a name="set-up-a-new-booking-calendar"></a>設定新的預約行事曆

### <a name="create-the-booking-calendar"></a>建立預約行事曆

在 Teams 中，移至 [**Bookings**  >  **開始使用**]，然後選取 **[新增預約行事曆]**。 完成表單，並務必為貴組織選擇相關的商務類型。

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="顯示商務類型之新預約行事曆畫面的螢幕擷取畫面":::

如果您是大型組織，如果您希望出席者收到來自特定部門而不是整個組織的預約電子郵件，請考慮建立多個預約行事曆。
若要深入瞭解，請參閱 [建立 Bookings 行事曆](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148)。

> [!NOTE]
> 如果這不是您第一次使用 Bookings 應用程式，或者如果您想要在現有的預約行事曆中工作，請在 Bookings 中選取組織名稱旁邊的下拉式箭號，然後選擇 **[現有的預約行事曆]**。 您可以從這裡搜尋您想要的檔案。

### <a name="add-staff"></a>新增教職員

在預約行事曆中，移至 [ **其他選項** (...) > **設定]**，然後選取 [ **教職員]**。 新增教職員成員，並將角色指派給您新增的每個人。 您最多可以在預約行事曆中新增 100 個教職員成員。

Bookings 應用程式與 Outlook 整合。 新增教職員成員之後，您就可以檢視其行事曆可用性，並為其排程預約。 若要深入瞭解，請參閱 [新增教職員和檢視 Bookings 行事曆](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0)。  

### <a name="create-appointment-types"></a>建立約會類型

建立特定的約會類型，以代表貴組織所提供的服務，並量身打造預約體驗。 排程器接著可以使用約會類型來排程約會。

在預約行事曆中，移至 [ **其他選項** (...) > **設定]**，選取 **[約會類型**]，然後選取 [ **新增約會類型]**。 輸入名稱 &mdash; ，例如開啟帳戶、續約、貸款諮詢、稅務準備 &mdash; ，以及您想要的任何其他資訊和設定。

您新增的資訊會包含在每次預約此類型的約會時傳送給出席者的電子郵件確認中。 您可以設定電子郵件提醒和其他選項，例如出席者是否可以 [從桌面或行動瀏覽器加入](browser-join.md) ，而不需要下載 Teams。

如果您是 Bookings 系統管理員，您最多可以連結四份表單，讓出席者在每一次預約此約會類型時填寫。 例如，您可能會要求出席者完成註冊表單後，才能加入約會。 若要連結表單，請選擇 **[連結表單]**。 輸入表單的 URL，然後選擇 **[連結]**。  (如果這是您第一次連結表單，系統會提示您建立 Microsoft 365 群組以儲存表單。 選擇 **[建立群組** ] 以建立群組。 預約行事曆只需執行此動作一次。) 

使用表單時，請記住：

- 若要變更已連結至約會類型的表單，請選取約會類型中的表單，或是從 Microsoft 365 群組中選取 。 [https://forms.office.com](https://forms.office.com)
- 當所有出席者都來自同一個組織時，會支援將檔案上 [傳到包含檔案上傳問題的](https://support.microsoft.com/office/add-questions-that-allow-for-file-uploads-6a75a658-c02b-450e-b119-d068f3cba4cf) 表單。

當排程器使用約會類型來排程約會時，他們就可以選擇包含表單、移除表單，或新增您連結到約會類型的任何其他表單。 出席者必須先填寫表單，才能加入約會。

> [!NOTE]
> 如果您是醫療保健提供者，您或病患在 Teams (中提供的任何資訊，包括 Forms 應用程式、Bookings 應用程式、若您啟用的會議錄製，或任何其他針對病歷連續性或保留目的所需的其他 Teams 虛擬約會服務) ，都應由您直接在這類記錄中下載、複製及/或附注。 此服務不會維護法律醫療記錄或指定的記錄集。

若要深入瞭解，請參閱 [建立約會類型](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)。

## <a name="schedule-an-appointment"></a>排程約會

在預約行事曆中，選取 **[新增預約]**。 選取約會類型，然後填寫相關資訊。

這包括出席者連絡資訊、將提供服務的員工、只有員工可以看到的內部記事、電子郵件提醒，以及出席者是否可以從行動瀏覽器加入。 如果表單已連結至約會類型，您可以選擇包含、移除表單或新增任何其他連結的表單。

傳送給出席者的電子郵件確認包含會議連結和附件，讓他們可以在行事曆中新增虛擬約會。 教職員成員也會收到電子郵件確認和會議邀請。 如果約會中包含表單，Bookings 系統管理員和排程器可以查看出席者是否已在約會前完成表單，並可檢視出席者的回應。

若要深入瞭解，請參閱 [在 Teams Bookings 應用程式中排程預約](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f)。

## <a name="conduct-an-appointment"></a>進行約會

在您的 Teams 或 Outlook 行事曆中，移至預約，然後選取 **[加入** ] 或 [Teams 會議] 連結。 檢查您的音訊和視訊設定，然後選取 [ **立即加入]**。 若要深入瞭解，請參閱 [進行 Bookings 約會](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd)。

## <a name="monitor-appointments-and-get-real-time-status-updates"></a>監控約會並取得即時狀態更新

Bookings 中的 [佇列檢視](https://support.microsoft.com/office/queue-view-in-bookings-3eea2840-a1e0-4bcd-8e09-d3cf51c184d6) 提供您的教職員儀表板，可即時監控當天的所有虛擬約會。 若要查看佇列，請移至 Bookings 中的 [ **佇列** ] 索引標籤。

:::image type="content" source="../media/bookings-virtual-visits-queue.png" alt-text="Teams 中 Bookings 應用程式中佇列檢視的螢幕擷取畫面" lightbox="../media/bookings-virtual-visits-queue.png":::

排程器可以從佇列新增預約、檢視相關的約會詳細資料，以及查看一整天的約會狀態。 當病患加入等候室時，狀態會變更，並顯示並追蹤其等待時間。 檢視會自動重新整理色彩編碼的更新，以便輕鬆識別變更。

員工甚至可以直接從佇列加入和管理約會。

> [!NOTE]
> 目前，Bookings 應用程式支援每個預約行事曆最多新增 100 名教職員。 如果您使用 Graph API 來設定並新增教職員至預約行事曆，則可能無法強制執行此限制。 在此案例中，[ **佇列** ] 索引標籤將無法呈現超過 100 位教職員的行事曆內容。 為獲得最佳體驗，建議您在預約行事曆中新增不超過 100 個教職員。 我們正努力在未來版本中解決此限制。

## <a name="additional-capabilities-with-the-bookings-web-app"></a>使用 Bookings Web App 的其他功能

Bookings Web App 提供您額外的功能。 例如，您可以發佈自助線上預約頁面，讓人員可以排程與您員工的約會。 若要存取 Bookings Web App，請移至 [**其他選項** (...) >**開啟 Bookings Web App。**

若要深入瞭解，請參[閱Microsoft Bookings](/microsoft-365/bookings/bookings-overview)。

## <a name="get-insight-into-virtual-appointments-usage"></a>深入瞭解虛擬約會使用量

Microsoft Teams 系統管理中心的 [虛擬造訪使用方式報告](../teams-analytics-and-reports/virtual-visits-usage-report.md) 可讓系統管理員概略瞭解貴組織中的 Teams 虛擬約會活動。 報告會顯示虛擬約會的詳細分析，包括 Bookings 約會。

您可以檢視重要指派，例如大廳等候時間和約會持續時間。 使用此資訊以深入瞭解使用趨勢，協助您優化虛擬約會，以提供更好的商務成果。

## <a name="related-articles"></a>相關文章

- [在行動瀏覽器上管理 Teams 虛擬約會的加入體驗](browser-join.md)

- [Teams 虛擬造訪使用方式報告](../teams-analytics-and-reports/virtual-visits-usage-report.md)

- [開始使用適用于醫療保健組織的 Teams](healthcare/teams-in-hc.md)

- [Teams 中的 Bookings 應用程式說明文件](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
