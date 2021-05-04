---
title: Teams 中的核准應用程式可用性
author: cichur
ms.author: v-cichur
ms.reviewer: farhazk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 了解 Microsoft Teams 中的核准應用程式可用性。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c71f08840ffa9c41622d07376933c14a7ae6b493
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2021
ms.locfileid: "52129792"
---
# <a name="teams-approvals-app-availability"></a>Teams 核准應用程式可用性

核准應用程式可以個人應用程式形式供所有 Microsoft Teams 使用者使用。
核准應用程式提供一個簡單的方法，將稽核、合規性、責任和工作流程帶到 Teams 中的結構化和非結構化核准。

 ![顯示核准應用程式](media/approvals-selection.png)

使用者可以釘選核准應用程式，以將其儲存到功能表列。

 ![顯示具有釘選選項的核准應用程式](media/approvalApp-pin.png)

從核准應用程式建立的第一個核准，會觸發在預設 Common Data Service (CDS) 環境中提供核准解決方案。 從核准應用程式建立的核准將會儲存在預設的 CDS 環境中。

本文章說明核准應用程式的需求和角色。

> [!NOTE]
> 這項功能尚未發行至 政府社群雲端 (GCC) 、政府社群雲端高 (GCCH) ，以及美國 (DOD) 使用者。

## <a name="required-permissions-and-licenses"></a>必要的權限和授權

若要使用核准應用程式，您需要下列項目的權限：

- 建立 Microsoft CDS 資料庫的權限。

- 位於 [flow.microsoft.com](https://flow.microsoft.com/) 的帳戶

- 目標環境中的系統管理員角色。

- [Power Automate](/power-automate/get-started-approvals)、Office 365 或 Dynamics 365 的授權。

## <a name="storage-with-cds"></a>CDS 的儲存空間

Common Data Model (CDN) 是 CDS 中商務和分析應用程式所使用的共用資料語言。 它包含一組由 Microsoft 和我們的合作夥伴所發佈的標準化、可延伸資料架構，可跨應用程式和商務程序實現資料的一致性及其意義。 深入了解 [Microsoft Power Platform 的 Common Data Model](/power-automate/get-started-approvals)。

深入了解[核准工作流程](/power-automate/modern-approvals)。

## <a name="approvals-teams-app-permissions"></a>核准 Teams 應用程式權限

核准 Teams 應用程式可讓您存取下列功能：

- 接收您提供的訊息和資料。

- 傳送訊息和通知給您。

- 在沒有 Teams 提供的標頭的情況下，呈現個人應用程式和對話方塊。

- 存取您的設定檔資訊，例如您的姓名、電子郵件地址、公司名稱和偏好的語言。

- 接收小組成員在頻道中提供的訊息和資料。

- 在頻道中傳送訊息和通知。

- 存取小組的資訊：
  - 小組名稱
  - 頻道清單
  - 名冊 (小組成員的名稱和電子郵件地址)。

- 使用小組的資訊來連絡他們。

## <a name="disable-the-approvals-app"></a>停用核准應用程式

核准應用程式預設可供使用。 您可以在 Teams 系統管理中心停用該應用程式。

  1. 登入 Teams 系統管理中心。

  2. 展開 [Teams 應用程式 **]**，然後選取 [管理應用程式 **]**。

  3. 搜尋核准應用程式。

     ![顯示系統管理中心瀏覽，並強調顯示 [Teams 應用程式] > [管理應用程式]](media/manage-approval-apps.png)

  4. 選取 [核准]。

  5. 選取切換以為組織停用該應用程式。

     ![顯示核准應用程式的詳細資料](media/approvals-details.png)

## <a name="retention-policy"></a>保留原則

從核准應用程式建立的核准會儲存在預設 CDS 環境中，該選項目前不支援備份。 深入了解如何[備份和還原環境 - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments)。

## <a name="auditing"></a>稽核

核准應用程式會記錄 Microsoft 365 安全性與合規性中心內的稽核事件。 您可以檢視稽核記錄。

1. 移至 Microsoft 365 合規性網站。

2. 選取 [稽核 **]** 區段。

3. 在 [Microsoft Teams 核准活動 **]** 下搜尋活動。

您可以搜尋下列活動：

- 建立新核准要求

- 檢視核准要求詳細資料

- 核准的核准要求

- 拒絕的核准要求

- 取消的核准要求

- 共用的核准要求

- 已附加到核准要求的檔案

- 重新指派的核准要求

- 已新增至核准要求的電子簽章

- 已查看電子簽章要求詳細資料

- 已審查電子簽章要求

- 已取消電子簽名要求

若要存取流程內的更多稽核核准，請針對主要核准實體「核准」、「核准要求」和「核准回應」，在預設環境中啟用和設定稽核。 建立、更新和刪除作業是核准記錄的可稽核事件。 深入了解[安全性與合規性的稽核資料和使用者活動 - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity)。

您可以在 [Microsoft 365 安全性與合規性中心](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)進一步自訂稽核。

1. 若要使用預先設定的報告，請登入 Microsoft 365 安全性與合規性。

2. 選取 [搜尋與調查 **]**。

3. 搜尋稽核記錄，並選取 [Dynamics 365 活動 **]** 索引標籤。

深入了解 [Microsoft Dataverse 和模型導向的應用程式活動記錄 - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing)。

## <a name="security"></a>安全性

使用者可以從 Teams 核准應用程式建立新的核准，並檢視他們已傳送和接收的核准。 使用者無法存取其他人所建立的核准，除非他們是回應者或要求的檢視者。

> [!Note]
> 如果使用者是建立核准所在的聊天或頻道的一部分，就會獲授與要求的檢視者角色。 如果在建立核准時未提供他們該角色，他們即無法對要求採取動作。

## <a name="approvals-e-signature-integration"></a>核准電子簽章整合

從核准應用程式建立的電子郵件簽章核准會儲存在所選提供者的雲端環境中。 有關電子簽章協定的儲存空間詳細資訊，請觀看所選提供者的儲存檔。

若要使用核准應用程式電子簽章功能，您需要下列專案：

- 您選擇使用的特定電子簽章提供者授權。 若要取得貴組織的授權，您必須前往提供者的網站。

針對核准電子簽章功能，協力廠商簽章合作夥伴預設會顯示Teams核准應用程式。 您可以在系統管理中心存取應用程式設定，以停用Teams簽名提供者。

1. 在 Teams系統管理中心 **，選取管理** 應用程式下的核准 **應用程式**，然後選擇 **設定。**

2. 每個電子簽章提供者旁邊都有一個開關，根據預設， (右) 位置。 將切換開關向左滑動以停用特定的電子簽名提供者。 如果Teams系統管理員停用提供者，則建立核准時，使用者不會看到提供者。 使用者也無法查看該提供者提出的任何電子簽章要求。

從核准應用程式建立之電子簽章核准會儲存在所選提供者的雲端。 因此，您必須前往提供者的網站，才能匯出任何電子簽章資料。 請參閱提供者關於匯出及保留這些協定的檔。
