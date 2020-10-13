---
title: Microsoft 團隊的管理快速入門
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: karuanag
localization_priority: Normal
search.appverid: MET150
description: '[快速入門] 涵蓋您在 Microsoft 團隊採用方案中需要進行的主要決策。'
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
ms.openlocfilehash: cd54902e00e984de740b7bbf6d0fd96e37e88aa9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424553"
---
# <a name="governance-quick-start-for-microsoft-teams"></a>Microsoft 團隊的管理快速入門

下列活動將會同時發生，而且它們可能會涉及全部或部分重要小組。 最佳做法是，在您使用團隊完成初次實驗之後，推遲大型規模的管理和安全性交談。 瞭解管轄性決定可能會如何影響最終使用者體驗，並將簡化您在該日後所需作出的決策。 在此階段中，需要進行一些決策。 若要成功進行，您必須先回答下列問題：

- 您先前評等的風險承擔者很適合參與此有限的商務用電腦？
- 有這個個別 (或一組人員) 建議的使用案例，適合這個階段嗎？  
- 他們是否有足夠的興趣，讓組織中的員工能成為早期的人員，並提供有意義且週期性意見反應？ 

若要深入瞭解，請閱讀 [小組中的管轄方案](plan-teams-governance.md) ，並 [規劃團隊中的週期管理](plan-teams-lifecycle.md)。

## <a name="an-icon-representing-a-decision-pointdecisions"></a>![代表決策點的圖示](media/teams-adoption-decision-icon.png)判斷

進行下列決策 (此時，這些決策只適用于階段 2) ：

### <a name="decision-1-who-can-create-teams"></a>決策1：可以建立團隊的人員 

針對此階段的用途，您可以限制誰能夠建立小組，除了您的核心專案小組以外。 這可讓您的早期採納者視需要建立其他團隊。 監控此行為會為您的廣泛部署提供重要資訊。

### <a name="decision-2-teams-naming-conventions"></a>決策2：團隊命名慣例 

您可能會想要針對大量的小組部署執行一些命名慣例，並檢查重複的名稱。 在階段2中，我們建議您只為初始專案實現手動命名慣例。 此做法的最佳做法是向先期消費者專案團隊進行互動式加入，並允許他們選取自己的名稱。 這可讓您深入瞭解員工如何思考其工作，並在日後建立較大的規模命名慣例。 本指南稍後會顯示有關互動式加入的元素 (其他資訊。 ) 

### <a name="decision-3-guest-access"></a>決策3：來賓存取

根據您專案的範圍與類型和行業的性質，啟用與合作夥伴或供應商的安全共同作業可能是您想要測試的重要功能。 您可以使用適當的租使用者控制項，限制哪些人可以將客人新增給小組，並使用敏感度標籤限制哪些團隊開啟給來賓。 您也可以確保來賓遵守組織的安全性需求，例如使用多重要素驗證 (MFA) 。

### <a name="decision-4-approved-apps"></a>決策4：已核准的 app

小組的最佳使用方式包括將其他 app 整合至體驗中。 您最少的技術小組應該在您的小組體驗中啟用第一方和主要 app。 視您的使用案例和貴組織中使用的其他應用程式而定，您可以加入宣告其他 app 作為您控制的實驗的一部分。 請務必 vet 任何協力廠商應用程式，以確保它們符合貴組織的安全性和合規性需求。

### <a name="decision-5-are-meetings-included-in-your-test"></a>決策5：您的測試中是否包含會議？ 

[團隊會議體驗] 是高品質、支援視頻聊天，且能讓員工更有效率。 諮詢您的技術小組，確認您的環境已準備好加入簡單的 VoIP 會議。 啟用音訊會議或語音服務，將會在您的實驗中排除此階段;不過，這取決於您的核心專案小組、您的技術準備，以及貴組織中其他語音/會議服務的狀態。 技術就緒應包括會議室設備、使用者裝置和附屬件等專案，以及網路。 我們建議您在實驗中包含影片聊天和 VoIP 會議，以從您的小組實施中取得更大的價值。 

### <a name="decision-6-content-management-and-structure"></a>決策6：內容管理與結構
當使用者在平臺內進行端對端工作時，最適合使用團隊，而不是要求他們連續切換回舊版系統和服務，並提供與使用者熟悉的方式不同的新方法。 在您的實驗中，請與您的參與者共同考慮在團隊中採用多種模式方式的小組結構和頻道，避免直接複製現有的資料夾和儲存結構。 此外，請考慮任何儲存在現有支援系統（例如記錄管理或備份系統）之外之內容的合規性需求。

### <a name="decision-7--data-security"></a>決策7：資料安全性

為您廣泛的部署準備，您可以選擇使用 [安全標籤] 來將您環境中的小組類型分類。 針對本次實驗的目的，我們建議您參考 [小組中的管轄規劃](plan-teams-governance.md) ，並確保已針對 Microsoft 365 中的小組資料設定基本的保留原則。 您可能需要將此工作與技術小組協調，因為需要 Microsoft 365 系統管理員許可權才能完成此作業。

### <a name="decision-8-length-of-your-experiment"></a>決策8：實驗的長度

成功的團隊實現會以良好的速度進行，以確保適當的動量、焦點及學習專案。 我們建議您專案的這個階段為60天，以確保您的早期消費者能完成足夠的商務週期。 延長太長時間的實驗會增加變更計畫失敗的風險;不過，這次會因每個組織而異。  

![代表下一個步驟的圖示 ](media/teams-adoption-next-icon.png) ： [定義使用案例](teams-adoption-define-usage-scenarios.md)
