---
title: 使用 Teams 的虛擬約會 - 整合至 Cerner EHR
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
description: 瞭解如何整合 Teams EHR 連接器，讓貴組織中的醫療保健提供者直接從 Cerner EHR 系統與 Teams 中的病患或其他提供者進行虛擬約會。
ms.openlocfilehash: 990d1816d33fde527195faf81ff6153b6aa9ab8f
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494820"
---
# <a name="virtual-appointments-with-teams---integration-into-cerner-ehr"></a>使用 Teams 的虛擬約會 - 整合至 Cerner EHR

Microsoft Teams 電子健康情況記錄 (EHR) 連接器可讓醫護人員輕鬆啟動虛擬病患預約，或直接從 Cerner EHR 系統洽詢 Microsoft Teams 中的另一個提供者。 Teams 建置於 Microsoft 365 雲端，可在單一中樞中使用聊天、視訊、語音和醫療保健工具進行簡單、安全的共同作業和通訊，支援符合 HIPAA、HITECH 認證等功能。

Teams 的通訊與共同作業平臺可讓求病者輕鬆地修閱雜亂的系統，讓他們能夠專注在提供最佳的保養上。 使用 Teams EHR 連接器，您可以：

- 使用整合式的醫療工作流程，從您的 Cerner EHR 系統進行 Teams 虛擬約會。
- 讓病患從電子郵件或簡訊通知加入 Teams 虛擬約會。
- 檢視已連線 EHR 之約會的消費資料包告和可自訂的通話品質資訊。

本文說明如何設定和設定 Teams EHR 連接器，以與 Cerner 平臺整合。 它也提供您來自 Cerner EHR 系統的 Teams 虛擬約會體驗概觀。

## <a name="before-you-begin"></a>開始之前

> [!NOTE]
> 啟用整合之前，請務必先洽詢您的 Cerner 代表，並檢閱您的 Cerner 整合指南。

### <a name="prerequisites"></a>必要條件

在您將 Teams EHR 連接器整合到您的醫療保健組織之前，您必須具備下列專案：

- 有效的Microsoft Cloud for Healthcare訂閱或 Microsoft Teams EHR 連接器獨立方案的訂閱。
- 使用者有適當的 Microsoft 365 或Office 365授權，其中包含 Teams 會議。
- Teams 已在您的醫療保健組織中採用和使用。
- 您的系統符合 Teams 的所有 [軟體和瀏覽器需求](../../hardware-requirements-for-the-teams-app.md) 。
- Cerner 版本 2018 年 11 月或更新版本

## <a name="set-up-the-teams-ehr-connector"></a>設定 Teams EHR 連接器

連接器設定需要您：

- [啟動 EHR 連接器設定入口網站](#launch-the-ehr-connector-configuration-portal)
- [輸入設定資訊](#enter-configuration-information)
- [啟用 SMS 通知 (選用) ](#enable-sms-notifications-optional)
- [檢閱並完成組態](ehr-admin-cerner.md#review-and-finish-the-configuration)

> [!IMPORTANT]
> 您組織中的 Microsoft 365 全域系統管理員必須完成這些步驟。  

### <a name="launch-the-ehr-connector-configuration-portal"></a>啟動 EHR 連接器設定入口網站

若要開始使用，您的 Microsoft 365 系統管理員會啟動 [EHR 連接器設定入口網站](https://ehrconnector.teams.microsoft.com) ，並使用他們的 Microsoft 認證登入。

您的 Microsoft 365 系統管理員可以設定單一部門或多個部門來測試整合。 在組態入口網站中設定測試與生產 URL。 移至生產之前，請務必從 Cerner 測試環境測試整合。

### <a name="enter-configuration-information"></a>輸入設定資訊

接下來，為了設定整合，您的 Microsoft 365 系統管理員新增了來自 Cerner 的「快速健康情況互通性資源」 (FHIR) 基礎 URL，並指定環境。 視貴組織的需求和您想要測試的環境而定，視需要設定任意數量的 FHIR 基礎 URL。

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="Teams EHR 連接器設定入口網站 [設定資訊] 頁面的螢幕擷取畫面。" lightbox="media/ehr-admin-cerner-configuration.png":::

- FHIR 基底 URL 是一個靜態位址，對應到您的伺服器 FHIR API 端點。 範例 URL 是 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`。

- 您可以設定測試與生產環境的整合。 對於初始設定，我們鼓勵您在進入生產之前，先從測試環境設定連接器。

驗證 FHIR 基底 URL 並選取環境之後，選擇 [ **完成]**。 然後視需要為其他環境新增更多 FHIR 基礎 URL。

選取 **[下一步** ] 以移至下一個步驟。

### <a name="enable-sms-notifications-optional"></a>啟用 SMS 通知 (選用) 

如果您的組織想要 Microsoft 管理您病患的簡訊通知，請完成此步驟。 當您啟用簡訊通知時，病患將會收到排程預約的確認和提醒訊息。

若要啟用簡訊通知，您的 Microsoft 365 系統管理員會執行下列動作：

1. 在 [簡訊通知] 頁面上，選取這兩個同意核取方塊：

    - 允許 Microsoft 代表貴組織傳送簡訊通知給病患。
    - 確認您將確保出席者已同意傳送和接收簡訊。

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="[簡訊通知] 頁面的螢幕擷取畫面，顯示 [同意] 核取方塊以及產生電話號碼的選項。" lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. 在 **[您的電話號碼**] 底下，選 **取 [產生新的電話號碼** ] 以產生組織的電話號碼。 這樣做會啟動要求並產生新電話號碼的程式。 此程式最多可能需要 2 分鐘才能完成。

    產生電話號碼之後，電話號碼會顯示在螢幕上。 此號碼將用來傳送簡訊確認和提醒給您的病患。 該編號已布建，但尚未連結到 FHIR 基礎 URL。 您會在下一個步驟中這麼做。

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="螢幕擷取畫面顯示所產生的電話號碼範例。" lightbox="media/ehr-admin-cerner-phone-number.png":::

    選擇 **[完成**]，然後選取 [ **下一步]**。

1. 若要將電話號碼連結到 FHIR 基底 URL，請在 [**SMS 設定**] 區段中的 **[電話號碼**] 底下，選取該號碼。 針對您要啟用 SMS 通知的每個 FHIR 基礎 URL 執行此動作。

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="螢幕擷取畫面顯示如何將電話號碼連結至 FHIR 基底 URL。" lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    如果這是您第一次設定連接器，您會看到先前步驟輸入的 FHIR 基底 URL。 相同的電話號碼可以連結至多個 FHIR 基 URL，這表示病患會收到來自不同組織和/或部門相同電話號碼的簡訊通知。

     選取 **[下一步]**。

### <a name="review-and-finish-the-configuration"></a>檢閱並完成組態

系統會為您提供病患和提供者啟動的整合記錄。 您必須有這些記錄才能在 Cerner 中完成虛擬約會設定。 如需詳細資訊，請參閱Cerner-Microsoft Teams Telehealth 整合指南。

> [!NOTE]
> 您的 Microsoft 365 系統管理員隨時可以登入組態入口網站，以視需要檢視整合記錄及變更組態設定。

## <a name="launch-teams-virtual-appointments"></a>啟動 Teams 虛擬約會

完成 EHR 連接器步驟和 Cerner 設定步驟之後，您的組織就可以使用 Teams 支援視訊約會。

### <a name="virtual-appointments-prerequisites"></a>虛擬約會先決條件

- 您的系統必須符合 Teams 的所有 [軟體和瀏覽器需求](../../hardware-requirements-for-the-teams-app.md) 。
- 您已完成 Cerner 組織與您的 Microsoft 365 組織之間的整合設定。

### <a name="provider-experience"></a>提供者體驗

貴組織中的醫療保健提供者可以從 PowerChart 入口網站使用 Teams 加入約會。 提供者必須流覽至可使用 Teams 選項的病患面板。

提供者可以從該處檢視約會資訊、加入約會，以及傳送會議連結。 一次性登入之後，提供者會直接前往 Teams 中的虛擬約會。

提供者體驗的主要功能：

- 提供者可以使用支援的瀏覽器或 Teams 應用程式加入約會。
- 提供者可以使用所有支援的 Teams 會議功能，包括螢幕畫面分享、自訂背景和錄製。
- 提供者可以在 PowerChart 中即時查看病患連線到指定預約預約的更新。
- 病患在預約期間看不到提供者資訊。

> [!NOTE]
> 針對醫療記錄連續性或保留目的，在會議聊天中輸入的任何資訊，都應由醫療保健提供者下載、複製及標注。 聊天不構成法律醫療記錄或指定的記錄集。 來自聊天的訊息會根據 Microsoft Teams 系統管理員建立的設定來儲存。

### <a name="patient-experience"></a>病患體驗

連接器透過簡訊中的連結，支援病患加入預約。 在預約時，病患可以點選簡訊中的連結來開始預約。

病患體驗的重要功能

- 病患可以在 [桌上型電腦和行動裝置上從新式網頁瀏覽器加入約會，而不需要安裝 Teams 應用程式](../browser-join.md)。
- 病患只要按一下即可加入約會，不需要其他帳戶或登入。
- 病患不需要建立 Microsoft 帳戶或登入即可啟動造訪。
- 病患會被置於大廳，直到提供者加入並接受。
- 病患可以先在大廳測試視訊和麥克風，然後再加入約會。

## <a name="get-insight-into-virtual-appointments-usage"></a>深入瞭解虛擬約會使用量

Microsoft Teams 系統管理中心的 [虛擬造訪使用方式報告](../../teams-analytics-and-reports/virtual-visits-usage-report.md) 可讓系統管理員概略瞭解貴組織中的 Teams 虛擬約會活動。 報告會顯示虛擬約會的詳細分析，包括從 EHR 系統進行的 Teams EHR 整合式會議。

您可以檢視重要指派，例如大廳等候時間和約會持續時間。 使用此資訊以深入瞭解使用趨勢，協助您優化虛擬約會，以提供更好的商務成果。

## <a name="privacy-and-location-of-data"></a>資料隱私權和位置

Teams 整合至 EHR 系統，可優化整合和虛擬約會流程期間所使用及儲存的資料量。 解決方案遵循 Teams 隱私權中概述的整體 Teams 隱私權和資料管理原則和指導方針。

Teams EHR 連接器不會從 EHR 系統儲存或傳輸任何可識別的個人資料或病患或醫療保健提供者的任何健康情況記錄。 EHR 連接器儲存的唯一資料是 EHR 使用者的唯一識別碼，該識別碼會在 Teams 會議設定期間使用。

EHR 使用者的唯一識別碼儲存在 [Microsoft 365 客戶資料儲存位置](/microsoft-365/enterprise/o365-data-locations)的三個地理區域其中之一。 所有由會議參與者在 Teams 中共用的聊天、錄製及其他資料，都會根據現有的儲存原則儲存。 若要深入瞭解 Teams 中資料的位置，請參閱 [Teams 中的資料位置](../../location-of-data-in-teams.md)。

## <a name="related-articles"></a>相關文章

- [Teams 虛擬造訪使用方式報告](../../teams-analytics-and-reports/virtual-visits-usage-report.md)
- [Teams EHR 連接器系統管理員報告](ehr-admin-reports.md)
- [開始使用適用于醫療保健組織的 Teams](teams-in-hc.md)
