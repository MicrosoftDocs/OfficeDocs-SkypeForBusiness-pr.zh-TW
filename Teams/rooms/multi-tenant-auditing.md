---
title: MTR Pro 入口網站中的稽核記錄
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: MTR Pro 入口網站的稽核記錄。
f1keywords: ''
ms.openlocfilehash: 0436618e257128deb38d890cb92813ae13921e7d
ms.sourcegitcommit: 64c01699022b47fdfec8dc6e2ca279e57eae3baa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2022
ms.locfileid: "68243914"
---
# <a name="audit-logging-in-the-mtr-pro-portal"></a>MTR Pro 入口網站中的稽核記錄

MTR Pro 入口網站的稽核記錄可讓您搜尋使用者和系統管理員所執行活動的稽核記錄。 此功能預設為啟用。 只有受管理的服務系統管理員具有匯出並檢視記錄的許可權。

> [!NOTE]
> 在 MTR Pro 入口網站中執行的動作不會記錄在 Microsoft 365 或Office 365稽核中 

## <a name="exporting-logs"></a>匯出記錄

當您匯出稽核記錄搜尋的所有結果時，會將整合稽核記錄的原始資料複製到下載至本機電腦的 CSV)  (逗號分隔值檔案。 

**下載記錄檔** 

1. 移至 **[一般] > [稽核記錄] >** [設定]。
1. 若要定義興趣記錄的日期範圍，請輸入 **開始日期** 和 **結束日期。**

   > [!NOTE]
   > 記錄最多隻能使用 180 天。

1. 選取 **[下載記錄]。**

   ![稽核記錄日期範圍](../media/multi-tenant-auditing.png)

   視窗底部顯示的訊息會提示您開啟或儲存 CSV 檔案。 

1. 選 **取 [另存**  >  **新檔**]，並將 CSV 檔案儲存到本機電腦。 

1. 搜尋所有活動或在廣泛日期範圍內搜尋搜尋結果時，需要一段時間才能下載許多搜尋結果。 CSV 檔案下載完成後，視窗底部會顯示一則訊息。

## <a name="detailed-properties-in-the-audit-log"></a>稽核記錄中的詳細屬性

下表說明 CSV 中包含的屬性。

|屬性|描述|
| - | - |
|activity.category|<p>執行動作的物件類別。 可能的值：</p><p>**使用者，指派，合作夥伴邀請，角色**</p>|
|activity.objectName|修改物件的名稱。|
|activity.operation|執行的作業類型。 可能的值為： **建立、更新、刪除** |
|activity.resultStatus|<p>表示 activity the action (指定的 **activity.operation** property) 是否成功。</p><p>值是 **成功** 或 **失敗**。</p>|
|activity.tenantId|執行動作之租使用者的 GUID|
|creationTime|當使用者執行活動時，以 ISO 格式 (UTC) 標準通用時間的日期和時間。|
|user.userId|執行導致記錄記錄的動作的使用者。|
|user.userTenantId|執行動作之使用者的租使用者 GUID|


