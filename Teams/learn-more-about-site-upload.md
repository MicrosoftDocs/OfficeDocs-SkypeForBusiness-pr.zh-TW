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
description: 瞭解如何上傳包含實體位置清單及相關子網的文字檔，以做為通話分析和通話品質儀表板報表的報告標籤。
ms.custom:
- NewAdminCenter_Update
f1.keywords:
- ms.teamsadmincenter.locations.reportinglabels.overview
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.location
- ms.teamsadmincenter.locations.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19d3197d91b7139089a940c19ff23c1dcc99a290
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707858"
---
<a name="add-and-update-reporting-labels"></a>新增和更新報告標籤
============================

您的組織會使用報表標籤來指示辦公室、建築物或組織網站的物理位置。 Microsoft [團隊管理中心] 中的 [報告標籤] 頁面可讓您提供內含物理位置及其相關網路子網清單的文字檔（.csv 或 tsv）。 此檔案是由 [通話分析] 和 [通話品質儀表板] 用來產生報告。 當您上傳子網對應時，這些服務所提供的報告也會包含位置名稱，讓報告更容易理解，並用於修正任何潛在問題。

您所提供的報表標籤和位置資料是單一資料結構，目前沒有可用來對資料進行個別編輯的介面。

**若要編輯子網和位置的表格**

1. 在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**位置** > **報告標籤**]。
2. 按一下 [**取代位置資料**]。
3. 在 [**取代位置資料**] 窗格中，按一下 [**選取**檔案]，然後流覽到並上傳已編輯的 .csv 或 tsv 檔案。
4. 按一下 **[上傳**]。

您可以在[這裡](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)下載範例範本。

使用下列範例來協助您建立資料檔案。

> [!IMPORTANT]
> 您的資料檔案不應該包含欄標題（例如 [網路]、[網路名稱] 等等）。 此處只是用來提供資訊的目的。 <br>

|網路|網路名稱|網路範圍|建築物名稱|擁有權類型|建築物類型|建立 Office 類型|座|郵遞區號|國家|市|地區|在 Corp 內|快速路線|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0 |SVC-1|32|USCAMTV001|Contoso 租賃 RE&F|Office|重新&F|山地視圖|94043|一下|頒發|一下|1|1|
|10.0.130.0 |SVC-1|32|USCAMTV001|Contoso 租賃 RE&F|Office|重新&F|山地視圖|94043|一下|頒發|一下|1|1|
|10.0.131.0 |SVC-1|32|USCAMTV001|Contoso 租賃 RE&F|Office|重新&F|山地視圖|94043|一下|頒發|一下|1|1|
|10.0.132.0 |SVC-1|32|USCAMTV001|Contoso 租賃 RE&F|Office|重新&F|山地視圖|94043|一下|頒發|一下|1|1|

如需格式化資料檔案的詳細資訊，請參閱[租使用者資料檔案格式及建立資料檔案結構](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-structure)。

## <a name="related-topics"></a>相關主題

[設定通話分析](set-up-call-analytics.md)
