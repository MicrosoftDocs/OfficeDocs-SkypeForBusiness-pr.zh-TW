---
title: 終止對商務用 Skype Online 的支援
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 瞭解 商務用 Skype Online 的淘汰計畫，以及 Microsoft 如何協助客戶移轉至 Teams。
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
ms.openlocfilehash: 13d7032c78a7863b46bb186553b0b67e67f8c626
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494490"
---
# <a name="skype-for-business-online-retirement"></a>終止對商務用 Skype Online 的支援

Microsoft 已于 2021 年 7 月 31 日淘汰 商務用 Skype Online。 我們于 2019 年 7 月宣佈淘汰，為客戶提前兩年通知他們規劃升級至 Microsoft Teams。 Teams 是 Microsoft 365 中用於通訊和共同作業的核心應用程式。 由於已淘汰 商務用 Skype Online，Microsoft 想要確保客戶擁有規劃並成功升級至 Teams 所需的資訊和資源。  Skype 消費者服務不會受到此淘汰的影響。 如需商務用 Skype Online 停用原因的背景資訊，請參閱[常見問題- 從 商務用 Skype 升級至 Microsoft Teams](FAQ-journey.yml)。

Microsoft 將于 2022 年 6 月 30 日或之後開始解除委任 商務用 Skype Online 基礎結構。 本文包含有關使用 Teams 的組織從任何版本升級商務用 Skype使用者的指導方針。


## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>部署內部部署 商務用 Skype Server 的組織

商務用 Skype Online 的淘汰不會影響商務用 Skype Server和 Lync Server 2013 內部部署的支援。 不過，混合式客戶以及在線上和內部部署的使用者必須升級任何 *線上* 使用者。 任何線上使用者都必須使用 TeamsUpgradePolicy 指派 TeamsOnly 模式。 Microsoft 提供協助升級，以協助將剩餘的 商務用 Skype Online 使用者升級至 TeamsOnly 模式。 由於此淘汰，混合式組織不需要將其 *內部部署* 商務用 Skype使用者移至雲端。 Microsoft 完全支援混合式組織與 TeamsOnly 使用者和內部部署商務用 Skype使用者。 擁有 商務用 Skype Server 或 Lync Server 2013 混合式部署的客戶應檢閱[商務用 Skype Online 的淘汰。](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online)

在您的內部部署的 Active Directory環境中建立新使用者時，如果這些使用者將同步處理到 Azure AD，而您打算授權他們使用 Teams，那麼 *在指派授權給這些使用者之前*，**您必須先在您的內部部署商務用 Skype部署中啟用這些使用者，並確保變更已透過 Azure AD 連線同步到雲** 端。  您可以使用 Get-CsOnlineUser 確認變更已完全同步處理至雲端。 如果使用者的 HostingProvider= 「SRV：」，則此變更已同步處理。  這不應該是「sipfed.online.lync.com」。   

## <a name="what-to-expect-post-retirement"></a>淘汰後會發生什麼事

雲端中的使用者無法再被指派 TeamsOnly 以外的模式。 這表示：

 - 授權非內部部署商務用 Skype Server的新使用者時，無論租使用者的 TeamsUpgradePolicy 全域原則為何，使用者都會自動獲派 TeamsOnly 模式。
 - 在混合式組織中，將內部部署使用者移至雲端時，無論是否在 `Move-CsUser` 中指定切換，系統都會 `MoveToTeams` 自動指派使用者 TeamsOnly 模式。
 - 位於雲端的使用者無法被指派 TeamsOnly 以外的模式。 在線上的使用者 *不會* 在內部部署使用商務用 Skype伺服器。

客戶可能還有其他在 商務用 Skype Online 中且尚未獲指派 TeamsOnly 模式的使用者。 客戶應儘快將 TeamsOnly 模式指派給這些使用者。 Microsoft 會為不在 TeamsOnly 模式的 商務用 Skype Online 使用者提供協助升級。 輔助升級體驗取決於您的組織是純粹線上組織，還是內部部署商務用 Skype使用者的組織。 如需詳細資訊，請參閱[協助從 商務用 Skype Online 升級至 Microsoft Teams](upgrade-assisted.md)。

完成協助升級之後，所有 *線上* 使用者都會處於 TeamsOnly 模式。 Teams 中的使用者在 Teams 中能在 Teams 中接收來電交談和通話，也可以在 Teams 中排程會議。 他們無法在 商務用 Skype Online 中啟動聊天、通話或排程會議。  不過，TeamsOnly 使用者可以加入他們未來已經或接收商務用 Skype會議。 最後， *任何內部部署的使用者都會保持在內部部署狀態，而且不會成為 TeamsOnly*。

## <a name="actions-to-take-before-june-30-2022"></a>2022 年 6 月 30 日之前要採取的動作
現在 商務用 Skype Online 已停用，Microsoft 將于 2022 年 6 月 30 日開始解除支援基礎結構。  對於任何使用 Teams 的組織從任何版本的 商務用 Skype 升級的使用者，如果其中一種情況適用，您必須採取動作：

- 如果您有任何 TeamsOnly 使用者在 商務用 Skype 中有連絡人，*且* 自升級以來尚未登入 Teams 的使用者。
- 如果您有任何 TeamsOnly 使用者在升級至 Teams 之前，仍然商務用 Skype他們召集的線上會議。

如果其中一種情況適用于您的組織，您必須在 2022 年 6 月 30 日之前採取行動，如下所述：

 - **商務用 Skype線上連絡人：** 在使用者升級至 TeamsOnly 模式之後，使用者第一次登入 Teams 時，該使用者商務用 Skype Online 帳戶中的任何現有連絡人都會移轉到 Teams。 Microsoft 移除商務用 Skype線上基礎結構之後，您就無法再移轉 *尚未登入 Teams 之使用者的連絡人。* 若要將連絡人從商務用 Skype移轉至 Teams，Microsoft 建議先前商務用 Skype登入 Teams 的所有使用者至少一次，再于 2022 年 6 月 30 日之前登入。

 - **商務用 Skype線上會議：** 將組織升級至 TeamsOnly 之後，使用者會將所有新會議建立為 Teams 會議。 在某些情況下，TeamsOnly 使用者可能仍有商務用 Skype先前召集的線上會議。 目前，已升級 TeamsOnly 使用者和任何受邀的出席者都可以使用其商務用 Skype用戶端加入這些商務用 Skype線上會議。 Microsoft 移除指定 Teams 的商務用 Skype線上基礎結構之後，使用者召集的任何剩餘商務用 Skype線上會議將不再存在。 召集人和任何出席者將無法加入這些會議。 如果 Teams 中的使用者在組織中還有任何他們召集的商務用 Skype線上會議，Microsoft 建議他們將這些會議重新排程為 Teams 會議。 或者，系統管理員也可以使用 [會議移轉服務](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet) ，將這些會議轉換為 Teams 會議。 無論哪種情況，請在 2022 年 6 月 30 日之前完成這些動作。  


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Microsoft 如何協助客戶升級至 Teams

我們強烈建議您立即開始從 商務用 Skype Online 升級至 Teams。 善用可用的資源來協助規劃您的 Teams 部署和從 商務用 Skype 升級：

- [Teams 部署和升級檔](upgrade-start-here.md) – 適用于 IT 系統管理員的免費技術指導方針。

- [Teams 升級規劃研討會](./upgrade-workshops-landing-page.yml) - 免費的互動式升級規劃研討會，您會在這裡收到指引、最佳做法，以及專為協助您規劃及實作升級至 Teams 所設計的資源。

- [協助從 商務用 Skype Online 升級至 Microsoft Teams](upgrade-assisted.md) – 協助您將 商務用 Skype Online 使用者升級至 Teams 的自動化計畫。

- [適用于 Microsoft 365 的 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) – 適用于合格方案的 Teams 部署協助。

- [Teams 即時訓練](./instructor-led-training-teams-landing-page.yml) – 免費的線上訓練課程，專為讓您的組織使用 Teams 而設計。

- [Teams 粉筆交談](./chalk-talks-landing-page.yml) – 適用于 IT 專業人員和決策者的免費線上研討會，說明 Teams 中重要案例的最佳做法。

- [Microsoft 合作夥伴](https://www.microsoft.com/solution-providers/home) – Microsoft 解決方案提供者可協助您充分利用 Teams。

- [Microsoft Teams 部落格](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) – Teams 新功能、採用與使用資源、Teams 裝置，以及與其他商務應用程式整合的相關消息。

如果您是目前商務用 Skype線上客戶，請立即開始規劃升級至 Teams。 我們很高興您能夠體驗其強大的通訊和共同作業功能，並致力於提供協助。  如需有關 商務用 Skype Online 淘汰的詳細資訊，請參閱[常見問題- 從 商務用 Skype 升級至 Microsoft Teams](FAQ-journey.yml)。





