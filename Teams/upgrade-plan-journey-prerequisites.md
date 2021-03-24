---
title: 升級至 Teams 的先決條件及環境相依性
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 使用此指南以瞭解在組織中部署 Teams 的先決條件及環境相依性
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
ms.openlocfilehash: 6ceca08be6d69a10fe84daa64d0da4e31c61c67c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092191"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Teams 的先決條件及環境相依性

![升級歷程圖，強調技術準備階段](media/upgrade-banner-tech-readiness.png "升級歷程的階段，強調技術準備階段")

本文是升級過程中技術整備階段的一部分，此階段是您與使用者整備階段同時完成的活動。 在繼續進行之前，請確認您已完成上述階段的活動：

- [已招募專案專案關係人](upgrade-enlist-stakeholders.md)
- [已定義專案範圍](./upgrade-define-project-scope.md)
- [瞭解商務用 Skype 和 Teams 的共存與互通性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [已選擇升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams 會合並多個 Microsoft 365 和 Office 365 服務，因此取決於這些服務的正確實現與運作。 這些服務包括但不限於 SharePoint Online、Exchange Online 和商務用 OneDrive。

雖然並非所有服務都為必填專案，但強烈建議您全部實現。 如果您選擇不實行特定服務，將會影響 Teams 可以提供貴組織的功能。 例如，雖然您不需要執行 SharePoint Online，但 Teams 確實會仰賴 SharePoint Online 提供特定功能，例如群組交談中的檔案共用，因此不執行這項服務將會減少透過用戶端提供的功能。

請參閱下列文章以瞭解先決條件，以及 Teams 與其他技術互動的方式：

- 如果貴組織尚未部署任何 Microsoft 365 或 Office 365 工作負載，請參閱 [開始使用](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)。

- 如果貴組織尚未新增或已針對 Microsoft 365 或 Office 365 新增或已驗證網域，請參閱 [網域常見問題](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)。

- 如果貴組織尚未將身分識別同步到 Azure Active Directory，請參閱 Microsoft Teams 中的身分識別模型 [和驗證](identify-models-authentication.md)。

- 如果貴組織沒有 Exchange Online，請參閱瞭解 Exchange 與 [Microsoft Teams 的互動方式](Exchange-Teams-interact.md)。

- 如果貴組織沒有 SharePoint Online，請參閱瞭解 [SharePoint Online](SharePoint-OneDrive-interact.md)和商務用 OneDrive 如何與 Microsoft Teams 互動。

- 若要瞭解 [Microsoft 365 群組與 Microsoft Teams 的互動方式](Office-365-groups.md)。

- 如果貴組織是教育機構，而且您使用學生資訊系統，請參閱部署 Microsoft Teams 前歡迎使用 [Microsoft 學校](/schooldatasync) 資料同步處理。

- 如果貴組織考慮公用交換電話網路 (PSTN) 通話選項，請參閱語音 -電話系統與[PSTN](cloud-voice-landing-page.md)連接、哪一[](calling-plan-landing-page.md)個通話方案適合您，以及電話[系統直接路由](direct-routing-landing-page.md)。

- 若要在推出 Teams 之前確保所有網路需求都符合，請參閱準備貴組織的 [Microsoft Teams 網路](prepare-network.md)。

- 如果您目前使用商務用 Skype Online Connector 來管理您的服務，您必須移至 Teams PowerShell 模組，並更新現有的 PowerShell 腳本。 請參閱 [從商務用 Skype Online Connector 移至 Teams PowerShell 模組](teams-powershell-move-from-sfbo.md) 以瞭解更多資訊。

確認您的環境符合所有適用的先決條件之後，請評估 [您目前的 Teams 環境](upgrade-plan-journey-evaluate-environment.md)。