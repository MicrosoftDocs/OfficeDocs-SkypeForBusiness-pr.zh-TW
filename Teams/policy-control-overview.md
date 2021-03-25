---
title: Microsoft Teams 原則控制概覽
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Microsoft Teams 原則控制的概覽。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b4e87103a5325e231bb07ca56ee5c14b8f48294a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117781"
---
# <a name="policy-control-overview-for-microsoft-teams"></a>Microsoft Teams 原則控制概覽

Microsoft 致力於為您提供所需的資訊和控制，以便您在使用 Microsoft Teams (Microsoft 365 的一部分) 時對收集和使用資料的方式做出選擇。

本文旨在提供以下區域隱私權控制的相關資訊：

- 收集並傳送給 Microsoft 的 **診斷資料**，其中包含您的組織中執行 Windows 的電腦上所使用 Teams 和 Office 軟體的資料。
- **[連線體驗]**：使用以雲端為基礎的功能來為您和您的使用者提供增強的 Teams 和 Office 功能。

這些變更的其中一個部分，是提供新的及更新的使用者介面 (UI) 元素和原則設定。

> [!IMPORTANT]
> 如想進一步閱讀，請參閱 M365 內容的 [原則控制概覽](/deployoffice/privacy/overview-privacy-controls)。

## <a name="diagnostic-data-sent-from-microsoft-365-apps-for-enterprise-to-microsoft"></a>從 Microsoft 365 Apps 企業版傳送到 Microsoft 的診斷資料

診斷資料的用途：

- 保持 Teams 的安全和最新狀態。
- 偵測、診斷和修復問題。
- 改善產品。

其中一些收集的資料範例包括：

- 應用程式語言
- 使用者類型
- OS 的組建版本

## <a name="clients-that-adhere-to-diagnostic-controls"></a>遵循診斷控制的用戶端

下列用戶端遵循診斷控制，並將提交資料：

- iOS
- Android
- 桌上型電腦 (僅限使用 win32 API 的元件)

有關所需的行動裝置診斷資料，請參閱 [行動裝置的原則控制診斷資料](policy-control-diagnostic-data-mobile.md)。

有關所需的桌上型電腦診斷資料，請參閱 [桌上型電腦的原則控制診斷資料](policy-control-diagnostic-data-desktop.md)。

## <a name="diagnostic-data-sent-from-the-teams-app-to-microsoft"></a>從 Teams 應用程式傳送到 Microsoft 的診斷資料

系統會收集此診斷資料並傳送給 Microsoft，其中包含您的組織中執行 Windows 的電腦上所使用的 Teams 軟體的資料。

Teams 軟體有三個層級的診斷資料可供選擇：

- **必要**：最基本的資料，以保持 Office 的安全、最新狀態且在安裝它的裝置上如預期地運作。
- **選用**：額外的資料，可協助我們改善產品，並提供增強的資料來協助我們偵測、診斷和修復問題。
- **無**：不收集也不傳送給我們任何使用者裝置上執行的 Teams 軟體的診斷資料。 不過，這個選項會大幅限制我們偵測、診斷以及修復您的使用者使用 Teams 時可能會遇到的問題。

必要的診斷資料可能包括：例如用戶端在裝置上所安裝的 Teams 版本的相關資料，或包括指出 Teams 應用程式在嘗試加入會議時當機的資料。 選用的診斷資料可能包括：開始撥打電話所耗費的時間，這可能代表連線能力和網路效能方面的問題。

如果您選擇將選用的診斷資料傳送給我們，則也會包含必要的診斷資料。

身為組織的系統管理員，您可以使用原則設定來選擇要傳送給我們的診斷資料層級。 除非您變更設定，否則會將選用的診斷資料傳送給 Microsoft。 提供選用的診斷資料有助於 Microsoft 的 Office 工程團隊偵測、診斷以及減輕問題，以降低對組織的影響。

如果使用者是使用其組織的認證 (有時稱為公司或學校帳戶) 登入 Office，使用者將無法為他們的裝置變更診斷資料層級。

此診斷資料不會包含使用者的名稱、他們的電子郵件地址或其 Office 檔案的內容。 我們的系統會建立一個唯一的識別碼，該識別碼會與使用者的診斷資料建立關聯。 當我們收到的診斷資料顯示我們的 Teams 應用程式當機了 100 次，這個唯一識別碼可讓我們判斷是單一使用者當機了 100 次，還是 100 個不同的使用者各當機一次。 我們不會使用此唯一識別碼來識別出特定使用者。

## <a name="required-service-data-for-connected-experiences"></a>連線體驗的必要服務資料

必要的服務資料是使我們能夠提供這些雲端型連線體驗並協助保護體驗的安全及讓其如預期執行的資料。 必要服務資料包含三種資訊類型。

- **客戶內容**，這是您使用 Office 建立的內容，例如在 Word 文件中輸入的文字。
- **功能資料**，這包括連線體驗執行其工作所需的資訊，例如有關 App 的組態資訊。
- **服務診斷資料**，這是讓服務安全、最新且如預期執行所需的資料。 因為此資料嚴格上來說僅與連線體驗相關，它會與必要或選用診斷資料層級分開。

您可以選擇不提供這項功能給您的使用者，在這種情況下，此資料就不會提供給 Microsoft 來支援連線體驗的功能。 您可以深入瞭解 [必要服務資料](/deployoffice/privacy/required-service-data)。

## <a name="essential-services-for-microsoft-teams"></a>Microsoft Teams 的基本服務

還有一組服務是 Microsoft 365 Apps 企業版運作的基礎，因此不能停用。 例如，可確認您取得使用 Microsoft 365 Apps 企業版正確授權的授權服務。 無論您設定了哪些其他原則設定，都會收集有關這些服務的必要服務資料並將其傳送給 Microsoft。

如需詳細資訊，請參閱 [Office 的基本服務](/deployoffice/privacy/essential-services)。