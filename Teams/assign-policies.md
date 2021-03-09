---
title: 在 Microsoft Teams 中將原則指派給使用者
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
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
description: 瞭解在 Microsoft Teams 中指派策略給使用者的不同方式。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 50d0ddf3da73addde36cb045a3d61eb9a5618e8c
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568989"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a>在 Microsoft Teams 中將原則指派給使用者

做為系統管理員，您可以使用策略來控制組織中使用者可用的 Teams 功能。 例如，通話政策、會議政策及傳訊策略只是幾個。

組織擁有不同類型的使用者，具有獨特的需求。 您建立並指派的自訂策略，讓您根據這些需求量身訂做不同的使用者群組原則設定。

為了輕鬆管理貴組織內的政策，Teams 提供數種指派策略給使用者的方法。 直接指派一個策略給使用者，無論是個別指派或透過批次指派來縮放，或是指派給使用者是成員的群組。 您也可以使用策略套件，為組織中具有類似角色的使用者指派一組預先設定好的政策集合。 您選擇的選項取決於您所管理之策略的數量，以及您指派之策略的使用者數目。 全域 (全組織的預設) 原則會適用于貴組織中數量最多的使用者。 您只需要將策略指派給需要特殊策略的使用者。

本文將說明您可以指派策略給使用者的不同方式，以及使用方法的建議案例。

## <a name="which-policy-takes-precedence"></a>哪一個優先？

使用者針對每一種政策類型都有一個有效政策。 使用者有可能直接被指派一個策略，也是一或多個指派相同類型之策略的群組成員。 在這類情況下，哪一個策略會優先？ 使用者的有效原則是根據優先順序規則決定，如下所示。

如果使用者是個別或透過批次指派 (指派，該) 優先。 在下列視覺化範例中，使用者的有效政策是直接指派給使用者的長方形會議政策。

![顯示直接指派之策略的優先順序圖表](media/assign-policies-example-directly-assigned.png)

如果使用者未直接指派指定類型的策略，則指派給使用者為成員之群組的規則會優先。 如果使用者是多個群組的成員，則具有指定之策略類型最高群組指派排名[](#group-assignment-ranking)的規則會優先。

在此視覺化範例中，使用者的有效原則是 Exec Teams 和 HD 策略，其工作分派排名相對於使用者成員的其他群組最高，而且也會被指派相同政策類型的策略。  

![圖表顯示繼承自群組之策略的優先順序](media/assign-policies-example-group.png)

如果使用者未直接指派一個策略，或不是任何已指派策略之群組的成員，該使用者會取得該政策類型的全域 (組織) 預設) 策略。 以下是視覺化範例。

![顯示全域原則如何優先的圖表](media/assign-policies-example-global.png)

若要深入瞭解，請參閱優先順序 [規則](#precedence-rules)。

## <a name="ways-to-assign-policies"></a>指派政策的方法

以下是您可以指派策略給使用者的方法概觀，以及每個使用者的建議案例。 選取連結以深入瞭解。

在指派原則給個別使用者或群組之前，請從設定全域 [ (全組織](#set-the-global-policies) 的預設) 原則開始，以將原則適用于貴組織中數量最多的使用者。  設定全域原則之後，您只需要將策略指派給需要特殊策略的使用者。

|請這麼做  |如果。。。  | 使用。。。
|---------|---------|----|
|[指派一個策略給個別使用者](#assign-a-policy-to-individual-users)    | 您剛開始使用 Teams，或者只需要將一或多個策略指派給少數使用者。 |Teams PowerShell 模組中的 Microsoft Teams 系統管理中心或 PowerShell Cmdlet
|[指派一個策略給群組](#assign-a-policy-to-a-group) |根據使用者的群組成員資格指派策略。 例如，將一個策略指派給安全性群組或通訊群組清單中的所有使用者。| Teams PowerShell 模組中的 Microsoft Teams 系統管理中心或 PowerShell Cmdlet|
|[指派一個策略給一批使用者](#assign-a-policy-to-a-batch-of-users)   | 指派策略給大量使用者。 例如，一次指派一個策略給貴組織數百或數千個使用者。 |Teams PowerShell 模組中的 Microsoft Teams 系統管理中心或 PowerShell Cmdlet|
| [指派一個策略套件給使用者](#assign-a-policy-package-to-users)  |將多個策略指派給組織中具有相同或類似角色的特定使用者集合。 例如，將教育 (教師) 套件指派給您學校的教師，讓他們能完全存取聊天、通話和會議。 將教育 (中學生) 套件指派給中學生，以限制某些功能，例如私人通話。  |Teams PowerShell 模組中的 Microsoft Teams 系統管理中心或 PowerShell Cmdlet|
| [在私人預覽版中將](#assign-a-policy-package-to-a-group) (套件指派給群組)    |指派多個策略給貴組織中具有相同或類似角色的使用者群組。 例如，將策略套件指派給安全性群組或通訊群組清單中的所有使用者。 |Microsoft Teams 系統管理中心 (Teams PowerShell 模組) 或 PowerShell Cmdlet 即將推出|
| [指派一個策略套件給一批使用者](#assign-a-policy-package-to-a-batch-of-users)|指派多個策略給貴組織中具有相同或類似角色的一批使用者。 例如，使用批次 (指派) 指派給學校的所有教師，讓他們能完全存取聊天、通話和會議。 將教育 (中學生) 套件指派給一批中學生，以限制某些功能，例如私人通話。|Teams PowerShell 模組中的 PowerShell Cmdlet|

## <a name="set-the-global-policies"></a>設定全域原則

請遵循下列步驟，針對每個 (設定整個組織的預設) 規則。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往您想要更新之政策類型之政策頁面。 例如 **，Teams**  >  **Teams 政策**、**會議**  >  **政策**、**傳訊政策** 或 **語音**  >  **通話政策**。
2. 選取 **全域 (整個組織的預設)** 來查看目前的設定。
3. 請根據需要更新原則，然後選取 **"Apply"。**

### <a name="using-powershell"></a>使用 PowerShell

若要使用 PowerShell 設定全域原則，請使用全域識別碼。  首先，請從檢查目前的全域原則開始，決定要變更的設定。

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

接下來，請根據需要更新全域原則。  您只需要指定要變更之設定的值。

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a>指派一個策略給個別使用者

請遵循下列步驟，將一個策略指派給個別使用者，或一次指派給少數使用者。

### <a name="use-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

若要指派一個策略給使用者：

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往 **使用者**，然後選取使用者。
2. 按一下使用者名稱左側以選取使用者，然後選取編輯 **設定**。
3. 選取您想要指派原則， **然後選取** Apply。

或者，您也可以執行下列操作：

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往該政策頁面。
2. 按一下該策略名稱的左側，選取您想要指派的策略。
3. 選取 [管理使用者]。
4. 在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。 針對要新增的每一個使用者重複此步驟。
5. 當您完成新增使用者時， **請選取應用程式**。

### <a name="use-powershell"></a>使用 PowerShell

每一種策略類型都有一組自己的 Cmdlet 來管理它。 使用 ```Grant-``` 指定之策略類型的 Cmdlet 來指派該策略。 例如，使用 ```Grant-CsTeamsMeetingPolicy``` Cmdlet 將 Teams 會議政策指派給使用者。 這些 Cmdlet 包含在 Teams PowerShell 模組中，並記錄在商務用 [Skype Cmdlet 參照中](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)。

 如果您尚未安裝 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) (，請下載並安裝) ，然後執行下列操作以連結。

> [!NOTE]
> 商務用 Skype Online Connector 目前是最新 Teams PowerShell 模組的一部分。
>
> 如果您使用的是最新的 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)公開發行，則不需要安裝商務用 Skype Online Connector。

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

在此範例中，我們將名為 Student Meeting Policy 的 Teams 會議政策指派給名為 Reda 的使用者。

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

若要深入瞭解，請閱讀透過 [PowerShell 管理原則](teams-powershell-managing-teams.md#manage-policies-via-powershell)。

## <a name="assign-a-policy-to-a-group"></a>指派一個策略給群組

將策略指派給群組可讓您將策略指派給一組使用者，例如安全性群組或通訊群組清單。 原則指派將根據優先順序規則傳播到群組成員。 在群組中新增或移除成員時，系統會相應地更新其繼承的原則指派。

建議最多 50，000 個使用者群組使用指派至群組的策略，但也會與較大的群組一起使用。

當您指派該策略時，該策略會立即指派給群組。 不過，將策略指派傳播給群組成員會做為背景作業執行，視群組大小不同，可能需要一些時間。 當從群組中取消分配一個策略，或將成員新增到群組或移除群組時，也是如此。

群組原則指派只會傳播給群組的直接成員。 指派不會傳播到巢式群組的成員。

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>關於將策略指派給群組的需知

在您開始使用之前，瞭解優先順序規則和群組指派排名非常重要。

#### <a name="precedence-rules"></a>優先順序規則

針對給定政策類型，使用者的有效政策會依據下列條件判斷：

- 直接指派給使用者的規則會優先于指派給群組之相同類型的其他任何政策。 換句話說，如果使用者直接獲指派指定類型的策略，該使用者不會從群組繼承相同類型之策略。 這也表示，如果使用者擁有已直接指派給該使用者之指定類型的策略，您必須從使用者移除該策略，他們才能從群組繼承相同類型之策略。
- 如果使用者未直接指派一個策略，而且它是兩個或多個群組的成員，而且每個群組都有指派給該群組的相同類型之策略，則使用者會繼承排名最高的群組指派之策略。
- 如果使用者不是任何指派原則之群組的成員，該原則類型的全域 (組織預設) 原則會適用于該使用者。

使用者的有效原則會根據這些規則更新：

- 將使用者新加入或移除已指派策略的群組時。
- 系統會從群組中取消分配一個策略。
- 直接指派給使用者的政策會移除。

#### <a name="group-assignment-ranking"></a>群組作業排名

當您將策略指派給群組時，您可以指定群組作業的排名。 這是用來判斷如果使用者是兩個或多個群組的成員，且每個群組都獲得相同類型之政策，使用者應繼承為有效政策。

群組作業排名相對於其他相同類型的群組作業。 例如，如果您要將通話策略指派給兩個群組，將一個作業的排名設定為 1，另一個設定為 2，其中 1 為最高排名。 群組工作分派排名指出哪些群組成員資格在繼承方面比其他群組成員資格重要或更相關。

例如，您擁有兩個群組：Store Employees 和 Store Managers。 這兩個群組會分別指派 Teams 通話政策、Store 員工通話政策與市管理員通話政策。 對於同時位於這兩個群組中的商店經理，其經理角色比員工角色更相關，因此指派給市管理群組的通話政策應該具有較高的排名。

|組 |Teams 通話政策名稱  |排名|
|---------|---------|---|
|商店管理員   |商店管理員通話政策         |1|
|儲存員工    |儲存員工通話政策      |2|

如果您沒有指定排名，則系統會提供最低排名。

### <a name="in-the-teams-admin-center"></a>在 Teams 系統管理中心

> [!NOTE]
> 目前，使用 Microsoft Teams 系統管理中心將政策指派給群組僅適用于 Teams 通話政策、Teams 通話公園政策、Teams 政策、Teams 即時活動政策、Teams 會議政策及 Teams 傳訊政策。 針對其他策略類型，請使用 PowerShell。

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往該政策類型頁面。 例如，前往 **會議**  >  **會議政策**。
2. 選取 **群組原則工作分派的選項卡** 。
3. 選取 **新增群組**，然後在指派群組原則 **窗格中** ，執行下列操作：
    1. 搜尋並新增要指派該策略的群組。
    2. 設定群組作業的排名。
    3. 選取您想要指派的策略。
    4. 選取Apply 。

若要移除群組原則工作分派，請在策略頁面的群組原則工作分派分頁上，選取群組指派，**然後選取移除**。

若要變更群組作業的排名，您首先必須移除群組原則工作分派。 然後，按照上述步驟，將策略指派給群組。

### <a name="use-the-powershell-option"></a>使用 PowerShell 選項

> [!NOTE]
> 目前，並非所有 Teams 策略類型都提供使用 PowerShell 將策略指派給群組。 請參閱 [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 以尋找支援之政策類型的清單。

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>安裝並連接到 Microsoft Teams PowerShell 模組

有關逐步指引，請參閱安裝 Teams [PowerShell。](teams-powershell-install.md)

#### <a name="assign-a-policy-to-a-group-of-users"></a>指派一個策略給一組使用者

使用 [New-CsGroupPolicyAssignment Cmdlet](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 將策略指派給群組。 您可以使用物件識別碼、SIP 位址或電子郵件地址來指定群組。

在此範例中，我們將名為零售管理員會議策略的 Teams 會議政策指派給工作分派排名為 1 的群組。

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>取得群組的策略指派

使用 [Get-CsGroupPolicyAssignment Cmdlet](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) 取得指派給群組的所有策略。 請注意，即使使用群組的 SIP 位址或電子郵件地址來指派策略，群組還是會一直以群組識別碼列出。

在此範例中，我們會取回指派給特定群組的所有策略。

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

在此範例中，我們會退回所有指派為 Teams 會議策略的群組。

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>從群組移除策略

使用 [Remove-CsGroupPolicyAssignment Cmdlet](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) 從群組移除策略。 當您從群組移除一個策略時，會更新指派給該群組之相同類型且排名較低的其他政策優先順序。 例如，如果您移除排名為 2 的策略，則排名為 3 和 4 的策略會更新以反映其新排名。 下列兩個表格顯示此範例。

以下是 Teams 會議政策之政策指派和優先順序的清單。

|組名  |政策名稱  |排名|
|---------|---------|---------|
|銷售    |銷售政策       | 1        |
|西部地區     |西部地區政策         |2         |
|劃分    |部門政策         |3         |
|附屬   |子公司政策        |4         |

如果我們從西部區域群組移除西部區域政策，則政策指派和優先順序會更新如下。

|組名  |政策名稱  |排名|
|---------|---------|---------|
|銷售    |銷售政策       | 1        |
|劃分    |部門政策         |2         |
|附屬   |子公司政策        |3        |

在此範例中，我們會從群組移除 Teams 會議政策。

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a>變更群組的策略指派

> [!NOTE]
> [Set-CsGroupPolicyAssignment Cmdlet](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment)即將推出。 同時，若要變更群組原則工作分派，您可以移除群組中的目前策略工作分派，然後新增新的策略工作分派。

指派群組原則之後，您可以使用 [Set-CsGroupPolicyAssignment Cmdlet](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) 變更該群組的策略指派，如下所示：

- 變更排名
- 變更給定政策類型的策略
- 變更給定政策類型和排名

在此範例中，我們將群組的 Teams 通話公園政策變更為名為 SupportCallPark 且作業排名為 3 的策略。

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>變更使用者的有效政策

以下是如何針對直接指派策略的使用者變更有效原則的範例。

首先，我們將 [Get-CsUserPolicyAssignment Cmdlet](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) 與參數一起使用，以取得與使用者關聯的 ```PolicySource``` Teams 會議廣播政策詳細資料。

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

輸出顯示使用者已直接獲指派名為員工事件的 Teams 會議廣播政策，其優先順序會高於指派給使用者所屬群組的廠商即時事件。

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

現在，我們會從使用者移除員工事件政策。 這表示使用者不再有直接指派給他們的 Teams 會議廣播政策，而且會繼承指派給使用者所屬群組的廠商即時事件政策。

在商務用 Skype PowerShell 模組中使用下列 Cmdlet 執行此工作。

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

在 Teams PowerShell 模組中，使用下列 Cmdlet 可縮放執行此作業，但批次$users指派，其中 $users 是您指定的使用者清單。

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>指派一個策略給一批使用者

### <a name="use-the-admin-center"></a>使用系統管理中心

若要大量指派一個策略給使用者：

1. 在 Microsoft Teams 系統管理中心的左側流覽中，選取 **使用者**。
2. 搜尋您想要指派該策略的使用者，或篩選該視圖以顯示您想要的使用者。
3. 在 [&#x2713;] (核取方塊) 欄中，選取使用者。 若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713;] (核取方塊)。
4. 選取 **編輯設定**，進行您想要的變更， **然後選取** Apply。

若要查看原則工作分派的狀態，請在選取應用程式以提交原則工作分派後，于使用者頁面頂端的橫幅中，選取 **活動記錄**。 或者，在 Microsoft Teams 系統管理中心的左側流覽中，前往儀表板，然後在活動記錄下選取查看 **詳細資料**。 活動記錄會顯示過去 30 天內透過 Microsoft Teams 系統管理中心分批指派給超過 20 個使用者的策略指派。 若要深入瞭解，請參閱 [在活動記錄中查看您的政策指派](activity-log.md)。

### <a name="use-powershell-method"></a>使用 PowerShell 方法

> [!NOTE]
> 目前，並非所有 Teams 策略類型都提供使用 PowerShell 的批次策略指派。 請參閱 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 以尋找支援原則類型的清單。

有了批次策略指派，您一次可以將一組大組使用者指派一個策略，而不需要使用腳本。 您可以使用 [New-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 提交一批使用者和您想要指派原則。 系統會將工作處理為背景作業，並為每個批次產生作業識別碼。 接著，您可以使用 [Get-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) 來追蹤批次中作業的進度和狀態。

根據使用者的物件識別碼或會話初始通訊協定或 SIP (指定) 位址。 使用者的 SIP 位址通常與 UPN (或電子郵件地址的使用者主體名稱) 相同，但這不是必要的。 如果使用者是使用 UPN 或電子郵件指定，但其值與 SIP 位址不同，則使用者無法指派策略。 如果批次包含重複的使用者，則重複專案會先從批次中移除，然後再處理，而狀態只會提供給批次中其餘的唯一使用者。

批次最多可包含 5000 個使用者。 為獲得最佳結果，請勿一次提交多個批次。 在提交更多批次之前，允許批次完成處理。

#### <a name="install-and-connect-to-the-teams-powershell-module"></a>安裝並連接到 Teams PowerShell 模組

執行下列操作以安裝 [Microsoft Teams PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)。 請務必安裝版本 1.0.5 或更新版本。

```powershell
Install-Module -Name MicrosoftTeams
```

執行下列操作以連接到 Teams 並開始會話。

```powershell
Connect-MicrosoftTeams
```

當系統提示您時，請用您的系統管理員認證來登錄。

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>安裝並連接到 Azure AD PowerShell for Graph 模組 (選) 

如果您尚未下載並安裝 [Azure AD PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 模組 (如果您尚未) 並連接到 Azure AD，以便您可以取回貴組織的使用者清單。

執行下列操作以連接到 Azure AD。

```powershell
Connect-AzureAD
```

當系統提示您時，請以您用來連接到 Teams 的相同系統管理員認證來登錄。

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a>指派設定策略給一批使用者

在此範例中，我們使用 [New-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 將名為 HR 應用程式設定原則的應用程式設定原則指派給 Users_ids.文字檔中列出的一批使用者。

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

在此範例中，我們會連接至 Azure AD 以取回使用者集合，然後將名為新進員工傳訊政策的訊息原則指派給一批使用 SIP 位址指定的使用者。

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a>取得批次指派的狀態

執行下列操作以取得批次指派的狀態，其中 OperationId 是 Cmdlet 針對指定批次所返回 ```New-CsBatchPolicyAssignmentOperation``` 的作業識別碼。

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

如果輸出顯示發生錯誤，請執行下列操作以取得屬性中錯誤的詳細資訊 ```UserState``` 。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

若要深入瞭解，請參閱[Get-CsBatchPolicyAssignmentOperation。](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)

## <a name="assign-a-policy-package-to-users"></a>指派一個策略套件給使用者

Teams 中的策略套件是預先定義之策略和策略設定的集合，您可以指派給組織中擁有相同或類似角色的使用者。 每個策略套件都是以使用者角色為設計，並包含預先定義且支援該角色一般活動之政策設定。 一些政策套件範例包括教育 (教師) 套件和醫療保健 (員工) 套件。 若要深入瞭解，請參閱在 [Teams 中管理原則套件](manage-policy-packages.md)。

### <a name="assign-a-policy-package-to-one-user"></a>指派一個策略套件給一個使用者

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往 **使用者**，然後選取使用者。
2. 在使用者的頁面上，**選取政策，** 然後在策略套件 **旁，選取****編輯。**
3. 在指派 **策略套件窗格中** ，選取要指派的套件， **然後選取儲存**。

### <a name="assign-a-policy-package-to-multiple-users"></a>指派一個策略套件給多個使用者

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往政策套件，然後按一下套件名稱左側，選取您想要指派的套件。
2. 選取 [管理使用者]。
3. 在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。 針對要新增的每一個使用者重複此步驟。
4. 完成新增使用者後， **請選取儲存**。

## <a name="assign-a-policy-package-to-a-group"></a>將原則套件指派給群組

透過向群組指派原則套件，可以將多個原則指派給一組使用者，例如安全性群組或通訊群組。 原則指派將根據優先順序規則傳播到群組成員。 在群組中新增或移除成員時，系統會相應地更新其繼承的原則指派。

建議最多 50，000 個使用者群組將策略套件指派給群組，但也適用于較大的群組。

當您指派策略套件時，該套件會立即指派給群組。 不過，將策略指派傳播給群組成員會做為背景作業執行，視群組大小不同，可能需要一些時間。 當從群組中取消分配一個策略，或將成員新增到群組或移除群組時，也是如此。

> [!IMPORTANT]
> 在您開始使用之前，瞭解優先順序規則和群組指派排名[非常重要](#group-assignment-ranking)。 [](#precedence-rules) 請確定您閱讀並瞭解本文稍早所[](#what-you-need-to-know-about-policy-assignment-to-groups)說明的關於將政策指派給群組的需知概念。

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>將政策套件指派給系統管理中心的一組使用者

1. 請登出 Teams 系統管理中心。
2. 在左側流覽中，前往政策套件頁面。
3. 選取群組原則工作分派的選項卡。
4. 選取 **新增群組**，然後在指派策略套件至群組窗格中，執行下列操作：

    a. 搜尋並新增要指派策略套件的群組。

    b. 選取一個策略套件。

    C。 設定每個策略類型的排名。

    D。 選取Apply 。

    ![顯示群組原則指派](media/group-pkg-assignment.png)

5. 若要管理特定政策類型的排名，請流覽至特定政策頁面。
6. 若要將策略套件重新指派給群組，請先移除群組原則指派。 然後，按照上述步驟，將策略套件指派給群組。

### <a name="work-with-powershell"></a>使用 PowerShell

#### <a name="get-the-teams-powershell-module"></a>取得 Teams PowerShell 模組

有關逐步指引，請參閱安裝 Teams [PowerShell。](teams-powershell-install.md)

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>將策略套件指派給一組使用者

使用 [Grant-CsGroupPolicyPackageAssignment Cmdlet](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) 將策略套件指派給群組。 您可以使用物件識別碼、SIP 位址或電子郵件地址來指定群組。 當您指派策略套件時 [，請指定](#group-assignment-ranking) 策略套件中每一種策略類型的群組指派排名。

在此範例中，我們將 Education_Teacher 策略套件指派給一個群組，其中 TeamsAppSetupPolicy 和 TeamsMeetingBroadcastPolicy 的作業排名為 1，而 TeamsMeetingPolicy 的排名為 2。

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>指派一個策略套件給一批使用者

有了批次策略套件指派，您一次可以將一組大組使用者指派一個策略套件，而不需要使用腳本。 您可以使用 [New-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 提交一批使用者和您想要指派原則套件。 系統會將工作處理為背景作業，並為每個批次產生作業識別碼。 接著，您可以使用 [Get-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) 來追蹤批次中作業的進度和狀態。

根據使用者的物件識別碼或會話初始通訊協定或 SIP (指定) 位址。 使用者的 SIP 位址通常與 UPN (或電子郵件地址的使用者主體名稱) 相同，但這不是必要的。 如果使用者是使用 UPN 或電子郵件指定，但其值與 SIP 位址不同，則使用者無法指派策略。 如果批次包含重複的使用者，則重複專案會先從批次中移除，然後再處理，而狀態只會提供給批次中其餘的唯一使用者。

批次最多包含 5，000 個使用者。 為獲得最佳結果，請勿一次提交多個批次。 在提交更多批次之前，允許批次完成處理。

### <a name="use-the-teams-powershell-module"></a>使用 Teams PowerShell 模組

如果您尚未安裝 Microsoft [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 模組， (執行下列) 。 請務必安裝版本 1.0.5 或更新版本。

```powershell
Install-Module -Name MicrosoftTeams
```

執行下列操作以連接到 Teams 並開始會話。

```powershell
Connect-MicrosoftTeams
```

當系統提示您時，請用您的系統管理員認證來登錄。

### <a name="assign-policy-packages-to-a-batch-of-users"></a>指派策略套件給一批使用者

在此範例中，我們使用 [New-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 將 Education_PrimaryStudent 原則套件指派給一批使用者。

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>查看批次指派的狀態

執行下列操作以取得批次指派的狀態，其中 OperationId 是 Cmdlet 針對指定批次所返回 ```New-CsBatchPolicyAssignmentOperation``` 的作業識別碼。

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

如果輸出顯示發生錯誤，請執行下列操作以取得屬性中錯誤的詳細資訊 ```UserState``` 。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

若要深入瞭解，請參閱[Get-CsBatchPolicyAssignmentOperation。](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)

## <a name="related-topics"></a>相關主題

[Teams PowerShell 概觀](teams-powershell-overview.md)
