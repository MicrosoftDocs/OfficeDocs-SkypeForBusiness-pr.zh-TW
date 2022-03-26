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
ms.openlocfilehash: dcd2148a3f939bd8799b7b3f8b86118359936b7c
ms.sourcegitcommit: d3d3d5a70a69359fc71f072ad6c651556f4eda00
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2022
ms.locfileid: "63783902"
---
# <a name="skype-for-business-online-retirement"></a>終止對商務用 Skype Online 的支援

Microsoft 于 2021 年 7 月 31 日商務用 Skype Online。 我們于 2019 年 7 月宣佈將這項停用方案提前兩年通知客戶，以規劃升級至Microsoft Teams。 Teams是通訊和共同合作的核心應用程式，Microsoft 365。 隨著 商務用 Skype Online 的淘汰，Microsoft 想要確保客戶擁有必要的資訊和資源，以規劃並執行成功升級至 Teams。  Skype消費者服務不受此停用影響。 若要瞭解為何商務用 Skype Online，請參閱[常見問題 -](FAQ-journey.yml)從 商務用 Skype 升級Microsoft Teams。

Microsoft 將于 2022 年 6 月 30 商務用 Skype開始解除授權線上基礎結構。 本文包含已從任何版本升級之 TeamsOnly 使用者商務用 Skype。


## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>擁有內部部署商務用 Skype Server

線上版 商務用 Skype的停用不會影響對 商務用 Skype Server Lync Server 2013 內部部署的支援。 不過，混合使用線上和內部部署使用者混合的混合式客戶必須升級任何 *線上* 使用者。 任何線上使用者都必須使用 TeamsUpgradePolicy 指派 TeamsOnly 模式。 Microsoft 提供輔助升級，以協助將線上商務用 Skype升級至 TeamsOnly 模式。 由於這項停用，混合式組織商務用 Skype內部部署使用者移至雲端。 Microsoft 完全支援混合使用 TeamsOnly 使用者和內部部署使用者商務用 Skype組織。 使用混合式部署 商務用 Skype Server Lync Server 2013 的客戶應審查停用[商務用 Skype Online](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online)。

## <a name="what-to-expect-post-retirement"></a>退休後預期的結果

雲端使用者無法再指派 TeamsOnly 外的模式。 這表示：

 - 在授權未位於內部部署 商務用 Skype Server 的新使用者時，系統會自動指派使用者 TeamsOnly 模式，無論租使用者對 TeamsUpgradePolicy 的全域原則如何。
 - 在混合式組織中，將內部部署使用者移轉至雲端時，系統會自動將使用者指派 TeamsOnly `MoveToTeams` 模式，無論切換是在 中指定 `Move-CsUser` 。
 - 雲端使用者無法指派 TeamsOnly 外的模式。 家用線上使用者 *不會商務用 Skype* 內部部署伺服器。

客戶可能擁有目前位於 商務用 Skype，且尚未指派 TeamsOnly 模式的剩餘使用者。 客戶應儘快指派 TeamsOnly 模式給這些使用者。 Microsoft 將針對不在 TeamsOnly 商務用 Skype Online 使用者提供輔助升級。 輔助升級體驗取決於您的組織是純粹線上組織，還是具有內部部署使用者商務用 Skype組織。 若要詳細資訊，請參閱從 商務用 Skype [Online Microsoft Teams](upgrade-assisted.md)。

輔助升級完成後，所有 *線上* 使用者將進入 TeamsOnly 模式。 TeamsOnly 模式中的使用者會以通話方式Teams傳入聊天和Teams。 他們無法啟動聊天或通話，或排程線上商務用 Skype會議。  不過，TeamsOnly 使用者可以加入商務用 Skype或未來收到的會議。 最後，任何內部部署的使用者都維持在內部部署，且 *不會成為 TeamsOnly*。

## <a name="actions-to-take-before-june-30-2022"></a>2022 年 6 月 30 日之前要採取的行動
現在，商務用 Skype線上已停用，Microsoft 將于 2022 年 6 月 30 日開始停用支援基礎結構。  對於從任何版本升級的 TeamsOnly 使用者的任何組織商務用 Skype，如果發生以下任一情況，您必須採取動作：

- 如果您擁有任何 TeamsOnly 使用者，這些使用者在 商務用 Skype 中具有連絡人，且使用者尚未登入Teams升級之後。
- 如果您擁有任何 TeamsOnly 使用者，商務用 Skype升級至 TeamsOnly 之前，他們組織的線上會議。

如果上述任一情況適用于貴組織，您必須在 2022 年 6 月 30 日前採取行動，如下所示：

 - **商務用 Skype線上** 連絡人：將使用者升級至 TeamsOnly 模式之後，使用者第一次登到 Teams 時，該使用者 商務用 Skype Online 帳戶中的任何現有連絡人都會移至 Teams。 Microsoft 移除線上基礎結構商務用 Skype之後，您無法再將尚未登入使用者的連絡人移Teams *。* 若要將連絡人從 商務用 Skype Teams，Microsoft 建議所有先前商務用 Skype的使用者在 2022 年 6 月 30 Teams 之前至少登入一次。

 - **商務用 Skype線上會議**：將組織升級至 TeamsOnly 之後，使用者會以會議Teams會議。 在某些情況下，TeamsOnly 使用者可能商務用 Skype之前組織的線上會議。 目前，已升級的 TeamsOnly 使用者和任何受邀的出席者都可以商務用 Skype他們的用戶端加入這些商務用 Skype會議。 不過，在 Microsoft 移除商務用 Skype TeamsOnly 使用者的線上基礎結構之後，該使用者商務用 Skype線上會議的任何剩餘內容將不再存在。 召集人和任何出席者將無法加入這些會議。 如果 TeamsOnly 組織中使用者商務用 Skype線上會議，Microsoft 建議您將這些會議重新排定為Teams會議。 或者，系統管理員可以使用會議移轉[服務](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet)將這些會議轉換成Teams會議。 在這兩種情況下，請于 2022 年 6 月 30 日完成這些動作。  


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Microsoft 如何協助客戶升級至 Teams

我們強烈建議您立即開始從 商務用 Skype Online Teams升級。 利用可用的資源，協助規劃您的Teams部署和 商務用 Skype升級：

- [Teams部署和升級檔](upgrade-start-here.md)- IT 系統管理員的免費技術指南。

- [Teams規劃](./upgrade-workshops-landing-page.yml)研討會 – 免費的互動式升級規劃研討會，您將在這裡獲得可協助規劃及實作升級至 Teams 的指引、最佳做法和資源。

- [協助從線上商務用 Skype](upgrade-assisted.md)升級Microsoft Teams - 可協助您將線上使用者升級至 商務用 Skype 的自動化Teams。

- [FastTrack適用于Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365) – Teams計畫可用的部署協助。

- [Teams即時訓練](./instructor-led-training-teams-landing-page.yml)– 免費線上訓練課程，專為讓貴組織在 Teams。

- [Teams粉](./chalk-talks-landing-page.yml)筆交談 – 適用于 IT 專業人員和決策者的免費線上研討會，這些研討會會針對 Teams 中的關鍵案例描述最佳做法。

- [Microsoft 合作夥伴](https://www.microsoft.com/solution-providers/home)- Microsoft 解決方案提供者可協助您充分利用Teams。

- [Microsoft Teams部落](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)格 – Teams新功能、採用和使用資源、Teams裝置，以及與其他商務應用程式整合等最新消息。

如果您是目前線上商務用 Skype，請立即開始規劃升級至Teams方案。 我們很高興您能夠體驗強大的通訊和共同合作功能，我們承諾一路協助。  若要進一步瞭解線上商務用 Skype，請參閱[常見問題 -](FAQ-journey.yml)從 商務用 Skype 升級Microsoft Teams。





