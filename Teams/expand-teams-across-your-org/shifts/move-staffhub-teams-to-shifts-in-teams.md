---
title: 將您的 StaffHub 團隊移到倒班
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu, gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何移動 Microsoft StaffHub 小組，並安排資料在 Microsoft 團隊中的變化。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- SPO_Content
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3c93e01624883d9db755479baf6e87c80feba2e1
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139592"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>將 Microsoft StaffHub 小組移至 Microsoft 團隊中的倒班

> [!IMPORTANT]
> 2019年12月31日生效，Microsoft StaffHub 將停用。 我們正在將 StaffHub 功能組建至 Microsoft 團隊。 今天，小組包含針對排程管理的倒班應用程式，而其他功能則會隨著時間推移而推出。 StaffHub 將會停止針對2019年12月31日的所有使用者使用。 任何試圖開啟 StaffHub 的人，都會顯示一則訊息，讓他們下載小組。 若要深入瞭解，請參閱[Microsoft StaffHub 停用](microsoft-staffhub-to-be-retired.md)。

團隊中的 [倒班] 應用程式提供簡單的方法來管理排程，以及每天發生的 shift 交換與取消轉移的持續流程。 小組成員可以直接在應用程式和其裝置上存取其排程及轉移資訊，以設定其喜好設定、管理其排程，並要求下班時間。

本文將引導您瞭解如何移動貴組織的 StaffHub 小組，並排程資料給小組中的倒班。 包括：

- [移至團隊所需注意的事項](#what-you-need-to-know-about-the-move-to-teams)
- [製作](#prepare)
- [進行試驗](#conduct-a-pilot) 
- [超越您的試驗並移動所有 StaffHub 團隊](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [監視團隊使用量](#monitor-teams-usage)
- [疑難排解](#troubleshooting)

無論您是有一個或兩個 StaffHub 小組的小型企業，還是有數百個 StaffHub 團隊的大型企業，在這裡，您會發現您需要的系統管理指導方針，以協助您的團隊順利轉至團隊。

您必須是全域系統管理員，才能執行本文中的步驟。 如果您尚未這麼做，請參閱[StaffHub 退休常見問題](microsoft-staffhub-to-be-retired.md)，以取得您可能遇到的任何問題的解答。

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>移至團隊所需注意的事項

### <a name="when-to-move-to-teams"></a>移至團隊的時機

2019年12月31日生效，StaffHub 將會停用。 我們鼓勵您立即開始使用團隊，並開始從 StaffHub 轉變貴組織的小組和使用者。 在 StaffHub 中，如果 [排程管理] 是最常用的功能，建議您在小組中使用 [倒班] app。

### <a name="what-is-moved-to-teams"></a>移至團隊的專案

當您移動 StaffHub 小組時，小組成員資格、使用者詳細資料、小組排程及聊天資料都會移至團隊。 當您移動 StaffHub 小組時，檔案不會移動。 如果 StaffHub 小組包含您也想要移至團隊的檔案，您可以在個別步驟中移動檔案。

每個 StaffHub 小組都需要對應的 Office 365 群組。 如果 StaffHub 小組與 Office 365 群組相關聯，當您移動小組時，會保留該群組的隱私權設定。 如果 StaffHub 小組沒有與其相關聯的 Office 365 群組，系統會自動為您建立一個隱私權設定為「私人」的群組，以支援該轉場。  考慮到團隊與 StaffHub 之間的小組和群組命名差異，您可能會在團隊中看到不同的團隊名稱。 

當您將團隊從 StaffHub 轉至團隊時，使用者將無法再存取其在 StaffHub 中的排程，且會重新導向團隊中的時間。 我們建議您在組織中溝通此變更，以減少中斷並鼓勵使用者採納和探索團隊。 如果您有 Azure AD Premium，您可以[執行報告](run-report-to-show-staffhub-usage.md)，以取得貴組織中需要瞭解此變更的 StaffHub 使用者清單。  

將 StaffHub 小組移至團隊之後，沒有回滾選項。

### <a name="user-experience-when-you-move-a-team"></a>移動團隊時的使用者體驗

當使用者的小組從 StaffHub 切換至團隊中時，會有最少的停機時間（只要有的話）。 使用者可以繼續使用 StaffHub，直到完成 [移至] 團隊為止。 完成移動後，小組成員會看到一則訊息，讓他們知道他們需要開始使用小組中的倒班來存取其小組排程。 以下是使用者在 StaffHub 團隊移至團隊之後，在 StaffHub 中看到的訊息範例。

![使用者看到的訊息範例。](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "在 StaffHub 團隊移至團隊之後，使用者在 StaffHub 中看到的訊息範例")

## <a name="prepare"></a>製作

以下說明如何準備移至團隊。

### <a name="check-that-prerequisites-are-met"></a>檢查是否符合先決條件

在您將 StaffHub 小組移至團隊之前，請確認下列事項：

- 已登入的使用者是全域系統管理員。
- 已針對租使用者中的所有使用者啟用團隊。
- 已在租使用者啟用 Office 365 群組建立。
- StaffHub teamId 是有效的。
- StaffHub 小組至少有一個團隊擁有者。
- StaffHub 小組包含成員。
- 所有 StaffHub 小組成員都連結至 Azure AD 帳戶。
- 所有 StaffHub 小組成員都會獲指派「團隊」授權。  

如果不符合這些先決條件，移動要求將會失敗。

### <a name="assign-teams-licenses"></a>指派 Teams 授權

每個使用者都必須從[符合資格的方案](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in)中擁有有效的 Microsoft 365 或 Office 365 授權，且必須指派團隊授權。 指派團隊授權給使用者可讓他們存取小組。

您可以在 Microsoft 365 系統管理中心管理團隊授權。 若要深入瞭解，請參閱[管理使用者對團隊的存取權](../../user-access.md)。

> [!NOTE]
> 如果您的組織使用商務用 Skype，而您還沒有準備好將您的所有使用者移至團隊，您可以為第一線員工工作人員啟用團隊，然後在商務用 Skype 中執行團隊。 在此共存模式（稱為*孤島*）中，每個用戶端應用程式都是以個別的解決方案的方式運作。 若要深入瞭解，請參閱[瞭解團隊及商務用 Skype 共存與互通性](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

### <a name="install-the-prerelease-version-of-the-staffhub-powershell-module"></a>安裝 StaffHub PowerShell 模組的預發行版本本

如果您尚未安裝，請[安裝 StaffHub PowerShell 模組的預發行版本本](install-the-staffhub-powershell-module.md)。

您必須已安裝預發行的模組版本，才能將您的 StaffHub 團隊移至團隊。

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a>連結 Azure AD 帳戶給沒有 StaffHub 小組成員的人員

每個 StaffHub 小組成員都必須連結至 Azure Active Directory （Azure AD）帳戶。 如果下列任何一種情況適用，貴組織中的使用者將無法連結至 Azure AD 帳戶：

- 小組擁有者已新增沒有 Azure AD 帳戶的使用者。
- 小組擁有者受邀使用者加入 StaffHub 小組，而該使用者並未接受邀請。

這些使用者擁有非作用中的帳戶，並顯示使用者狀態為 [未知]、[受邀] 或 [InviteRejected]。 您可以連結這些使用者的 Azure AD 帳戶。  方法如下。

#### <a name="get-a-list-of-all-inactive-accounts-on-staffhub-teams"></a>取得 StaffHub 小組中所有非作用中帳戶的清單

執行下列系列命令，以取得 StaffHub 小組中所有非作用中帳戶的清單，並將清單匯出為 CSV 檔案。 每個命令都應該單獨執行。

```PowerShell
$InvitedUsersObject = @()

$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }

foreach($team in $StaffHubTeams[0])
{ 
    Write-host $team.name
    $StaffHubUsers = Get-StaffHubMember -TeamId $team.Id | where {$_.State -eq "Invited"}
    foreach($StaffHubUser in $StaffHubUsers) {
        $InvitedUsersObject  += New-Object PsObject -Property @{
          "TeamID"="$($team.Id)"
          "TeamName"="$($team.name)"
          "MemberID"="$($StaffHubUser.Id)"
            }
    }
}

$InvitedUsersObject | SELECT * | export-csv InvitedUsers.csv -NoTypeInformation  
```

#### <a name="link-the-account"></a>連結帳戶

請執行下列其中一項操作：

- 轉換及連結帳戶。

  StaffHub 小組擁有者和管理員可以轉換非作用中的帳戶，並將其連結至 StaffHub 中的 Azure AD 帳戶，做法是將使用者的電子郵件地址變更為 [StaffHub 小組設定] 頁面上的有效 UPN。

- 移除未連結的帳戶，然後使用 UPN 重新加入該帳戶。
    1. 執行[StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) Cmdlet，以從 StaffHub 團隊中移除未預配的帳戶。
    2. 執行[StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) Cmdlet，以使用 UPN 將帳戶重新新增到 StaffHub 小組。

- 移除非作用中的帳戶。 如果不再需要使用者帳戶，請使用這個選項。

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>將 FirstlineWorker 應用程式設定原則指派給使用者

團隊包含內建的 FirstlineWorker 應用程式設定原則，您可以用來自訂小組，以醒目提示貴組織中的第一線員工工人最重要的 app。 當您將此原則指派給使用者時，原則中的應用程式會釘選在團隊中的應用程式行上，以便快速且輕鬆地存取。 您可以在應用程式行中，按一下 [...]，在應用程式行中找到新增至團隊的其他 app。 **... More apps**小組桌面及網頁用戶端中的其他應用程式，以及在小組行動用戶端中向上輕掃。 根據預設，FirstlineWorker 應用程式的設定原則包括活動、班次、聊天及呼叫 app。

如需如何將 FirstlineWorker 應用程式設定原則指派給使用者的步驟，請參閱[使用 FirstlineWorker 應用程式設定原則將倒班移至團隊](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams)。 指派原則之後，最多可能需要24小時才能生效。

我們建議您至少在一周完成此步驟，然後再將您的 StaffHub 團隊和使用者移至團隊。 當使用者在團隊中時，請確認他們可以查看和存取倒班 app。

您也可以建立自訂應用程式設定原則，並編輯全域 app 設定原則中的設定。 若要深入瞭解，請參閱[管理團隊中的 app 設定原則](../../teams-app-setup-policies.md)。

### <a name="onboard-users-to-teams"></a>在團隊中的使用者

在您的加入戰略中，請為使用者提供訓練與指導方針，以協助他們熟悉團隊。 與使用者共用下列資源，讓他們知道要取得團隊用戶端、訓練及支援的位置：

- [Teams Web 用戶端](https://teams.microsoft.com)
- [桌面和行動用戶端下載連結](https://teams.microsoft.com/downloads)
- [Teams 訓練影片](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [Teams 說明文件](https://support.office.com/teams)

如需部署團隊及促進團隊採納的指導方針，請參閱[如何推出](../../How-to-roll-out-teams.md)團隊並[採用團隊](../../adopt-microsoft-teams-landing-page.md)。

## <a name="conduct-a-pilot"></a>進行試驗

我們建議您先將兩個或三個 StaffHub 小組移出一組早期採用者的選取群組。 執行試驗可協助您調整轉場計畫，並確保您已準備好將貴組織的所有 StaffHub 小組移至團隊。 它也會識別可協助推動整個組織採用的擁護者。 如果您是小型企業，且不需要分階段的方法，本節中的步驟可能就是，您必須從 StaffHub 到團隊進行切換。

### <a name="identify-pilot-teams"></a>找出試生產團隊

向外延伸以找出兩個或三個試驗小組。 所有小組成員都應該承諾使用小組中的倒班來管理自己的排程，並相互溝通與共同作業。

### <a name="identify-team-champions"></a>識別團隊擁護人員

在試驗小組中找出擁護者，並登記它們以協助 evangelize 倒班。 小組擁護者會熱情他們的功能，分享自己的學習專案，以提供給小組成員的支援與指導方針。 團隊擁護者可以是團隊擁有人或管理員。

團隊擁護者應該確保小組成員已設定為每個人[取得團隊用戶端](../../get-clients.md)所需的時間，登入小組，並在倒班中查看他們的排程，並開始彼此交談。 已熟悉 StaffHub 的使用者將會在倒班中快速啟動並執行。 您也可以將其指向[協助](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)以取得其他協助。

### <a name="move-a-staffhub-team"></a>移動 StaffHub 小組

使用這些步驟，一次移動一個 StaffHub 小組。 我們建議您試用版團隊採用這種方法。 之後，當您準備好要移動您組織的所有 StaffHub 小組時，請參閱[移動您的 StaffHub 小組](#move-your-staffhub-teams)，以取得如何一次移動多個團隊的步驟。

執行下列動作來移動 StaffHub 小組。

```PowerShell
Move-StaffHubTeam -TeamId <String>
```
範例

```PowerShell
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

以下是當您提交要求以將 StaffHub 小組移至團隊時所取得的回應範例。

```console
 jobId                                      teamId                                      teamAlreadyInMicrosofteams  
---------------------------------------    ----------------------------------------    ---------------------------          
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

若要檢查移動要求的狀態，請執行下列動作。

```PowerShell
Get-TeamMigrationJobStatus <String>
```
範例

```PowerShell
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

以下是您在移動進行中時所取得的回應範例。

```console
jobId                                     status       teamId                                     isO365GroupCreated  Error
----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a>將檔案從 StaffHub 小組移至團隊

此步驟僅適用于您移至團隊的 StaffHub 小組是否有您想要移至團隊的檔案。 您可以直接在 SharePoint Online 或使用 PowerShell 中移動檔案。

#### <a name="in-sharepoint-online"></a>在 SharePoint Online 中

瞭解[如何在 SharePoint Online 中移動](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30)檔案。

#### <a name="using-powershell"></a>使用 PowerShell

如果您尚未下載並安裝[SharePoint Online 管理命令](https://www.microsoft.com/download/details.aspx?id=35588)介面，請先下載並安裝。 它包含您要移動檔案所需的 Cmdlet。  

使用[PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) Cmdlet 連線至 SharePoint Online 小組網站。

```PowerShell
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

針對您要從 StaffHub 移至 [團隊] 的每個檔案，請使用[PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) Cmdlet 來移動檔案。

```PowerShell
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

若要移動多個檔案，請迴圈流覽檔案，然後在迴圈上執行第二個命令。 如果會話保持作用中，您就不需要重複第一個命令。

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a>超越您的試驗並移動所有 StaffHub 團隊

### <a name="raise-awareness"></a>提高知名度

當您準備好超越您的試驗小組，並將貴組織的 StaffHub 小組移至團隊時，請務必先在組織中溝通所做的變更。 將有關倒班與轉場的相關資訊散佈在團隊中，以提高知名度、產生驚喜，以及推動採用。

### <a name="move-your-staffhub-teams"></a>移動您的 StaffHub 團隊

使用這些步驟來大量移動 StaffHub 團隊。 您可以選擇移動您組織的所有 StaffHub 小組，或移動特定的 StaffHub 團隊。 如果您想要一次移動一個 StaffHub 小組，請參閱[移動 StaffHub 團隊](#move-a-staffhub-team)。

#### <a name="move-all-staffhub-teams"></a>移動所有 StaffHub 團隊

執行下列動作，取得貴組織中所有 StaffHub 小組的清單。

```PowerShell
$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }
```

然後，執行下列動作來移動所有團隊。

```PowerShell
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

以下是回應的範例。

針對已移至團隊或已存在於團隊中的任何小組，該作業將會是 "null"，因為工作不需要提交就能移動該小組。

```console
jobId                                      teamId                                      teamAlreadyInMicrosofteams  
----------------------------------------   -----------------------------------------   --------------------------         
null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a>移動特定的 StaffHub 團隊

執行下列動作，取得貴組織中所有 StaffHub 小組識別碼的清單。

```PowerShell
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

在您先前執行的`Get-StaffHubteamsForTenant` Cmdlet 所傳回的結果中，選取您要移動的團隊識別碼，然後將它們新增到逗號分隔值（CSV）檔案。

以下是如何格式化 CSV 檔案的範例。

|標識號  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000|

建立 CSV 檔案之後，請執行下列動作，以移動您在 CSV 檔案中指定的小組。

```PowerShell
$StaffHubTeams = Import-Csv .\teams.csv

foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a>確認您的 StaffHub 小組已移至團隊

執行下列動作，以取得貴組織中所有團隊成員的清單。 

```PowerShell
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a>將檔案從您的 StaffHub 團隊移至團隊

如果您移動的 StaffHub 小組包含您也想要移至團隊的檔案，請參閱[將檔案從 StaffHub 團隊移至 [小組](#move-files-from-a-staffhub-team-to-teams)]。

## <a name="monitor-teams-usage"></a>監視團隊使用量

使用方式報告可協助您更好地瞭解使用模式，並讓您深入瞭解組織中的訓練和溝通工作的優先順序。 您可以執行報表，顯示整體團隊的使用量、使用者在團隊中執行的活動類型、使用者連線至團隊的方式等等。 如需詳細資訊，請參閱 microsoft[團隊系統管理中心的團隊報告](../../teams-analytics-and-reports/teams-reporting-reference.md)，以及[microsoft 365 系統管理中心的小組活動報告](../../teams-activity-reports.md)。

## <a name="troubleshooting"></a>疑難排解

**如何取得失敗錯誤的詳細資訊**

執行下列動作，以取得當您嘗試移動小組時所發生的「失敗」錯誤的詳細資訊：

```PowerShell
Move-StaffHubTeam -TeamId <TeamId>

$res = Get-TeamMigrationJobStatus -JobId <JobId>

$res.Status
```

您會看到下列其中一個傳回的狀態：成功、失敗、InProgress、排隊。

如果傳回「失敗」，請執行下列動作以取得錯誤的詳細資訊：

```PowerShell
$res.Result.Error.Innererror
```

**當您嘗試移動 StaffHub 小組時，狀態會顯示為「失敗」，而且您會收到「無法為使用者取得適用的 SKU 類別」錯誤訊息**

如果一或多個小組成員沒有團隊授權，可能會發生這種情況。 移至 portal.office.com，找出群組，然後確認群組成員已獲指派「團隊授權」。

**當您嘗試移動 StaffHub 小組時，狀態會顯示為「失敗」，而且您會收到「找不到小組擁有者」的錯誤訊息**

如果與 StaffHub 小組相關聯的群組沒有團隊擁有者，就會發生這種情況。 移至 [portal.office.com]，找到群組，然後將一個或多個擁有者新增至群組。

**當您嘗試將檔案從 StaffHub 移至 [團隊] 時，您會收到「許可權被拒絕」錯誤訊息。**

如果您嘗試將檔案移動到您不是其成員的私人 Office 365 群組中，可能會發生這種情況。 如果是這種情況，請使用[AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) Cmdlet 將自己新增至 StaffHub 小組，然後移動檔案。 移動檔案之後，請使用[StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) Cmdlet 將自己從團隊中移除。 

**當您嘗試將檔案從 StaffHub 移至 [團隊] 時，會出現錯誤，指出一般資料夾不存在。**

執行下列命令以將一般資料夾新增至 SharePoint，然後再試一次：

  ```PowerShell
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a>相關主題
- [如何推出 Microsoft Teams](../../How-to-roll-out-teams.md)
- [終止對 Microsoft StaffHub 的支援](microsoft-staffhub-to-be-retired.md)
- [在 Microsoft 團隊中為您的組織管理倒班應用程式](manage-the-shifts-app-for-your-organization-in-teams.md)
- [StaffHub PowerShell 參考](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
