---
title: Microsoft 應用程式驗證和應用程式測試概觀
ms.reviewer: ''
description: 瞭解 Teams 應用程式的品質檢查和應用程式驗證做法。
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fa6a03c5408afcd7cce1d3e48b78b3b1ddb3675a
ms.sourcegitcommit: b70f01d7eae2e3e6f7495c685518a2037aaece31
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/11/2022
ms.locfileid: "64756989"
---
# <a name="validation-performed-by-microsoft-for-all-teams-apps"></a>Microsoft 針對所有 Teams 應用程式執行的驗證

Microsoft 需要所有應用程式通過強制驗證，才能列入終端用途市集。 它適用於 Teams 應用程式市集上發佈的所有應用程式 (除自訂應用程式以外)。 此外，Microsoft 也強烈建議應用程式開發人員參與應用程式的選用認證，其指示增強的合規性、安全性和隱私權控制。

所有應用程式都必須遵守 Microsoft 應用程式認證原則。 Teams 市集團隊會執行 400 次以上的測試，以確保這些應用程式可供使用，並遵循隱私權和安全性高標準。

若要瞭解應用程式開發人員遵守的詳細驗證指導方針，請參閱 [適用於開發人員的驗證指導方針](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines)。 此指導方針是根據 [Teams 應用程式認證原則](/legal/marketplace/certification-policies#1140-teams)。

> [!NOTE]
> Microsoft 的驗證和檢查不適用於自訂應用程式，因為它是在貴組織內開發，而且僅供貴組織成員使用。

## <a name="app-validation-and-testing"></a>應用程式驗證與測試

我們為每一個應用程式執行 400 個以上的測試案例，之後才能在 Teams 市集上提供。 測試會確保適當的功能、使用者體驗和安全性，並確保所有應用程式都遵守公開列出的 CMO 原則。 以下是 Microsoft 應用程式驗證團隊針對每個應用程式發佈之前所進行的一些測試：

* 確定應用程式要求的 Graph 權限確實是應用程式功能需要的權限，而不是任何額外的權限。 會定期檢查現有應用程式的 Graph 權限，以確保應用程式不需要額外的權限。
* 要求使用者登入的應用程式有登出選項。
* 所有應用程式發行者都會在 Microsoft 合作夥伴中心進行詳細的驗證流程。 驗證包括電子郵件驗證、商務驗證等等。 若要深入了解應用程式發佈，請參閱 [開發人員如何建立合作夥伴中心帳戶](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account)、[適用於開發人員的提交指南](/office/dev/store/add-in-submission-guide)，以及 [開發人員如何發佈應用程式](https://aka.ms/PublishToTeamsStore)。
* 只有經過驗證的發行者提供的應用程式才能向使用者尋求 Graph 權限。
* 沒有應用程式可以下載可執行檔。
* 應用程式經測試不包含廣告及對其他應用程式的促銷
* 應用程式經測試，不具攻擊性語言、網路攻擊機器人、垃圾郵件或詐騙內容而適當地運作。
* 應用程式中的所有連結都可正常運作，且僅與應用程式供應方案相關。
* 我們會定期測試和評估所有已發佈的 Teams 應用程式，做為應用程式市集健康情況檢查的一部分。
* 涵蓋 Teams 應用程式的隱私權原則和使用規定是由 ISV 所發佈
* ISV 的連絡人詳細資料可在 Microsoft 市集清單及其個別的[發行者證明頁面](/microsoft-365-app-certification/teams/teams-apps)上取得。

此外，Microsoft 鼓勵應用程式開發人員參與其合規性計畫，這是確保應用程式品質、安全性和合規性的雙層嚴格方法。 Teams 市集中有數百個應用程式，這些應用程式除了符合已詳細列出的驗證指導方針之外，也遵循這些計畫。

## <a name="publisher-verification"></a>發行者驗證

應用程式開發人員必須先經過驗證，才能將應用程式提交給 Microsoft。 發行者使用其 Microsoft 合作夥伴網路 (MPN) 帳戶驗證其身分識別，並將此 MPN 帳戶與其應用程式註冊建立關聯。 發行者驗證可協助系統管理員和使用者瞭解整合Microsoft 身分識別平台之應用程式開發人員的真實性。 發行者驗證具有下列優點：

* 提高客戶的透明度和降低風險 - 這項功能可協助客戶瞭解其組織中使用的應用程式是由他們信任的開發人員所發佈。
* 改良的商標 - `verified` 徽章會顯示在 Azure Active Directory 同意提示、企業應用程式頁面，以及使用者和系統管理員使用的其他使用者介面上。
* 更順暢的企業採用 - 系統管理員可以設定使用者同意原則，並以發行者驗證狀態做為主要原則準則。

## <a name="see-also"></a>另請參閱

* [Microsoft 365 應用程式合規性計畫的系統管理員概觀](overview-of-app-certification.md)
