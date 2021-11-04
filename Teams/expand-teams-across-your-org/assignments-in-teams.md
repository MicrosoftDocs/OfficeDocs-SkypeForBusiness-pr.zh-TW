---
title: 作業Teams
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: 瞭解如何在 Microsoft Teams 系統管理中心管理Teams 教育版。
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1c2dbc67fdbc55c9ff2a7b2e16cb0957886de3dd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60758305"
---
# <a name="assignments-in-teams-for-education"></a>Teams 教育版中的作業

課程的作業和成績功能Teams 教育版教師將工作、工作或測驗指派給學生。 教師可以管理作業時程表、指示、新增資源以上交、以成績評分等等。 他們也可以追蹤課程和個別學生的進度在 "成績" 選項卡中。

[深入瞭解作業和成績Teams 教育版。](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

> [!Note]
> 有關在不同平臺上Teams作業的詳細資訊，請參閱[Teams功能。](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>系統管理中心中的作業Microsoft Teams整合

使用系統管理中心Microsoft Teams設定，您可以開啟或關閉貴組織內部教育人員及其學生的功能。 以下是與作業相關的設定：

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>每週監護人電子郵件摘要


監護人電子郵件會在每個週末寄給家長或監護人。 電子郵件包含前一周和下周的作業相關資訊。 家長和監護人同步設定可以使用[學校資料同步處理。](/schooldatasync/parent-contact-sync)

1. 在 SDS 中透過家長和監護人同步操作來輸入家長連絡人資訊。 有關如何啟用家長和監護人同步處理的指示，請參閱 [啟用家長和監護人同步處理](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)。

2. 在系統管理中心Microsoft Teams監護人設定，因為設定預設為關閉。 這可讓教師傳送每週摘要。

   > [!NOTE]
   > 教師可以退出宣告摘要，在他們自己的個人班級小組中取消選擇設定 (作業設定 >家長 **/** 監護人電子郵件) 。

若要確認家長會收到電子郵件，下列三個專案必須正確：

 - 附加至 SDS 中學生個人資料的電子郵件地址，並標記為 _家長或__監護人_。 詳細資料請參閱 [家長和監護人同步檔案格式](/schooldatasync/parent-contact-sync-file-format)。

 - 學生至少屬於一個班級，教師不會在作業設定中停用 [電子郵件](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)。

 - 電子郵件會包含在前一周或下周有到期日的作業相關資訊。

此功能的預設設定為 - **關閉**。


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode 是一個區塊式編碼平臺，能讓所有學生都瞭解電腦科學。 

MakeCode 是 Microsoft 產品，受 Microsoft[使用條款和](https://go.microsoft.com/fwlink/?LinkID=206977)[隱私權](https://go.microsoft.com/fwlink/?LinkId=521839)政策所規範。

此功能的預設設定為 - **關閉**。

若要在 Teams中啟用 MakeCode 作業，請Teams系統管理中心、流覽 **至** 作業區段，然後將 MakeCode 切換選項切換到 **開啟**。 按一下 [儲存]。 允許幾個小時讓這些設定生效。

有關此功能運作方式的資訊，請參閱這段 [影片示範](https://makecode.com/blog/teams/teams-assignments)。

[深入瞭解 MakeCode](https://aka.ms/makecode)。

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) 是一項學術誠信服務。 這是受其條款和隱私權政策所保護的協力廠商產品或服務。 您有責任使用任何協力廠商產品和服務。

此功能的預設設定為 - **關閉**。

若要為貴組織啟用 Turnitin，您需要一個 Turnitin 訂閱。 然後，您可以輸入下列資訊，這些資訊可在 Turnitin 系統管理主控台找到：

  * **TurnitinApiKey：** 這是一個 32 個字元的 GUID，位於系統管理主控台的整合下。
  * **TurnitinApiUrl：** 這是您 Turnitin 系統管理主控台的 HTTPS URL。

以下是一些指示，可協助您取得這項資訊。

**TurnitinApiUrl** 是系統管理主控台的主機位址。
範例：`https://your-tenant-name.turnitin.com`

您可以在系統管理主控台建立整合與與整合相關聯的 API 金鑰。

從 **側邊功能表中** 選取整合，然後選取新增 **整合** 並命名整合。

![顯示新增整合的螢幕擷取畫面。](./educationImages/Assignments_mopo_turnitin2.png)

在您遵循提示後，系統就會提供 **TurnitinApiKey。** 複製 API 金鑰並貼到系統管理Microsoft Teams中心。  這是您唯一可以查看金鑰的時間。

![顯示覆制 API 金鑰的螢幕擷取畫面。](./educationImages/Assignments_mopo_turnitin3.png)

按一下系統管理 **中心中的** 此設定中的儲存按鈕後，請允許幾個小時讓這些設定生效。

### <a name="removing-assignments-and-grades"></a>移除作業和成績
您可以使用新的Teams移除特定使用者或整個租使用者的工作分派和成績。 

若要移除個別使用者的作業和成績，請Teams系統管理中心，然後流覽至 Teams 應用程式>**權限原則，以** 建立新的應用程式許可權政策定義。  建立新策略定義時，請設定 **Microsoft 應用程式** 政策以封鎖 _特定應用程式_，並允許所有其他應用程式，並新增作業到封鎖的應用程式清單中。 儲存新策略定義後，請將其指派給適當的使用者。

若要移除整個租使用者的工作分派和成績，請前往 **Teams** 系統管理中心，流覽至 Teams 應用程式 **>管理應用程式**，然後從應用程式清單中搜尋及選取作業。  將作業應用程式設定頁面中的狀態設定變更為 _已封鎖_。 
