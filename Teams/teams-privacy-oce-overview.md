---
title: Teams 選擇性連線體驗
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: ''
ms.localizationpriority: high
search.appverid: MET150
description: 本文概述您會在 Microsoft Teams 中看到的選擇性連結體驗。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03c23ccc1e9d24733f083c3e1d780b38138d366e
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396264"
---
# <a name="overview-of-optional-connected-experiences-in-microsoft-teams"></a>Microsoft Teams 中選擇性連線體驗的概觀

如果您有公司或學校帳戶，在使用 Microsoft Teams 的同時，組織的系統管理員可能已提供您使用一或多個以雲端為基礎服務的能力 (也稱為 **選擇性連線體驗**)，例如 GIPHY 和/或 URL 預覽服務。 這些以雲端為基礎的服務是選擇性的。 是否使用由您決定。 這些服務是根據與 [Microsoft 線上服務條款](https://www.microsoft.com/licensing/product-licensing/products)不同的條款提供給您，如每個選擇性服務的個別說明。 本文將列出我們的 Teams 雲端支援服務。

如果您的系統管理員允許你在 Teams 中使用選擇性連線體驗，您可以轉到 Teams 中的 **[設定]** > **[隱私]** 並選擇是否要使用選擇性連線體驗。

> [!NOTE]
> 如果您是系統管理員，您可以授與或限制使用者使用選擇性連線體驗的能力。 要執行此操作，您可以使用 [[Office 雲端原則服務]](/deployoffice/overview-office-cloud-policy-service) 並設定 *[允許在 Office 中使用其他選擇性連線體驗]* 原則設定。 這是相同的原則設定，可控制您的使用者在 Microsoft 365 Apps 企業版提供的 Office 應用程式 (例如 Word、Excel 和 PowerPoint) 中是否可以使用選擇性連線體驗。

## <a name="giphy"></a>GIPHY

GIPHY 是雲端支援的服務，可讓您在 Teams 聊天中使用 GIF。 如果您在 **Teams**  >  **GIF**  >  **搜尋** 中，搜尋字詞會傳送至 GIPHY。 如果您的系統管理員允許，且在您選擇使用這些體驗之後，即受限於 [GIPHY 隱私權原則](https://support.giphy.com/hc/articles/360032872931-GIPHY-Privacy-Policy)和[服務條款](https://support.giphy.com/hc/articles/360020027752-GIPHY-User-Terms-of-Service)。

:::image type="content" source="media/giphy-menu.png" alt-text="此功能表顯示 Giphy 選項按鈕，以及文字方塊用於輸入資訊，以擷取一或多個 Giphy 影像。":::

## <a name="url-preview-service"></a>URL 預覽服務

當使用者傳送 URL 字串，URL 預覽服務會自動產生預覽程式碼片段，並在程式碼片段底下附加 URL。 當使用者輸入訊息時，此服務就會向服務 URL 提出要求。 如果服務 URL 沒有任何 schema.org 資料，它會傳送要求給 Bing 搜尋，以取得產生預覽片段所需的資料。 仰賴 Bing 的體驗會根據 [Microsoft 服務合約](https://www.microsoft.com/servicesagreement) 的條款授權給您，並由 [隱私權聲明](https://privacy.microsoft.com/privacystatement)涵蓋。 使用這些服務時，您提供給 Microsoft Teams 的任何 URL 都可以傳送至 Microsoft Bing。 Bing 組織不會將它們與您連結。

:::image type="content" source="media/url-preview.png" alt-text="顯示文字方塊中 Microsoft 首頁 URL 預覽範例的畫面。":::

## <a name="teams-apps-link-previews"></a>Teams 應用程式連結預覽

Teams 應用程式連結預覽服務會產生應用程式介面卡的預覽片段，當使用者傳送對應到 Teams 市集中應用程式的 URL 字串時，會將它附加在 URL 下方。 當使用者輸入訊息時，此服務就會向服務 URL 提出要求。

## <a name="teams-device-store-checkout"></a>Teams 裝置存放區結帳  

Teams 裝置存放區位於 Teams 系統管理中心，可讓您探索和購買 Teams 認證的裝置。 若要啟用結帳，Teams 裝置存放區會與 UnifiedCommunications.com 共用基本使用者和公司資訊，包括使用者電子郵件地址、使用者 GUID 和租使用者 GUID。 如果允許在 Office   原則設定 **中使用其他選用的連線體驗**，則此體驗受服務條款和 UnifiedCommunications.com 隱私權聲明所約束。

:::image type="content" source="media/teams-device-store-buttons.png" alt-text="Teams 裝置存放區頁面部分的螢幕擷取畫面，其中包含由 UnifiedCommunications.com 提供的結帳選項，這是可從 Teams 系統管理中心進行裝置購買的協力廠商公司。":::

若要深入瞭解 Teams 裝置存放區，請參閱： [在 Teams 裝置市集中購買裝置](devices/device-store.md)

## <a name="related-articles"></a>相關文章

- [Teams 原則控制的概觀](policy-control-overview.md)
- [隱私權和 Microsoft Teams](teams-privacy.md)
- [Office 中選擇性連線體驗的概觀](/deployoffice/privacy/optional-connected-experiences)
- [Office 的必要服務資料](/deployoffice/privacy/required-service-data)
- [帳戶隱私權設定](https://support.microsoft.com/office/3e7bc183-bf52-4fd0-8e6b-78978f7f121b)
