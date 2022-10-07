---
title: Microsoft 應用程式驗證和應用程式測試概觀
description: 了解根據市集認證原則的 Teams 應用程式驗證指導方針。 了解 Microsoft 如何確保 Teams 應用程式遵守高標準的隱私權和安全性。
ms.topic: article
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
audience: admin
ms.subservice: teams-apps
ms.service: msteams
ms.date: 08/11/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: eeb0c49dcf560b858b8723f813cc86b6b51c1daa
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377551"
---
# <a name="testing-and-validation-done-by-microsoft-for-all-teams-apps"></a>Microsoft 針對所有 Teams 應用程式完成測試和驗證

Microsoft 需要所有應用程式通過強制驗證，才能列入終端用途市集。 它適用於 Teams 應用程式市集上發佈的所有應用程式 (除自訂應用程式以外)。 此外，Microsoft 也強烈建議應用程式開發人員參與應用程式的選用認證，其指示增強的合規性、安全性和隱私權控制。

所有應用程式都必須遵守 Microsoft 應用程式認證原則。 Teams 市集團隊會執行 400 次以上的測試，以確保這些應用程式可供使用，並遵循隱私權和安全性高標準。

若要瞭解應用程式開發人員遵守的詳細驗證指導方針，請參閱 [適用於開發人員的驗證指導方針](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines)。 此指導方針是根據 [Teams 應用程式認證原則](/legal/marketplace/certification-policies#1140-teams)。

> [!NOTE]
> Microsoft 的驗證和檢查不適用於自訂應用程式，因為它是在貴組織內開發，而且僅供貴組織成員使用。

## <a name="app-validation-and-testing"></a>應用程式驗證與測試

我們為每一個應用程式執行 400 個以上的測試案例，之後才能在 Teams 市集上提供。 測試會確保適當的功能、使用者體驗和安全性，並確保所有應用程式都遵守公開列出的 CMO 原則。 以下是 Microsoft 應用程式驗證團隊針對每個應用程式發佈之前所進行的一些測試：

* 確定應用程式要求的 Graph 權限確實是應用程式功能需要的權限，而不是任何額外的權限。 會定期檢查現有應用程式的 Graph 權限，以確保應用程式不需要額外的權限。
* 要求使用者登入的應用程式有登出選項。
* 所有應用程式的開發人員都會在 Microsoft 合作夥伴中心進行詳細的驗證程式。 驗證包括電子郵件驗證、商務驗證等等。 若要深入了解應用程式發佈，請參閱 [開發人員如何建立合作夥伴中心帳戶](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account)、[適用於開發人員的提交指南](/office/dev/store/add-in-submission-guide)，以及 [開發人員如何發佈應用程式](https://aka.ms/PublishToTeamsStore)。
* 只有經過驗證的開發人員提供的應用程式才能向使用者尋求 Graph 權限。
* 沒有應用程式可以下載可執行檔。
* 應用程式經測試不包含廣告及對其他應用程式的促銷。
* 應用程式經測試，不具攻擊性語言、網路攻擊機器人、垃圾郵件或詐騙內容而適當地運作。
* 應用程式中的所有連結都可正常運作，且僅與應用程式供應方案相關。
* 我們會定期測試和評估所有已發佈的 Teams 應用程式，做為應用程式市集健康情況檢查的一部分。
* 涵蓋 Teams 應用程式的隱私權原則和使用規定是由應用程式開發人員提供。
* 應用程式開發人員的連絡人詳細資料可在 Microsoft 市集清單及其個別的[發行者證明頁面](/microsoft-365-app-certification/teams/teams-apps)上取得。

此外，Microsoft 鼓勵應用程式開發人員參與其合規性計畫，這是確保應用程式品質、安全性和合規性的雙層嚴格方法。 Teams 市集中有數百個應用程式，這些應用程式除了符合已詳細列出的驗證指導方針之外，也遵循這些計畫。

## <a name="related-article"></a>相關文章

* [Microsoft 365 應用程式合規性計畫的系統管理員概觀](overview-of-app-certification.md)
