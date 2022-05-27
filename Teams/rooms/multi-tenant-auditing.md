---
title: 多租使用者稽核
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: TRM 的稽核記錄。
f1keywords: ''
ms.openlocfilehash: 3681f50f0e15a7688a944c14e69907ba53dd2817
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676606"
---
# <a name="audit-logging-in-the-teams-rooms-managed-service"></a>Teams 會議室受管理服務中的稽核記錄

Teams 會議室 Managed (TRM) 服務中的稽核可讓您搜尋由使用者和系統管理員在入口網站中執行之活動的稽核記錄。 此功能預設為啟用。 只有受管理的服務系統管理員具有匯出並檢視記錄的許可權。

> [!NOTE]
> 在 TRM 服務中執行的動作不會記錄在Microsoft 365或Office 365稽核中 

## <a name="exporting-logs"></a>匯出記錄

當您匯出稽核記錄搜尋的所有結果時，會將整合稽核記錄的原始資料複製到下載至本機電腦的 CSV)  (逗號分隔值檔案。 

**下載記錄檔** 

1. 移至 **設定 >一般>稽核記錄]**。
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


