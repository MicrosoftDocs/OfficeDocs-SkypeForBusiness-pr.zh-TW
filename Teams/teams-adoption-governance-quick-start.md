---
title: 管理快速入門Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: karuanag
ms.localizationpriority: medium
search.appverid: MET150
description: 快速入門，涵蓋您為採用計畫的第 2 階段Microsoft Teams決策。
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eaeec25c90e800fcc688dad924ecac8de687841a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733712"
---
# <a name="governance-quick-start-for-microsoft-teams"></a>管理快速入門Microsoft Teams

下列活動會同時進行，而且可能涉及您所有或部分的關鍵小組。 最佳做法是在您完成初始實驗之後，延後進行大規模的管理和安全性Teams。 請務必瞭解管理決策會對使用者體驗造成什麼影響，並簡化您稍後需要做出的決策。 在這個階段中，有一些決策需要做出。 若要成功完成這些工作，您首先必須回答下列問題：

- 您先前評定的哪一位專案關係人是參與此有限業務入門的好人選？
- 此個人或 (群組是否) 適合此階段使用的建議使用案例？  
- 他們的組織員工是否有足夠的興趣做為早期採用者，並給予您有意義且週期性意見回饋？ 

若要深入瞭解，請參閱在[](plan-teams-governance.md)Teams 中的管理計畫及生命週期[管理Teams。](plan-teams-lifecycle.md)

## <a name="an-icon-representing-a-decision-pointdecisions"></a>![代表決策點的圖示。](media/teams-adoption-decision-icon.png)決定

此時，請 (做出下列決策，這些決策僅適用于階段 2) ：

### <a name="decision-1-who-can-create-teams"></a>決策 1：神秘團隊 

為了這個階段的目的，除了核心專案小組之外，您還可以將誰能夠建立團隊限制到早期採用者人口。 這可允許您的初期採用者建立額外的團隊 。如果需要的話。 監控此行為會提供您廣泛部署的重要資訊。

### <a name="decision-2-teams-naming-conventions"></a>決策 2：Teams命名慣例 

您可能想要針對您的廣泛部署專案，執行一些命名Teams，並檢查重複的名稱。 在第 2 階段中，我們建議您只針對初始專案執行手動命名慣例。 最佳作法是與早期採用者專案小組進行互動式的上線，並允許他們選取自己的名稱。 這可深入說明員工對工作的想法，對於日後建立較大規模的命名慣例至關重要。  (本指南稍後會提供互動式上線元素的其他資訊。) 

### <a name="decision-3-guest-access"></a>決策 3：來賓存取

根據您專案的範圍和類型以及產業性質，與合作夥伴或廠商進行安全共同合作可能是您想要測試的一項必要功能。 您可以使用適當的租使用者控制項來限制誰可以新增來賓至團隊，以及使用敏感度標籤來限制哪些團隊會向來賓開放。 此外，您也可以確保來賓遵守組織安全性需求，例如使用多重要素驗證或 MFA (MFA) 。

### <a name="decision-4-approved-apps"></a>決策 4：核准的應用程式

應用程式的最佳Teams包括將其他應用程式整合到體驗中。 您的技術小組至少應啟用您體驗中第一方和精選Teams應用程式。 視您的使用案例和貴組織中所使用的其他應用程式不同，您可以選擇將其他 App 納入您控管實驗的一部分。 請務必檢查任何協力廠商應用程式，以確保其符合貴組織的安全性與合規性需求。

### <a name="decision-5-are-meetings-included-in-your-test"></a>決策 5：測試是否包含會議？ 

會議Teams品質高、支援視音訊聊天，並提升員工效率。 請詢問您的技術小組，確定您的環境已準備好包含簡單的 VoIP 會議。 啟用音訊會議或語音服務一般會排除在實驗的這個階段;不過，這取決於您的核心專案小組、您的技術準備狀態，以及貴組織中其他語音/會議服務的狀態。 技術準備應包含會議室設備、使用者裝置和配件，以及網路等專案。 我們建議您在實驗中包含視像聊天和 VoIP 會議，以從您的Teams中取得更多價值。 

### <a name="decision-6-content-management-and-structure"></a>決策 6：內容管理和結構
Teams使用者在平臺內進行端對端作業時效果最佳，而不是要求他們持續切換回舊版系統和服務，並提供與使用者習慣不同的新工作方式。 做為實驗的一部分，請與參與者合作，考慮採用 Teams 內多模式共同作業方式的團隊結構和頻道，並避免複製現有的資料夾和儲存結構。 此外，請考慮儲存在現有支援系統以外內容的任何合規性需求，例如記錄管理或備份系統。

### <a name="decision-7--data-security"></a>決策 7：資料安全性

在準備進行廣泛部署時，您可以選擇使用安全性標籤來分類環境中的團隊類型。 基於此實驗的目的，建議您參閱[Teams](plan-teams-governance.md)中的管理計畫，並確保已針對 Teams 資料設定基本保留原則Microsoft 365。 您可能需要與技術小組協調這項工作，Microsoft 365系統管理員許可權才能完成這項工作。

### <a name="decision-8-length-of-your-experiment"></a>決策 8：實驗的長度

成功Teams以健康的速度進行，以確保適當的動力、專注和學習。 我們建議您專案的這個階段長度為 60 天，以確保您的早期採用者完成足夠的商務週期。 延長實驗時間過長會增加變更計畫失敗的風險;不過，這一次會因每個組織而異。  

![代表下一個步驟的圖示。](media/teams-adoption-next-icon.png) 下一 [步：定義使用案例](teams-adoption-define-usage-scenarios.md)
