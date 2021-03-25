---
title: Microsoft Teams 中的公開預覽
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解 Microsoft Teams 中的公開預覽。嘗試新功能並提供意見反應。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: cc3dca351924daa368658a8f0c110099768e9986
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117701"
---
# <a name="microsoft-teams-public-preview"></a>Microsoft Teams 公開預覽

> [!NOTE]
> 預覽中包含的功能可能不完整，且在公開發行之前可能會變更。提供預覽版僅針對評估和探索目的。Office 365 政府社群雲端 (GCC) 中不支援。

Microsoft Teams 的公開預覽可提供 Teams 中尚未發行功能的早期存取。預覽版可讓您探索並測試即將推出的功能。我們也歡迎您提供對於公開預覽中任何功能的意見反應。公開預覽將針對每個 Teams 使用者啟用，因此您不需要擔心會影響整個組織。

如需 Teams 公開預覽中所提供內容的清單，請瀏覽 [Office 目前通道 (預覽) 的版本資訊](/officeupdates/current-channel-preview)。

## <a name="set-the-update-policy"></a>設定更新原則

公開預覽將針對以每個使用者為基礎啟用，而開啟公開預覽的選項會在系統管理原則中控制。 更新原則可用來管理會在 Teams 應用程式中看到搶鮮版或預覽版功能的 Teams 和 Office 預覽版使用者。 您可以使用全域 (全組織預設值) 原則並進行自訂，或為您的使用者建立一或多個自訂原則。 因為該原則不會覆寫全域原則，必須將原則指派給特定使用者。

1. 登入系統管理中心。
2. 選取 [Teams **]** > [更新原則 **]**。

   ![選取 [更新原則] 選項](media/updatePolicies.png)

3. 選取 [新增 **]**。
4. 為更新原則命名，新增描述，然後開啟 [顯示預覽功能 **]**。

您也可以使用 `CsTeamsUpdateManagementPolicy` Cmdlet 透過 PowerShell 設定原則。

## <a name="enable-public-preview"></a>啟用公開預覽

若要在桌面或 Web 用戶端上啟用公開預覽，您必須執行下列工作：

1. 選取您的設定檔以顯示 Teams 功能表。
2. 選取 [關於] → [公開預覽]。
3. 選取 [切換至公開預覽]。

## <a name="related-topics"></a>相關主題

[公開開發人員預覽](/microsoftteams/platform/resources/dev-preview/developer-preview-intro)