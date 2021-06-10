---
title: IT 系統管理員的升級策略
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 本文適用于 IT 系統管理員，並說明從企業升級商務用 Skype升級Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e4bfb5594b64eb06041e7f761eb0d85cec8c3e5
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52306037"
---
# <a name="upgrade-strategies-for-it-administrators"></a>IT 系統管理員的升級策略

![升級歷程的階段，強調部署與執行階段](media/upgrade-banner-deployment.png "升級歷程的階段，強調部署與執行階段")

本文適用于想要從 Teams 升級至 商務用 Skype 的 IT 系統管理員。

在執行升級之前，我們建議您閱讀下列文章，說明重要的升級概念和共存行為：

- [瞭解Microsoft Teams商務用 Skype及互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [共存模式 - 參照](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 用戶端體驗和遵從共存模式](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>升級選項

本節說明如何使用下列其中一個升級選項來實施升級：

- [使用群島模式 (功能更新) ](#overlapping-capabilities-upgrade-using-islands-mode)
- [尚未開始使用新版Teams](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [針對已在群島模式中使用Teams的選取功能更新](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

如果您需要有關選項的詳細資訊，請確定您已經閱讀過選擇從 商務用 Skype[到 Teams 的升級Teams。](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>使用群島模式 (功能更新) 

針對重迭功能更新選項：

- 如果您能針對整個組織執行快速升級，請考慮使用此選項。  由於執行這兩個用戶端的使用者有可能會混淆，因此最好能將使用者必須同時執行這兩個用戶端的時段降到最低。 您應該確保您的使用者知道要執行這兩個用戶端。

- 此選項是開箱即用模型，不需要系統管理員動作，Teams指派授權或Microsoft 365 Office 365授權。 如果您的使用者已經有 商務用 Skype Online，您可能已經在這個模型中。

- 若要擺脫重迭的功能模式，並移往 TeamsOnly，可能會非常困難。 因為升級的使用者只會透過Teams通訊，因此組織中與該使用者通訊的其他使用者必須使用Teams。  如果您的使用者尚未開始使用Teams，他們將會暴露在遺失的郵件中。 此外，他們也不會在 商務用 Skype 中看到 TeamsOnly 商務用 Skype。 有些組織選擇使用租使用者全域原則執行整個租使用者升級，以避免這種情況，不過這需要預先規劃，並等到所有使用者準備好升級。


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>尚未開始使用新版Teams

如果貴組織尚未在 Teams 中有任何作用中使用者，第一個步驟是將 TeamsUpgradePolicy 的預設租使用者範圍政策設定為 商務用 Skype 模式之一，例如 SfbWithTeamsCollab。  尚未開始使用此Teams不會注意到行為有任何差異。 不過，在租使用者層級設定此策略，就可以開始將使用者升級至 TeamsOnly 模式，並確保升級的使用者仍然可以與未升級的使用者通訊。  一旦找出您的試驗使用者，就可以將它們升級至 TeamsOnly。  如果是內部部署，請使用 Move-CsUser。 如果他們在線上，只要使用 Grant-CsTeamsUpgradePolicy 指派 TeamsOnly 模式。 根據預設，商務用 Skype使用者排定的任何會議都會移Teams。

以下是關鍵命令：

1. 將整個租使用者的預設設定為模式 SfbWithTeamsCollab，如下所示：

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. 將試驗使用者升級至 TeamsOnly，如下所示：

   - 適用于線上使用者：

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - 適用于內部部署的使用者：

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

注釋
 
- 您可以設定 SfbWithTeamsCollabs，而不是將整個租使用者的政策設定為 SfbWithTeamsCollabAndMeetings。 這會使所有使用者在會議中排程Teams。
- `Move-CsUser` 是內部部署工具中的 Cmdlet。 切換 `MoveToTeams` 需要 2019 商務用 Skype Server 2015 或 2015 商務用 Skype Server CU8 或更高版本。 如果您使用的是先前版本，您可以先將使用者移至 商務用 Skype，然後將 TeamsOnly 模式授予該使用者。
- 根據預設，商務用 Skype升級至 TeamsOnly 模式Teams或指派 SfbWithTeamsCollabAndMeetings 模式時，會議會移至其他會議。  

> [!NOTE]
> 為了準備即將商務用 Skype Online，Microsoft 將會簡化組織在近期內Teams如何移至線上。 將使用者從內部部署移至Teams，很快就會不再需要指定移入，將使用者直接從內部部署移至 `-MoveToTeams` `Move-CsUser` TeamsOnly。 目前如果未指定此切換，使用者會從內部部署中的商務用 Skype Server切換到 商務用 Skype Online，其模式會維持不變。 停用之後，將使用者從內部部署移動到雲端時，系統會自動將使用者指派 TeamsOnly 模式，而他們的會議從內部部署會自動轉換成 Teams 會議，就像無論實際指定切換是否一樣。 `Move-CsUser` `-MoveToTeams switch had been specified` 我們預期在 2021 年 7 月 31 日實際停用之前發行此功能。


下圖顯示組織中未事先使用特定功能之組織之選取功能更新的概念Teams。 長條的高度代表使用者數目。 在升級的任何階段，所有使用者都可以彼此通訊。  商務用 Skype使用 Interop 與 TeamsOnly 使用者通訊，反之亦然。 在群島模式中的使用者必須確定要同時執行這兩個用戶端。

![顯示選取功能更新的圖表，無需事先Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>針對已在群島模式中使用Teams的選取功能更新

如果貴組織中某些使用者Teams群島模式使用此功能，您可能不想移除現有使用者的功能。 因此，變更整個租使用者的政策之前，需要額外的步驟。 解決方案是先將這些現有的使用中使用者「Teams群島模式」，然後再將租使用者範圍的政策設定為 SfbWithTeamsCollab。  完成之後，您可以繼續如上所述進行部署，不過，您將有兩組使用者正在移往 TeamsOnly：使用 Teams 的使用者會位於群島模式，而其餘的使用者將位於 SfbWithTeamsCollab 模式中。 您可以逐步將這些使用者移至 TeamsOnly 模式。

1. 尋找使用中使用者Teams如下所示：

   1. 從 Microsoft 365系統管理中心，在左側流覽中，前往報告，然後前往使用狀況。 
   2. 在 「選取報表」下拉Microsoft Teams，然後選擇 「使用者活動」。 這會提供一個可匯出的使用者資料表，這些使用者已在 Teams。 
   3. 按一下 [匯出Excel，然後篩選，只顯示使用中Teams。

2. 針對步驟 1 Teams找到的每個使用中使用者，在遠端 PowerShell 中指派其群島模式。 這可讓您前往下一個步驟，並確保您不會變更使用者體驗。  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. 將租使用者範圍的政策設定為 SfbWithTeamsCollab：

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. 將選取的使用者升級至 TeamsOnly 模式。 您可以選擇在群島模式或 SfbWithTeamsCollab 模式中升級使用者，不過您可能想要先優先在群島模式中升級使用者，以將使用者進入群島模式時可能會出現的混淆降到最低。   

   適用于在 商務用 Skype Online 中商務用 Skype的使用者：  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   對於位於內部部署商務用 Skype Server的使用者：  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

下圖顯示選取功能轉換的概念階段，其中一開始有使用中的群島使用者。 長條的高度代表使用者數目。 在升級的任何階段，所有使用者都可以彼此通訊。  商務用 Skype使用交互操作與 TeamsOnly 使用者通訊，反之亦然。 


![顯示在群島模式中與使用中使用者進行選取功能更新的圖表](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>相關連結

[適用于與應用程式一起使用Teams的移商務用 Skype](migration-interop-guidance-for-teams-with-skype.md) 

[設定商務用 Skype Server或Microsoft 365之間的Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議移 (MMS) ](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
