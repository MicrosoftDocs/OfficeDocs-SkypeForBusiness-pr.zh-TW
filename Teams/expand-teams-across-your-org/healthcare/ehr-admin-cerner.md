---
title: 使用虛擬Teams - 整合至 Cerner EHR
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
description: 瞭解如何整合 Teams EHR 連接器，讓貴組織的醫療保健提供者直接從 Cerner EHR 系統與 Teams 中的病患或其他提供者進行虛擬拜訪。
ms.openlocfilehash: d7f34be9729989f7930cc6f478738b43b716f6ac
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435877"
---
# <a name="virtual-visits-with-teams---integration-into-cerner-ehr"></a>使用虛擬Teams - 整合至 Cerner EHR

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft Teams電子健康記錄 (EHR) 連接器，讓臨床醫師可以直接從 Cerner EHR 系統啟動虛擬病患拜訪，或向 Microsoft Teams 中的另一個提供者諮詢。 在雲端Microsoft 365，Teams在支援 HIPAA、HITECH 認證等合規性的單一中樞中，使用聊天、視視、語音和醫療保健工具，輕鬆、安全地共同合作及通訊。

診所通訊和共同Teams平臺，讓診所醫師能輕鬆從零散的系統中剪下雜亂無章的雜物，讓他們能專注于提供最佳的照護。 使用 Teams EHR 連接器，您可以：

- 使用整合Teams，從 Cerner EHR 系統進行虛擬訪問。
- 可讓病患從電子郵件Teams簡訊通知加入虛擬訪問。
- 查看消費資料包告和可自訂的 EHR 相關訪問通話品質資訊。

本文將說明如何設定及設定 EHR 連接器Teams與 Cerner 平臺整合。 它也提供您從 Cerner EHR Teams虛擬流覽體驗概觀。

## <a name="before-you-begin"></a>開始之前

> [!NOTE]
> 啟用整合之前，請務必先與 Cerner 代表交談，並查看您的 Cerner 整合指南。

### <a name="prerequisites"></a>必要條件

在醫療保健組織中Teams EHR 連接器之前，您必須有下列專案：

- 使用 EHR 連接器獨立Microsoft Teams訂閱， (在生產 EHR 環境中測試時) 。
- 使用者擁有適當的Microsoft 365或Office 365授權，Teams會議。
- Teams採用並用於您的醫療保健組織。
- 您的系統符合[所有軟體與瀏覽器Teams](../../hardware-requirements-for-the-teams-app.md)。
- Cerner 版本 2018 年 11 月或更新版本

## <a name="set-up-the-teams-ehr-connector"></a>設定 EHR Teams連接器

連接器設定需要您：

- [啟動 EHR 連接器組式入口網站](#launch-the-ehr-connector-configuration-portal)
- [輸入組組資訊](#enter-configuration-information)
- [啟用簡訊通知 (選) ](#enable-sms-notifications-optional)
- [檢閱並完成組態](ehr-admin-cerner.md#review-and-finish-the-configuration)

> [!IMPORTANT]
> 這些步驟必須由貴組織的全域系統管理員Microsoft 365完成。  

### <a name="launch-the-ehr-connector-configuration-portal"></a>啟動 EHR 連接器組式入口網站

若要開始使用，您的系統管理員Microsoft 365[啟動 EHR 連接器組組入口](https://ehrconnector.teams.microsoft.com)網站，然後使用他們的 Microsoft 認證進行登錄。

您的Microsoft 365系統管理員可以設定單一部門或多個部門來測試整合。 在組態入口網站中設定測試與生產 URL。 在移往生產之前，請務必先從 Cerner 測試環境測試整合。

### <a name="enter-configuration-information"></a>輸入組組資訊

接下來，若要設定整合，您的系統管理員Microsoft 365從 Cerner 新增快速健康 (互通性資源) 基本 URL 並指定環境。 視貴組織的需求和您想要測試的環境，視需要設定盡可能多的 FHIR 基本 URL。

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="EHR 連接器組Teams之組Teams頁面的螢幕擷取畫面。" lightbox="media/ehr-admin-cerner-configuration.png":::

- FHIR 基本 URL 是對應到伺服器 FHIR API 端點的靜態位址。 範例 URL 是 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`。

- 您可以設定測試與生產環境的整合。 針對初始設定，我們建議您先從測試環境設定連接器，再移往生產。

驗證 FHIR 基本 URL 並選取環境之後，**請選擇完成。** 然後，根據需要，為其他環境新增更多 FHIR 基本 URL。

選取 **下** 一步以前往下一個步驟。

### <a name="enable-sms-notifications-optional"></a>啟用簡訊通知 (選) 

如果您的組織想要 Microsoft 管理病患的簡訊通知，請完成此步驟。 當您啟用簡訊通知時，您的病患會收到預定的拜訪的確認和提醒訊息。

若要啟用簡訊通知，您的Microsoft 365系統管理員會執行下列操作：

1. 在簡訊通知頁面上，選取兩個同意核取方塊以：

    - 允許 Microsoft 代表貴組織傳送簡訊通知給病患。
    - 確認您將確保出席者已同意傳送及接收簡訊。

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="簡訊通知頁面的螢幕擷取畫面，顯示同意核取方塊，以及產生電話號碼的選項。" lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. 在 **電話號碼下**， **選取產生新電話號碼** ，為貴組織產生電話號碼。 這麼做會啟動要求並產生新電話號碼的過程。 此程式最多可能需要 2 分鐘才能完成。

    產生電話號碼之後，電話號碼會顯示在螢幕上。 這個號碼會用來傳送簡訊確認和提醒給病患。 號碼已撥備，但尚未連結至 FHIR 基本 URL。 您可以在下一個步驟中執行這項操作。

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="顯示產生的電話號碼範例的螢幕擷取畫面。" lightbox="media/ehr-admin-cerner-phone-number.png":::

    選擇 **完成**，然後選取下 **一步**。

1. 若要將電話號碼連結至 FHIR 基本 URL，請在 **電話的號碼** 下，選取該號碼。 針對要啟用簡訊通知的每個 FHIR 基本 URL 執行此操作。

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="顯示如何將電話號碼連結至 FHIR 基本 URL 的螢幕擷取畫面。" lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    如果這是您第一次配置連接器，會看到先前步驟中輸入的 FHIR 基本 URL。 相同的電話號碼可以連結至多個 FHIR 基本 URL，這表示病患會收到來自不同組織和/或部門之相同電話號碼的簡訊通知。

     選取 **下一步**。

### <a name="review-and-finish-the-configuration"></a>檢閱並完成組態

系統將會提供病患與提供者啟動的整合記錄。 這些記錄在 Cerner 中完成虛擬訪問組組時是必要的。 詳細資訊請參閱遠端Cerner-Microsoft Teams整合指南。

> [!NOTE]
> 您的系統管理員隨時都可以Microsoft 365入口網站來查看整合記錄，並視需要變更設定設定。

## <a name="launch-teams-virtual-visits"></a>啟動Teams虛擬訪問

完成 EHR 連接器步驟和 Cerner 組組步驟之後，貴組織就可以使用 Teams 支援視Teams。

### <a name="virtual-visits-prerequisites"></a>虛擬訪問的先決條件

- 您的系統必須符合[所有軟體與瀏覽器需求，](../../hardware-requirements-for-the-teams-app.md)Teams。
- 您已完成 Cerner 組織與貴組織之間的整合Microsoft 365設定。

### <a name="provider-experience"></a>提供者體驗

貴組織的醫療保健提供者可以使用 PowerChart 入口網站Teams加入訪問。 提供者必須流覽至提供 Teams 選項的病患區。

提供者可以在那裡查看流覽資訊、加入流覽，以及傳送會議連結。 一次登錄之後，提供者會直接進入 Teams。

提供者體驗的主要功能：

- 提供者可以使用支援的瀏覽器或應用程式加入Teams流覽。
- 提供者可以使用所有支援的Teams功能，包括螢幕分享、自訂背景和錄製。
- 提供者可以在 PowerChart 中查看連接到指定約會之病患即時更新。
- 病患在流覽期間看不到提供者資訊。

> [!NOTE]
> 醫療保健提供者應下載、複製及記錄醫療記錄持續性或保留用途所需的會議聊天中輸入的資訊。 聊天不構成合法的醫療記錄或指定的記錄集。 來自聊天的郵件會根據系統管理員所建立Microsoft Teams儲存。

### <a name="patient-experience"></a>病患體驗

連接器支援透過簡訊連結加入病患。 在預約時，病患可以點一下簡訊中的連結來開始看診。

病患體驗的主要功能

- 病患可以在桌面和行動版上加入新式網頁瀏覽器的流覽，[而不需要](../mobile-browser-join.md)安裝 Teams App。
- 病患只需按一下即可加入看診，而不需要其他帳戶或登錄。
- 病患不需要建立 Microsoft 帳戶或登錄以啟動流覽。
- 病患會放在大廳，直到提供者加入並准許他們。
- 病患可以在加入拜訪前，先在大廳測試視像和麥克風。

## <a name="get-insight-into-virtual-visits-usage"></a>深入瞭解虛擬訪問的使用狀況

系統[管理中心中的](../../teams-analytics-and-reports/virtual-visits-usage-report.md)虛擬Microsoft Teams使用方式報告，提供系統管理員Teams貴組織虛擬流覽活動概觀。 報告顯示虛擬約會的詳細分析，Teams EHR 系統召開 EHR 整合會議。

您可以查看重要度量單位，例如大廳等候時間和流覽持續時間。 使用這項資訊來深入瞭解使用趨勢，協助優化虛擬訪問，以提供更好的商務成果。

## <a name="privacy-and-location-of-data"></a>資料隱私權和位置

Teams整合至 EHR 系統，可優化整合和虛擬訪問流程期間使用及儲存的資料量。 解決方案遵循 Teams 隱私權中概述的整體 Teams 隱私權和資料管理原則和指導方針。

EHR Teams連接器不會從 EHR 系統儲存或傳輸任何可識別的個人資料，或病患或醫療保健提供者的任何健康記錄。 EHR 連接器所儲存的唯一資料是 EHR 使用者的唯一識別碼，用於Teams設定期間。

EHR 使用者的唯一識別碼儲存在 [Microsoft 365 客戶資料儲存位置](/microsoft-365/enterprise/o365-data-locations)的三個地理區域其中之一。 會議參與者在 Teams共用的所有聊天、錄製及其他資料，都是根據現有的儲存策略儲存。 若要深入瞭解資料在 Teams 中的位置，請參閱[資料在](../../location-of-data-in-teams.md)Teams。

## <a name="related-articles"></a>相關文章

- [Teams虛擬訪問使用方式報告](../../teams-analytics-and-reports/virtual-visits-usage-report.md)
- [Teams EHR 連接器系統管理員報告](ehr-admin-reports.md)
- [開始使用醫療保健組織Teams服務](teams-in-hc.md)
