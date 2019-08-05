---
title: 新增及更新位置資料
author: tonysmit
ms.author: tonysmit
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 瞭解如何上傳至網站。
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.locations.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e7e9211b207c008de22fe86ae0c7bb6c9f9ac51
ms.sourcegitcommit: 1336f6c182043016c42660d5f21632d82febb658
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/31/2019
ms.locfileid: "36184023"
---
<a name="adding-and-updating-locations-data"></a>新增及更新位置資料
============================

位置是在您的組織中用來指出辦公室、建築物或組織網站的物理位置。 [位置] 頁面可讓系統管理員提供一個文字檔 (.csv 或 tsv), 其中包含物理位置的清單及其相關聯的網路子網。 此檔案是由 [通話分析] 和 [通話品質儀表板] 用來產生報告。 當客戶上傳其子網對應時, 這些服務所提供的報告也會包含位置名稱, 讓報告更容易理解, 並用於修正任何潛在問題。

您所提供的位置資料是單一資料結構, 目前沒有介面可供對位置資料進行個別編輯。 

**若要編輯子網和位置的表格**

1. 按一下 [**取代位置資料**]。
2. 在 [**取代位置資料**] 窗格中, 按一下 [**選取**檔案], 然後流覽到並上傳已編輯的 .csv 或 tsv 檔案。 
3. 按一下 **[上傳**]。 


您可以在[這裡](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)下載範例範本。

您可以使用下列範例來協助您建立資料檔案。 

> [!IMPORTANT]
> 您的資料檔案不應該包含欄標題 (例如 [網路]、[網路名稱] 等等)。 此處只是用來提供資訊的目的。 </br>

|局域網|網路名稱|網路範圍|建築物名稱|擁有權類型|建築物類型|建立 Office 類型|座|郵遞區號|國家|市|國家|在 Corp 內|快速路線|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0 |SVC-1|32|USCAMTV001|Contoso 租賃 RE&F|辦事處|重新&F|山地視圖|94043|一下|頒發|一下|sr-1|sr-1|
|10.0.130.0 |SVC-1|32|USCAMTV001|Contoso 租賃 RE&F|辦事處|重新&F|山地視圖|94043|一下|頒發|一下|sr-1|sr-1|
|10.0.131.0 |SVC-1|32|USCAMTV001|Contoso 租賃 RE&F|辦事處|重新&F|山地視圖|94043|一下|頒發|一下|sr-1|sr-1|
|10.0.132.0 |SVC-1|32|USCAMTV001|Contoso 租賃 RE&F|辦事處|重新&F|山地視圖|94043|一下|頒發|一下|sr-1|sr-1|


如需格式化資料檔案的詳細資訊, 請參閱[租使用者資料檔案格式及建立資料檔案結構](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-structure)。


## <a name="related-topics"></a>相關主題

[設定通話分析](set-up-call-analytics.md)
