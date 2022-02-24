---
title: 使用 Microsoft Teams 和 Bookings 應用程式進行虛擬訪問
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
description: 瞭解如何使用 Teams 中的 Bookings 應用程式排程、管理及執行虛擬Teams。
ms.openlocfilehash: 6241c377cc5daa0986081fbfa30eca5fa7146efc
ms.sourcegitcommit: 5ca04ee10e3f254e1b24506de116591fdfd51d18
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2022
ms.locfileid: "62929268"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>使用 Microsoft Teams 和 Bookings 應用程式進行虛擬會面

## <a name="overview"></a>概觀

Microsoft Teams[中的 Bookings](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)應用程式，讓組織能輕鬆排程及管理教職員和出席者虛擬約會。 使用它來排程約會，例如醫療保健訪問、財務諮詢、面試、客戶支援、虛擬配件和諮詢、教育用辦公室時數等。

Bookings App 可輕鬆管理任何組織的複雜排程需求。 排程器可以從單一體驗管理多個部門與員工行事曆，以及與內部和外部出席者之間的通訊。

虛擬約會會透過會議Microsoft Teams，提供強大的視訊會議功能。 例如，醫生可以與病患共用螢幕並檢閱測試結果。 或者，銀行顧問可以在檔上要求電子簽章，讓他們遠端關閉交易。

每個虛擬約會Teams一個會議連結，會以電子郵件寄給出席者，他們可以輕鬆地從網頁瀏覽器加入會議，或在Teams裝置上加入。 自動電子郵件提醒有助於減少未顯示，並提升客戶和客戶的參與度。

使用 Bookings，您可以獲得專為您的產業量身打造的體驗。 以下是一些如何在組織中使用它的範例：

|行業 | 範例 |
|---------|---------|
|金融服務    |  遠端銷售與服務的虛擬訪問<br/>排程及管理銀行關係管理員、財務顧問及理賠調整員的約會，以提升效率與便利性，為客戶提供服務。  |
|零售   | 虛擬試裝和諮詢 <br/>排程及管理銷售人員、產品專家和設計顧問的約會，以與客戶進行虛擬配件和諮詢。   |
|醫療   |  病患照護的虛擬訪問 <br/>為護理小組成員排程及管理約會，以與病患或其他醫療保健提供者開會，討論醫療保健問題。   |

本文提供您如何使用 Teams 中的 Bookings 應用程式排程、管理及進行虛擬Teams。

## <a name="before-you-get-started"></a>開始之前

如果您是系統管理員，請參閱管理[Teams 中的 Bookings](../bookings-app-admin.md)應用程式，以瞭解在 Teams 中使用 Bookings 應用程式的先決條件、如何控制貴組織中 Bookings 的存取權，以及建議的政策和系統管理設定。

請記住，只有貴組織的排程者需要在 Teams 中安裝 Bookings 應用程式。 進行或參與虛擬約會的員工不需要應用程式。 他們從自己的會議Teams或Outlook，或在預約確認電子郵件中使用會議連結加入約會。

## <a name="set-up-a-new-booking-calendar"></a>設定新的預約日曆

### <a name="create-the-booking-calendar"></a>建立預約日曆

在 Teams中，前往 **BookingsGet**  >  **Started，** 然後選取新的 **預約日曆**。 完成表單，並請務必為貴組織選擇相關的商務類型。

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="顯示商務類型的新預約日曆畫面螢幕擷取畫面":::

如果您是較大的組織，如果您希望出席者收到來自特定部門而非整個組織的預約電子郵件，請考慮建立多個預約日曆。
若要深入瞭解，請參閱 [建立 Bookings 日曆](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148)。

> [!NOTE]
> 如果這不是您第一次使用 Bookings App，或您想要使用現有的預約日曆，請在 Bookings 中選取組織名稱旁的下拉箭號，然後選擇現有的預約 **日曆**。 您可以在這裡搜尋您想要的。

### <a name="add-staff"></a>新增教職員

在預約日曆中，前往其他 **選項 (...****) >設定，** 然後選取教 **職員**。 新增教職員成員，並將角色指派給每個新增的人員。 您可以新增最多 100 位教職員成員至預約日曆。

Bookings App 會與 Outlook。 新增教職員之後，您就能查看該人員的日曆可用性，並排程他們的預約。 若要深入瞭解，請參閱 [新增教職員並查看 Bookings 日曆](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0)。  

### <a name="create-appointment-types"></a>建立約會類型

建立特定的約會類型來代表貴組織提供的服務，並量身訂做預約體驗。

在預約日曆中，前往更多 **選項 (...** ) > **約會類型**，然後選取新增 **約會類型**。 輸入名稱， &mdash; 例如帳戶開啟、開單續約、貸款諮詢、稅務準備 &mdash; ，以及您想要的其他資訊和設定。

每次預約這類約會時，您新增的資訊和連結都會包含在寄給出席者的電子郵件確認中。 您甚至可以設定電子郵件提醒和其他選項，例如出席者是否可以從行動瀏覽器加入[](mobile-browser-join.md)，而不需要下載Teams。 若要深入瞭解，請參閱 [建立約會類型](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)。

## <a name="schedule-a-visit"></a>排程流覽

在預約日曆中，選取新增 **預約**。 選取約會類型，然後填寫相關資訊。

這包括出席者連絡人資訊、將提供服務的員工成員、只有教職員可以看到的內部記事、電子郵件提醒，以及出席者是否可以從行動瀏覽器加入。 若要深入瞭解，請參閱[在 Bookings Teams中排程預約](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f)。

寄給出席者的電子郵件確認包含會議連結和附件，以便他們新增虛擬約會至他們的日曆。 教職員也會收到電子郵件確認和會議邀請。

## <a name="conduct-a-visit"></a>進行流覽

在會議Teams或Outlook中，前往預約，然後選取加入或Teams連結。**** 檢查您的音訊和視音訊設定，然後選取立即 **加入**。 若要深入瞭解，請參閱執行 [Bookings 約會](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd)。

## <a name="monitor-visits-and-get-real-time-status-updates"></a>監控訪問並取得即時狀態更新

Bookings [中的](https://support.microsoft.com/office/queue-view-in-bookings-3eea2840-a1e0-4bcd-8e09-d3cf51c184d6) 佇列視圖提供您的教職員儀表板，可監控當天的所有虛擬約會，並即時更新。 若要查看佇列，請前往 Bookings **中的佇列** 選項卡。

:::image type="content" source="../media/bookings-virtual-visits-queue.png" alt-text="中 Bookings 應用程式中佇列視圖的螢幕擷取畫面Teams" lightbox="../media/bookings-virtual-visits-queue.png":::

排程員可以從佇列中新增預約、查看相關的約會詳細資料，以及查看全天的約會狀態。 當病患加入等候室時，狀態會變更，並且會顯示並追蹤他們的等待時間。 該視圖會自動重新使用色彩編碼的更新，以便輕鬆識別變更。

教職員甚至可以直接從佇列加入及管理約會。

> [!NOTE]
> 目前，Bookings App 支援每個預約日曆新增最多 100 個員工。 如果您用Graph API 來設定並新增員工至預約日曆，可能不會強制執行此限制。 在此情境中 **，無法針對** 超過 100 名教職員的日曆呈現內容。 為了獲得最佳體驗，建議您在預約的日曆中新增不超過 100 名員工。 我們正努力在未來版本中解決此限制。

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Bookings Web App 的其他功能

Bookings Web App 提供您其他功能。 例如，您可以發佈自助線上預約頁面，使用者可以在這裡與員工排程約會。 若要存取 Bookings Web App，請前往開啟 Bookings web app (...) >**其他選項**。

若要深入瞭解，請參閱 [Microsoft Bookings](/microsoft-365/bookings/bookings-overview)。

## <a name="related-articles"></a>相關文章

- [管理行動瀏覽器上Teams虛擬流覽的加入體驗](mobile-browser-join.md)

- [Teams虛擬訪問使用方式報告](../teams-analytics-and-reports/virtual-visits-usage-report.md)

- [開始使用醫療保健組織Teams服務](healthcare/teams-in-hc.md)

- [在說明文件中Teams預約應用程式](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
