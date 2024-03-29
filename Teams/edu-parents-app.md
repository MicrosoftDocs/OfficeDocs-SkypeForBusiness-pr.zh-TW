---
title: 在 Teams 教育版 中管理員家長設定
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 在 Teams 教育版 中記錄家長的先決條件和設定的 Microsoft Teams 文章。
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- admindeeplinkTEAMS
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32ef76aeff228bc9386917cb2214965942b8be4e
ms.sourcegitcommit: 1f4a0b7cf03f63438bb37668d053853494c92168
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/23/2023
ms.locfileid: "69948570"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>在 Microsoft Teams 教育版 中設定父系連線

Teams 教育版中的家長連線可協助授課者使用 Teams 安全地與班級團隊中的學生家長和監護人聯繫並互動。

本文提供有關父系連線需求與設定之教育 IT 專業人員的指引。

## <a name="share-guardian-and-educator-resources"></a>共用監護人和授課者資源

以下是 IT 系統管理員可以與監護人和授課者共用的一些資源，以瞭解如何開始使用家長連線。

- 如需有關設定監護人的指導方針，請參閱 [在 Microsoft Teams 中與監護人通訊](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e?ui=en-us&rs=en-us&ad=us)。
- 如需讓授課者進行設定的指導方針，請參閱 [在 Teams 中與授課者聯繫](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960)。

## <a name="benefits-of-parent-connection"></a>父系連線的優點

家長連線可讓授課者和監護人使用 Teams 聊天、傳送電子郵件和通話。

- 授課者可以與監護人開始聊天。
  - 如果監護人沒有 Teams 消費者帳戶或尚未加入 Teams，他們將會收到來自教育人員的訊息，並附上前往 Teams 的電子郵件邀請。 只有在未達到邀請限制，且聊天是從父系連線重新輸入的新聊天或現有聊天時，才適用此功能。
- 它適用于受監督的聊天。 如需詳細資訊，請參閱 [在 Microsoft Teams 中使用受監督的聊天](supervise-chats-edu.md)。
  - 根據預設，監護人具有限制的許可權，因此他們無法與學生聊天或將使用者從聊天中移除。
  - 租使用者管理員可以變更此設定。
- 授課者可以選取監護人的電子郵件，以使用他們原生的電子郵件客戶程式傳送電子郵件給他們。
- 授課者可以選取監護人的電話號碼，在 Teams 中撥打他們。

> [!IMPORTANT]
> 若要按一下 Teams 中的通話功能，您的租使用者需要：
>
> - 公開分支 Exchange (PBX) 功能。
> - 連線到 PSTN。
>
> Microsoft 365 A1和 A3 方案不包含 PBX 功能或 PSTN 連線。 您可以為每一項購買 [附加元件授權](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。
>
> Microsoft 365 A5方案只包含使用 Teams Phone System 的 PBX 功能。 您仍然需要 [購買 Teams 通話方案，或使用協力廠商解決方案](pstn-connectivity.md) 連線到 PSTN 上的外部號碼。
>
> 如需取得 PSTN 連線的所有選項的詳細資訊，請參閱 [PSTN 連線選項](pstn-connectivity.md)。
>
> 如需 Teams 通話授權的詳細資訊，請參閱 [Teams 附加元件授權選項](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。

## <a name="requirements"></a>需求

您必須使用 Microsoft Graph 或學校資料同步處理 (SDS) 來填入每個學生的家長和監護人的相關連絡資訊。

### <a name="graph-api"></a>Graph API

如果您已經使用 [Microsoft Graph PowerShell SDK](/powershell/microsoftgraph/overview) 來建立學生身分識別，您可以輕鬆地包含 [相關連線資源類型](/graph/api/resources/relatedcontact)。

### <a name="school-data-sync"></a>學校資料同步處理

當 SDS 設定為定期同步時，使用學校資料同步 (SDS) ，Teams 監護人連絡人資料會在 SIS 中保持最新狀態。

如果監護人已從 *學生的* 記錄中移除，任何涉及他們的現有聊天都會包含聊天擁有者可見的橫幅。 此橫幅會讓聊天擁有者知道變更，要求他們從聊天中移除監護人。 Microsoft 不會自動更新聊天成員資格以移除監護人。

- 您需要學校資料同步 (SDS) 以填入每個學生的家長和監護人的 **相關連絡** 資訊。
  - [部署SDS](/schooldatasync/parents-and-guardians-in-sds)

- 如果您需要有關為租使用者中的學生設定 SDS 並填入家長和監護人 **相關連絡人的** 協助，請透過以下方式連絡 EDU Customer Success 小組：
  - 在 [FastTrack](https://www.microsoft.com/fasttrack?rtc=1)完成 RFA 程式。
  - 在 [[支援]](https://aka.ms/sdssupport)開啟票證。

- 目前，SDS 只支援上層連絡人的 CSV 型資料;不過，您可以針對所有名冊資料使用 [PowerSchool API 同步](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) 處理或 [OneRoster API 同步](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) 處理，只要使用 CSV 新增家長連絡人即可。
  - 使用 [SDS v1 CSV 格式](/schooldatasync/school-data-sync-format-csv-files-for-sds) 或 [SDS v2.1 CSV 格式](/schooldatasync/sds-v2.1-csv-file-format-classic)建立第二個同步處理設定檔。
  - 將兩個填入的 [父檔案](/schooldatasync/parent-contact-sync-file-format) ，其餘的 v1/v2.1 檔案清空， (只有標題) 。
    - User.csv
    - Guardianrelationship.csv
      - 必須為每個家長和監護人完成 *角色* 值，以指出他們是否為 `parent` 或 `guardian` 。
        - 應用程式中僅支援或 `guardian` 支援這些值 `parent` 。 其他值會造成錯誤。
        - SDS v1 格式會標示為 **角色**，但 SDS v2.1 格式則會標示為 **relationshipRole**。
  - 若要檢視 CSV 檔案的範例集，請參閱 [最小必要屬性 GitHub 檔案](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes)。
  - 如果您想要在初始同步處理之後自動拉入 CSV 檔案，請閱讀我們的[CSV 檔案同步 Automation 檔](/schooldatasync/csv-file-sync-automation)。
  - 如需設定 SDS 資料同步處理的說明，請連絡 [我們的客戶成功小組](https://www.microsoft.com/fasttrack?rtc=1) 或 [開啟支援票證](https://edusupport.microsoft.com/support?product_id=data_sync)。

### <a name="teams-admin-center-policies"></a>Teams 系統管理中心原則

- 班級團隊擁有者必須開啟 Teams 聊天。
- 班級團隊擁有者必須擁有外部存取權， **且 Teams 帳戶不受開啟的組織管理** 。
  - 這必須在租使用者層級和使用者層級上開啟。 您可以在 Teams 系統管理中心的 [ **使用者>外部存取** ] 中找到租使用者層級設定。 您也可以透過 PowerShell 存取此設定。 使用者層級外部存取原則只能透過 PowerShell 存取。 如需詳細資訊，請參閱 [下方的 PowerShell 命令](#allow-external-access-with-teams-accounts-not-managed-by-an-organization)。
- 若要允許從父系連線應用程式建立會議，必須開啟下列原則：
  - [允許私人會議排程](meeting-policies-in-teams.md#allow-scheduling-private-meetings)。
  - [允許匿名使用者加入會議](meeting-policies-participants-and-guests.md#let-anonymous-people-join-a-meeting)。

#### <a name="parent-and-guardian-restrictions"></a>家長和監護人限制

家長和監護人在「家長關係」中被歸類為 *外部使用者* ，這表示他們沒有完整的租使用者許可權。 他們只能存取屬於聊天或聊天的一部分，以及聊天中共用的檔案、影像及其他內容。

對於外部聊天，內部和外部使用者都可以將使用者新增至聊天。 若要深入瞭解外部聊天體驗，請參閱 [在 Microsoft Teams 中管理外部會議和聊天](manage-external-access.md)。

此外，外部使用者可以看到貴組織使用者的目前狀態 (離線、線上、忙碌等) ，但您可以使用 PowerShell 關閉此功能以保護使用者的隱私權。 在 PowerShell 中，使用 [Set-CsPrivacyConfiguration](/powershell/module/skype/set-csprivacyconfiguration) 並設定 ``EnablePrivacyMode=true`` 。

即使家長和監護人是外部使用者，他們對於聊天的貢獻仍可被探索。 瞭解如何透過閱讀對 [Microsoft Teams 中的內容進行電子檔探索調查](ediscovery-investigation.md)來進行 Teams 電子檔探索調查。

> [!IMPORTANT]
> IT 系統管理員應該教育所有班級擁有者最佳做法，以便透過聊天分享學生資訊，包括學生隱私權的風險。

#### <a name="blocking-a-parent-or-guardian-in-a-chat"></a>在聊天中封鎖家長或監護人

授課者可以在 [家長連線] 中啟動的聊天中封鎖監護人。

班級擁有者可以：

1. 開啟監護人的個人檔案卡片，選取省略號並 **封鎖使用者**。
2. 然後，從聊天中移除監護人。

封鎖的使用者將無法開始與班級擁有者進行其他聊天。

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>使用未由組織管理的 Teams 帳戶允許外部存取

若要允許授課者與 Teams 中的家長和監護人通訊，教育版租使用者的 IT 系統管理員必須更新租使用者的原則，以允許外部存取租使用者以外的 Teams 帳戶。 如需管理外部存取的詳細資訊，請參閱 [在 Microsoft Teams 中管理外部存取](manage-external-access.md)。

以下是為家長和監護人開啟外部存取的步驟。

1. 在這裡 [https://www.powershellgallery.com/packages/MicrosoftTeams](https://www.powershellgallery.com/packages/MicrosoftTeams) 安裝最新的 Microsoft Teams PowerShell 模組。

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```

2. 使用具有系統管理員許可權的認證，執行下列命令：

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

    根據預設，會針對所有使用者層級外部存取原則開啟不由使用者層級 () `EnableTeamsConsumerAccess` 管理之 Teams 帳戶的外部存取原則設定。 必須同時開啟租使用者層級設定和使用者層級原則設定，使用者才能使用組織未管理的 Teams 帳戶來擁有外部存取權。 如果您不希望租使用者中的每個使用者都開啟此存取，您應該確保您的租使用者層級設定已關閉、更新指派給使用者的使用者層級外部存取原則，然後開啟租使用者層級設定。

    若要檢查哪些使用者層級外部存取原則存在，以及哪些原則被指派給誰，您可以使用下列步驟：

3. 檢查使用者層級外部存取原則是否存在。

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. 針對「全域」原則以外的每個原則，檢查哪些使用者已指派原則。

    > [!NOTE]
    > 任何未指派特定原則的使用者都會回復到「全域」原則。 任何新增至租使用者的新使用者都會獲得「全域」原則指派。

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

由於所有使用者層級的外部存取原則 `EnableTeamsConsumerAccess` 預設為 True，如果您想要調整 `EnableTeamsConsumerAccess` 特定使用者的設定，您可以使用調整的設定來建立/修改現有的外部存取原則，以及/或使用下列 PowerShell Cmdlet 將使用者重新指派給新的或現有的原則：

- 建立新的外部存取原則： [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- 自訂現有的外部存取原則 (包括「全域」原則) ： [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> 下列訂閱預設原則無法修改：'FederationAndPICDefault'、'FederationOnly'、'NoFederationAndPIC'。 根據預設，系統會指派「FederationAndPICDefault」原則給所有使用者，不過新使用者現在預設會獲派「全域」原則。 如果您需要為已指派這些訂閱預設原則的使用者變更原則設定，請將具有正確設定的不同原則指派給這些使用者。

- 將外部存取原則指派給單一使用者： [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- 指派原則給一組使用者： [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

一旦使用者層級外部存取原則為租使用者中的使用者正確設定後，您可以使用下列 Cmdlet 開啟租使用者的租使用者層級設定 (`AllowTeamsConsumer`) ：

- 設定租使用者的同盟設定： [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>在 Teams 系統管理中心開啟家長應用程式

家長 App 預設為關閉，因此班級團隊擁有者必須透過 Teams 系統管理中心才能在班級團隊中看到它。 在 Teams 系統管理中心使用允許 [被開發人員封鎖的應用程式](manage-apps.md#allow-and-block-apps)開啟 [家長] 應用程式。

您可以隨時使用 Teams 系統管理中心的 [[允許並封鎖應用程式](manage-apps.md#allow-and-block-apps) ]，在租使用者層級關閉應用程式。 如果在租使用者層級關閉此設定，即使已開啟使用者層級許可權，也會封鎖所有使用者。

您也可以使用 [Microsoft Teams 中的管理應用程式許可權原則](teams-app-permission-policies.md)，在使用者層級關閉家長應用程式。

## <a name="set-a-preferred-invitation-channel"></a>設定慣用的邀請通道

系統管理員可以選擇電子郵件或簡訊做為其慣用的家長連線邀請通道。

傳送給家長和監護人的郵件會是純文字，不會套用 HTML、格式設定或樣式。

> [!NOTE]
> 如果您選擇 [簡訊] 做為傳送家長連線邀請給家長和監護人的慣用頻道，請注意：
>
> - 家長和監護人電話號碼必須採用 E.164 格式，SMS 邀請和設定檔查閱才能運作。
>   - 例如，將電話號碼格式化為 `+[country code][area code][phone number]` ，例如 `+12223334444` 。
> - 收到簡訊邀請的家長和監護人可能會向行動電信業者收取簡訊費用。

### <a name="set-a-preferred-invite-channel-in-the-teams-admin-center"></a>在 Teams 系統管理中心設定慣用的邀請頻道

1. 登入 [Teams 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)。
1. 移至 **教育版**  >  **家長和監護人設定**。
1. 在 [**偏好的連絡人方法]** 欄位中，選 **取 [Email**] 或 [**行動電話 - 簡訊]**。
1. 儲存變更。

### <a name="set-a-preferred-invite-channel-using-powershell"></a>使用 PowerShell 設定慣用的邀請頻道

1. 在 安裝 *4.9.0 版本或更新* 版本的 Teams PowerShell 模組。 [https://www.powershellgallery.com/packages/MicrosoftTeams](https://www.powershellgallery.com/packages/MicrosoftTeams)

1. 執行下列命令，並使用系統管理員認證登入。

    ```powershell
    Connect-MicrosoftTeams
    ```

1. 執行下列命令以檢視目前的值 `ParentGuardianPreferredContactMethod` 。

    ```powershell
    Get-CsTeamsEducationConfiguration
    ```

1. 執行下列其中一個命令以變更值。

    ```powershell
    Set-CsTeamsEducationConfiguration -ParentGuardianPreferredContactMethod Email
    ```

    ```powershell
    Set-CsTeamsEducationConfiguration -ParentGuardianPreferredContactMethod SMS
    ```

## <a name="more-information"></a>詳細資訊

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
