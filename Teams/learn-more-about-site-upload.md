---
title: 新增和更新報告標籤
author: tonysmit
ms.author: tonysmit
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何上傳包含實體位置及相關子網清單的文字檔，以新增及更新報告標籤。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.locations.reportinglabels.overview
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.location
- ms.teamsadmincenter.locations.overview
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4a1af7f14695d1f933a9c3902b373eb668044e24
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918639"
---
<a name="add-and-update-reporting-labels"></a>新增和更新報告標籤
============================

報告標籤在貴組織中是用來指出辦公室、建築物或組織網站實際位置。 Microsoft Teams 系統管理中心的報告標籤頁面可讓您提供文字檔 (.csv 或 .tsv) ，其中包含實體位置與其關聯網路子網的清單。 Call Analytics 會使用這個檔案來產生報告。 當您上傳子網地圖時，這些服務所提供的報告也會包含位置名稱，使報告更容易瞭解及用於補救任何潛在問題。

> [!IMPORTANT]
> 您上傳的報告標籤將依照您的 Office  365 協定處理為支援資料，包括任何會被視為客戶 *資料* 或 *個人資料的資訊*。 請勿包含您不想提供給 Microsoft 作為支援資料的資料，因為Microsoft 工程師將會為了支援目的看到此資訊。

您提供的報表標籤和位置資料是單一的資料結構，目前沒有任何介面可供個別編輯資料。

**編輯子網和位置資料表**

1. 在 Microsoft Teams 系統管理中心的左側流覽區中，按一下 [**位置**  >  **報告標籤**。
2. 按一下 **[取代位置資料**。
3. 在 [**取代位置資料窗格**>中，按一下 [選取檔案，然後流覽至並上傳您編輯的 .csv 或 .tsv 檔案。
4. 按一下 **[上傳**。

您可以在這裡下載範本 [範例](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)。

使用下列範例來協助建立您的資料檔案。

> [!IMPORTANT]
> 您的資料檔案不應該包含欄標題 (例如網路、網路名稱等) 。 這些僅供參考。 <br>

|網路|網路名稱|網路範圍|建築物名稱|擁有權類型|建築物類型|建建 Office 類型|城市|郵遞區號|國家|狀態|地區|Inside Corp|Express Route|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMHD001|Contoso 租用 RE&F|Office|RE&F|山脈視圖|94043|我們|約|我們|1|1|
|10.0.130.0    |SVC-1|32|USCAMHD001|Contoso 租用 RE&F|Office|RE&F|山脈視圖|94043|我們|約|我們|1|1|
|10.0.131.0    |SVC-1|32|USCAMHD001|Contoso 租用 RE&F|Office|RE&F|山脈視圖|94043|我們|約|我們|1|1|
|10.0.132.0    |SVC-1|32|USCAMHD001|Contoso 租用 RE&F|Office|RE&F|山脈視圖|94043|我們|約|我們|1|1|

有關格式化資料檔案的資訊，請參閱租使用者資料檔案格式 [和建築物資料檔案結構](CQD-upload-tenant-building-data.md#upload-building-data-file)。

## <a name="related-topics"></a>相關主題

[設定通話分析](set-up-call-analytics.md)

[使用通話分析來疑難排解不佳的通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)
