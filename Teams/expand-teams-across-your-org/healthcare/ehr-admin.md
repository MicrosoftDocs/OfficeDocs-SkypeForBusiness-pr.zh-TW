---
title: 使用虛擬Teams - 整合至Epic EHR
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ansantam
description: 瞭解如何整合 EHR Teams，讓貴組織的醫療保健提供者直接從Epic EHR 系統與病患或其他提供者進行虛擬Teams。
ms.openlocfilehash: 47dde0f4314a5506ddede7543f1a294523e84598
ms.sourcegitcommit: 5ca04ee10e3f254e1b24506de116591fdfd51d18
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2022
ms.locfileid: "62929148"
---
# <a name="virtual-visits-with-teams---integration-into-epic-ehr"></a>使用虛擬Teams - 整合至Epic EHR

Microsoft Teams電子健康記錄 (EHR) 連接器，讓診所醫師可以直接從Epic EHR 系統，在 Microsoft Teams 中啟動虛擬病患拜訪或諮詢。 在雲端Microsoft 365上，Teams可在支援 HIPAA、HITECH 認證等合規性的單一中樞中，使用聊天、視視、語音和醫療保健工具進行簡單、安全的共同合作與通訊。

診所通訊和共同Teams平臺，讓診所醫師能輕鬆從零散的系統中剪下雜亂無章的雜物，讓他們能專注于提供最佳的照護。 使用 Teams EHR 連接器，您可以：

- 使用整合Teams，從Epic EHR 系統啟動虛擬訪問。
- 讓病患從病患入口Teams或透過簡訊加入虛擬訪問。
- 支援其他案例，包括多重參與者、群組訪問和翻譯服務。
- 將中繼資料寫回 EHR 系統，Teams出席者連接、中斷連接，以及啟用自動稽核和記錄保留時，錄製虛擬訪問。
- 查看消費資料包告和可自訂的 EHR 相關訪問通話品質資訊。

請觀看這段影片，以概觀瞭解如何從 EHR 入口網站管理虛擬流覽。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

本文將說明如何設定及設定 EHR 連接器Teams整合至您醫療保健組織的Epic平臺。 它也提供您從Epic EHR 系統Teams虛擬流覽體驗概觀。

## <a name="before-you-begin"></a>開始之前

在您開始使用之前，有一些操作可以準備整合。

### <a name="get-familiar-with-the-integration-process"></a>熟悉整合程式

請閱閱下列資訊，瞭解整體整合程式。

:::image type="content" source="media/ehr-connector-epic-flow.png" alt-text="摘要整體整合程式步驟的影像。":::

||||||
|---------|---------|---------|---------|---------|
|**動作**：[您要求存取Teams應用程式](#request-access-to-the-teams-app)。 <br> **結果**：我們授權貴組織進行測試。|**動作**：我們建立公用和私密金鑰憑證，並上傳至Epic。 <br> **結果**：將公用金鑰憑證同步。|**動作**：在 EHR 連接器組式入口網站中完成組組步驟。 <br> **結果**：您會收到一般配置的 FDI 記錄。| **動作**：您與Epic 技術人員合作，在Epic中設定 FDI 記錄。<br> **結果**：完成組組。 準備好測試。|**動作**：在測試環境中完成測試。<br> **結果**：流程的完整驗證，以及移至生產階段的決策。|

### <a name="request-access-to-the-teams-app"></a>要求存取 Teams 應用程式

您必須要求存取應用程式Teams應用程式。

1. 要求在Epic App Teams [App Marketplace](https://apporchard.epic.com/Gallery?id=6153)中下載應用程式。 這麼做會觸發從Epic到 Microsoft EHR 連接器小組的要求。
1. 提出要求之後，請傳送一封電子郵件 TeamsForHealthcare@service.microsoft.com 貴[](mailto:teamsforhealthcare@service.microsoft.com)組織名稱、租使用者識別碼，以及Epic 技術連絡人的電子郵件地址。
1. Microsoft EHR 連接器小組會回復您的電子郵件，並確認啟用。

### <a name="review-the-epic-microsoft-teams-telehealth-integration-guide"></a>請閱Epic-Microsoft Teams遠端醫療整合指南

請與您的 Epic 技術專家檢視 [Epic-Microsoft Teams 遠距健康整合指南](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)。 確定符合所有先決條件。

## <a name="prerequisites"></a>必要條件

- 只有在生產 EHR 醫療保健版 Microsoft Cloud環境中測試時，才能Microsoft Teams EHR 連接器獨立版訂閱或訂閱 (才能強制執行) 。
- 2018 年 11 月或更新版本。
- 使用者擁有適當的Microsoft 365或Office 365授權，Teams會議。
- Teams採用並用於您的醫療保健組織。
- 您的系統符合[所有軟體與瀏覽器Teams](../../hardware-requirements-for-the-teams-app.md)。

> [!IMPORTANT]
> 在繼續整合之前，請務必完成整合前的步驟，並符合所有先決條件。

整合步驟由貴組織的下列人員執行：

- **Microsoft 365全域系統管理員**：負責整合的主要人員。 系統管理員會設定連接器， (啟用簡訊) ，並新增將核准該配置的一般客戶分析師。
- **高震客戶分析師**：貴組織中擁有Epic登入認證的人。 他們核准系統管理員輸入的設定設定，並提供設定記錄至Epic。

系統管理員Microsoft 365和Epic客戶分析師可以是同一個人。

## <a name="set-up-the-teams-ehr-connector"></a>設定 EHR Teams連接器

連接器設定需要您：

- [啟動 EHR 連接器組式入口網站](#launch-the-ehr-connector-configuration-portal)
- [輸入組組資訊](#enter-configuration-information)
- [啟用簡訊通知 (選) ](#enable-sms-notifications-optional)
- [核准或查看組組](#approve-or-view-the-configuration)
- [檢閱並完成組態](#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>啟動 EHR 連接器組式入口網站

若要開始使用，您的系統管理員Microsoft 365 [EHR 連接器](https://ehrconnector.teams.microsoft.com)組組入口網站，然後使用他們的認證Microsoft 365登錄。

您的Microsoft 365系統管理員可以設定單一組織或多個組織來測試整合。 在組態入口網站中設定測試與生產 URL。 在移往生產之前，請務必先從Epic測試環境測試整合。

> [!NOTE]
> 您的Microsoft 365系統管理員和Epic 客戶分析師必須完成組組入口網站中的整合步驟。 如需Epic組組步驟，請聯絡指派給貴組織的Epic技術人員。

### <a name="enter-configuration-information"></a>輸入組組資訊

接下來，若要設定整合，您的Microsoft 365系統管理員會執行下列操作：

1. 在 FHIR 中新增快速健康 (資源) Epic 技術人員提供的基本 URL，並指定環境。 視貴組織的需求和您想要測試的環境，視需要設定盡可能多的 FHIR 基本 URL。

    - FHIR 基本 URL 是對應到伺服器 FHIR API 端點的靜態位址。 範例 URL 是 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`。

    - 您可以設定測試與生產環境的整合。 針對初始設定，我們建議您先從測試環境設定連接器，再移往生產。

1. 新增將在稍後的步驟中核准該配置的Epic客戶分析師的使用者名稱。

    :::image type="content" source="media/ehr-connector-epic-configure.png" alt-text="顯示新增核准者之組組頁面的螢幕擷取畫面。" lightbox="media/ehr-connector-epic-configure.png":::

### <a name="enable-sms-notifications-optional"></a>啟用簡訊通知 (選) 

> [!NOTE]
> 簡訊通知目前僅適用于美國。 我們正努力在未來版本的其他區域提供這項功能Teams並更新本文 。

如果您的組織想要 Microsoft 管理病患的簡訊通知，請完成此步驟。 當您啟用簡訊通知時，您的病患會收到預定的拜訪的確認和提醒訊息。

若要啟用簡訊通知，您的Microsoft 365系統管理員會執行下列操作：

1. 在簡訊通知頁面上，選取兩個同意核取方塊以：

    - 允許 Microsoft 代表貴組織傳送簡訊通知給病患。
    - 確認您將確保出席者已同意傳送及接收簡訊。
    
    :::image type="content" source="media/ehr-connector-epic-sms-notifications.png" alt-text="簡訊通知頁面的螢幕擷取畫面，顯示同意核取方塊，以及產生電話號碼的選項。" lightbox="media/ehr-connector-epic-sms-notifications.png":::

1. 在 **電話號碼下**， **選取產生新電話號碼** ，為貴組織產生電話號碼。 這麼做會啟動要求並產生新電話號碼的過程。 此程式最多可能需要 2 分鐘才能完成。

    產生電話號碼之後，電話號碼會顯示在螢幕上。 這個號碼會用來傳送簡訊確認和提醒給病患。 號碼已撥備，但尚未連結至 FHIR 基本 URL。 您可以在下一個步驟中執行這項操作。

    :::image type="content" source="media/ehr-connector-epic-phone-number.png" alt-text="顯示產生的電話號碼範例的螢幕擷取畫面。" lightbox="media/ehr-connector-epic-phone-number.png":::

    選擇 **完成**，然後選取下 **一步**。

1. 若要將電話號碼連結至 FHIR 基本 URL，請在 **電話的號碼** 下，選取該號碼。**** 針對要啟用簡訊通知的每個 FHIR 基本 URL 執行此操作。

    :::image type="content" source="media/ehr-connector-epic-link-phone-number.png" alt-text="顯示如何將電話號碼連結至 FHIR 基本 URL 的螢幕擷取畫面。" lightbox="media/ehr-connector-epic-link-phone-number.png":::

    如果這是您第一次配置連接器，會看到先前步驟中輸入的 FHIR 基本 URL。 相同的電話號碼可以連結至多個 FHIR 基本 URL，這表示病患會收到來自不同組織和/或部門之相同電話號碼的簡訊通知。

1. 選取 **每個 FHIR** 基本 URL 旁的簡訊設定，設定要傳送給病患的簡訊通知類型。

    :::image type="content" source="media/ehr-connector-epic-sms-setup.png" alt-text="顯示簡訊設定設定之螢幕擷取畫面。" lightbox="media/ehr-connector-epic-sms-setup.png":::

    - **確認簡** 訊：在 EHR 系統中排程、更新或取消流覽時，通知會寄給病患。
    - **提醒簡** 訊：通知會依據您指定的時間間隔和預定的流覽時間，發送給病患。

    選擇 **儲存**。

1. 選取 **Upload以** 上傳公用金鑰憑證。 您必須針對每個環境只 (.cer) Base64 編碼的金鑰。

    若要接收傳送簡訊通知的約會資訊，需要公用金鑰憑證。 需要憑證才能確認傳入的資訊來自有效的來源。

    當連接器用來傳送簡訊提醒時，當約會以Epic建立時，病患的電話號碼會以 HL7v2 有效負載由Epic傳送。 這些數位會儲存于貴組織的地理位置中，並保留到約會進行之前。 若要深入瞭解如何設定 HL7v2 訊息，請參閱[Epic-Microsoft Teams整合指南](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)。

    選擇 **下一步**。

> [!NOTE]
> 您的系統管理員隨時Microsoft 365任何簡訊設定。 請記住，變更設定可能會導致簡訊服務停止。 若要瞭解如何查看簡訊報告，請參閱[Teams連接器系統管理員報告](ehr-admin-reports.md)。

### <a name="approve-or-view-the-configuration"></a>核准或查看組組

您組織中新增為核准者的客戶分析師會啟動[EHR](https://ehrconnector.teams.microsoft.com)連接器組組入口網站，然後使用他們的認證Microsoft 365登錄。 驗證成功後，核准者會要求使用其Epic認證來驗證Epic組織。

> [!Note]
> 如果Microsoft 365系統管理員和Epic客戶分析師是同一個人，您仍然需要登錄Epic來驗證您的存取權。 長篇大語的登錄僅用於驗證您的 FHIR 基本 URL。 Microsoft 不會使用此登錄來儲存認證或存取 EHR 資料。

:::image type="content" source="media/ehr-connector-epic-login-approve.png" alt-text="顯示登入和核准選項的核准或查看組組頁面的螢幕擷取畫面。" lightbox="media/ehr-connector-epic-login-approve.png":::

成功登錄Epic之後，Epic 客戶分析師 **必須** 核准該組配置。 如果設定不正確，您的系統管理員Microsoft 365登錄設定入口網站並變更設定。

:::image type="content" source="media/ehr-connector-epic-approve.png" alt-text="顯示核准選項的核准或查看組組頁面的螢幕擷取畫面。" lightbox="media/ehr-connector-epic-approve.png":::

### <a name="review-and-finish-the-configuration"></a>檢閱並完成組態

當 Epic 系統管理員核准組態資訊時，將會顯示病患和提供者啟動的整合記錄。 整合記錄包括：

- 病患和提供者記錄
- 直接簡訊記錄
- 簡訊組組記錄
- 裝置測試組組記錄

Epic 客戶分析師必須提供這些記錄給Epic，以完成在Epic中的虛擬訪問組。 詳細資訊請參閱[Epic-Microsoft Teams整合指南](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)。

> [!Note]  
> 客戶或Microsoft 365人員隨時都可以登錄組組入口網站，以視需要查看整合記錄並變更組織組配置。

:::image type="content" source="media/ehr-connector-epic-finish.png" alt-text="顯示整合資訊的檢查和完成頁面的螢幕擷取畫面。" lightbox="media/ehr-connector-epic-finish.png":::

> [!Note]
> 客戶分析師必須完成由系統管理員所建立之每個 FHIR 基本 URL 的核准程式Microsoft 365程式。

## <a name="launch-teams-virtual-visits"></a>啟動Teams虛擬訪問

完成 EHR 連接器步驟和長篇大說之後，貴組織就可以使用 Teams 支援視Teams。

### <a name="virtual-visits-prerequisites"></a>虛擬訪問的先決條件

- 您的系統必須符合[所有軟體與瀏覽器需求，](../../hardware-requirements-for-the-teams-app.md)Teams。

- 您已完成了Epic 組織與貴組織之間的整合Microsoft 365設定。

### <a name="provider-experience"></a>提供者體驗

貴組織的醫療保健提供者可以使用來自超Teams、海庫 (Canto) 的 App 加入) 。 **[開始虛擬就診]** 按鈕內嵌在提供者流程中。

提供者體驗的主要功能：

- 提供者可以使用支援的瀏覽器或應用程式加入Teams。

- 提供者第一次加入流覽時，必須使用Microsoft 365帳戶進行一次登錄。

- 一次登錄之後，提供者會直接進入 Teams。  (提供者必須登錄至Teams) 。

- 提供者可以看到參與者對指定約會進行連接和中斷連接即時更新。 提供者可以看到病患何時與看診連接。

  ![與病患一起流覽的提供者體驗。](media/ehc-provider-experience-6.png)

> [!NOTE]
> 醫療保健提供者應下載、複製及記錄醫療記錄持續性或保留用途所需的會議聊天中輸入的資訊。 聊天不構成合法的醫療記錄或指定的記錄集。 來自聊天的郵件會根據系統管理員所建立Microsoft Teams儲存。

### <a name="patient-experience"></a>病患體驗

連接器支援透過 MyChart Web 和 Mobile 加入看診的病患。 預約時，病患可以使用開始虛擬瀏覽按鈕從 MyChart **開始** 流覽。

病患體驗的主要功能：

- 病患可以在桌面和行動版上加入新式網頁瀏覽器的流覽，[而不需要](../mobile-browser-join.md)安裝 Teams App。

- 病患只需按一下即可加入看診，而不需要其他帳戶或登錄。

- 病患不需要建立 Microsoft 帳戶或登錄以啟動流覽。

- 病患會放在大廳，直到提供者加入並准許他們。

- 病患可以在加入拜訪前，先在大廳測試視像和麥克風。

  ![病患的流覽體驗。](media/ehc-virtual-visit-5.png)

> [!Note]
> Epic、MyChart、Haiku 和 Canto 是 Epic Systems Corporation 的商標。

### <a name="privacy-and-location-of-data"></a>資料隱私權和位置

Teams整合至 EHR 系統，可優化整合和虛擬訪問流程期間使用及儲存的資料量。 解決方案遵循 Teams 隱私權中概述的整體 Teams 隱私權和資料管理原則和指導方針。

EHR Teams連接器不會從 EHR 系統儲存或傳輸任何可識別的個人資料，或病患或醫療保健提供者的任何健康記錄。 EHR 連接器儲存的唯一資料是 EHR 使用者的唯一識別碼，在 Teams 會議設定期間使用。

EHR 使用者的唯一識別碼儲存在 [Microsoft 365 客戶資料儲存位置](/microsoft-365/enterprise/o365-data-locations)的三個地理區域其中之一。 會議參與者共用的所有聊天、錄製Teams共用的其他資料，都是根據現有的儲存策略儲存。 若要深入瞭解資料在 Teams 中的位置，請參閱[資料在](../../location-of-data-in-teams.md)Teams。

## <a name="related-articles"></a>相關文章

- [Teams虛擬訪問使用方式報告](../../teams-analytics-and-reports/virtual-visits-usage-report.md)
- [Teams EHR 連接器系統管理員報告](ehr-admin-reports.md)
- [開始使用醫療保健組織Teams服務](teams-in-hc.md)
