---
title: 升級至團隊的先決條件與環境相依性
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 使用本指導方針來瞭解在貴組織中部署小組所需的先決條件與環境相依性
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
ms.openlocfilehash: bcd3de45954ea500a6be0d325370ab0660604a65
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578276"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>團隊的先決條件與環境相依性

![升級歷程圖表，強調技術就緒階段](media/upgrade-banner-tech-readiness.png "升級歷程階段，重點放在技術準備階段")

本文是您升級歷程的技術就緒階段（您可以與使用者準備階段並行完成的活動）的一部分。 繼續之前，請先確認您已從先前階段完成這些活動：

- [已登記您的專案干係人](upgrade-enlist-stakeholders.md)
- [已定義您的專案範圍](https://aka.ms/SkypetoTeams-Scope)
- [已瞭解商務用 Skype 與團隊的共存與互通性](https://aka.ms/SkypeToTeams-Coexist)
- [已選擇升級歷程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

團隊結合了多個 Microsoft 365 和 Office 365 服務，因此依賴于這些服務的正確實現與運作。 這些服務包括（但不限於） SharePoint Online、Exchange Online 和商務用 OneDrive。

雖然並非所有服務都是必要的，但我們強烈建議您實現所有服務。 如果您選擇不執行某些服務，會影響團隊可為您的組織提供的功能。 例如，雖然您不需要執行 SharePoint Online，但小組會針對特定的功能（例如群組交談中的檔案共用）而依賴 SharePoint Online，因此不需要執行此服務就能減少透過用戶端提供的功能。

請參閱下列文章以瞭解先決條件，以及團隊如何與其他技術互動：

- 如果您的組織尚未部署任何 Microsoft 365 或 Office 365 的工作負荷，請參閱 [快速入門](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)。

- 如果您的組織尚未新增或設定 Microsoft 365 或 Office 365 的驗證網域，請參閱 [網域常見問題](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)。

- 如果您的組織尚未將身分識別與 Azure Active Directory 同步處理，請參閱 [Microsoft 團隊中的身分識別模型和驗證](identify-models-authentication.md)。

- 如果您的組織沒有 Exchange Online，請參閱 [瞭解 exchange 與 Microsoft 團隊互動的方式](Exchange-Teams-interact.md)。

- 如果您的組織沒有 SharePoint Online，請參閱 [瞭解 Sharepoint online 與商務用 OneDrive 與 Microsoft 團隊互動的方式](SharePoint-OneDrive-interact.md)。

- 瞭解 [microsoft 365 群組與 Microsoft 團隊互動](Office-365-groups.md)的方式。

- 如果您的組織是教育機構，且您使用的是學生資訊系統，請參閱在部署 Microsoft 團隊之前 [歡迎使用 Microsoft 學校資料同步](https://docs.microsoft.com/schooldatasync) 處理。

- 如果您的組織正在考慮公用交換電話網絡 (PSTN) 呼叫選項，請參閱 [語音電話系統和 PSTN](cloud-voice-landing-page.md)連線， [這是您最適合您](calling-plan-landing-page.md)的通話方案，以及 [電話系統直式路由](direct-routing-landing-page.md)。

- 若要確保在推出小組之前已符合所有的網路需求，請參閱 [準備貴組織的 Microsoft 團隊網路](prepare-network.md)。

確認您的環境符合所有適用的先決條件之後，請 [評估您目前的團隊環境](upgrade-plan-journey-evaluate-environment.md)。
