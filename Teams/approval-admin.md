---
title: 在團隊中核准應用程式可用性
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 瞭解 Microsoft 團隊中的 [核准應用程式可用性]。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4326408b7e27aa19af8e6c404d7275d26ba90969
ms.sourcegitcommit: d73d732591944b899a9366f79b4ea97f4a7f2260
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/15/2020
ms.locfileid: "49675171"
---
# <a name="teams-approvals-app-availability"></a>團隊核准應用程式可用性

[!INCLUDE [preview-feature](includes/preview-feature.md)]

[核准] 應用程式可作為個人 app 提供給所有 Microsoft 團隊使用者使用。
核准 app 提供一種簡單的方法，可將審核、合規性、責任及工作流程帶入小組中的結構化和非結構化核准。

 ![顯示核准應用程式](media/approvals-selection.png)

使用者可以釘選 [核准] 應用程式，將其儲存至功能表列。

 ![顯示具有 [pin] 選項的 [核准] 應用程式](media/approvalApp-pin.png)

從核准 app 建立的第一次核准將會觸發在預設的一般資料服務 (光碟) 環境中提供核准方案。 從核准 app 建立的核准將會儲存在預設的 CD 環境中。

本文將說明核准 app 需求與角色。

## <a name="required-permissions-and-licenses"></a>所需的許可權和授權

若要使用 [核准] 應用程式，您需要下列專案的許可權：

- 建立 Microsoft CD 資料庫的許可權。

- [Flow.microsoft.com](https://flow.microsoft.com/)上的帳戶

- 目標環境中的系統管理員角色。

- [ [電源自動化](https://docs.microsoft.com/power-automate/get-started-approvals)]、[Office 365] 或 [Dynamics 365] 的授權。

## <a name="storage-with-cds"></a>使用光碟儲存檔案

常見的資料模型 (CDM) 是在 CD 中的商務與分析應用程式所使用的共用資料語言。 它包含由 Microsoft 和合作夥伴所發佈的一組標準化、可擴展資料架構，可在應用程式和業務程式之間一致資料及其意義。 進一步瞭解 [Microsoft Power Platform 的一般資料模型](https://docs.microsoft.com/power-automate/get-started-approvals)。

深入瞭解 [核准工作流程](https://docs.microsoft.com/power-automate/modern-approvals)。

## <a name="approvals-teams-app-permissions"></a>核准小組 app 許可權

[核准團隊] 應用程式可讓您存取下列功能：

- 接收您提供給它的訊息和資料。

- 傳送訊息和通知給您。

- 在沒有團隊提供的標頭的情況下，轉譯個人 app 與對話方塊。

- 存取您的個人檔案資訊，例如您的名稱、電子郵件地址、公司名稱及喜好語言。

- 接收小組成員在頻道中提供給它的訊息和資料。

- 傳送頻道中的訊息和通知。

- 存取您團隊的資訊：
  - 團隊名稱
  - 頻道清單
  - [名單] (小組成員的名稱和電子郵件地址) 。

- 使用小組的資訊來與他們取得聯繫。

## <a name="disable-the-approvals-app"></a>停用核准應用程式

預設會提供 [核准] app。 您可以在 [團隊系統管理中心] 中停用應用程式。

  1. 登入團隊系統管理中心。

  2. 展開 [ **團隊 app** ]，然後選取 [ **管理應用程式**]。

  3. 搜尋 [核准] 應用程式。

![顯示 [系統管理中心導覽] 與 [團隊 App] > [管理應用程式] 醒目提示](media/manage-approval-apps.png)

  4. 選取 [核准]。

  5. 選取 [切換] 來針對您的組織停用應用程式。

![顯示核准 app 的詳細資料](media/approvals-details.png)

## <a name="retention-policy"></a>保留原則

從核准 App 建立的核准會儲存在預設的 CD 環境中，這項功能目前不支援備份。 深入瞭解如何 [備份及還原環境-Power Platform \| Microsoft 文檔](https://docs.microsoft.com/power-platform/admin/backup-restore-environments)。

## <a name="auditing"></a>表明

核准 App 會在 Microsoft 365 安全性與合規性中心內記錄審核事件。 您可以查看審核記錄。

1. 移至 M365 規範網站。

2. 選取 [ **審計** ] 區段。

3. 搜尋 **Microsoft 團隊核准活動** 下的活動。

您可以搜尋下列活動：

- 建立新的核准要求

- 查看核准要求詳細資料

- 核准核准要求

- 拒絕核准要求

- 已取消核准要求

- 共用核准要求

- 附加至核准要求的檔案

- 指派核准要求

- 已將電子簽名新增至核准要求

若要存取流程中的更多審核核准，請在主要核准實體核准、核准要求和核准回應的預設環境中啟用和設定審核。 [建立]、[更新] 和 [刪除] 作業是核准記錄的可審核事件。 深入瞭解有關 [安全性與合規性的審核資料和使用者活動-Power Platform \| Microsoft](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity)檔。

您可以在 [Microsoft 365 安全性與合規性中心](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)中進一步自訂審核。

1. 若要使用預先設定的報告，請登入 Office 365 安全性與合規性。

2. 選取 [ **搜尋 & 調查**]。

3. 搜尋 [審計記錄]，然後選取 [ **Dynamics 365 活動** ] 索引標籤。

深入瞭解 [Microsoft Dataverse 及模型驅動的 app 活動記錄-Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing)。

## <a name="security"></a>安全性

在團隊核准應用程式中，使用者有權建立新核准並查看他們已傳送和接收的核准。 使用者無法存取其他人所建立的核准，除非他們是要求的回應者或查看者。

> [!Note]
> 如果使用者是已建立核准的聊天或頻道的一部分，就會有該要求的查看者角色。 如果您在建立核准時沒有取得該角色，他們就不能在要求上採取動作。
