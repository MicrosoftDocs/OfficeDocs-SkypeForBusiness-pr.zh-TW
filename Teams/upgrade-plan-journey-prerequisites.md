---
title: 升級至 Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 使用此指南來瞭解在組織中部署Teams的先決條件及環境相依性
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f10df8849e6efe4e6ceac38cb46d118dff5a8ff8
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725452"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>環境的先決條件及環境相依性Teams

![升級歷程圖，強調技術準備階段。](media/upgrade-banner-tech-readiness.png "升級歷程的階段，強調技術準備階段")

本文是升級過程中技術整備階段的一部分，此階段是您與使用者整備階段同時完成的活動。 在繼續進行之前，請確認您已完成上述階段的活動：

- [已招募專案專案關係人](upgrade-enlist-stakeholders.md)
- [已定義專案範圍](./upgrade-define-project-scope.md)
- [瞭解共同使用和商務用 Skype互通性Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [已選擇升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams合併多個Microsoft 365和Office 365服務，因此取決於這些服務的正確實現與運作。 這些服務包括但不限於線上、SharePoint、Exchange Online和商務用 OneDrive。

雖然並非所有服務都為必填專案，我們強烈建議您全部實現。 如果您選擇不實行特定服務，將會影響貴組織Teams的功能。 例如，雖然您不需要執行 SharePoint Online，Teams 確實會仰賴 SharePoint Online 來使用群組交談中的檔案共用等特定功能，因此不執行此服務將會減少透過用戶端提供的功能。

請參閱下列文章以瞭解先決條件，以及Teams與其他技術互動的方式：

- 如果貴組織尚未部署任何Microsoft 365或Office 365，請參閱[開始使用](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)。

- 如果貴組織尚未新增或為網域新增或Microsoft 365驗證Office 365網域[常見問題](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)。

- 如果貴組織尚未將身分識別同步Azure Active Directory，請參閱在 Microsoft Teams 中識別[Microsoft Teams。](identify-models-authentication.md)

- 如果您的組織沒有 Exchange Online，請參閱[了解 Exchange 和 Microsoft Teams 如何互動](Exchange-Teams-interact.md)。

- 如果您的組織沒有 SharePoint Online，請參閱[了解 SharePoint Online 和商務用 OneDrive 如何與 Microsoft Teams 互動](SharePoint-OneDrive-interact.md)。

- 若要瞭解如何[Microsoft 365群組Microsoft Teams互動](Office-365-groups.md)。

- 如果貴組織是教育機構，而且您使用學生資訊系統，[請參閱](/schooldatasync)在部署 microsoft 學校資料同步處理之前Microsoft Teams。

- 如果貴組織考慮公用交換電話網路 (PSTN) 通話選項，請參閱語音 - 電話系統 和[PSTN](cloud-voice-landing-page.md)連接、哪一[](calling-plan-landing-page.md)個通話方案適合您，以及 電話系統[直接路由](direct-routing-landing-page.md)。

- 若要在推出之前確保所有網路需求都符合Teams，請參閱準備貴組織的網路[Microsoft Teams。](prepare-network.md)

- 如果您目前使用 商務用 Skype連線連接器來管理您的服務，您必須移至 PowerShell 模組Teams並更新現有的 PowerShell 腳本。 請參閱[從線上連接器商務用 Skype移至 powerShell Teams模組以](teams-powershell-move-from-sfbo.md)瞭解更多資訊。

確認您的環境符合所有適用的先決條件之後，請評估您目前[Teams。](upgrade-plan-journey-evaluate-environment.md)