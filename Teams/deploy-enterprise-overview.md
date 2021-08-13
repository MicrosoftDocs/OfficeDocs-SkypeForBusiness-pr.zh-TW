---
title: Microsoft Teams 企業部署概觀
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: 瞭解如何部署 Microsoft Teams 的企業功能。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: f8521de23466f0551d9c09e072aa0b10b487bbedd6ed473e4ff2a9997f456d28
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54346309"
---
# <a name="teams-enterprise-deployment-overview"></a>Teams 企業部署概觀

如果您是中型或大型企業，您需要思考如何向使用者推出服務、如何向使用者部署 Microsoft Teams 用戶端、您的網路設計對即時通訊品質的影響等等。請查看下列各節的文章指標，協助您在組織中規劃 Teams。

> [!NOTE]
> 如果您尚未部署 Teams，我們強烈建議您使用試驗版，開始您的 Teams 部署。 試驗將可使您和一些早期採用者在您進行規劃和最終推出之前熟悉 Teams 及其功能。若需更多資訊說明如何開始試驗，請查閱 [開始使用 Microsoft Teams](get-started-with-teams-quick-start.md)。

在您完成閱讀下列章節並準備開始在組織中部署 Teams 之後，請參閱 [在企業中設定 Microsoft Teams](deploy-enterprise-setup.md)。

## <a name="architecture"></a>架構

Teams 與 Microsoft 365 緊密整合，並且使用許多功能以開啟聊天、檔案共用、會議、電話語音、影片串流等其他功能。 推出 Teams 之前，請查看 [Microsoft Teams IT 架構設計人員與電話語音解決方案海報](teams-architecture-solutions-posters.md) 以熟悉 Teams 與其他 Microsoft 365 一起運作的方式，並為使用者建立完整的共同作業體驗。

## <a name="workloads"></a>工作負載

Teams 有三種工作負載可以彼此獨立部署：**聊天、Teams 和頻道**；**會議和研討會**；和 **電話系統和 PSTN (公用交換電話網路) 連線**。 在我們的文件中每個工作負載都有各自的章節，可更容易找到該工作負載的資訊。 這包括部署規劃資訊。

若要查看您想要部署之工作負載的部署規劃資訊，請參閱下列文章：

- [聊天、Teams 和頻道](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [會議和研討會](deploy-meetings-microsoft-teams-landing-page.md)
- [電話系統與 PSTN 連線](cloud-voice-landing-page.md)

## <a name="network-planner"></a>網路規劃中心

當您擁有大量使用者、或複雜網路或兩者皆具備時，Teams 的網路規劃即非常重要。 Teams 支援語音通話和視訊會議，兩者都仰賴即時通訊，以盡可能為使用者提供最佳體驗。 網路必須具備：

- 充足的頻寬容量，以容納並行的語音通話、視訊會議、會議、螢幕畫面分享等等。
- 具有支援即時通訊協定的網路硬體。
- 允許在您網路上的裝置、Microsoft 365 服務與外部使用者之間的必要網路埠。

請參閱下列文章，以協助您瞭解 Microsoft Teams 的網路需求：

- [針對 Microsoft Teams 準備組織的網路](prepare-network.md)
- [適用於 Microsoft Teams 或商務用 Skype® 2015 Online 的 Proxy 伺服器](proxy-servers-for-skype-for-business-online.md)

為協助您進行規劃，Teams 包含網路規劃工具。 網路規劃中心會詢問有關您擁有的使用者數量和類型、貴組織擁有的網站數量、您的網路連結頻寬容量等問題。 透過使用這項資訊，網路規劃中心會建立一份報告，其中會顯示每個活動的頻寬需求及建議。

 > [!div class="nextstepaction"]
> [前往網路規劃中心](https://admin.teams.microsoft.com/networkplanner/organization)

(您必須是 [Microsoft 365 全域系統管理員](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) 才能開啟網路規劃中心。)

有關網路規劃中心運作方式的詳細資訊，請參閱 [使用 Microsoft Teams 的網路規劃中心](network-planner.md)。

若要瞭解網路規劃中心如何規劃您的網路範例，請參閱 [使用網路規劃中心 - 範例案例](tutorial-network-planner-example.yml)。

## <a name="teams-advisor"></a>Teams 顧問

Teams 顧問是 Teams 內的解決方案，將 Teams、頻道、檔案共用和 Microsoft Planner 彙集在一起，以為您的組織建立部署專案。 Teams 顧問會針對您選取的工作負載 (例如聊天、團隊和頻道) 建立專案計劃，其中包含在部署期間您應執行的建議工作。 每項工作都包含相關文章的指示、建議和連結，以引導您完成此程序。 您可以輕鬆地將工作指派給一或多個人員，並為每個工作指定開始日期和結束日期。

> [!TIP]
> 完成 Microsoft Learn 上的 [使用 Teams 顧問執行](/learn/modules/m365-teams-rollout-using-advisor/) 模組，以瞭解如何使用 Teams 顧問協助您規劃 Teams 部署。

> [!div class="nextstepaction"]
> [前往 Teams 顧問](https://admin.teams.microsoft.com/teams-deployment)

(您必須是 [Microsoft 365 全域系統管理員](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) 才能開啟 Teams 顧問。)

如需 Teams 顧問運作方式的詳細資訊，請參閱 [使用適用於 Teams 的建議程式以協助您執行 Microsoft Teams](use-advisor-teams-roll-out.md)。

## <a name="lifecycle-and-governance-planning"></a>生命週期與控管規劃

當您在規劃 Teams 部署時，您必須考慮在貴組織中的 Teams、頻道、檔案等的生命週期。 您也應該考慮要將哪些類型的資訊儲存其中。 Teams 可能為特定專案、部門而建立，或作為整個組織的中央資源。 每個用途都有不同的需求，也就推動了下列問題：

- Teams 維持使用中的狀態可達多長時間？
- 誰應該擁有及管理 Teams 及其頻道？
- 某些合規性需求是否應該只套用到某些 Teams，但不能套用至其他？
- 是否應該有命名原則以協助使用者識別正確的 Teams？

建立原則與指導方針並做為初始部署的一部分，將可協助確保您的使用者可以找到所需的資訊。 同樣重要的是，適當的原則將可協助保護貴組織避免資訊外泄、協助您符合法規需求，並協助您針對保存目的保留需要的資訊。

若要深入瞭解 Teams 中的生命週期管理和控管，請參閱下列內容：

- [Teams 中的生命週期管理方案](plan-teams-lifecycle.md)
- [Teams 中的控管方案](plan-teams-governance.md)

## <a name="adoption"></a>採用

若要確保貴組織和使用者能從 Teams 獲得最大收益，您需要一份採用計畫。 一份有效的採用計畫可以動員早期採用者，這些採用者可以：

- 向同事以及企業或群組領導者說明 Teams 的好處。
- 在看到 Teams 如何改善共同作業的其他人中，激發他們的熱情並使他們更輕鬆地彼此聯繫。
- 協助評估現有的商務程序，並針對 Teams 如何整合到其中的方式提出建議。
- 向部署小組回報成功之處和困難之處，以協助改善採用程序。

有關設定採用計畫的詳細資訊，請參閱 [採用 Microsoft Teams](adopt-microsoft-teams-landing-page.md)。