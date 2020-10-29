---
title: 針對虛擬走訪的小組
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 使用 Microsoft 團隊設定您的虛擬走訪系統
ms.openlocfilehash: ed952f678fb353ae623a0020ac565ee4e8288445
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790455"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a>與團隊整合的虛擬走訪融入 EHR

Microsoft 團隊電子健康情況記錄 (EHR) 連接器可讓臨床醫師輕鬆地從 EHR 系統開始與其他團隊中的另一個提供者進行虛擬患者造訪或諮詢。 Microsoft 團隊是以 Microsoft 365 雲端為基礎，在單一中樞中使用聊天、影片、語音和醫療保健工具來實現簡單、安全的共同作業及通訊，這些功能可支援與 HIPAA、高科技認證等的相容性。

團隊的通訊與共同作業平臺可讓臨床醫師更容易地透過大量零散的系統來剪下，讓他們花時間提供最佳的功能。 Microsoft 團隊電子健康情況記錄 (EHR) 連接器可以：

- 啟動團隊從提供者和患者入口網站進行虛擬走訪。

- 在 connect 和中斷線上活動上寫回到 EHR 中繼資料，以啟用自動審核並保留記錄。

- 整合現有的 clinician 和患者工作流程，同時允許他們使用 Microsoft 團隊。

  觀看影片，瞭解如何從 EHR 入口網站管理虛擬走訪。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a>開始之前

您必須先確認您具備下列先決條件，才能整合 EHR 連接器：

- 適用于 Microsoft 雲端保健或訂閱 Microsoft 團隊 EHR 連接器獨立優惠的有效訂閱。

- 使用者必須具備適當的 Microsoft 365 或 Office 365 授權，包括 Microsoft 團隊會議。

- 您應該在組織內部採用並使用 Microsoft 團隊。

- 組織必須具有長篇故事版本2018年11月或更新版本。

- 您的系統必須符合所有 [軟體和瀏覽器的先決條件](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)。

您也需要來自貴組織中下列人員的資訊：

- Microsoft 365 系統管理員

- 長篇故事系統管理員

> [!Note]
> 要求長篇故事管理員提供長篇 marketplace 中提供的 Epic-Microsoft 團隊 Telehealth 整合指南。

## <a name="connector-setup"></a>連接器設定

連接器設定要求您：

- [啟動 EHR 連接器配置入口網站](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [設定提供者組織資訊](ehr-admin.md#configure-provider-organization-information)
- [驗證及核准設定](ehr-admin.md#verify-and-approve-the-configuration)
- [審查並完成設定](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[啟動 EHR 連接器配置入口網站](#launch-the-ehr-connector-configuration-portal)

您可以透過啟動 EHR 連接器設定入口網站，將您的保健組織設定為使用 Microsoft 團隊啟動虛擬走訪。 使用測試 URL 來設定長篇測試環境的連接器。 當您準備好要啟用長篇生產環境時，請使用生產 URL。
  
- 測試環境 [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)
- 生產環境 [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)

貴組織的 Microsoft 365 系統管理員和長篇電腦系統管理員必須完成配置入口網站中的資訊與整合步驟。 針對長篇配置步驟，請與分派給您組織的長篇資源。

### <a name="configure-provider-organization-information"></a>[設定提供者組織資訊](#configure-provider-organization-information)

此步驟將由 Microsoft 365 管理員完成。 Microsoft 365 管理員必須啟動連接器配置入口網站，並以 Microsoft 認證登入，才能開始設定程式。

若要完成此步驟，Microsoft 365 管理員必須從您的 Microsoft 365 系統管理員 () FHIR 基本 URL，以及將核准設定的長篇故事管理員的使用者名稱。 Microsoft 365 管理員必須啟動連接器設定頁面，並以 Microsoft 認證登入，以開始設定程式。

- FHIR 基底 URL 是與您的伺服器 FHIR API 端點相對應的靜態位址。 範例 URL 是 [https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST](https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST) 。

- [設定核准者名稱] 是將負責核准設定的長篇故事系統管理員名稱。

  ![設定核准者的名稱是從 EHR 連接器的清單中選取。](../../media/ehc-provider-1.png)

### <a name="verify-and-approve-the-configuration"></a>[驗證及核准設定](#verify-and-approve-the-configuration)

以核准者身分新增之醫療保健組織的長篇故事管理員必須立即使用相同的 EHR 連接器 URL，才能使用其 Microsoft 365 認證登入。 成功驗證之後，系統會要求核准者使用其長篇認證登入，以驗證長篇組織。

> [!Note]
> 貴組織中的 Microsoft 365 管理員和長篇故事系統管理員可以是相同的人員。 在這種情況下，請在第一個步驟中新增您自己的使用者名稱作為核准者。 您仍需登入長篇故事來驗證您的存取權。 長篇故事只能用來驗證您的 FHIR 基本 URL。 Microsoft 不會使用此登入來儲存認證或存取 EHR 資料。

  ![驗證及核准認證設定。](../../media/ehc-provider-2.png)

成功長篇故事登入時，長篇故事管理員 **必須** 核准設定。 如果設定不正確，Microsoft 365 系統管理員就能再次登入 Microsoft EHR 連接器入口網站來修改原始設定。

![確認已設定 EHR 連接器，並選擇變更配置。](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[審查並完成設定](#review-and-finish-the-configuration)

當長篇管理員核准配置資訊時，您會看到患者與提供者啟動的整合記錄。 需要這些記錄，才能在長篇故事中完成虛擬就診設定。 如需詳細資訊，請參閱 Epic-Microsoft 團隊 Telehealth 整合指南。

> [!Note]  
> 在任何時候，Microsoft 365 或長篇故事管理員都可以登入配置入口網站，以查看整合記錄及修改組織設定（如有需要）。

![隨即會顯示整合資訊。](../../media/ehc-final-config-4.png)

## <a name="launch-teams-virtual-visits"></a>啟動團隊虛擬走訪

完成 EHR 連接器步驟和長篇設定之後，您的組織就已準備好支援與 Microsoft 團隊進行的影片走訪。

### <a name="virtual-visit-prerequisites"></a>虛擬造訪先決條件

- 您的系統必須符合所有 [軟體和瀏覽器的先決條件](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)。

- 醫療保健組織必須已完成長篇組織與 Microsoft 365 組織之間的設定。

### <a name="provider-experience"></a>提供者體驗

貴組織的醫療保健提供者也可以將虛擬造訪從其長篇故事提供者的應用程式 (超空間、Haiku、Canto) 。 [ **開始虛擬造訪** ] 按鈕會內嵌在提供者流程中。

提供者體驗的主要功能：

- 提供者可以使用支援的瀏覽器或 Microsoft 團隊應用程式加入虛擬走訪。

- 當您第一次加入虛擬就診時，提供者必須進行一次登入其 Microsoft 365 帳戶。

- 一次登入後，提供者會直接取得 Microsoft 團隊中的虛擬約會。  (提供者必須登入 Microsoft 團隊) 。

- 提供者可以查看特定約會的參與者連線和中斷連線更新。 提供者可以查看患者連線至虛擬造訪的時間。

  ![使用患者的虛擬造訪提供者體驗](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a>患者體驗

連接器支援患者透過 MyChart 網頁和行動裝置加入虛擬走訪。 在約會時，患者可以使用「 **開始虛擬造訪** 」按鈕，從 MyChart 進行虛擬造訪。

患者體驗的主要功能：

- 患者可以在桌面和行動裝置上從新式網頁瀏覽器加入虛擬造訪，而不需安裝 app。

- 患者只要按一下就能加入虛擬走訪，且不需要其他帳戶或登入。

- 您不需要患者即可建立 Microsoft 帳戶或登入以啟動虛擬造訪。

- 患者將放在大廳，直到醫療保健提供者加入約會並允許給虛擬造訪為止。

- 您可以在加入虛擬造訪前，在大廳中測試影片和麥克風。

  ![[虛擬造訪] 的患者體驗](../../media/ehc-virtual-visit-5.png)

> [!Note]
> 長篇故事、MyChart、Haiku 和 Canto 是長篇系統公司的商標。

### <a name="privacy-and-location-of-data"></a>資料的隱私權和位置

整合在 EHR 系統中的團隊可優化整合和虛擬就診流程期間要使用及儲存的資料量。 本方案遵循團隊隱私權中的整體小組隱私權與資料管理原則及指導方針。

Microsoft 團隊 EHR 連接器不會在 EHR 系統中儲存或轉移任何可識別的個人資料，或患者或醫療保健提供者的任何健康記錄。 EHR 連接器所儲存的唯一資料是 EHR 使用者的唯一識別碼，可在小組會議設定期間使用。 EHR 使用者的唯一識別碼會儲存在 [Microsoft 365 客戶資料儲存在其中](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) 的三個地理區域之一。 會議參與者會根據現有的儲存原則來儲存所有聊天、錄製及其他透過會議參與者輸入至團隊的資料。 如果您想要深入瞭解 Microsoft 團隊中的資料位置，請造訪 [團隊中的資料](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)位置。
