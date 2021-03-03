---
title: 適用于 IT 系統管理員的升級策略
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 本文適用于 IT 系統管理員，並說明從商務用 Skype 升級至 Teams 的策略
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb884f26862466dcd70c9efe81e5293d277adbde
ms.sourcegitcommit: b0753baa55841a2c6c5dc006dcdd117704af3b42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2021
ms.locfileid: "50401338"
---
# <a name="upgrade-strategies-for-it-administrators"></a>適用于 IT 系統管理員的升級策略

![升級旅程的階段，強調部署與執行階段](media/upgrade-banner-deployment.png "升級旅程的階段，強調部署與執行階段")

本文適用于想要從商務用 Skype 升級至 Teams 的 IT 系統管理員。

在實行升級之前，建議您閱讀下列文章，說明重要的升級概念和共存行為：

- [瞭解 Microsoft Teams 和商務用 Skype 共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [共存模式 - 參照](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 用戶端體驗和遵從共存模式](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>升級選項

本節說明如何使用下列其中一個升級選項來執行升級：

- [使用群島模式升級 (功能) ](#overlapping-capabilities-upgrade-using-islands-mode)
- [尚未開始使用 Teams 的組織之選取功能更新](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [針對已在群島模式中使用 Teams 的組織進行選取功能更新](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

如果您需要選項的詳細資訊，請確定已閱讀選擇從商務用 Skype 到 Teams 的 [升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)。

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>使用群島模式升級 (功能) 

針對重迭的功能更新選項：

- 如果您可以為整體組織執行快速升級，請考慮此選項。  由於使用者可能因為執行這兩個用戶端而產生混淆的風險，因此最好能將使用者必須執行這兩個用戶端的期間最小化。 您應該確保您的使用者知道要執行這兩個用戶端。

- 此選項是開箱即用模型，不需要系統管理員動作，您只需要指派 Microsoft 365 或 Office 365 授權，才能開始使用 Teams。 如果您的使用者已經有商務用 Skype Online，您可能已經在這個模型中了。

- 要退出重迭功能模式並移往 TeamsOnly 可能會是一項挑戰。 由於升級的使用者只會透過 Teams 進行通訊，因此組織中與該使用者通訊的其他使用者都必須使用 Teams。  如果您有尚未開始使用 Teams 的使用者，他們會暴露在遺失的郵件中。 此外，他們也不會在商務用 Skype 中線上看到 TeamsOnly 使用者。 有些組織會選擇使用租使用者全域原則進行全租使用者升級，以避免這種情況，不過這需要預先規劃，並等到所有使用者準備好升級之後才能升級。


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>尚未開始使用 Teams 的組織之選取功能更新

如果貴組織尚未在 Teams 中有任何作用中使用者，第一個步驟是設定 TeamsUpgradePolicy 的預設全租使用者政策至其中一種商務用 Skype 模式，例如 SfbWithTeamsCollab。  尚未開始使用 Teams 的使用者不會注意到任何行為差異。 不過，在租使用者層級設定此策略可讓使用者開始將使用者升級至 TeamsOnly 模式，並確保升級的使用者仍然可以與未升級的使用者通訊。  一旦識別您的試驗使用者之後，您可以將他們升級至 TeamsOnly。  如果是內部部署，請使用 Move-CsUser。 如果他們在線上，只要使用 Grant-CsTeamsUpgradePolicy 指派 TeamsOnly 模式。 根據預設，這些使用者排程的任何商務用 Skype 會議都會移至 Teams。

以下是主要命令：

1. 將全租使用者的預設設定為模式 SfbWithTeamsCollab，如下所示：

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. 將試驗使用者升級至 TeamsOnly，如下所示：

   - 對於在線上的使用者：

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - 對於內部部署的使用者：

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

注釋
 
- 您可以設定 SfbWithTeamsCollabs，而不是將全租使用者策略設定為 SfbWithTeamsCollabAndMeetings。 這會導致所有使用者在 Teams 中排程所有新會議。
- `Move-CsUser` 是內部部署工具中的 Cmdlet。 切換 `MoveToTeams` 需要商務用 Skype Server 2019 或商務用 Skype Server 2015 與 CU8 或更新版。 如果您使用的是先前的版本，您可以先將使用者移至商務用 Skype Online，然後將 TeamsOnly 模式授予該使用者。
- 根據預設，升級到 TeamsOnly 模式或指派 SfbWithTeamsCollabAndMeetings 模式時，商務用 Skype 會議會移至 Teams。  

下圖顯示未事先使用 Teams 的組織之部分功能更新的概念性階段。 長條的高度代表使用者數目。 在升級的任何階段，所有使用者都可以彼此通訊。  商務用 Skype 使用者會使用 Interop 與 TeamsOnly 使用者通訊，反之亦然。 位於群島模式的使用者必須同時執行這兩個用戶端。

![圖表顯示未事先使用 Teams 的選取功能更新](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>針對已在群島模式中使用 Teams 的組織進行選取功能更新

如果貴組織的部分使用者正以群島模式主動使用 Teams，您可能不想移除現有使用者的功能。 因此，變更全租使用者政策之前，需要執行額外的步驟。 解決方法是在將全租使用者政策設定為 SfbWithTeamsCollab 之前，將這些現有使用中的 Teams 使用者「重新組成群島模式」。  完成之後，您可以繼續如上所述進行部署，不過，您將有兩組使用者正在移往 TeamsOnly：在 Teams 中活動的使用者會位於群島模式，其餘的使用者將位於 SfbWithTeamsCollab 模式。 您可以逐漸將這些使用者移至 TeamsOnly 模式。

1. 在 Teams 中尋找使用中使用者，如下所示：

   1. 從 Microsoft 365 系統管理中心左側流覽，前往報告，然後前往使用狀況。 
   2. 在 「選取報告」下拉，選擇 Microsoft Teams，然後選擇使用者活動。 這會提供已使用 Teams 的可匯出使用者資料表。 
   3. 按一下 [匯出、開啟 Excel 並篩選，只顯示 Teams 中的使用中使用者。

2. 針對步驟 1 找到的每個使用中的 Teams 使用者，在遠端 PowerShell 中指派他們群島模式。 這可讓您進入下一個步驟，並確保您不會變更使用者體驗。  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. 將全租使用者策略設定為 SfbWithTeamsCollab：

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. 將選取的使用者升級至 TeamsOnly 模式。 您可以選擇以群島模式或 SfbWithTeamsCollab 模式升級使用者，不過您可能會想要優先升級位於群島模式的使用者，以將使用者進入群島模式時可能出現的混淆降到最低。   

   針對在商務用 Skype Online 中家用的使用者：  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   針對位於商務用 Skype Server 內部部署的使用者：  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

下圖顯示選取功能轉換的概念階段，其中一開始有使用中的群島使用者。 長條的高度代表使用者數目。 在升級的任何階段，所有使用者都可以彼此通訊。  商務用 Skype 使用者會使用交互操作與 TeamsOnly 使用者通訊，反之亦然。 


![圖表顯示以群島模式與使用中使用者一起升級的選取功能](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>相關連結

[適用于將 Teams 與商務用 Skype 一起使用的組織之移移和互通性指南](migration-interop-guidance-for-teams-with-skype.md) 

[設定商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議移 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

