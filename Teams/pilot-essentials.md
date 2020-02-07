---
title: 使用商務用 Skype 試用 Microsoft 團隊 |部署、採納實現
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
audience: admin
description: 啟動 Microsoft 團隊試點專案的指導方針，以探索所有團隊都能在您繼續使用商務用 Skype 時提供您的組織。
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
ms.openlocfilehash: ec60beb606224a5b202a03187027b8e3e002dfd1
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833893"
---
![升級歷程圖表，醒目提示部署與實現](media/upgrade-banner-deployment.png "升級歷程階段，重點是部署與實施階段")

本文是您升級歷程的部署與實施階段的一部分，並分享深入的執行試驗。 繼續之前，請確認您已完成下列活動：

- [已登記您的專案干係人](upgrade-enlist-stakeholders.md)
- [已定義您的專案範圍](https://aka.ms/SkypetoTeams-Scope)
- [已瞭解商務用 Skype 與團隊的共存與互通性](https://aka.ms/SkypeToTeams-Coexist)
- [已選擇升級歷程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [準備好您的環境](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [準備好貴組織](https://aka.ms/SkypeToTeams-UserReadiness)

# <a name="conduct-a-user-pilot"></a>舉辦使用者試驗

透過部署新的技術，您的組織可以實現成本節約、安全性合規性、員工滿意度及運作效率等業務價值，但也會影響使用者的生產力與組織基礎結構（您的網路）。 在您的整個組織啟用新技術之前，請先執行正式的使用者試驗。 就像您在繪製整個聊天室前，在牆上繪製小的色彩片一樣，您可以執行試驗來驗證技術與使用者的就緒性、找出並減少問題，並協助確保成功全組織的實現。

若要達到最實際的結果，試驗應涉及實際的使用者、模仿其溝通與共同作業的方式，以及驗證技術與使用者體驗。 無論您的組織是考慮並排執行商務用 Skype 和團隊、日後升級至小組，或是部署通話或會議等新功能，試驗都能協助您為貴組織找出正確的路徑。 您有時會考慮推出的階段1，理想的試驗會利用您已開始的準備，並以目標使用者群組來實現您定義的方案。

| | |
|---|---|
| ![描述決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>您要如何使用試驗來通知專案方向？</li></ul> |
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>請使用以下指導方針來設計及執行您的正式試點。</li></ul>|

> [!Tip]
> 使用範例[試驗資源](https://aka.ms/UpgradeSuccessKit)，協助您設計通訊、測試計劃及意見反應問卷。

## <a name="1-outline-pilot-logistics"></a>1. 大綱試驗物流

成功的試驗已定義開始和結束日期，以及[明確定義](upgrade-define-project-scope.md#project-goals)的評估成功目標。 這些目標應該與您更多專案的範圍相符，就像您在[定義專案範圍](upgrade-define-project-scope.md)時所記錄的一樣，並將用來在您的試驗結束後通知您的路徑。 您也應該確定您已在專案工期中包含正確的專案關係人。 您可能會想要允許足夠的時間執行試驗並評估其影響：我們建議您至少30天。

開始小型，並視需要新增至您的試驗（無論是加入工作負載或功能或其他使用者），讓您在進行反覆運算時評估結果並調整您的試執行時間。 您甚至可以選擇執行後續的試點，因為我們會在每個藍圖中發佈新的團隊功能。

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a>2. 選取您的試點參與者和測試案例

最重要的試驗規劃工作之一是精心的參與者選擇。 請記住，小組已針對團隊合作進行優化，因此請務必自行根據角色或角色選取試驗參與者，但也要根據其專案和小組工作來進行。 最適合開始的地方是向您的風險承擔者和部門經理要求您可以在小組中驗證的真實專案。 角色式專案的範例可能是將團隊與您的銷售組織搭配使用，以確保欄位代表能輕鬆存取他們所需的資源，並與其他欄位成員共用見解。 以專案為基礎的工作範例，就是將產品啟動活動與行銷、訓練、公用關係及活動規劃小組協調。 無論您所選的是哪一種情況，試驗都應該延伸至 IT 中的主要人員、訓練及您的支援人員，讓您可以在充分優化專案管理資源的同時，全面驗證方案。

> [!Tip]
> 選取您的小組試點群組參與者時，請務必包含商務用 Skype 的最上層使用者。 請諮詢這些使用者，瞭解他們目前如何使用商務用 Skype，然後組建一個測試方案，以確認團隊能滿足其目前的需求。

## <a name="3-design-your-test-plan-and-feedback-survey"></a>3. 設計您的測試方案與意見反應問卷

若要取得成功的試驗體驗，請為參與者提供明確定義的工作，並將其與他們分享意見反應的方式共同作業。 將任務組成群組，為您的使用者提供真實世界的案例，示範其日常活動的關聯性。 讓您在[評估組織變更準備](https://aka.ms/OrgReadiness)指南中定義的使用案例，瞭解您的測試方案。

貴組織可以選擇一次試驗所有功能，或使用逐步式方法，例如，先進行先導共同作業，然後再進行聊天與通話。 確定您有已開啟的意見反應頻道，以追蹤進度及測量結果。 使用預先定義的問卷來輕鬆捕獲和評估試點結果;問卷設計應根據測試方案中的案例和功能而定。

## <a name="4-create-your-communications-plan"></a>4. 建立通訊方案

您對試驗的成功至關重要，那就是您可以讓試點參與者掌握所發生的問題、時間和原因，以及它們的預期。 若要推動感興趣和最大的參與，請務必包含使用者價值訊息，以及使用者在逐步完成試驗時可取得其他資訊的訓練與支援的連結。 以下是一些可讓您開始使用試驗通訊方案的範例資源：

- [試驗資源](https://aka.ms/UpgradeSuccessKit)，包括電子郵件範本和樣本意見問卷調查問題
- [從商務用 Skype 切換至 [小組](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964)]，這是一種快速入門手冊，可協助商務用 skype 使用者開始使用團隊

## <a name="5-conduct-your-pilot"></a>5. 進行試驗

完成所有物流之後，您就可以開始進行試驗了。 您的試驗包括與您的使用者進行通訊、監控您的網路與使用狀況，以確保您的網路效能和通話品質保持正常、收集參與者的意見反應，以及查看技術支援人員的相關問題協同.

### <a name="tips-for-pilot-success"></a>試驗成功的秘訣

下列秘訣可協助確保您的試驗成功：

- 開始試用之前，請確認所有試點參與者都已啟用適當的 [共存模式]
- （https://aka.ms/SkypeToTeams-SetCoexistence)您想要驗證。
- 每週，在整個試驗期間，與您的專案干係人見面，以查看使用者的意見反應、使用方式資料、網路資料和技術支援人員，以確保您的試點程式順暢運作。 視需要進行調整。

### <a name="suggested-timeline"></a>建議的時程表

以下是30天試用版的建議時程表：

- 試生產動員前的一周：傳送初始通訊至試驗使用者。
- 第1天：將動員會通訊傳送給試驗使用者。
- 第7天：保留第一周的專案小組檢查點會議。
- 第14天：傳送中間點溝通給您的試驗使用者，請按住每週專案小組檢查點會議。
- 第21天：保留每週專案小組檢查點會議。
- 第30天：傳送最終的通訊給您的試驗使用者。
- Days 31 至45：評估試運行結果，並規劃後續步驟。

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a>6. 評估學習專案並評估您的轉寄方案

完成試驗之後，就可以收集所有意見反應問卷、最終的網路統計資料，以及針對您的目標進行分析的支援入場券，判斷是否要實施您的轉寄方案。 您可能會發現貴組織已準備好進行廣泛的部署，或者您想要將您的試驗延伸到更多使用者，或者您想要在您發現的任何問題遭到緩解之後，日後再重新查看試用版。 請記住，您的試驗是在_可控_環境中預測技術與使用者結果的絕佳方式。小心地提前跳躍了。

如果您的結果指出：

- **您的試驗目標（例如，使用者滿意度和網路品質）** 已經完成，您應該準備好繼續進行下一階段的推出。 根據專案的目標，這可能是下列其中一項：
  - 將試生產延伸至其他參與者
  - [針對部分或所有組織啟用團隊與商務用 Skype （**孤島**模式）](https://aka.ms/SkypeToTeams-SetCoexistence)
  - [從商務用 Skype 將使用者升級至小組（**僅限團隊**模式），適用于部分或所有組織](https://aka.ms/SkypeToTeams-SetCoexistence)
- **您的試用版並未達到您想要的結果（例如，使用者滿意度和網路品質）**，請花一些時間來調整方案的適當調整，並重新取得您的試用版。

> [!Tip]
> 登記您的試點參與者作為對等擁護者，協助 evangelize 及將新使用者新增至團隊。 對等擁護者可以輕鬆與其他使用者、共用自己的體驗與學習專案，以及為其同事提供支援與指導方針。 深入瞭解[擁護](https://go.microsoft.com/fwlink/?linkid=859068)程式，以及如何在您自己的推出中使用它們。
