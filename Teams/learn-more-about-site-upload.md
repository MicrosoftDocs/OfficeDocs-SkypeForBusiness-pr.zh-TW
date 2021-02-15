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
description: 瞭解如何上傳文字檔來新增及更新報告標籤，該文字檔包含實體位置及相關聯的子網清單。
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
ms.openlocfilehash: 481e087a6cfe2b641f6b81fcfc893d50f27cbf47
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237483"
---
<a name="add-and-update-reporting-labels"></a>新增和更新報告標籤
============================

報告標籤在貴組織中用來指出辦公室、建築物或組織網站實際位置。 Microsoft Teams 系統管理中心的報告標籤頁面可讓您提供文字檔 (.csv 或 .tsv) ，其中包含實體位置及其關聯網路子網的清單。 Call Analytics 會使用這個檔案來產生報告。 當您上傳子網地圖時，這些服務所提供的報告也會包含位置名稱，讓報告更容易理解並用於補救任何潛在問題。

> [!IMPORTANT]
> 您上傳的報告標籤將依據 Office  365 之協定處理為支援資料，包括任何會被視為客戶 *資料* 或 *個人資料的資訊*。 請勿將您不想提供給 Microsoft 的資料做為支援資料，因為 Microsoft 工程師為了支援目的將會看到此資訊。

您提供的報表標籤和位置資料為單一資料結構，目前沒有任何介面可供個別編輯資料。

**編輯子網和位置的表格**

1. 在 Microsoft Teams 系統管理中心的左側流覽中，按一下 **位置**  >  **報告標籤**。
2. 按一下 **[上傳資料**。
3. 在 [**上傳資料窗格**>中，按一下 [選取檔案，然後流覽至並上傳您編輯的 .csv 或 .tsv 檔案。
4. 按一下 **[上傳**。

您可以在這裡下載範本 [範例](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)。

使用下列範例來協助建立資料檔案。

> [!IMPORTANT]
> 您的資料檔案不應該包含欄標題 (例如網路、網路名稱等) 。 這些僅供參考之用。 <br>

|網路|網路名稱|網路範圍|建築物名稱|擁有權類型|建築物類型|建建 Office 類型|城市|郵遞區號|國家|狀態|地區|Inside Corp|Express Route|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|山脈景觀|94043|我們|約|我們|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|山脈景觀|94043|我們|約|我們|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|山脈景觀|94043|我們|約|我們|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|山脈景觀|94043|我們|約|我們|1|1|

有關格式化資料檔案的資訊，請參閱租使用者 [資料檔案格式和建案資料檔案結構](CQD-upload-tenant-building-data.md#upload-building-data-file)。

## <a name="related-topics"></a>相關主題

[設定通話分析](set-up-call-analytics.md)

[使用通話分析來疑難排解不佳的通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)
