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
ms.openlocfilehash: b28b61a6b2d4c441fc69d0e50124df50f95b4a49
ms.sourcegitcommit: 2e8a61abdd586bf8f0f88cac3b7d4ca4b9d9be34
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "44889972"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>管理 Microsoft 團隊中的團隊原則

做為管理員，您可以使用 Microsoft 團隊中的小組原則來控制貴組織中的使用者可在團隊和頻道中進行的動作。 例如，您可以設定是否允許使用者在搜尋結果和小組圖庫中發現私人小組，以及是否允許使用者建立私人頻道。

您可以移至**Teams**  >  Microsoft 團隊系統管理中心的小組**小組原則**，管理小組原則。 您可以使用全域 (預設為全組織) 原則或建立自訂原則，並指派給使用者。 除非您建立並指派自訂原則，否則貴組織中的使用者將會自動取得全域原則。

您可以編輯全域原則，或建立並指派自訂原則。 如果指派給使用者的是自訂原則，該原則會套用給使用者。 如果使用者未獲指派自訂原則，則全域原則會套用至使用者。 在您編輯全域原則或指派原則後，可能需要幾個小時的時間，變更才會生效。

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

您可以使用 Microsoft 團隊系統管理中心，將自訂原則指派給一或多個使用者或商務用 Skype PowerShell 模組，將自訂原則指派給使用者群組，例如安全群組或通訊群組。

### <a name="assign-a-custom-teams-policy-to-users"></a>將自訂團隊原則指派給使用者

若要將原則指派給一個使用者：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]****，然後按一下該使用者。
2. 按一下 [**原則**]，然後在 [**指派的原則**] 旁，按一下 [**編輯**]。
3. 在 [**團隊原則**] 底下，選取您要指派的原則，然後按一下 [**儲存**]。

若要一次將原則指派給多位使用者：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]****，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。
2. 在 [&#x2713;]**** (核取方塊) 欄中，選取使用者。 若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713;] (核取方塊)。
3. 按一下 [編輯設定]****，進行所需的變更，然後按一下 [套用]****。  

或者，您也可以執行下列動作：

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊**  >  **小組原則**]。
2. 按一下原則名稱的左側來選取原則。
3. 選取 [管理使用者]****。
4. 在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。 針對要新增的每一個使用者重複此步驟。
5. 完成新增使用者後，請按一下 [**儲存**]。

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a>將自訂團隊原則指派給群組中的使用者

您可能會想要將自訂團隊原則指派給已識別的多個使用者。 例如，您可能會想要將原則指派給安全性群組中的所有使用者。 您可以透過連線到 Azure Active Directory PowerShell for Graph 模組及商務用 Skype PowerShell 模組來執行此動作。 如需有關使用 PowerShell 來管理團隊的詳細資訊，請參閱[團隊 PowerShell 概覽](teams-powershell-overview.md)。

在這個範例中，我們會將名為「行銷團隊」原則的小組原則指派給 Contoso 行銷群組中的所有使用者。  

> [!NOTE]
> 請依照在[單一 Windows PowerShell 視窗中連線至 [所有 Microsoft 365] 或 [Office 365 服務](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)] 中的步驟，確認您首先連線至 [圖形模組] 和 [商務用 Skype] powershell 模組的 [Azure Active Directory PowerShell]。

取得特定群組的 GroupObjectId。
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
取得指定群組的成員。
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
將群組中的所有使用者指派給特定的團隊原則。 在這個範例中，它是行銷團隊原則。
```PowerShell
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.UserPrincipalName}
``` 
根據群組中的成員數目而定，此命令可能需要幾分鐘的時間執行。

## <a name="related-topics"></a>相關主題

- [在 Teams 中管理私人小組的探索](manage-discovery-of-private-teams.md)
- [團隊中的私人頻道](private-channels.md)
- [指派策略給小組中的使用者](assign-policies.md)
