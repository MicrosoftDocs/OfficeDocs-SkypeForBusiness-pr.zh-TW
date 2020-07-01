---
title: 管理 Microsoft 團隊中的團隊原則
author: lanachin
ms.author: v-lanac
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
description: 瞭解如何使用及管理組織中的小組原則，以控制使用者可在團隊和頻道中執行的動作。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 9ed0bd3aadcde76835bb3d435429785ceaf562a2
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938142"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>管理 Microsoft 團隊中的團隊原則

做為管理員，您可以使用 Microsoft 團隊中的小組原則來控制貴組織中的使用者可在團隊和頻道中進行的動作。 例如，您可以設定是否允許使用者在搜尋結果和小組圖庫中發現私人小組，以及是否允許使用者建立私人頻道。

您可以移至**Teams**  >  Microsoft 團隊系統管理中心的小組**小組原則**，管理小組原則。 您可以使用全域（組織範圍預設值）原則，或建立並指派自訂原則。 除非您建立並指派自訂原則，否則貴組織中的使用者將會自動取得全域原則。

您可以編輯全域原則，或建立並指派自訂原則。 在您編輯全域原則或指派原則後，可能需要幾個小時的時間，變更才會生效。

## <a name="create-a-custom-teams-policy"></a>建立自訂團隊原則

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊**  >  **小組原則**]。
2. 按一下 [**新增**]。
3. 輸入原則的名稱和描述。

    ![團隊原則設定的螢幕擷取畫面](media/teams-policies.png)
4. 選擇您想要的設定：

- **探索私人小組**（在私人預覽版中）<a name="discoverteams"> </a> ：開啟此設定，可讓使用者在搜尋結果和小組圖庫中探索私人小組。
- **建立私人頻道**： <a name="createchannels"> </a>開啟此設定可允許使用者建立私人頻道。

5. 按一下 [儲存]****。

## <a name="edit-a-teams-policy"></a>編輯團隊原則

您可以編輯全域原則或您建立的任何自訂原則。

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊**  >  **小組原則**]。
2. 按一下原則名稱左邊的，然後按一下 [**編輯**]，選取原則。
3. 開啟或關閉您想要的設定，然後按一下 [**儲存**]。

## <a name="assign-a-custom-teams-policy-to-users"></a>將自訂團隊原則指派給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>相關主題

[在 Teams 中管理私人小組的探索](manage-discovery-of-private-teams.md)

[團隊中的私人頻道](private-channels.md)

[指派策略給小組中的使用者](assign-policies.md)
