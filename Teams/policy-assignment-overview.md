---
title: 在 Teams 中指派原則
author: mkbond007
ms.author: mabond
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
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解在 Microsoft Teams 中將原則和原則套件指派給使用者和群組的不同方式。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 3dec8bf23167c5166302942140fcfe49e9ea3720
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156511"
---
# <a name="assign-policies-in-teams--getting-started"></a>在 Teams 中指派原則 – 快速入門

身為系統管理員，您可以使用原則來控制組織中使用者可使用的 Teams 功能。 例如，有通話原則、會議原則和傳訊原則，僅舉幾例。

組織有不同類型的使用者，有唯一的需求。 您建立及指派的自訂原則可讓您根據這些需求，為不同的一組使用者量身訂做原則設定。

為了輕鬆管理組織中的原則，Teams 提供數種指派原則給使用者的方式。 直接將原則指派給使用者、個別或透過批次指派來縮放，或指派給使用者為其成員的群組。 您也可以使用原則套件，將原則的預設集合指派給組織中具有類似角色的使用者。 您選擇的選項取決於您管理的原則數目，以及您要指派原則的使用者數目。 全域 (組織的預設) 原則適用于組織中人數最多的使用者。 您只需要將原則指派給需要特殊原則的使用者。

本文將說明您可以指派原則給使用者的不同方式，以及使用時機的建議案例。

如需如何 **將原則指派給使用者和群組** 的詳細資訊，請參閱 [指派原則給使用者和群組](assign-policies-users-and-groups.md)。 如需如何 **指派原則套件** 的詳細資料，請參閱 [指派原則套件](assign-policy-packages.md)。

## <a name="which-policy-takes-precedence"></a>哪些原則優先？

使用者對於每種原則類型都有一個有效的原則。 使用者有可能直接獲派原則，同時也是指派相同類型原則之一或多個群組的成員。 在這類案例中，哪一種原則優先？ 使用者的有效原則是根據優先順序規則來決定，如下所示。

如果使用者直接獲指派原則 (個別或透過批次指派) ，則該原則會優先。 在下列視覺範例中，使用者的有效原則是直接指派給使用者的[方塊] 會議原則。

![顯示直接指派原則優先順序的圖表。](media/assign-policies-example-directly-assigned.png)

如果使用者並未直接指派指定類型的原則，則指派給使用者為其成員之群組的原則優先。 如果使用者是多個群組的成員，則指定原則類型) 最高 ([群組指派排名](assign-policies-users-and-groups.md#group-assignment-ranking) 的原則會優先。

在這個視覺化範例中，使用者的有效原則是 Exec Teams 和 HD 原則，其指派排名相對於使用者所屬的其他群組最高，而且也會指派相同原則類型的原則。  

![顯示從群組繼承的原則優先順序的圖表。](media/assign-policies-example-group.png)

如果使用者未直接獲派原則，或不是獲指派原則之任何群組的成員，使用者會取得該原則類型的全域 (預設) 原則。 以下是視覺化範例。

![顯示全域原則優先順序的圖表。](media/assign-policies-example-global.png)

若要深入瞭解，請參閱 ([優先順序規則](assign-policies-users-and-groups.md#precedence-rules)) 。

## <a name="ways-to-assign-policies"></a>指派原則的方式

以下是您可以指派原則給使用者的方式概觀，以及每個原則的建議案例。 選取連結以深入瞭解。

在指派原則給個別使用者或群組之前，請先 [設定全域 (組織的預設) 原則](#set-the-global-policies) ，以套用至貴組織中人數最多的使用者。  設定全域原則後，您只需要將原則指派給需要特殊原則的使用者。

|執行此動作  |如果。。。  | 用。。。
|---------|---------|----|
|[指派原則給個別使用者](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | 您剛開始使用 Teams，或者只需要將一或多個原則指派給少數使用者。 |Teams PowerShell 模組中的 Microsoft Teams 系統管理中心或 PowerShell Cmdlet
|[指派原則給群組](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |根據使用者的群組成員資格指派原則。 例如，將原則指派給安全性群組或通訊群組清單中的所有使用者。| Teams PowerShell 模組中的 Microsoft Teams 系統管理中心或 PowerShell Cmdlet|
|[指派原則給一批使用者](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | 指派原則給大量使用者。 例如，一次指派原則給組織中的數百或數千個使用者。 |Teams PowerShell 模組中的 Microsoft Teams 系統管理中心或 PowerShell Cmdlet|
|[指派原則套件給使用者](assign-policy-packages.md#assign-a-policy-package-to-users)  |將多個原則指派給組織中具有相同或相似角色的特定一組使用者。 例如，將教育 (教師) 原則套件指派給學校的教師，讓他們可以完整存取聊天、通話和會議。 將教育 (中學生) 原則套件指派給次要學生，以限制私人通話等特定功能。  |Teams PowerShell 模組中的 Microsoft Teams 系統管理中心或 PowerShell Cmdlet|
|[將原則套件指派給群組](assign-policy-packages.md#assign-a-policy-package-to-a-group)  |將多個原則指派給組織中角色相同或相似的使用者群組。 例如，將原則套件指派給安全性群組或通訊群組清單中的所有使用者。 |Microsoft Teams 系統管理中心 (即將推出，) Teams PowerShell 模組中的 PowerShell Cmdlet|
|[指派原則套件給一批使用者](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|指派多個原則給組織中具有相同或相似角色的一批使用者。 例如，使用批次處理作業將教育 (教師) 原則套件指派給學校的所有教師，讓他們可以完整存取聊天、通話和會議。 將教育 (中學生) 原則套件指派給一批次要學生，以限制私人通話等特定功能。|Teams PowerShell 模組中的 PowerShell Cmdlet|

> [!NOTE]
> 若要取消指派原則，您可以大量移除直接指派給原則之所有使用者的指派。 若要深入瞭解，請閱讀 [大量取消指派原則](assign-policies-users-and-groups.md#unassign-policies-in-bulk)。

## <a name="set-the-global-policies"></a>設定全球原則

請依照下列步驟，針對每個原則類型設定全域 (組織預設) 原則。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至您要更新的原則類型原則頁面。 例如，**Teams Teams**  >  **原則**、**會議**  >  **會議原則**、**訊息原則** 或 **語音**  >  **通話原則**。
2. 選取 **全域 (組織的預設)** 原則以檢視目前的設定。
3. 視需要更新原則，然後選取 [ **套用]**。

![在 Teams 系統管理中心更新全域原則。](media/assign-globalpolicy.png)

### <a name="using-powershell"></a>使用 PowerShell

若要使用 PowerShell 設定全域原則，請使用全域識別碼。  首先檢閱目前的全域原則，以判斷您要變更的設定。

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

接下來，視需要更新全域原則。  您只需要為您要變更的設定指定值。

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="view-your-policy-assignments-in-the-activity-log"></a>在活動記錄中檢視您的原則指派

當您在 Microsoft Teams 系統管理中心將原則指派給使用者時，您可以在 [[活動] 記錄](https://admin.teams.microsoft.com/activitylog)檔中檢視這些原則指派的狀態。 活動記錄顯示過去 30 天內，來自 Teams 系統管理中心和 PowerShell 的網路記錄上傳資訊、群組原則作業，以及來自 Teams 系統管理中心) 超過 20 個使用者 (批次原則作業。

![[活動記錄] 頁面的螢幕擷取畫面。](media/Activity_Log.png)

若要在 [活動] 記錄中檢視您的原則操作：

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 **[儀表板**]，然後在 [ **活動記錄檔**] 底下，選 **取 [檢視詳細資料]**。
2. 您會看到每個原則作業的下列相關資訊：
    - **活動**：原則作業的名稱。 例如： **群組原則指派**
    - **組名**：原則作業完成的組名。
    - **原則類型**：原則類型。
    - **原則名稱**：原則作業的名稱。 針對批次處理原則指派，您可以選取連結以檢視更多詳細資料。 這包括獲指派原則的使用者數目，以及已完成、進行中且未開始的作業數目。 您也會看到批次中的使用者清單，以及每個使用者的狀態和結果。
    - **提交者**：提交原則作業的使用者名稱。
    - **提交日期**：提交原則作業的日期和時間。
    - **于：** 原則作業完成的日期和時間。
    - **受影響：** 批次或群組中的使用者數目。
    - **整體狀態**：原則作業的狀態。 原則可以具有下列其中一種狀態：
        - **未開始**：系統管理員已提交原則作業。
        - **進行中**：原則作業已開始處理。
        - **向使用者推出**：系統已開始將原則更新套用至使用者。
        - **已完成**：原則更新已套用至所有使用者。
        - **已完成「x」錯誤**：原則作業已完成，但出現錯誤。

> [!NOTE]
> 您也可以從 [ **使用者** ] 頁面移至 [活動] 記錄檔。 選取 [ **套** 用] 以提交大量原則指派後，您會在頁面頂端看到橫幅。 選取橫幅中的 **[活動記錄** 檔] 連結。

## <a name="related-topics"></a>相關主題

- [指派原則給使用者和群組](assign-policies-users-and-groups.md)
- [將原則套件指派給使用者和群組](assign-policy-packages.md)
- [使用原則管理 Teams](manage-teams-with-policies.md)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
