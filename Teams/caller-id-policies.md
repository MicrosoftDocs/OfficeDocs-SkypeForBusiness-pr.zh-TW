---
title: 管理 Microsoft 團隊中的呼叫者識別碼原則
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中使用和管理本機號碼原則，以變更或封鎖貴組織中的小組使用者本機號碼。
ms.openlocfilehash: a4dbdbac0922bb475f47447a3cf8b2d0f001909c
ms.sourcegitcommit: a7c823f61d9ab88424bad924113d780ce11e509f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44224249"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>管理 Microsoft 團隊中的呼叫者識別碼原則

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

做為管理員，您可以使用 Microsoft 團隊中的本機號碼原則來變更或封鎖本機號碼（也稱為呼叫線路識別碼）。 根據預設，當使用者撥打電話給 PSTN 手機時，可以看到他們的電話號碼，以及當他們呼叫團隊使用者時，可以看到 PSTN 呼叫者的電話號碼。 您可以使用本機號碼原則，為您組織中的小組使用者顯示備用電話號碼，或封鎖要顯示的傳入號碼。

例如，當使用者撥打電話時，您可以變更本機號碼，以顯示貴組織的主要電話號碼，而不是使用者的電話號碼。

您可以移至**Voice**  >  Microsoft 團隊系統管理中心的語音**本機號碼原則**來管理本機號碼原則。 您可以使用全域 (預設為全組織) 原則或建立自訂原則，並指派給使用者。 除非您建立並指派自訂原則，否則貴組織中的使用者將會自動取得全域原則。

您可以編輯全域原則，或建立並指派自訂原則。 如果指派給使用者的是自訂原則，該原則會套用給使用者。 如果使用者未獲指派自訂原則，則全域原則會套用至使用者。

## <a name="create-a-custom-caller-id-policy"></a>建立自訂本機號碼原則

1. 在 Microsoft [團隊管理中心] 的左導覽中，移至 [**語音**  >  **本機號碼原則**]。
2. 按一下 [**新增**]。 <br>
![系統管理中心 [新增本機號碼原則] 頁面的螢幕擷取畫面](media/caller-id-policies-add-policy.png)
3. 輸入原則的名稱和描述。
4. 從這裡選擇您想要的設定：

    - **封鎖來電**的本機號碼：開啟此設定可封鎖來電的本機號碼。
    - 覆**寫本機號碼原則**：開啟此設定可讓使用者覆寫原則中的設定，以將他們的號碼顯示在 callees 中。 這表示使用者可以選擇是否要顯示其本機號碼。 如需詳細資訊，請參閱[結束使用者對輸出來電者識別碼的控制](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id)。
    - **使用本機號碼取代來電**顯示：若要為使用者設定本機號碼，請選取下列其中一項：

        - **使用者號碼**：顯示使用者的號碼。 
        - [**服務號碼**]：可讓您設定要顯示為本機號碼的服務電話號碼。
        - **匿名**：以匿名方式顯示本機號碼。

    - **以這個服務號碼取代本機號碼**：選擇服務號碼來取代使用者的本機號碼。 如果您在 [**取代本機號碼者識別碼**] 中選取了 [**服務號碼**]，就可以使用此選項。

5. 按一下 [儲存]****。

## <a name="edit-a-caller-id-policy"></a>編輯本機號碼原則

您可以編輯全域原則或您建立的任何自訂原則。 

1. 在 Microsoft [團隊管理中心] 的左導覽中，移至 [**語音**  >  **本機號碼原則**]。
2. 按一下原則名稱左邊的，然後按一下 [**編輯**]，選取原則。
3. 變更您想要的設定，然後按一下 [**儲存**]。

## <a name="assign-a-custom-caller-id-policy-to-users"></a>將自訂本機號碼原則指派給使用者

您可以使用 Microsoft 團隊系統管理中心，將自訂原則指派給一或多個使用者或商務用 Skype PowerShell 模組，將自訂原則指派給使用者群組，例如安全群組或通訊群組。

### <a name="assign-a-custom-caller-line-id-policy-to-a-user"></a>為使用者指派自訂來電者行識別碼原則

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]****，然後按一下該使用者。
2. 按一下 [**原則**]，然後在 [**指派的原則**] 旁，按一下 [**編輯**]。
3. 在 [**本機號碼原則**] 底下，選取您要指派的原則，然後選擇 [**儲存**]。

### <a name="assign-a-custom-calling-line-id-policy-to-multiple-users-at-a-time"></a>一次將自訂通話行識別碼原則指派給多位使用者

若要一次將自訂通話行識別碼原則指派給多位使用者，請參閱[大量編輯團隊使用者設定](edit-user-settings-in-bulk.md)。

或者，您也可以執行下列動作：

1. 移至**Microsoft 團隊系統管理中心**的  >  **語音**  >  **本機號碼原則**。
2. 按一下原則名稱的左側來選取原則。
3. 選取 [管理使用者]****。
4. 在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。 針對要新增的每一個使用者重複此步驟。
5. 完成新增使用者後，請選取 [**儲存**]。

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a>將自訂本機號碼原則指派給群組中的使用者

您可能會想要將自訂原則指派給已識別的多個使用者。 例如，您可能會想要將原則指派給安全性群組中的所有使用者。 您可以透過連線到 Azure Active Directory PowerShell for Graph 模組及商務用 Skype PowerShell 模組來執行此動作。 如需有關使用 PowerShell 來管理團隊的詳細資訊，請參閱[團隊 PowerShell 概覽](teams-powershell-overview.md)。

在這個範例中，我們會將自訂來電者蓋原則（稱為支援本機號碼原則）指派給 Contoso 支援群組中的所有使用者。  

> [!NOTE]
> 請依照在[單一 Windows PowerShell 視窗中連線至 [所有 Office 365 服務]](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步驟，確認您首先連線至 [圖形模組] 和 [商務用 Skype] powershell 模組的 [Azure Active Directory PowerShell]。

取得特定群組的 GroupObjectId。
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
取得指定群組的成員。
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
將群組中的所有使用者指派給特定的呼叫者 ID 原則。 在這個範例中，它支援本機號碼原則。
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
根據群組中的成員數目而定，此命令可能需要幾分鐘的時間執行。

 ## <a name="related-topics"></a>相關主題

- [新-CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

