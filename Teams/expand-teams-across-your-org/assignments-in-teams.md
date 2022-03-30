---
title: 作業Teams
author: DaniEASmith
ms.author: danismith
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
ms.openlocfilehash: 529240db27824ce8bf872d23636b904198ef7db1
ms.sourcegitcommit: ecc67b7b9378cc72f85517f30c32680045056fda
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/28/2022
ms.locfileid: "64504133"
---
# <a name="assignments-in-teams-for-education"></a>Teams 教育版中的作業

課程的作業和成績功能Teams 教育版教師將工作、工作或測驗指派給學生。 教師可以管理作業時程表、指示、新增資源以上交、以成績評分等等。 他們也可以追蹤課程和個別學生的進度在 "成績" 選項卡中。

[深入瞭解作業和成績](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)Teams 教育版。

> [!Note]
> 有關在不同平臺上Teams作業的詳細資訊，請參閱[Teams功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>系統管理中心中的作業Microsoft Teams整合

使用系統管理中心Microsoft Teams設定，您可以開啟或關閉貴組織內部教育人員及其學生的功能。 以下是與作業相關的設定：

<a name="#bkemaildigest"> </a>

### <a name="weekly-guardian-email-digest"></a>每週監護人電子郵件摘要

監護人電子郵件會在每個週末寄給家長或監護人。 電子郵件包含前一周和下周的作業相關資訊。 家長和監護人同步設定[可以使用學校資料同步處理。](/schooldatasync/parent-contact-sync)

1. 在 SDS 中透過家長和監護人同步操作來輸入家長連絡人資訊。 有關如何啟用家長和監護人同步處理的指示，請參閱 [啟用家長和監護人同步處理](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)。

2. 在系統管理中心Microsoft Teams監護人設定，因為設定預設為關閉。 這可讓教師每週傳送摘要。

   > [!NOTE]
   > 教師可以退出宣告摘要，在他們自己的個人班級小組中取消選擇設定 (作業設定 >家長 **/** 監護人電子郵件) 。

若要確認家長會收到電子郵件，下列三個專案必須正確：

- 附加至 SDS 中學生個人資料並標記為家長 _或_ 監護人 _的電子郵件地址_。 詳細資料請參閱家長 [和監護人同步檔案格式](/schooldatasync/parent-contact-sync-file-format)。

- 學生至少屬於一個班級，教師不會在作業設定中停用 [電子郵件](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)。

- 電子郵件會包含與作業有關的資訊，這些作業的到期日為前一周或下周。

此功能的預設設定為 - **關閉**。

<a name="bkmakecode"> </a>

### <a name="makecode"></a>MakeCode

Microsoft MakeCode 是一個區塊式編碼平臺，能讓所有學生都瞭解電腦科學。

MakeCode 是 Microsoft 產品，受 Microsoft[使用條款和](https://go.microsoft.com/fwlink/?LinkID=206977)[隱私權](https://go.microsoft.com/fwlink/?LinkId=521839)政策所規範。

此功能的預設設定為 - **關閉**。

若要在系統Teams啟用 MakeCode 作業，請Teams系統管理中心、流覽 **至作業區** 段，然後將 MakeCode 切換選項切換為 **開啟**。**** 選取 [儲存 **]**。 允許幾個小時讓這些設定生效。

有關此功能運作方式的資訊，請觀看這段 [影片示範](https://makecode.com/blog/teams/teams-assignments)。

[深入瞭解 MakeCode](https://aka.ms/makecode)。

<a name="#turnitin"> </a>

### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) 是一項學術誠信服務。 這是協力廠商服務，受其條款和隱私權政策所影響。 您有責任使用任何協力廠商產品和服務。

此功能的預設設定為 - **關閉**。

若要為貴組織啟用 Turnitin，您需要一個 Turnitin 訂閱。 然後，您可以輸入下列資訊，這些資訊可在 Turnitin 系統管理主控台找到：

- **TurnitinApiKey**：這是一個 32 個字元的 GUID，位於系統管理主控台的整合下。
- **TurnitinApiUrl**：這是您 Turnitin 系統管理主控台的 HTTPS URL。

以下是一些指示，可協助您取得這項資訊。

**TurnitinApiUrl** 是系統管理主控台的主機位址。
範例：`https://your-tenant-name.turnitin.com`

您可以在系統管理主控台建立整合與與整合相關聯的 API 金鑰。

從 **側邊功能表中** 選取整合，然後選取新增 **整合** 並命名整合。

![顯示新增整合的螢幕擷取畫面。](./educationImages/Assignments_mopo_turnitin2.png)

在您遵循提示後，系統就會提供 **TurnitinApiKey** 。
複製 API 金鑰並貼到系統管理Microsoft Teams中心。  這是您唯一可以查看金鑰的時間。

![顯示覆制 API 金鑰的螢幕擷取畫面。](./educationImages/Assignments_mopo_turnitin3.png)

按一下系統 **管理中心中的** 此設定中的儲存按鈕後，請允許幾個小時讓這些設定生效。

## <a name="assignments-data"></a>作業資料

作業會儲存教師和學生所產生的資訊。 所有資料在教師與特定學生之間共同共用，而該資訊是供班級使用。 此資料有兩個存放區，SharePoint及外部SharePoint。

>[!NOTE]
>相同的規則也適用于第一方整合，例如閱讀進度。

### <a name="assignments-data-in-sharepoint-document-libraries"></a>文件庫中SharePoint作業資料

與作業提交相關聯的學生檔案會儲存在文件庫中， (名為： *學生作業*) 。 與教師所建立且學生易於訪問的作業相關聯的檔案會儲存在另一個文件庫中 (*名為：課程* 檔案) 在對應的課程小組SharePoint網站。 第一方整合也可以將作業資料儲存在相同的對應課程小組SharePoint網站 (名為：作業標題 *+* 時間戳記) 。

#### <a name="files-associated-with-the-student"></a>與學生相關聯的檔案

IT 系統管理員可以使用內容搜尋工具搜尋學生檔案 (學生作業、課程檔案或其他第一方整合檔案) 這些檔案與作業提交和作業相關的檔案相關。 例如，系統管理員可以搜尋組織中所有 SharePoint 網站，並使用學生的名稱和班級或作業名稱在搜尋查詢中尋找資料主體要求 (DSR) 。

#### <a name="files-associated-with-the-teacher"></a>與教師相關聯的檔案

IT 系統管理員可以使用內容搜尋工具搜尋教師檔案 (學生作業、課程檔案或其他第一方整合檔案 **) 這些檔案與作業中教師在作業中散發給學生的作業和檔案相關。 例如，系統管理員可以搜尋SharePoint網站，並使用教師的名稱和班級或作業名稱在搜尋查詢中尋找與 DSR 相關的資料。

### <a name="assignments-data-outside-of-sharepoint-document-libraries"></a>文件庫SharePoint作業資料

與作業相關的某些資料不會儲存在課程小組SharePoint網站中，這表示內容搜尋無法發現。 這包括：

- 學生成績和教師的意見
- 每個學生提交作業的檔案清單
- 作業詳細資料 ，例如到期日等。
- 第一方整合資料，例如閱讀進度段落或學生髮音資料

針對這類資料，IT 系統管理員或資料擁有者 ，例如教師，可能必須進入班級小組中的作業，才能尋找與 DSR 相關的資料。 管理員可以將自己新增為班級的擁有者，並查看該班級小組的所有作業。

>[!NOTE]
>如果學生不再是班級的一部分，他們的資料可能仍在班級中，因為已 *註冊*。 學生必須提供租使用者系統管理員他們曾經參與的這類課程清單。

### <a name="bulk-export-assignment-data-outside-of-sharepoint-document-libraries"></a>大量匯出文件庫SharePoint作業資料

#### <a name="for-a-student"></a>針對學生

若要大量匯出單一學生的資料 [](/microsoft-365/education/deploy/configure-assignments-for-teams) ``userId`` ，在將學生從他們屬於的班級移除之前，請執行腳本並提供 。 如果學生已從 ``userId`` ``classId`` 網站中移除，系統管理員可以在執行腳本之前將學生新增回班級，或者管理員可以提供 學生曾經參與的 。

學生提交的資料將會匯出。

#### <a name="for-a-teacher"></a>適用于教師

大量匯出作業資料對學生運作的方式相同，但教師可存取的所有提交都會匯出。

### <a name="bulk-delete-assignment-data-outside-of-sharepoint-document-libraries"></a>大量刪除文件庫SharePoint作業資料

#### <a name="for-a-student"></a>針對學生

若要大量刪除單一學生的資料[](/microsoft-365/education/deploy/configure-assignments-for-teams) ``userId`` ，在將學生從他們屬於的班級移除之前，請執行腳本並提供 。 如果學生已從 ``userId`` ``classId`` 網站中移除，系統管理員可以在執行腳本之前將學生新增回班級，或者管理員可以提供 學生曾經參與的 。

提供將 ``ClassId`` 允許系統管理員只刪除特定班級中學生的資訊。

#### <a name="for-a-teacher"></a>適用于教師

由於教師的作業資料會在整個班級中共用，因此沒有大量刪除選項。 相反地，系統管理員可以自行新增到班級、前往應用程式，然後刪除作業。

詳細資訊，請參閱為作業 [Teams](/microsoft-365/education/deploy/configure-assignments-for-teams)。

## <a name="removing-assignments-and-grades"></a>移除作業和成績

您也可以使用Teams來移除特定使用者或整個租使用者的工作分派和成績。

若要移除個別使用者的作業和成績，請Teams系統管理中心，Teams許可權>**來** 建立新的應用程式許可權政策定義。  建立新策略定義時，請設定 **Microsoft 應用程式** 政策以封鎖 _特定應用程式_，並允許所有其他應用程式，並新增作業到封鎖的應用程式清單中。 儲存新策略定義後，請將其指派給適當的使用者。

若要移除整個租使用者的工作分派和成績，請前往 **Teams 系統** 管理中心、流覽至 Teams 應用程式 **>管理應用程式**，然後搜尋及選取應用程式清單中的作業。**** 將作業應用程式設定頁面中的狀態設定變更為 _已封鎖_。

## <a name="assignments-diagnostic-tool-for-users"></a>使用者作業診斷工具

Microsoft 支援服務已建立工具，為 Microsoft 工程小組收集診斷資料，以調查與作業功能相關的問題。

此工具可在使用者遇到問題的任何畫面的作業記憶體取。

若要在 Teams中啟動診斷工具，使用者可以：

- **在桌面和 Web 上：**
  - 選取 Ctrl+/
- **在行動裝置上：**
  - 使用兩指觸控螢幕，然後旋轉手指 45 度，或
  - 以三指點一下螢幕 15 秒

診斷工具出現後，使用者會看到 Microsoft 技術支援可能需要的資料清單。

提取的資料可能包括：

- 群組識別碼
- 租用戶識別碼
- 會話識別碼
- 作業識別碼
- 提交識別碼
- 使用者識別碼

此資料不會自動送往 Microsoft。 使用者需要複製資料並貼上至 Microsoft 支援代理程式，以使用支援票證。

如果使用者拉起診斷工具，然後關閉它，系統不會送出任何資料。

當資料送往 Microsoft 支援代理程式時，資料會依照貴組織的服務Microsoft 365處理。

有關使用此診斷工具與教師和學生共用的指示，請參閱取得診斷資料以疑 [難解答作業](https://support.microsoft.com/topic/b40793f5-dbae-4c8a-841a-6baa7f232e2e)。
