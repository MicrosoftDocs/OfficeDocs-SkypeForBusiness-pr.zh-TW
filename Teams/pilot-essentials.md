---
title: 進行使用者試驗，評估並測試 Microsoft Teams 在貴組織中如何工作
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 啟動 Microsoft Teams 試驗指南，探索 Teams 提供貴組織的所有功能，同時您繼續使用商務用 Skype
localization_priority: Normal
ms.custom: Teams-upgrade-guidance
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e2d909722674f23e253d0ae937efddb14d96d7a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108369"
---
# <a name="conduct-a-user-pilot"></a>舉辦使用者試驗

![升級歷程圖，強調部署與執行](media/upgrade-banner-deployment.png "升級歷程的階段，強調部署與執行階段")

本文是升級歷程的部署與執行階段的一部分，並分享執行有效試驗的深入見解。 繼續進行之前，請確認您已完成下列活動：

- [已招募專案專案關係人](upgrade-enlist-stakeholders.md)
- [已定義專案範圍](./upgrade-define-project-scope.md)
- [瞭解商務用 Skype 和 Teams 的共存與互通性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [已選擇升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [準備您的環境](./upgrade-prepare-environment.md)
- [準備您的組織](./upgrade-prepare-organization.md)

部署新技術，貴組織可以發揮節省成本、安全性合規性、員工滿意度及營運效率等商業價值，但也會影響使用者的生產力和組織基礎結構 (網路) 。 在全組織啟用新技術之前，請進行正式的使用者試驗。 就像在繪製整個會議室之前，在牆面繪製一小片色彩一樣，您也得進行試驗，以驗證技術和使用者的整備狀態、找出並減輕問題，以及協助確保整個組織的成功實施，以在較小的範圍內測試廣泛推行。

若要取得最實際的結果，試驗應讓實際使用者參與、模仿使用者溝通和共同合作的方式，以及驗證技術和使用者體驗。 無論貴組織正考慮並排進行商務用 Skype 和 Teams、日後升級至 Teams，或部署通話或會議等新功能，試驗都可以協助找出適合貴組織前進的路徑。 有時被視為推出的第 1 階段，理想的試驗會運用您已開始的準備工作，並針對目標使用者群組來實施您定義的計畫。

| | |
|---|---|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>您將如何使用試驗來告知專案方向？</li></ul> |
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>請使用下列指南來設計並執行正式試驗。</li></ul>|

> [!Tip]
> 使用範例 [試驗資源](https://aka.ms/UpgradeSuccessKit) ，協助設計通訊、測試計劃及意見回饋問卷。

## <a name="1-outline-pilot-logistics"></a>1. 大綱試驗物流

成功的試驗已定義開始日期和結束日期，並明確 [定義衡量](upgrade-define-project-scope.md#project-goals) 成功的目標。 如您定義專案範圍時所記載的，這些目標應該會與您更廣泛的專案範圍[](upgrade-define-project-scope.md)保持一致，並可用來在試驗結束後提供您前進的路徑。 您也應該確保您在專案期間包含正確的專案關係人。 您務必要允許足夠的時間執行試驗並評估其影響：我們建議您至少 30 天。

從小型開始，並在適當的時候加入您的試驗 ，無論是新增工作量或功能，還是新增其他使用者，都能夠花時間評估結果，並隨著您的試驗進行調整。 您甚至可以選擇執行後續試驗，因為新的 Teams 功能會根據藍圖發佈。

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a>2. 選取您的試驗參與者和測試案例

試驗規劃最重要的工作之一是周全的參與者選擇。 請記住，Teams 已針對團隊合作優化，因此請務必根據角色或角色，也根據他們的專案和跨小組工作來選取試驗參與者。 首先，請詢問專案關係人及部門主管，瞭解您可以在 Teams 中驗證的實際專案。 角色型專案的範例可能是使用 Teams 與銷售組織，以確保現場代表可以輕鬆存取所需的資源，並與其他欄位成員共用深入見解。 專案型工作的範例可能是將產品啟動活動與行銷、訓練、公關及活動規劃小組協調。 無論您選取哪一種案例，試驗應該會延伸至 IT、訓練和技術支援中心的重要人員，因此您可以徹底驗證解決方案，同時充分優化專案管理資源。

> [!Tip]
> 選取 Teams 試驗群組參與者時，請務必包含商務用 Skype 的熱門使用者。 請與這些使用者確認他們目前如何使用商務用 Skype，然後建立測試計劃，確認 Teams 可以符合他們目前的需求。

## <a name="3-design-your-test-plan-and-feedback-survey"></a>3. 設計您的測試計劃與意見回饋問卷

若要獲得成功的試驗體驗，請給予參與者明確定義的工作來完成，並讓他們分享他們的意見。 將工作分組在一起，提供實際案例給使用者，顯示其每日活動的相關性。 讓您在評估組織變更準備狀況中定義的使用 [案例](./upgrade-org-change-readiness.md) 引導您的測試計劃。

貴組織可能會選擇一次試驗所有功能，或使用漸進式方法，例如先試驗共同合作，然後再試驗會議，然後進行聊天和通話。 請確保您擁有開放式的意見回饋通道，以追蹤進度並衡量結果。 使用預先定義的問卷，輕鬆取得及評估試驗結果;問卷設計應該以測試方案中的情境和功能為基礎。

## <a name="4-create-your-communications-plan"></a>4. 建立通訊計畫

您必須教育試驗參與者瞭解進行中的專案、時間、原因，以及預期目標，這是試驗成功的關鍵。 若要提高興奮感和最大參與度，請務必加入使用者價值訊息，以及訓練與支援的連結，讓使用者在試驗進行時取得其他資訊。 以下是一些範例資源，可引導您開始使用試驗通訊計畫：

- [試驗資源](https://aka.ms/UpgradeSuccessKit)，包括電子郵件範本和範例意見回饋問卷問題
- [從商務用 Skype 切換到 Teams，](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964)這是專為協助商務用 Skype 使用者開始使用 Teams 設計的快速入門手冊

## <a name="5-conduct-your-pilot"></a>5. 進行您的試驗

所有物流就緒後，就可以開始試驗了。 進行試驗包括與使用者通訊、監控您的網路和使用狀況，以確保您的網路績效和通話品質維持健康、收集參與者的意見，以及檢閱 Teams 相關問題的服務台票證。

### <a name="tips-for-pilot-success"></a>試驗成功的秘訣

下列秘訣可協助確保試驗成功：

- 開始試驗之前，請確認所有試驗參與者都已啟用適當的 [共存模式]
-  (https://aka.ms/SkypeToTeams-SetCoexistence) 驗證。
- 每週在試驗期間與專案關係人開會，以審查使用者的意見回饋、使用方式資料、網路資料和服務台票證，以確保您的試驗順利進行。 根據需要進行任何調整。

### <a name="suggested-timeline"></a>建議的時程表

以下是為期 30 天的試驗建議時程表：

- 試驗啟動前一周：傳送初始通訊給試驗使用者。
- 第 1 天：傳送啟動通訊給試驗使用者。
- 第 7 天：召開第一次每週專案小組檢查會議。
- 第 14 天：傳送中間點通訊給試驗使用者，召開每週的專案小組檢查會議。
- 第 21 天：每週召開一次專案小組檢查檢查會議。
- 第 30 天：傳送最終通訊給試驗使用者。
- 第 31 天至第 45 天：評估試驗結果，並規劃下一個步驟。

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a>6. 評估學習並評估您的進一步計畫

試驗完成後，該是收集所有意見回饋問卷、最終網路統計資料，以及針對目標進行分析的支援票證，然後決定是否要執行您的進一步計畫。 您可能會發現貴組織已準備好進行廣泛部署，或您想要將試驗範圍擴大到更多使用者，或是在已減輕您發現的任何疑慮之後，于日後重新檢查試驗。 請記住，您的試驗是預測受控制環境中技術和使用者結果 _的很好_ 方法;考慮一下跳得太快。

如果結果顯示：

- **您的試驗 (** 例如使用者滿意度和網路品質) 已經達成，您應該準備好繼續進行下一階段的推出。 根據您的專案目標，這可能是下列其中一項：
  - 將試驗延伸到其他參與者
  - [啟用 Teams 與商務用 Skype (**群島** 模式) 部分或所有組織啟用](./setting-your-coexistence-and-upgrade-settings.md)
  - [將商務用 Skype 使用者升級 (**Teams**) 部分或所有組織使用 Teams 模式](./setting-your-coexistence-and-upgrade-settings.md)
- **您的試驗沒有** 取得想要的結果，例如 (使用者滿意度和網路品質) 花一些時間調整您的計畫，然後重新檢查您的試驗。

> [!Tip]
> 將試驗參與者招募為同儕支援者，協助宣傳新使用者並加入 Teams。 同儕支援者可以輕鬆地與其他使用者聯繫、分享自己的體驗和學習，以及提供支援和指引給同事。 深入瞭解冠軍 [，](https://go.microsoft.com/fwlink/?linkid=859068) 以及如何在您自己的推出中使用它們。