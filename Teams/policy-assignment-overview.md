---
title: 在 Teams
author: KarliStites
ms.author: kastites
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
description: 瞭解在 Microsoft Teams 中將策略和策略套件指派給使用者和群組的不同Microsoft Teams。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 00f78b3b134c6741a89c0d7b3f43d32a11c182cc
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574302"
---
# <a name="assign-policies-in-teams--getting-started"></a>在 Teams 中指派Teams – 開始使用

做為系統管理員，您可以使用Teams，控制貴組織使用者可使用的功能。 例如，有通話策略、會議策略和傳訊策略，僅舉幾例。

組織有不同類型的使用者，具有獨特的需求。 您建立及指派的自訂策略，讓您根據這些需求，為不同的使用者量身訂做策略設定。

若要輕鬆管理貴組織的政策，Teams提供數種指派策略給使用者的方法。 直接指派一個策略給使用者，無論是個別指派，或是透過批次工作分派來縮放，或是指派給使用者是成員的群組。 您也可以使用策略套件，為組織中具有類似角色的使用者指派一組預先設定的策略。 您選擇的選項取決於您管理的策略數量，以及您指派策略的使用者數目。 全域 (全組織的預設) 原則會適用于貴組織中人數最多的使用者。 您只需要將策略指派給需要特殊策略的使用者。

本文將說明您可以指派策略給使用者的不同方式，以及使用方法的建議案例。

若要瞭解如何指派策略 **給使用者** 和群組的詳細資訊，請參閱 [指派策略給使用者和群組](assign-policies-users-and-groups.md)。 若要瞭解如何指派策略 **套件的詳細資訊，** 請參閱 [指派策略套件](assign-policy-packages.md)。

## <a name="which-policy-takes-precedence"></a>哪一個策略優先？

使用者針對每個策略類型有一個有效原則。 使用者有可能或甚至有可能被直接指派一個策略，而且也是指派相同類型之策略的一或多個群組的成員。 在這類情況下，哪一個策略會優先？ 使用者的有效原則是根據優先順序規則所決定，如下所示。

如果使用者是個別或透過批次指派 (指派給使用者，該) 優先。 在下列視覺化範例中，使用者的有效政策是直接指派給使用者的林肯平方會議政策。

![顯示直接指派之策略優先順序的圖表](media/assign-policies-example-directly-assigned.png)

如果使用者未直接指派指定類型之策略，則指派給該使用者為成員之群組的策略會優先使用。 如果使用者是多個群組的成員，則針對指定 (指派排名) 優先順序最高的策略優先。 [](assign-policies-users-and-groups.md#group-assignment-ranking)

在此視覺化範例中，使用者的有效原則是 Exec Teams 和 HD 策略，其指派排名相對於使用者是成員之其他群組最高，而且也會指派相同策略類型的策略。  

![顯示從群組繼承之策略的優先順序圖表](media/assign-policies-example-group.png)

如果使用者未直接指派策略，或不是任何指派策略之群組的成員，該使用者會取得該策略類型的全域 (組織) 預設) 策略。 以下是一個視覺化範例。

![顯示全域原則如何優先的圖表](media/assign-policies-example-global.png)

若要深入瞭解，請參閱 ([優先順序) 。](assign-policies-users-and-groups.md#precedence-rules)

## <a name="ways-to-assign-policies"></a>指派策略的方法

以下概述您可以指派策略給使用者的方式，以及每個使用者的建議案例。 選取連結以深入瞭解。

在將原則指派給個別使用者或群組之前，首先請設定全域 (組織) 預設 [) 原則](#set-the-global-policies) ，讓原則適用于貴組織中人數最多的使用者。  設定全域原則之後，您只需要將策略指派給需要特殊策略的使用者。

|執行此  |如果。。。  | 使用。。。
|---------|---------|----|
|[指派策略給個別使用者](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | 您剛開始使用Teams才剛開始使用，或者您只需要指派一或多個策略給少數使用者。 |PowerShell Microsoft Teams中的系統管理中心或 PowerShell Teams Cmdlet
|[將策略指派給群組](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |根據使用者的群組成員資格指派策略。 例如，將策略指派給安全性群組或通訊群組清單中的所有使用者。| PowerShell Microsoft Teams中的系統管理中心或 PowerShell Teams Cmdlet|
|[指派一個策略給一批使用者](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | 指派策略給大量使用者。 例如，一次指派一個策略給貴組織中數百或數千個使用者。 |PowerShell Microsoft Teams中的系統管理中心或 PowerShell Teams Cmdlet|
|[指派策略套件給使用者](assign-policy-packages.md#assign-a-policy-package-to-users)  |為貴組織中具有相同或類似角色的特定使用者組指派多個策略。 例如，將教育 (教師) 方案套件指派給學校的教師，讓他們能完全存取聊天、通話和會議。 將教育 (中) 方案套件指派給中學生，以限制某些功能，例如私人通話。  |PowerShell Microsoft Teams中的系統管理中心或 PowerShell Teams Cmdlet|
|[在私人預覽中將](assign-policy-packages.md#assign-a-policy-package-to-a-group) (套件指派給群組)    |將多個策略指派給貴組織中具有相同或類似角色的一組使用者。 例如，將策略套件指派給安全性群組或通訊群組清單中的所有使用者。 |系統Microsoft Teams系統管理中心 (PowerShell 模組) PowerShell Cmdlet 即將推出Teams Cmdlet|
|[將策略套件指派給一批使用者](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|將多個策略指派給貴組織中具有相同或類似角色的一批使用者。 例如，使用批次作業將 (教師) 教師策略套件指派給學校的所有教師，讓他們能完全存取聊天、通話和會議。 將教育 (中學生) 套件指派給一批中學生，以限制某些功能，例如私人通話。|PowerShell 模組中的 PowerShell Cmdlet Teams PowerShell 模組|

## <a name="set-the-global-policies"></a>設定全域原則

請遵循下列步驟，針對每個 (設定整個組織的預設) 策略。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在系統管理中心的左側導Microsoft Teams，請前往您想要更新之策略類型的政策頁面。 例如 **，Teams Teams、**  >  ******會議**  >  **政策**、**傳** 訊政策或 **語音**  >  **通話政策**。
2. 選取全域 **(全組織的預設)** 來查看目前的設定。
3. 請根據需要更新原則， **然後選取** Apply 。

![更新系統管理中心Teams全域原則](media/assign-globalpolicy.png)

### <a name="using-powershell"></a>使用 PowerShell

若要使用 PowerShell 設定全域原則，請使用全域識別碼。  首先，請審查目前的全域原則，決定要變更的設定。

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

接下來，請根據需要更新全域原則。  您只需要為要變更的設定指定值。

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="view-your-policy-assignments-in-the-activity-log"></a>在活動記錄中查看您的策略指派

當您在系統管理中心指派Microsoft Teams，您可以在活動記錄中查看那些策略指派的狀態。 活動記錄會顯示過去 30 天內透過系統管理中心Microsoft Teams超過 20 個使用者批次的策略指派。 請記住，活動記錄不會顯示策略套件指派、透過 Microsoft Teams 系統管理中心將策略指派給少於 20 位使用者的批次，或透過 PowerShell 進行策略指派。

![活動記錄頁面的螢幕擷取畫面](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>在活動記錄中查看您的策略作業活動

若要在活動記錄中查看您的策略指派：

1. 在系統管理中心的左側導Microsoft Teams，前往 **儀表板，然後在** 活動記錄 **下，選取** 查看 **詳細資料**。
2. 您可以查看所有策略指派，或根據狀態篩選清單，只顯示尚未開始、進行中或 **已完成的作業**。  您會看到每個作業的下列資訊：
    - **名稱**：策略指派的名稱。 按一下連結以查看更多詳細資料。 這包括已指派策略的使用者數目，以及已完成、進行中及尚未開始的指派數目。 您也會看到批次中的使用者清單，以及每個使用者的狀態和結果。 以下是範例：

        ![螢幕擷取畫面](media/activity-log-policy-assignment-detail.png)

    - **提交日期**：已提交政策分派的日期和時間。
    - **完成時間**：完成策略作業的日期和時間。
    - **影響：** 批次中的使用者數目。
    - **整體狀態**：策略工作分派的狀態。

> [!NOTE]
> 您也可以從使用者頁面取得 **活動記錄。** 按一下 [ **申請** 以提交大量原則作業後，就會在頁面頂端看到橫幅。 按一下 **橫幅中的** [活動記錄連結。

## <a name="related-topics"></a>相關主題

- [指派策略給使用者和群組](assign-policies-users-and-groups.md)
- [指派策略套件給使用者和群組](assign-policy-packages.md)
- [使用Teams管理](manage-teams-with-policies.md)
- [TeamsPowerShell 概觀](teams-powershell-overview.md)