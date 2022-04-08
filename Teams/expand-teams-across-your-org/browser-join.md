---
title: 管理瀏覽器上Teams虛擬造訪的加入體驗
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
ms.reviewer: hafarmer
description: 瞭解Teams瀏覽器上虛擬流覽的加入體驗。
ms.openlocfilehash: 276e33b16972f0543566014adf264fd12e45c4ae
ms.sourcegitcommit: 1e8cff687b12348d4ecc538084ab57bbba23b523
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2022
ms.locfileid: "64703740"
---
# <a name="manage-the-join-experience-for-teams-virtual-visits-on-browsers"></a>管理瀏覽器上Teams虛擬造訪的加入體驗

Microsoft Teams可讓使用者輕鬆加入虛擬約會，而不需要下載Teams。 為獲得更順暢的體驗，出席者可以從桌面或行動瀏覽器加入約會，例如醫療探訪和財務諮詢。 出席者不需要在他們的裝置上安裝Teams應用程式。

使用瀏覽器加入時，當出席者加入約會時，系統不會提示他們下載Teams。 相反地，Teams會在瀏覽器中開啟，出席者可以選取 [**立即加入**] 加入。 使用此功能時，請記住，如果裝置上已安裝Teams，Teams會在瀏覽器中開啟，而非在應用程式中開啟。

目前，瀏覽器加入適用于已排程到下列的約會：

- [Bookings應用程式](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)
- Microsoft Teams電子健康情況記錄 (EHR) 連接器

  - 與 [Cerner EHR 整合](healthcare/ehr-admin-cerner.md)
  - 與 [EHR 整合](healthcare/ehr-admin.md)

## <a name="set-up-browser-join"></a>設定瀏覽器加入

### <a name="appointments-scheduled-through-the-bookings-app"></a>透過 Bookings 應用程式排程的約會

貴組織中的排程器可以在Bookings應用程式中針對特定約會類型和個別約會開啟此功能。

開啟此功能之後，傳送給出席者的確認電子郵件或簡訊會包含在桌面或行動瀏覽器中開啟Teams的會議加入連結。 如需支援的瀏覽器清單，請參閱 [支援的瀏覽器](#supported-browsers)。

#### <a name="turn-on-browser-join-for-an-appointment-type"></a>開啟約會類型的瀏覽器加入

在 Bookings 中，移至 **設定**  >  **Appointment 類型**，選取 [約會類型](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)，然後開啟 [**允許出席者從瀏覽器加入]**。 這樣做可讓瀏覽器針對此類型的所有約會加入。

:::image type="content" source="../media/browser-join-bookings-appointment-type.png" alt-text="在 Bookings 應用程式中，允許出席者從約會類型的瀏覽器設定加入的螢幕擷取畫面":::

#### <a name="turn-on-browser-join-for-an-individual-appointment"></a>開啟個別約會的瀏覽器加入

在 Bookings 中，選取 **[新增預約**]，然後開啟 [**允許出席者從瀏覽器加入]**。

:::image type="content" source="../media/browser-join-bookings-form.png" alt-text="在 Bookings 應用程式中，新預約表單上的 [允許出席者從瀏覽器加入] 設定的螢幕擷取畫面":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>透過 Teams EHR 連接器排定約會

您或您的員工不需要設定！

**與 Cerner EHR** 整合：Teams EHR 連接器支援透過簡訊中的連結加入虛擬約會。 在預約時，病患可以點選簡訊中的連結來加入，Teams在瀏覽器中開啟。

**與 EHR 整合**：Teams EHR 連接器支援透過 MyChart Web 和行動裝置加入虛擬約會的病患。 在預約時，病患可以使用 [**開始] 虛擬造訪** 按鈕從 MyChart 開始造訪，Teams在瀏覽器中開啟。

## <a name="supported-browsers"></a>支援的瀏覽器

以下是目前支援的瀏覽器。 除非另有指示，否則我們支援最新版本加上前兩個版本。

|平台  |鉻 |Safari |Edge (Chromium) |
|---------|:---|:---|:---:|
|Android   | &#x2714; &sup1;      |         |         |
|iOS    |         | &#x2714; &sup1;&sup2; |         |
|macOS     | &#x2714; | &#x2714;|         |
|Windows    | &#x2714; |   | &#x2714; |
|Ubuntu/Linux     | &#x2714;         |     |         |

&sup1;iOS 或 Android 不支援外寄螢幕畫面分享。

&sup2;Safari 上的 iOS 應用程式無法選取麥克風和喇叭裝置。 例如，藍牙裝置。 這是控制預設裝置選取範圍的作業系統限制。

## <a name="things-to-consider"></a>考慮事項

進行此流覽的教職員成員可以從他們的Teams桌面、行動裝置或網頁用戶端，與從桌上型電腦或行動瀏覽器加入的出席者共用他們的螢幕。 不過，出席者無法從桌面或行動瀏覽器共用螢幕。

## <a name="related-articles"></a>相關文章

- [含 Teams 和 Bookings 應用程式的虛擬造訪](bookings-virtual-visits.md)
- [建立Bookings約會類型](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [以出席者身分加入Bookings約會](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [含 Teams 的虛擬造訪 - 整合至 Cerner EHR](healthcare/ehr-admin-cerner.md)
- [含 Teams 的虛擬造訪 - 整合至 EHR](healthcare/ehr-admin.md)
