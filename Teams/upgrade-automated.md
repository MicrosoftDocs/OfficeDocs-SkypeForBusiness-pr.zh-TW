---
title: 自動升級|Skype Business 升級至 Teams
author: serdarsoysal
ms.author: billkau
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: 從商務用 Skype 升級到 Teams 的自動化升級概觀
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb3fef455e4031c61b6769e114d9cbd1d8bd3805
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120537"
---
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>從商務用 Skype Online 自動升級至 Microsoft Teams

Microsoft 提供 Teams 的自動化升級，協助小型企業在 2021 年 7 月 31 日服務結束之前，順利從商務用 Skype Online 進行轉換。 自動升級可以減少客戶所需的技術工作數量，並更專注于組織準備、使用者認知和 Teams 訓練。

從商務用 Skype 成功升級至 Microsoft Teams 需要規劃技術和使用者準備。 當您準備好開始使用時，Microsoft 會提供升級行動計畫，[](upgrade-basic.md)提供核心建議活動和相關資源，以成功從商務用 Skype 移至 Teams。

## <a name="notifications-for-scheduled-customers"></a>已排程客戶的通知

符合自動升級 Teams 資格的商務用 Skype Online 客戶，將在排定的升級日期前 30 天收到一系列的升級通知。 這些通知會以系統管理訊息中心中的變更文章計畫、將電子郵件升級至全域系統管理員，以及將應用程式內標標傳送給使用者。

這些通知會傳達自動升級的排程日期、連結至升級資源與訓練，協助推動 Teams 的採用和使用，並讓客戶選擇在未準備好在預定日期之前再延後 30 天進行自動升級。

## <a name="the-automated-upgrade-experience"></a>自動升級體驗

自動升級會于排定的升級日期執行，此日期會傳送至通知電子郵件、訊息中心，以及 Teams 系統管理入口網站。 升級大約需要 15 分鐘，在此期間，使用者仍可存取商務用 Skype Online 功能。 升級完成後，使用者登出商務用 Skype Online 後，使用者只能使用 Teams 進行傳訊、會議和通話。

## <a name="the-post-upgrade-experience"></a>升級後的體驗

當您的自動升級完成時，共存模式會設定為僅 Teams，且 Microsoft 只能變更為不同的共存模式。 系統管理員在升級之前，應 [先審查 Teams](teams-only-mode-considerations.md) Only 模式考慮事項。 下表提供 Teams Only 使用者體驗的高層次概觀。


|  |  |
|---------|---------|
|**聊天和通話**     | <UL><LI>在 Teams 中啟動和接收所有通話和聊天<LI>使用者可以與任何商務 (使用者) 聊天/通話<LI>使用者無法與使用消費者用 Skype 的使用者通訊<LI>如果使用者嘗試登錄商務用 Skype，會重新導向至 Teams      </UL>  |
|**會議**     |  <UL><LI>使用者在 Teams 中排程所有新會議 (外掛程式已取代)     </UL>   |
|**移移的資料**     |<UL><LI>商務用 Skype 的現有連絡人，包括 (但沒有通訊群組清單) <LI>現有的商務用 Skype 會議 (和線上會議) 轉換成 Teams 會議</UL>         |

## <a name="postponing-your-automated-upgrade"></a>延遲自動升級

從商務用 Skype Online 成功轉換至 Microsoft Teams，需要技術規劃及使用者準備，以確保貴組織準備好利用 Teams 的擴充功能與績效。 不過，當您規劃升級時，您可能會發現貴組織目前尚未準備好升級至 Teams。

如果您收到有關已排程的自動升級至 Teams 的通知，而且想要延後日期，全域系統管理員可能會登入 Teams 系統管理入口網站，然後按一下 [延後>*按鈕。* 如此一來，就會將自動升級日期推出 30 天。 當您在延後之後重新更新 Teams 系統管理入口網站時，會看到包含新自動升級日期的通知。

## <a name="requests-to-downgrade-to-skype-for-business"></a>降級至商務用 Skype 的要求

我們允許從 Teams 一次降級至 SfBO，讓租使用者進一步準備升級至 Teams。 降級的租使用者將在降級日期起 60 天內重新參與自動升級。

## <a name="related-content"></a>相關內容

- [開始升級您的 Microsoft Teams](upgrade-start-here.md)
- [終止對商務用 Skype Online 的支援](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [Teams 僅模式考慮事項](teams-only-mode-considerations.md)