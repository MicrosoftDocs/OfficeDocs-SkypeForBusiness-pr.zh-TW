---
title: 在 Microsoft Teams 中管理核准應用程式
author: LanaChin
ms.author: v-lanachin
ms.reviewer: farhazk
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中管理貴組織的核准應用程式。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4812626477d2f77ddd3c6913577aa7792293a993
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046633"
---
# <a name="manage-the-approvals-app-in-microsoft-teams"></a>在 Microsoft Teams 中管理核准應用程式

核准應用程式可以個人應用程式形式供所有 Microsoft Teams 使用者使用。
核准應用程式提供一個簡單的方法，將稽核、合規性、責任和工作流程帶到 Teams 中的結構化和非結構化核准。

 ![顯示核准應用程式。](media/approvals-selection.png)

使用者可以釘選核准應用程式，以將其儲存到功能表列。

 ![顯示具有 PIN 選項的核准應用程式。](media/approvalApp-pin.png)

從核准應用程式建立的第一個核准會觸發在預設 Microsoft Dataverse 環境中布建核准解決方案。 從核准應用程式建立的核准會儲存在預設的 Microsoft Dataverse 環境中。

本文章說明核准應用程式的需求和角色。

> [!NOTE]
> 這項功能尚未發佈給政府社群雲端高 (GCCH) 和美國商務部 (DOD) 使用者。

## <a name="required-permissions-and-licenses"></a>必要的權限和授權

若要部署核准應用程式，您需要下列專案的許可權：

- 建立 Microsoft Dataverse 資料庫的許可權。

- [powerautomate.microsoft.com](https://powerautomate.microsoft.com/)上的帳戶

- 目標環境中的系統管理員角色。

- [Power Automate](/power-automate/get-started-approvals)、Office 365 或 Dynamics 365 的授權。

- 使用者必須具備Microsoft Forms授權，才能設定新的核准範本。

若要使用[核准] 應用程式，您需要 Power Automate 的授權，而且您的帳戶會在第一次核准指派時自動新增至目標環境中的核准使用者角色。

## <a name="storage-with-microsoft-dataverse"></a>Microsoft Dataverse 的儲存空間

一般資料模型 (CDM) 是 Microsoft Dataverse 中商務和分析應用程式所使用的共用資料語言。 它包含一組由 Microsoft 和我們的合作夥伴所發行的標準化、可延伸資料架構，可在應用程式和商務程式之間保持資料的一致性及其意義。 深入了解 [Microsoft Power Platform 的 Common Data Model](/power-automate/get-started-approvals)。

深入了解[核准工作流程](/power-automate/modern-approvals)。

從範本建立的核准仍會在 Microsoft Dataverse 中儲存資料，例如標題、詳細資料、範本識別碼等。 在核准要求上提交的回應會儲存在 Forms 中。 深入瞭解[Microsoft Forms 的資料儲存空間](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe)。

>[!Note]
>如果您刪除Microsoft Forms網站上的表單範本，該範本會中斷您的核准範本，且使用者無法啟動要求。 使用者在嘗試開啟已在 Microsoft Forms 上刪除的核准範本時，收到「CDB TableNotFound」錯誤。

組織範圍的範本與租使用者的整個生命週期相同，而團隊範圍的範本則共用團隊的相同生命週期。 因此，永久刪除團隊會刪除相關的範本。

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

核准範本許可權

- 所有團隊擁有者都可以為他們擁有的團隊建立核准範本。

- 當系統管理員第一次為整個組織建立範本時，系統會自動為租使用者的所有系統管理員建立新的 Azure Active Directory (AAD) 群組，包括全域和 Teams 服務系統管理員。 這些系統管理員會新增為群組的擁有者，讓他們可以共同管理組織範本。 建立團隊之後，組織新手的系統管理員必須手動新增為群組擁有者，這樣他們才擁有管理整個組織範本的相同許可權。

> [!Note]
> 如果系統管理員刪除該群組，您在 Azure Active Directory (AAD) 入口網站內有一個月的時間可以還原該群組，以還原所有相關資料。 一個月後，或如果系統管理員在回收站中刪除此群組，您將會遺失所有相關資料。

## <a name="disable-the-approvals-app"></a>停用核准應用程式

核准應用程式預設可供使用。 您可以在 Teams 系統管理中心停用該應用程式。

  1. 登入 Teams 系統管理中心。

  2. 前往 **[Teams 應用程式]** >  **[管理應用程式]**。

  3. 搜尋核准應用程式。

     ![顯示管理員中心導覽，其中醒目提示 [Teams 應用程式>管理應用程式]。](media/manage-approval-apps.png)

  4. 選 **取 [核准]**。

  5. 選取切換以為組織停用該應用程式。

     :::image type="content" alt-text="顯示核准應用程式的詳細資料。" source="media/approvals-details-new.png" lightbox="media/approvals-details-new.png":::

## <a name="pin-approvals-to-teams"></a>將核准釘選到 Teams

### <a name="use-the-tailored-frontline-app-experience-to-pin-approvals-and-other-apps-to-teams"></a>使用量身打造的第一線應用程式體驗，將核准和其他應用程式釘選到 Teams

Teams 中量身打造的第一線應用程式體驗可為擁有 [F 授權](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)的使用者釘選 Teams 中最相關的應用程式。 釘選的應用程式包括核准、無線對講機、工作和班次。 根據預設，此功能為您的第一線工作人員提供專為其需求量身打造的全新體驗。

應用程式會釘選到應用程式行，也就是 Teams 桌面用戶端側邊和 Teams 行動用戶端底部的列，使用者可以在此快速且輕鬆地存取它們。

若要深入瞭解，包括體驗如何與您所設定的應用程式原則搭配運作，請參閱 [為您的第一線員工量身打造 Teams 應用程式](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)。

### <a name="use-an-app-setup-policy-to-pin-approvals-to-teams"></a>使用應用程式設定原則將核准釘選到 Teams

應用程式設定原則可讓您自訂 Teams，以釘選對使用者中使用者最重要的應用程式。

若要為使用者釘選核准應用程式，您可以編輯全域 (組織的預設) 原則，或建立及指派自訂應用程式設定原則。 若要深入了解，請參閱[管理 Teams 中的應用程式設定原則](teams-app-setup-policies.md)。

## <a name="retention-policy"></a>保留原則

從核准應用程式建立的核准會儲存在預設的 Microsoft Dataverse 環境中，目前不支援備份。 深入了解如何[備份和還原環境 - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments)。

在團隊擁有者從 Microsoft Forms Web App 的 [**已刪除** 的表單] 索引標籤中清除資料之前，不會刪除儲存在 Forms 中的資料。

## <a name="conditional-access-policies"></a>條件式存取原則

目前，Teams 中的核准應用程式不支援針對 Microsoft Teams 設定的條件式存取原則。

## <a name="data-limitations"></a>資料限制

每個小組最多可以包含 400 個核准範本，而每個範本可以根據 Microsoft Forms 中目前的功能，收集最多 50，000 個要求。

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

- 已檢視電子簽名要求詳細資料

- 已檢閱電子簽名要求

- 已取消電子簽名要求

- 建立新範本

- 編輯現有的範本

- 啟用/停用範本

- 已檢視的範本

若要在 Power Automate 中存取更多稽核核准，請啟用並設定主要核准實體核准、核准要求和核准回應的預設環境中的稽核。 建立、更新和刪除作業是核准記錄的可稽核事件。 深入了解[安全性與合規性的稽核資料和使用者活動 - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity)。

您可以在 [Microsoft 365 安全性與合規性中心](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)進一步自訂稽核。

1. 若要使用預先設定的報告，請登入 Microsoft 365 安全性與合規性。

2. 選取 [搜尋與調查 **]**。

3. 搜尋稽核記錄，並選取 [Dynamics 365 活動 **]** 索引標籤。

深入了解 [Microsoft Dataverse 和模型導向的應用程式活動記錄 - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing)。

## <a name="security"></a>安全性

使用者可以從 Teams 核准應用程式建立新的核准，並檢視他們已傳送和接收的核准。 使用者無法存取其他人所建立的核准，除非他們是回應者或要求的檢視者。

> [!Note]
> 如果使用者是建立核准的聊天或頻道的一部分，就會被指派一個檢視者角色。 如果在建立核准時未提供他們該角色，他們即無法對要求採取動作。

## <a name="approvals-e-signature-integration"></a>核准電子簽名整合

若要使用「核准」App 電子簽名功能，您需要特定電子簽名提供者的授權才能使用。 若要為貴組織取得授權，您必須移至提供者的網站。

### <a name="enable-or-disable-e-signature-providers"></a>啟用或停用電子簽名提供者

您可以使用 Teams 系統管理中心來控制哪些協力廠商電子簽名提供者可在 [核准] 應用程式中提供給您的使用者。 根據預設，電子簽章提供者會在 [核准] 應用程式中啟用。 當您停用電子簽名提供者時，您的使用者在建立核准時將無法存取該提供者。 您的使用者也無法檢視使用該提供者建立的電子簽名要求。

1. 在 Teams 系統管理中心的左窗格中，移至 **Teams 應用程式**  >  **管理應用程式**。
2. 搜尋核准應用程式，然後選取它。
3. 移至 [ **設定] 索引** 標籤，然後執行下列一或多個動作：

    - 若要啟用或停用 Adobe Sign，請將開關切換為 [ **開** 啟] 或 **[關閉]**。
    - 若要啟用或停用 DocuSign，請將開關切換為 [ **開** 啟] 或 **[關閉]**。
4. 選取 **[提交]**。

從核准應用程式建立的電子簽章核准會儲存在選取的提供者的雲端環境中。 若要匯出電子簽章的相關資料，您必須移至提供者的網站。 如需儲存、匯出及保留電子簽章合約的詳細資訊，請參閱提供者的檔。
