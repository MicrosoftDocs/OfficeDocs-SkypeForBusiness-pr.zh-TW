---
title: 管理頻道Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
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
ms.localizationpriority: medium
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
description: 瞭解如何在組織中使用及管理團隊通道策略，以控制使用者在團隊和頻道中可以執行的工作。
ms.openlocfilehash: 5acac362485b1004e1db61229c437810fdbcbc6d
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711777"
---
# <a name="manage-channel-policies-in-microsoft-teams"></a>管理頻道Microsoft Teams

做為系統管理員，您可以使用 Microsoft Teams中的策略來控制貴組織中使用者可以在團隊和頻道中執行哪些工作。 例如，您可以設定是否允許使用者建立私人或共用頻道。

您可以在系統管理中心Teams ****  >  **Teams管理Microsoft Teams** 團隊策略。 您可以使用全域 (全組織預設值) 原則，或建立並指派自訂原則。 除非您建立並指派自訂原則，否則組織中的使用者將會自動取得全域原則。

您可以編輯全域原則，或建立及指派自訂策略。 編輯全域原則或指派策略後，可能需要 24 小時變更才能生效。

## <a name="channel-policies"></a>頻道政策

團隊頻道提供下列政策：

|政策|描述|
|:-----|:----------|
|**建立私人頻道**|當 **啟用時**，團隊擁有者和成員可以建立私人頻道。  (團隊擁有者可以控制成員是否可在每個團隊中建立私人頻道。) |
|**建立共用頻道**|當 **啟用時**，團隊擁有者可以建立共用頻道。 Teams您組織可用的應用程式，也可在共用頻道中使用。|
|**邀請外部使用者加入共用頻道**|啟用 **時**，共用頻道的擁有者和成員可以邀請已建立跨組織信任的組織的外部參與者。 Teams組織的政策適用于這些頻道。|
|**加入外部共用頻道**|當 **為 On** 時，使用者可以參與由已建立跨組織信任的其他組織所建立共用頻道。 Teams組織的其他原則適用于這些頻道。|

## <a name="create-a-custom-teams-policy"></a>建立自訂團隊策略

1. 在系統管理中心的左側導Microsoft Teams，**請前往Teams**  >  **Teams。**
2. 按一下 [新增 **]**。
3. 輸入原則的名稱和描述。

    ![團隊策略設定螢幕擷取畫面。](media/teams-policies.png)
4. 開啟或關閉您想要的設定，然後按一下 [ **儲存**。

5. 按一下 [儲存]。

## <a name="edit-a-teams-policy"></a>編輯團隊策略

您可以編輯全域原則或任何您建立的任何自訂策略。

1. 在系統管理中心的左側導Microsoft Teams，**請前往Teams**  >  **Teams。**
2. 按一下原則名稱左側來選取原則，然後按一下 [編輯 **]**。
3. 開啟或關閉您想要的設定，然後按一下 [ **儲存**。

## <a name="assign-a-custom-teams-policy-to-users"></a>指派自訂團隊策略給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>相關主題

[管理Teams網站和頻道網站](/SharePoint/teams-connected-sites)

[頻道中的私人Teams](private-channels.md)

[將原則指派給 Teams 中的使用者](policy-assignment-overview.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy)
