---
title: 管理在行動瀏覽器上Teams虛擬流覽的加入體驗
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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: hafarmer
description: 瞭解在行動瀏覽器上Teams虛擬流覽的加入體驗。
ms.openlocfilehash: 6183fccce1c455ac46f4eb7c166530535d5dbbe8
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432685"
---
# <a name="manage-the-join-experience-for-teams-virtual-visits-on-mobile-browsers"></a>管理在行動瀏覽器上Teams虛擬流覽的加入體驗

Microsoft Teams，使用者無需下載約會，即可在行動裝置上Teams。 為了獲得更順暢的體驗，出席者可以從行動瀏覽器加入約會，例如醫療保健訪問、財務諮詢、教育人員辦公室時數等。 出席者不需要在 Android 或 iOS 行動裝置上Teams行動裝置 App。

使用行動瀏覽器加入時，當出席者從行動裝置加入約會時，系統不會提示他們下載Teams。 相反地，Teams在行動瀏覽器中開啟，出席者可以在這裡選取立即 **加入** 以加入。 使用這項功能時，請記住，如果Teams已安裝在出席者行動裝置上，Teams在行動瀏覽器中開啟，而不是在應用程式中開啟。

目前，行動瀏覽器加入適用于透過下列方式排程的約會：

- [Bookings 應用程式](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-us&rs=en-us&ad=us#PickTab=Bookings)
- [Microsoft TeamsEHR (電子健康) 連接器](healthcare/ehr-admin.md)

## <a name="set-up-mobile-browser-join"></a>設定行動瀏覽器加入

### <a name="appointments-scheduled-through-the-bookings-app"></a>透過 Bookings 應用程式排程的約會

貴組織的排程者可以在 Bookings App 中針對特定約會類型及個別約會開啟此功能。

開啟此功能後，寄給出席者之確認電子郵件或簡訊將會包含在行動瀏覽器中開啟Teams加入連結。 在 Android 行動裝置上，Teams Chrome 中開啟。 在 iOS 行動裝置上，Teams Safari 中開啟。

#### <a name="turn-on-mobile-browser-join-for-an-appointment-type"></a>開啟約會類型的行動瀏覽器加入

在 Bookings 中，設定約會類型，選取約會類型，然後開啟允許出席者從行動瀏覽器  >  ******加入**。 [](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887) 這麼做可讓行動瀏覽器加入此類型的所有約會。

:::image type="content" source="../media/mobile-browser-join-bookings-appointment-type.png" alt-text="允許出席者從行動瀏覽器設定加入 Bookings 應用程式中約會類型的螢幕擷取畫面":::

#### <a name="turn-on-mobile-browser-join-for-an-individual-appointment"></a>開啟行動瀏覽器加入個別約會

在 Bookings 中，選取 **新的預約**，然後開啟允許出席者 **從行動瀏覽器加入**。

:::image type="content" source="../media/mobile-browser-join-bookings-form.png" alt-text="在 Bookings 應用程式的新預約表單上，允許出席者從行動瀏覽器加入的螢幕擷取畫面":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>透過 EHR 連接器排定Teams約會

您或教職員不需要設定！

EHR Teams連接器可支援透過 MyChart Web 和 Mobile 加入虛擬訪問的病患。 預約時，病患可以使用開始虛擬瀏覽按鈕，從 MyChart 開始 **虛擬流覽** 。 病患選擇他們想要的瀏覽器，然後Teams開啟該瀏覽器。

## <a name="supported-mobile-browsers"></a>支援的行動瀏覽器

以下是目前支援的移動瀏覽器。 除非另有說明，否則我們支援最新版本加上兩個先前版本。

|平台  |鉻 |Safari |Edge (Chromium) |
|---------|:---:|:---:|:---:|
|Android   |   &#x2714;      |         |         |
|iOS    |         |  &#x2714; &sup1;       |         |
|macOS     |         |  &#x2714; &sup2;    |         |

&sup1;Safari 上的 iOS 應用程式無法選取麥克風和喇叭裝置。 例如，藍牙裝置。 這是作業系統的限制，可控制預設裝置選取範圍。

&sup2;外發視像支援需要 Safari 14+ 和 macOS 11+ 才能使用。

> [!NOTE]
> 我們會在未來發行新版會議加入體驗中新增更多功能Teams，因此請回來查看最新資訊。 若要隨時瞭解即將推出的Teams功能，請查看 Microsoft 365[藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)。

## <a name="related-articles"></a>相關文章

- [使用 Teams 和 Bookings 應用程式進行虛擬訪問](bookings-virtual-visits.md)
- [建立 Bookings 約會類型](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [以出席者加入 Bookings 約會](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [使用 Teams 虛擬就診 - 整合至 EHR](healthcare/ehr-admin.md)
