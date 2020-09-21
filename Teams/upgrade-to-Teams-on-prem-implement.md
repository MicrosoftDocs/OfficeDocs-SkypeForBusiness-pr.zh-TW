---
title: 從商務用 Skype 內部部署（Microsoft 團隊）升級至團隊
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從商務用 Skype 升級至 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8239d1fdbda10a61cd0846a0d56b1f1ffa62f597
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955900"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>從商務用 Skype 升級至 &mdash; 適用于 IT 系統管理員的小組

本文說明如何實現升級。 本文是說明 IT 系統管理員升級概念與實現的第五個專案。  

- [概觀](upgrade-to-teams-on-prem-overview.md)
- [升級方法](upgrade-to-teams-on-prem-upgrade-methods.md)
- [管理升級的工具](upgrade-to-teams-on-prem-tools.md)
- [使用商務用 Skype 內部部署之組織的其他考慮事項](upgrade-to-teams-on-prem-considerations.md)
- **在本文中執行升級** () 
- [公用交換電話網絡 (PSTN) 考慮](upgrade-to-teams-on-prem-pstn-considerations.md)

此外，下列文章說明重要的升級概念與共存行為：

- [團隊與商務用 Skype 的共存](upgrade-to-teams-on-prem-coexistence.md)
- [共存模式-參考](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 用戶端體驗和遵從共存模式](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>升級選項

本節說明如何使用下列其中一個升級選項來實現升級：

- [使用孤島模式的重迭功能更新 () ](#overlapping-capabilities-upgrade-using-islands-mode)
- [尚未使用團隊開始的組織的 [選取功能更新]](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [已在孤島模式中使用團隊之組織的 [選取功能更新]](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

如果您需要更多選項的相關資訊，請確定您已閱讀 [升級的方法](upgrade-to-teams-on-prem-upgrade-methods.md)。

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>使用孤島模式的重迭功能更新 () 

針對 [重迭的功能更新] 選項：

- 如果您可以為整體組織執行快速升級，請考慮此選項。  由於對執行這兩個用戶端的使用者而言，可能會造成混淆，因此最好將使用者必須執行兩個用戶端期間的時段最小化。 您應該確保您的使用者知道同時執行這兩個用戶端。

- 此選項是現成的模型，而且不需要系統管理員指令即可開始使用小組，除非指派 Microsoft 365 或 Office 365 授權。 如果您的使用者已經有商務用 Skype Online，您可能已經在這個模型中了。

- 在重迭功能模式並移至 TeamsOnly 時，可能會造成困難。 由於升級的使用者只透過團隊進行通訊，組織中與該使用者進行通訊的任何其他使用者都必須使用團隊。  如果您有尚未開始使用小組的使用者，他們會面臨遺失的郵件。 此外，他們在商務用 Skype 中不會看到 TeamsOnly 使用者的線上狀態。 有些組織會選擇使用租使用者全域原則來執行租使用者範圍的升級，以避免這種情況，但需要前期規劃，並等到所有使用者都準備好進行升級。


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>尚未使用團隊開始的組織的 [選取功能更新]

如果您的組織在團隊中還沒有任何作用中的使用者，第一個步驟是將 TeamsUpgradePolicy 的預設租使用者範圍原則設定為其中一個商務用 Skype 模式，例如 SfbWithTeamsCollab。  尚未開始使用團隊的使用者，將不會注意到行為的任何差異。 不過，在租使用者層級設定此原則，就可以開始將使用者升級至 TeamsOnly 模式，並確保升級後的使用者仍可與未升級的使用者通訊。  一旦您發現您的試驗使用者，您就可以將其升級至 TeamsOnly。  如果他們是內部部署，請使用 Move-csuser。 如果它們是線上的，只要使用授與 CsTeamsUpgradePolicy，即可將其 TeamsOnly 模式指派給他們。 根據預設，由這些使用者排程的任何商務用 Skype 會議都會遷移至團隊。

下列是按鍵命令：

1. 將 [租使用者範圍] 的預設值設定為 mode SfbWithTeamsCollab，如下所示：

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. 將試驗使用者升級為 TeamsOnly，如下所示：

   - 針對處於線上狀態的使用者：

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - 針對內部部署的使用者：

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

筆記
 
- 您可以將整個租使用者的原則設定為 SfbWithTeamsCollabAndMeetings，而不是將它設定為 SfbWithTeamsCollab。 這會讓所有使用者排程團隊中的所有新會議。
- `Move-CsUser` 是內部部署工具中的一個 Cmdlet。 `MoveToTeams`切換開關需要有 CU8 或更新版本的商務用 Skype server 2019 或商務用 Skype server 2015。 如果您使用的是先前的版本，您可以先將使用者移至商務用 Skype Online，然後將 TeamsOnly 模式授與該使用者。
- 根據預設，當您升級至 TeamsOnly 模式或指派 SfbWithTeamsCollabAndMeetings 模式時，商務用 Skype 會議會遷移至團隊。  

下圖顯示的是沒有預先使用團隊之組織之 [選取功能更新] 的概念性階段。 橫條圖的高度代表使用者數目。 在升級的任何階段中，所有使用者都可以彼此通訊。  商務用 Skype 使用者使用互通性與 TeamsOnly 使用者進行通訊，反之亦然。 [孤島] 模式中的使用者必須務必同時執行這兩個用戶端。

![顯示 [沒有預先使用團隊的選取功能更新的圖表]](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>已在孤島模式中使用團隊之組織的 [選取功能更新]

如果貴組織中的部分使用者積極地在孤島模式中使用團隊，您可能不想移除現有使用者的功能。 因此，您必須先執行額外步驟，才能變更租使用者範圍的原則。 解決方案是在將租使用者範圍的原則設定為 SfbWithTeamsCollab 之前，將這些現有的活動團隊使用者「grandfather」成孤島模式。  完成之後，您就可以繼續進行部署，不過，您將會有兩個使用者群組會移至 TeamsOnly：在團隊中使用中的使用者將會處於孤島模式，其餘的使用者將處於 SfbWithTeamsCollab 模式。 您可以逐步將這些使用者移至 TeamsOnly 模式。

1. 在團隊中尋找活躍的使用者，如下所示：

   1. 從 Microsoft 365 系統管理中心的左側導覽中，移至 [報表]，然後移至 [使用方式]。 
   2. 在 [選取報表] 下拉式清單中，選擇 [Microsoft 團隊]，然後選擇 [使用者活動]。 這將提供已在團隊中使用中的使用者可匯出的資料表。 
   3. 按一下 [匯出]、[開啟 Excel] 和 [篩選]，只顯示在團隊中作用中的使用者。

2. 針對在步驟1中找到的每個作用中團隊使用者，在遠端 PowerShell 中指派其孤島模式。 這可讓您移至下一個步驟，並確保您不會變更使用者體驗。  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. 將租使用者的原則設定為 SfbWithTeamsCollab：

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. 將選取的使用者升級至 TeamsOnly 模式。 您可以選擇在 [孤島模式] 或 [SfbWithTeamsCollab] 模式中升級使用者，不過，您可能會想要優先處理在 [孤島] 模式中升級使用者的優先順序，以便將使用者處於 [孤島] 模式時所發生的混淆可能性降至最低。   

   針對駐留在商務用 Skype Online 的使用者：  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   針對駐留在內部部署的商務用 Skype 伺服器的使用者：  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

下圖顯示的是選取功能轉換的概念性階段，在開始時，有活躍的孤島使用者。 橫條圖的高度代表使用者數目。 在升級的任何階段中，所有使用者都可以彼此通訊。  商務用 Skype 使用者使用互通性與 TeamsOnly 使用者進行通訊，反之亦然。 


![圖表顯示在孤島模式中使用 [選取功能更新] 的活動使用者](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>相關連結

[與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南](migration-interop-guidance-for-teams-with-skype.md) 

[在商務用 Skype Server 與 Microsoft 365 或 Office 365 之間設定混合式連接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存與升級設定](setting-your-coexistence-and-upgrade-settings.md)

[授與 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議遷移服務 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

