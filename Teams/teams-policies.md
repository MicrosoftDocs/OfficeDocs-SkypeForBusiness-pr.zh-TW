---
title: 管理團隊Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
description: 瞭解如何在組織中使用及管理團隊策略，以控制使用者在團隊和頻道中可以執行的工作。
ms.openlocfilehash: 4c980f6881a1ec73131e35cae1f04bf33f844026dccb1c14045d8310e2c755a5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321105"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>管理團隊Microsoft Teams

做為系統管理員，您可以使用團隊策略Microsoft Teams控制貴組織中使用者可以在團隊和頻道中執行哪些工作。 例如，您可以設定是否允許使用者建立私人頻道。

您可以在系統管理中心 **Teams Teams**  >  **管理Microsoft Teams** 團隊策略。 您可以使用全域 (全組織預設值) 原則，或建立並指派自訂原則。 除非您建立並指派自訂原則，否則組織中的使用者將會自動取得全域原則。

您可以編輯全域原則，或建立及指派自訂策略。 編輯全域原則或指派策略後，可能需要幾個小時，變更才能生效。

## <a name="create-a-custom-teams-policy"></a>建立自訂團隊策略

1. 在系統管理中心的左側導Microsoft Teams，請前往 **Teams Teams。**  >  
2. 按一下 [新增 **]**。
3. 輸入原則的名稱和描述。

    ![團隊策略設定螢幕擷取畫面](media/teams-policies.png)
4. 視您是否 **要允許使用者**<a name="createchannels"></a>建立私人頻道，開啟或關閉建立私人頻道。

5. 按一下 [儲存]。

## <a name="edit-a-teams-policy"></a>編輯團隊策略

您可以編輯全域原則或任何您建立的任何自訂策略。

1. 在系統管理中心的左側導Microsoft Teams，請前往 **Teams Teams。**  >  
2. 按一下原則名稱左側來選取原則，然後按一下 [編輯 **]**。
3. 開啟或關閉您想要的設定，然後按一下 [ **儲存**。

## <a name="assign-a-custom-teams-policy-to-users"></a>指派自訂團隊策略給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>相關主題

[頻道中的私人Teams](private-channels.md)

[將原則指派給 Teams 中的使用者](assign-policies.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)