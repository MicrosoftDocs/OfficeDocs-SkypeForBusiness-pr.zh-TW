---
title: Microsoft 應用程式驗證和應用程式測試概觀
ms.reviewer: null
description: 瞭解Teams應用程式的品質檢查、應用程式驗證和認證程式。
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
---
# <a name="checks-and-validation-performed-by-microsoft-on-teams-apps"></a>Microsoft 在Teams應用程式上執行的檢查和驗證

Microsoft 需要所有應用程式通過強制驗證，才能在 Microsoft Store 中列出終端用途。 它適用于Teams App Store 上發佈的自訂應用程式) 以外的所有應用程式 (。 此外，Microsoft 也強烈建議應用程式開發人員參與應用程式的選擇性認證，以指出增強的合規性、安全性和隱私權控制。

若要遵守 Microsoft App 認證原則，所有應用程式都必須符合 mandatorily。 Teams市集小組會執行 400 次以上的測試，以確保這些應用程式可供使用，並遵循高標準的隱私權和安全性。

若要瞭解應用程式開發人員遵守的詳細驗證指導方針，請參閱 [適用于開發人員的驗證指導方針](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines)。

> [!NOTE]
> Microsoft 的驗證和檢查不適用於自訂應用程式，因為它是在貴組織內開發，而且僅供貴組織成員使用。

<!--- TBD: Add the link later. 
To review the certification policies of any app, see [App certification policies]().
Is the link /microsoft-365-app-certification/teams/teams-apps
--->

## <a name="app-validation-and-testing"></a>應用程式驗證與測試

我們為每一個應用程式執行 400 個以上的測試案例，之後才能在 Teams Store 上使用。 測試會確保適當的功能、使用者體驗和安全性，並確保所有應用程式都遵守公開列出的 CMO 原則。 以下是 Microsoft 應用程式驗證小組針對每個應用程式發佈之前所進行的一些測試：

* 確定應用程式要求的Graph許可權確實是應用程式功能需要的許可權，而不是任何額外的許可權。 Graph會定期檢查現有應用程式的許可權，以確保應用程式不需要額外的許可權。
* 需要使用者登入/登入的應用程式必須有 [登入/登出] 選項。
* 所有應用程式發行者都會在 Microsoft 合作夥伴中心進行詳細的驗證程式。 驗證封裝括電子郵件驗證、商務驗證等等。 若要深入瞭解應用程式發佈，請參閱 [開發人員如何建立合作夥伴中心帳戶](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account)、 [適用于開發人員的提交指南](/office/dev/store/add-in-submission-guide)，以及 [開發人員如何發佈應用程式](https://aka.ms/PublishToTeamsStore)。
* 只有經過驗證發行者提供的應用程式才能向使用者尋求Graph許可權。
* 沒有應用程式可以下載可執行檔。
* 應用程式經測試而無法包含廣告、針對其他應用程式進行促銷
* 應用程式經測試，可搭配不具攻擊性語言、網路攻擊機器人、垃圾郵件或詐騙內容的適當運作。
* 應用程式中的所有連結都可正常運作，且僅與應用程式方案相關。
* 我們會定期測試和評估所有已發佈的Teams應用程式，做為 App Store 健康情況檢查的一部分。
* 涵蓋Teams應用程式的隱私權原則和使用規定是由 ISV 發行
* ISV 的連絡人詳細資料可在 Microsoft Store 清單及其各自[的Publisher證明頁面](/microsoft-365-app-certification/teams/teams-apps)上取得。

## <a name="publisher-verification"></a>Publisher驗證

Publisher驗證可協助系統管理員和使用者瞭解與Microsoft 身分識別平臺整合之應用程式開發人員的真實性。 擁有經過驗證的發行者，表示該發行者已使用其 Microsoft 合作夥伴網路 (MPN) 帳戶驗證其身分識別，並已將此 MPN 帳戶與其應用程式註冊相關聯。

Publisher驗證提供下列優點：

* 提高客戶的透明度和降低風險 - 這項功能可協助客戶瞭解其組織中使用的應用程式是由他們信任的開發人員所發佈。
* 改良的商標 - `verified` 徽章會顯示在Azure Active Directory同意提示、Enterprise應用程式] 頁面，以及使用者和系統管理員使用的其他使用者介面上。
* 更順暢的企業採用 - 系統管理員可以設定使用者同意原則，並以發行者驗證狀態做為主要原則準則。

此外，Microsoft 鼓勵應用程式開發人員參與其合規性計畫，這是確保應用程式品質、安全性和合規性的嚴格雙層方法。 Teams市集中有數百個應用程式，除了履行已詳細的驗證指導方針之外，還遵循這些程式。

## <a name="microsoft-365-app-compliance-program"></a>Microsoft 365應用程式合規性計畫

Microsoft 合規性計畫示範某個應用程式已針對從領先產業標準架構衍生出的控制措施進行檢查，並且有強大的安全性與合規性做法來保護客戶資料。 此程式有兩個階段：

* Publisher證明。
* Microsoft 365認證。

### <a name="publisher-attestation"></a>Publisher證明

應用程式開發人員必須完成自我評估，其中包含客戶或 IT 系統管理員在評估應用程式安全性與合規性時經常詢問的問題。 Microsoft 接著發佈此資訊，以便更容易且更及時地評估。 此資訊包含在組織中啟用應用程式時的資料處理、安全性、合規性與隱私權的詳細資料。

若要深入瞭解，請參閱 [發佈證明指南](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide)。

### <a name="microsoft-365-certification"></a>Microsoft 365認證

應用程式認證是透過合格分析師對以應用程式安全性與合規性架構、程式和程式為中心的完整評估的審查與核准來達成。 此應用程式會根據一系列衍生自業界標準架構的安全性控制進行檢查。 憑證顯示強大的安全性與合規性做法，可在組織中啟用應用程式時保護客戶資料。

<!--- TBD: Parking some content for later review. Check if this content needs to be published.

We also have a few more quality and security checks for apps. We have launched Microsoft Cloud App Security (MCAS) program for the customer who have E5 or EMS license, where we rate risk for your cloud apps based on regulatory certification, industry standards, and best practices. We are also working on an Apps Quality Score system (launching soon) for all apps on Teams platform, and you will be able to check an app’s quality score quickly on Teams Store.

--->
