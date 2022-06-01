---
title: 進行使用者試驗以評估及測試Microsoft Teams在貴組織中的運作方式
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 在您繼續使用商務用 Skype時，開始進行Microsoft Teams試驗以探索Teams可為貴組織提供的所有功能的指導方針
ms.localizationpriority: medium
ms.custom: Teams-upgrade-guidance
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae69bab918a9c8bd542e5ec70a95df7544677d8d
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823222"
---
# <a name="conduct-a-user-pilot"></a>舉辦使用者試驗

![升級旅程圖，醒目提示部署和實作。](media/upgrade-banner-deployment.png "升級旅程的階段，強調部署和實作階段")

本文是升級旅程中部署與實作階段的一部分，並分享執行有效試驗的深入資訊。 繼續進行之前，請確認您已完成下列活動：

- [呼叫專案專案專案關係人](upgrade-enlist-stakeholders.md)
- [定義您的專案範圍](./upgrade-define-project-scope.md)
- [瞭解商務用 Skype與Teams的共存及互通性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [已選擇您的升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [準備好您的環境](./upgrade-prepare-environment.md)
- [為您的組織做好準備](./upgrade-prepare-organization.md)

藉由部署新技術，您的組織可以實現企業價值，例如成本節省、安全性合規性、員工滿意度和營運效率，但也可能影響使用者的生產力和組織基礎結構， (您的網路) 。 啟用貴組織中的新技術之前，請先進行正式的使用者試驗。 就像在繪製整個房間之前在牆上繪製一個小修補色彩一樣，您會進行試驗以驗證技術和使用者整備狀態、找出並減輕問題，並協助確保整個組織順利實作，以較小的規模測試廣泛的推行。

若要獲得最實際的結果，試驗應讓實際使用者參與、模擬使用者的通訊和共同作業方式，以及驗證技術和使用者體驗。 無論貴組織考慮並排執行商務用 Skype和Teams、未來升級至Teams，或部署電話或會議等新功能，試驗都能協助找出貴組織的正確路徑。 有時會被視為推行階段 1，理想的試驗會運用您已開始的準備工作，並與目標使用者群組實作已定義的計畫。

|&nbsp; | &nbsp;|
|---|---|
| ![描述決策點的圖示。](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>您要如何使用試驗來告知專案方向？</li></ul> |
| ![描繪下一個步驟的圖示。](media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>請使用下列指導方針來設計和執行正式的試驗。</li></ul>|

> [!Tip]
> 使用範例 [試驗資源](https://aka.ms/UpgradeSuccessKit) 來協助設計您的通訊、測試計劃和意見反應問卷。

## <a name="1-outline-pilot-logistics"></a>1. 大綱試驗物流

成功的試驗已定義開始和結束日期，並 [明確定義](upgrade-define-project-scope.md#project-goals) 衡量成功的目標。 這些目標應與您更廣泛的專案範圍一致，如您 [定義專案範圍](upgrade-define-project-scope.md)時所記錄，並且會在試驗結束之後用來通知您前進的路徑。 您也應該確保在專案期間內包含正確的專案關係人。 您必須有足夠的時間執行試驗並評估其影響：建議您至少 30 天。

從小開始，並視需要新增試驗，不論是新增工作負載或功能，還是其他使用者，都可讓您有時間評估結果，並在您反覆運算時調整試驗。 您甚至可以選擇執行後續的試驗，因為新的Teams功能會根據藍圖發行。

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a>2. 選取您的試驗參與者並測試案例

試驗規劃最重要的工作之一，就是慎重選擇參與者。 請記住，Teams已針對團隊合作優化，因此請務必根據角色或角色選取試驗參與者，同時也根據其專案和跨小組工作來選取試驗參與者。 一個很好的起點是要求專案關係人和部門經理提供您可以在Teams中驗證的實際專案。 角色型專案的範例可能是將Teams與銷售組織搭配使用，以確保欄位代表可以輕鬆存取所需的資源，並與其他欄位成員分享深入解析。 以專案為基礎的工作範例可能正在與行銷、訓練、公關和活動規劃小組協調產品上市活動。 無論您選取哪種案例，試驗應該延伸到 IT、訓練和技術服務的重要人員，這樣您才能徹底驗證解決方案，同時完全優化專案管理資源。

> [!Tip]
> 選取Teams試驗群組參與者時，請務必包含商務用 Skype的熱門使用者。 請洽詢這些使用者以瞭解他們目前使用商務用 Skype的方式，然後建立測試計劃以確認Teams是否能符合他們目前的需求。

## <a name="3-design-your-test-plan-and-feedback-survey"></a>3. 設計您的測試計劃和意見反應問卷

若要獲得成功的試驗體驗，請讓參與者清楚定義完成的工作，並讓他們分享意見反應。 將工作分組在一起，為您的使用者提供實務案例，並示範其每日活動的相關性。 讓您在 [評估組織變更整備](./upgrade-org-change-readiness.md) 指南中定義的使用案例，引導測試計劃。

您的組織可能會選擇一次試驗所有功能，或是採用漸進式的方法，例如先試驗共同作業、會議，然後聊天和通話。 請確定您有開放的意見反應通道來追蹤進度並測量結果。 使用預先定義的問卷來輕鬆擷取及評估試驗結果;問卷設計應以測試方案中的案例和功能為基礎。

## <a name="4-create-your-communications-plan"></a>4. 建立通訊計畫

對於試驗的成功至關重要，您必須教育試驗參與者瞭解發生的情況、時間和原因，以及預期的結果。 若要推動興奮和最大參與度，除了訓練和支援的連結之外，也請務必包含使用者價值傳訊，讓使用者在試驗進行時取得其他資訊。 以下是一些可協助您開始使用試驗通訊方案的範例資源：

- [試驗資源](https://aka.ms/UpgradeSuccessKit)，包括電子郵件範本和範例意見反應問卷問題
- [從 商務用 Skype 切換到Teams](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964)，這是一份快速入門手冊，專門協助商務用 Skype使用者開始使用Teams

## <a name="5-conduct-your-pilot"></a>5. 進行試驗

所有物流都已就位，您現在可以開始進行試驗了。 進行試驗包括與您的使用者通訊、監控您的網路和使用狀況以確保您的網路效能和通話品質保持良好、收集參與者的意見反應，以及檢閱與Teams相關問題的技術服務票證。

### <a name="tips-for-pilot-success"></a>提示試驗成功

下列秘訣可協助確保試驗成功：

- 開始試驗之前，請確認已針對適當的 [共存模式] 啟用所有試驗參與者
- https://aka.ms/SkypeToTeams-SetCoexistence) (您想要驗證。
- 在整個試驗期間，每週與專案專案關係人會面，以檢閱使用者意見反應、使用狀況資料、網路資料和技術服務服務票證，以確保試驗順利執行。 視需要進行任何調整。

### <a name="suggested-timeline"></a>建議的時程表

以下是 30 天試驗的建議時程表：

- 試驗啟動前一周：傳送初始通訊給試驗使用者。
- 第 1 天：傳送啟動通訊給試驗使用者。
- 第 7 天：召開第一個每週專案小組檢查點會議。
- 第 14 天：傳送中點通訊給試驗使用者、召開每週專案小組檢查點會議。
- 第 21 天：召開每週專案小組檢查會議。
- 第 30 天：傳送最終通訊給試驗使用者。
- 第 31 至 45 天：評估試驗結果，並規劃後續步驟。

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a>6. 評估學習並評估您的後續計畫

試驗完成之後，就可以收集所有意見反應問卷、最終的網路統計資料和支援票證，以便針對您的目標進行分析，並判斷您是否會實作您的後續計畫。 您可能會發現貴組織已準備好進行廣泛的部署，或者您想要將試驗延伸至更多使用者，或想要在您發現的任何疑慮已減輕之後，于日後重新流覽試驗。 請記住，試驗是在 _受控_ 環境中預測技術和使用者結果的好方法;對於跳到太快，請考慮一下。

如果您的結果顯示：

- **您的試驗目標 (例如使用者滿意度和網路品質) 已經達成**，您應該準備好繼續進行下一個推行階段。 視專案目標而定，這可能為下列其中一項：
  - 將試驗延伸至其他參與者
  - [為部分或所有組織啟用Teams商務用 Skype (**群島** 模式)](./setting-your-coexistence-and-upgrade-settings.md)
  - [針對部分或所有組織，將使用者從商務用 Skype升級為僅 **限 Teams (Teams** Teams模式)](./setting-your-coexistence-and-upgrade-settings.md)
- **您的試驗未達到您想要的結果，例如使用者滿意度和網路品質) 等 (**，請花一些時間對計畫進行適當的調整，然後重新流覽試驗。

> [!Tip]
> 讓您的試驗參與者成為同儕之星，以協助傳送和上線新使用者以Teams。 同儕冠軍可以輕鬆地與其他使用者建立關係、分享自己的經驗和學習，以及提供支援和指引給同事。 深入瞭解 [冠軍](
https://adoption.microsoft.com/become-a-champion/) ，以及如何在您自己的推行中使用冠軍。