---
title: 終止對商務用 Skype Online 的支援
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 瞭解 Microsoft Online 的商務用 Skype方案，以及 Microsoft 如何協助客戶遷移到 Teams。
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f70378e2be1dd47126ee3d83009759c63643ae2f
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711757"
---
# <a name="skype-for-business-online-retirement"></a>終止對商務用 Skype Online 的支援

Microsoft 于 2021 年 7 月 31 日商務用 Skype Online。 我們于 2019 年 7 月宣佈將這項停用方案提前兩年通知客戶，以規劃升級至Microsoft Teams。 Teams是通訊和共同合作的核心應用程式，Microsoft 365。 隨著 商務用 Skype Online 的淘汰，Microsoft 想要確保客戶擁有必要的資訊和資源，以規劃並執行成功升級至 Teams。  消費者Skype服務不受此停用影響。

## <a name="why-is-skype-for-business-online-retiring"></a>為什麼線上商務用 Skype淘汰？

自推出以來，商務用 Skype Online 一直是全球數百萬人的寶貴工具。 結合立即訊息、通話和視訊，商務用 Skype為商務通訊提供了新的可能性。 Teams是該願景的下一個章節。  除了線上Microsoft Teams之外，商務用 Skype功能。 持續平臺創新與開發Teams使用者受益于更豐富的性能、功能、彈性和安全性。 將下列功能結合成單一體驗，Teams新的工作方式：

- 聊天
- 影片
- 通話
- 檔共同處理
- 應用程式整合

Teams線上版升級商務用 Skype更多。 這是一項功能強大的工具，可讓學校和組織變得更敏捷，並改善關鍵工作流程的效率。 進一Teams Forrester[™](https://www.microsoft.com/microsoft-365/blog/wp-content/uploads/sites/2/2019/04/Total-Economic-Impact-Microsoft-Teams.pdf?rtc=1)白皮書中，進一Microsoft Teams。

## <a name="organizations-with-skype-for-business-online"></a>使用線上商務用 Skype組織

Microsoft 提供輔助升級程式，以協助組織將剩餘的線上商務用 Skype移至Teams。 Teams商務和Microsoft 365方案Enterprise，現有的授權投資會繼續Teams。 目前在商務用 Skype Online 中是進階工作負載的功能，在 Teams 中依然是進階工作負載。 例如，如果您獨立購買音訊會議，或作為 E5 的一部分商務用 Skype，音訊會議將在 Teams 中啟用。

## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>擁有內部部署商務用 Skype Server

停用 商務用 Skype Online 不會影響對 商務用 Skype Server Lync Server 2013 內部部署的支援。 不過，混合使用線上和內部部署使用者混合的混合式客戶必須升級任何 *線上* 使用者。 這些線上使用者必須Teams TeamsUpgradePolicy 的僅模式。 Microsoft 提供輔助升級，以協助將線上使用者的剩餘商務用 Skype自動化為Teams模式。 由於這項停用，混合式組織商務用 Skype內部部署使用者移至雲端。 Microsoft 完全支援混合式組織，Teams使用者和內部部署使用者商務用 Skype混合式組織。 使用混合式部署 商務用 Skype Server Lync Server 2013 的客戶應審查停用 Online 商務用 Skype[的影響](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online)。

## <a name="what-to-expect-post-retirement"></a>退休後預期的結果

雲端使用者無法再指派 TeamsOnly 外的模式。 這表示：
 - 授權新使用者 (內部部署 商務用 Skype Server) 使用者除外，無論租使用者全域 TeamsUpgradePolicy 政策如何，系統都會自動指派使用者 TeamsOnly 模式。
 - 在混合式組織中，當使用者將內部部署使用者移往雲端時，系統會自動將使用者指派 TeamsOnly 模式 (`MoveToTeams` `Move-CsUser` 重新指定是否以 .) 
 - 位於雲端中的使用者 (例如不使用 商務用 Skype 伺服器內部部署) 無法指派除 Teams 模式。

客戶可能擁有其使用者人口的剩餘部分，這些使用者位於 商務用 Skype Online 中，且尚未Teams模式。  客戶應Teams指派僅模式給這些使用者。  此外，Microsoft 會針對未在 商務用 Skype 模式的使用者，提供Teams升級。  輔助升級體驗取決於您的組織是純粹線上組織，還是具有內部部署使用者商務用 Skype組織。  若要詳細資訊，請參閱從 商務用 Skype [Online Microsoft Teams](upgrade-assisted.md)。

輔助升級完成之後，所有 *線上* 使用者都會Teams模式。 在僅Teams模式中，使用者會收到來電和來電，Teams，並排程 Teams。 他們無法在線上啟動聊天或通話或商務用 Skype會議。  不過，Teams使用者商務用 Skype他們已有或未來收到的會議加入會議。 最後 *，內部部署的任何* 使用者都會維持內部部署，且不會Teams使用。


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Microsoft 如何協助客戶升級至 Teams

我們強烈建議您立即開始從 商務用 Skype Online Teams升級。

利用可用的資源，協助規劃您的Teams部署和 商務用 Skype升級：

- [Teams部署和升級檔](upgrade-start-here.md)- IT 系統管理員的免費技術指南。

- [Teams規劃](./upgrade-workshops-landing-page.yml)研討會 – 免費的互動式升級規劃研討會，您將在這裡獲得可協助規劃及實作升級至 Teams 的指引、最佳做法和資源。

- [協助從線上商務用 Skype](upgrade-assisted.md)升級Microsoft Teams - 可協助您將線上使用者升級至 商務用 Skype 的自動化Teams。

- [FastTrack適用于Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365) – Teams計畫可用的部署協助。

- [Teams即時訓練](./instructor-led-training-teams-landing-page.yml)– 免費線上訓練課程，專為讓貴組織在 Teams。

- [Teams粉](./chalk-talks-landing-page.yml)筆交談 – 適用于 IT 專業人員和決策者的免費線上研討會，這些研討會會針對 Teams 中的關鍵案例描述最佳做法。

- [Microsoft 合作夥伴](https://www.microsoft.com/solution-providers/home)- Microsoft 解決方案提供者可協助您充分利用Teams。

- [Microsoft Teams部落](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)格 – Teams新功能、採用和使用資源、Teams裝置，以及與其他商務應用程式整合等最新消息。

如果您是目前線上商務用 Skype，請立即開始規劃升級至Teams方案。 我們很高興您能夠體驗強大的通訊和共同合作功能，我們承諾一路協助。  若要進一步瞭解線上商務用 Skype，請參閱常見問題 - 從 商務用 Skype[升級Microsoft Teams](FAQ-journey.yml)。





