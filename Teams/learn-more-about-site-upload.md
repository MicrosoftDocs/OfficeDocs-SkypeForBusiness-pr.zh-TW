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
description: 瞭解如何上傳包含實體位置和相關子網清單的文字檔來新增和更新報表標籤。
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
ms.openlocfilehash: 2b04b75ca85a3a1ac148434de00cadfc78680ef2259a85c2eb2dab0a4181db82
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/11/2021
ms.locfileid: "57849508"
---
# <a name="add-and-update-reporting-labels"></a>新增和更新報告標籤

貴組織中會使用報表標籤來表示辦公室、建築物或組織網站實際位置。 系統管理中心中的 Microsoft Teams 標籤頁面可讓您提供文字檔 (.csv 或 .tsv) ，其中包含實體位置及其相關聯的網路子網清單。 這個檔案是由通話分析用來產生報告。 當您上傳子網地圖時，這些服務所提供的報告也會包含位置名稱，讓報表更容易理解及用於補救任何潛在問題。

> [!IMPORTANT]
> 您上傳的報表標籤會依照您Office 365，以支援資料的方式處理，包括否則視為客戶 *資料* 或 *個人資料的任何資訊*。  請不要包含您不想以支援資料提供給 Microsoft 的資料，因為Microsoft 工程師會為了支援目的看到此資訊。

您提供的報表標籤和位置資料是單一的資料結構，目前沒有任何介面可供個別編輯資料。

**編輯子網和位置表格**

1. 在系統管理中心的左側導Microsoft Teams，按一下 **[位置**  >  **報告標籤**> 。
2. 按一下 **Upload 資料**。
3. 在 [Upload **窗格中**，按一下 [選取檔案，然後流覽並上傳您編輯的檔案.csv .tsv 檔案。
4. 按一下 **[Upload。**

您可以在這裡下載範例 [範本](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)。

請使用下列範例來協助建立資料檔案。

> [!IMPORTANT]
> 您的資料檔案不應包含欄標題 (例如網路、網路名稱等) 。 這些僅供參考之用。 <br>

|網路|網路名稱|網路範圍|建築物名稱|擁有類型|建築物類型|建立Office類型|城市|郵遞區號|國家|狀態|地區|內部公司|快速路由|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso 租賃 RE&F|Office|RE&F|山脈視圖|94043|我們|約|我們|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso 租賃 RE&F|Office|RE&F|山脈視圖|94043|我們|約|我們|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso 租賃 RE&F|Office|RE&F|山脈視圖|94043|我們|約|我們|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso 租賃 RE&F|Office|RE&F|山脈視圖|94043|我們|約|我們|1|1|

有關格式化資料檔案的資訊，請參閱租使用者 [資料檔案格式和建立資料檔案結構](CQD-upload-tenant-building-data.md#upload-building-data-file)。

## <a name="related-topics"></a>相關主題

[設定通話分析](set-up-call-analytics.md)

[使用通話分析來疑難排解通話品質不佳的問題](use-call-analytics-to-troubleshoot-poor-call-quality.md)
