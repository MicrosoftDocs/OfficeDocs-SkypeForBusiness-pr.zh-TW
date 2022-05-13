---
title: 在 Teams 教育版 中的家長管理設定
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams檔說明Teams 教育版中家長的先決條件和設定。
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f08ddd68d036d18e4ea18073dd0711e32e0c91e
ms.sourcegitcommit: 0c7d199b2f7580dbfa8ce755eda97ec70bc86978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2022
ms.locfileid: "65393867"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>在 Microsoft Teams 教育版 中設定父系連線

Teams 教育版中的家長連線可協助授課者使用Teams，安全地與班級團隊中學生的家長和監護人聯繫並互動。

本文提供有關父系連線需求與設定之教育 IT 專業人員的指引。

## <a name="share-guardian-and-educator-resources"></a>共用監護人和授課者資源

以下是 IT 系統管理員可以與監護人和授課者共用的一些資源，以瞭解如何開始使用家長連線。

- 如需有關設定監護人的指導方針，請[參閱與Teams中的授課者連線](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960)。
- 如需有關如何設定授課者的指導方針，請參閱[在 Microsoft Teams 中與監護人通訊](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e?ui=en-us&rs=en-us&ad=us)。

## <a name="benefits-of-parent-connection"></a>父系連線的優點

家長連線可讓授課者和監護人使用Teams聊天、傳送電子郵件和通話。

- Teams監護人連絡人資料使用 SIS 保持在最新狀態，學校資料同步處理 (SDS) 。
- 它適用于受監督的聊天。 如需詳細資訊，請參閱[在Microsoft Teams中使用受監督的聊天](supervise-chats-edu.md)。
  - 根據預設，監護人具有限制的許可權，因此他們無法與學生聊天或將使用者從聊天中移除。
  - 租使用者管理員可以變更此設定。
- 授課者可以與監護人開始聊天。
  - 如果監護人沒有Teams的消費者帳戶，他們會收到授課者的初始訊息和前往Teams的電子郵件邀請。
- 授課者可以按一下監護人的電子郵件，使用他們原生的電子郵件客戶程式傳送電子郵件給他們。
- 授課者可以按一下監護人的電話號碼，在Teams內撥打他們。

> [!IMPORTANT]
> 若要按一下來通話Teams中的功能，您的租使用者需要：
>
> - 公用分支Exchange (PBX) 功能。
> - 連線到 PSTN。
>
> Microsoft 365 A1和 A3 方案不包含 PBX 功能或 PSTN 連線。 您可以為每一項購買 [附加元件授權](/teams-add-on-licensing/microsoft-teams-add-on-licensing)。
>
> Microsoft 365 A5方案僅包含使用 Teams 電話系統 的 PBX 功能。 您仍然需要[購買Teams通話方案，或使用協力廠商解決方案](pstn-connectivity.md)連線到 PSTN 上的外部號碼。
>
> 如需取得 PSTN 連線的所有選項的詳細資訊，請參閱 [PSTN 連線選項](pstn-connectivity.md)。
>
> 如需Teams通話授權的詳細資訊，請[參閱Teams附加元件授權選項](/teams-add-on-licensing/microsoft-teams-add-on-licensing)。

## <a name="requirements"></a>需求

### <a name="school-data-sync"></a>學校資料同步處理

- 您需要學校資料同步處理 (SDS) 填入每個學生的家長和監護人的 **相關連絡** 資訊。
  - [部署SDS](/schooldatasync/parents-and-guardians-in-sds)

- 如果您需要有關為租使用者中的學生設定SDS及填入家長和監護人 **相關連絡人的** 協助，請透過以下方式連絡 EDU Customer Success 小組：
  - 在[FastTrack](https://www.microsoft.com/fasttrack?rtc=1)完成 RFA 程式。
  - 在 [[支援]](https://aka.ms/sdssupport)開啟票證。

- 目前，SDS只支援家長連絡人的 CSV 型資料;不過，您可以針對所有名冊資料使用[PowerSchool API 同步](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync)處理或[OneRoster API 同步](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync)處理，並直接使用 CSV 新增家長連絡人。
  - 使用[SDS v1 CSV 同步處理格式](/schooldatasync/school-data-sync-format-csv-files-for-sds)建立第二個同步處理設定檔。
  - 將兩個填入的 [父檔](/schooldatasync/parent-contact-sync-file-format) ，其餘的 v1 檔案清空， (只有標題) 。
    - User.csv
    - Guardianrelationship.csv
  - 若要檢視 v1 CSV 檔案的範例集，請參閱[檔案的最低必要屬性GitHub](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes)。
  - 如果您想要在初始同步處理之後自動拉入 CSV 檔案，請閱讀我們的[CSV 檔案同步 Automation 檔](/schooldatasync/csv-file-sync-automation)。
  - 如需設定SDS資料同步處理的說明，請連絡[我們的客戶成功小組](https://www.microsoft.com/fasttrack?rtc=1)或[開啟支援票證](https://edusupport.microsoft.com/support?product_id=data_sync)。

### <a name="teams-admin-center-policies"></a>Teams系統管理中心原則

- 班級團隊擁有者必須開啟Teams聊天。
- 班級團隊擁有者必須擁有外部存取權 **，Teams未由開啟的組織管理的帳戶**。
  - 這必須在租使用者層級和使用者層級上開啟。 您可以在 Teams 系統管理中心的 **[使用者>外部存取**] 中找到租使用者層級設定。 您也可以透過 PowerShell 存取此設定。 使用者層級外部存取原則只能透過 PowerShell 存取。 如需進一步指導方針，請參閱下方的 PowerShell 命令。

#### <a name="parent-and-guardian-restrictions"></a>家長和監護人限制
家長和監護人在「家長關係」中被歸類為「外部使用者」，這表示他們並沒有完整的租使用者許可權。 他們只能存取新增的聊天或聊天，以及在聊天中共用的檔案、影像和其他內容。

此外，外部使用者可以看到貴組織使用者的目前狀態 (離線、線上、忙碌等) ，但您可以使用 PowerShell 關閉此功能以保護使用者的隱私權。 在 PowerShell 中，使用 [Set-CsPrivacyConfiguration](/powershell/module/skype/set-csprivacyconfiguration) 並設定 ``EnablePrivacyMode=true`` 。

雖然家長和監護人是外部使用者，他們對於聊天的貢獻仍可被探索。 瞭解如何透過閱讀對Microsoft Teams[中的內容進行電子檔探索調查，以進行Teams](ediscovery-investigation.md)電子檔探索調查。

#### <a name="blocking-a-parent-or-guardian-in-a-chat"></a>在聊天中封鎖家長或監護人
授課者可以在 [家長連線] 中啟動的聊天中封鎖監護人。

班級擁有者可以：

1. 開啟監護人的個人檔案卡片，選取省略號並 **封鎖使用者**。 
2. 然後，從聊天中移除監護人。 

封鎖的使用者將無法開始與班級擁有者進行其他聊天。

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>使用未由組織管理的Teams帳戶允許外部存取

若要允許授課者與Teams中的家長和監護人通訊，教育版租使用者的 IT 系統管理員必須更新租使用者的原則，以允許外部存取租使用者以外的Teams帳戶。 如需管理外部存取的詳細資訊，請參閱[在 Microsoft Teams 中管理外部存取](manage-external-access.md)。

以下是為家長和監護人開啟外部存取的步驟。

1. 安裝最新Microsoft Teams PowerShell 模組預覽。

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```

2. 使用具有系統管理員許可權的認證，執行下列命令：

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

    根據預設，所有使用者層級的外部存取原則會開啟 () 未由組織管理Teams `EnableTeamsConsumerAccess` 帳戶的外部存取。 必須同時開啟租使用者層級設定和使用者層級原則設定，使用者才能擁有組織未管理之Teams帳戶的外部存取權。 如果您不希望租使用者中的每個使用者都開啟此存取，您應該確保您的租使用者層級設定已關閉、更新指派給使用者的使用者層級外部存取原則，然後開啟租使用者層級設定。

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

[家長] 應用程式預設為關閉，因此班級團隊擁有者必須透過Teams系統管理中心才能在班級團隊中看到它。 [家長] 應用程式會在Teams系統管理中心使用[[允許被發行者封鎖的應用程式]](manage-apps.md#apps-blocked-by-publishers)開啟。

您隨時可以在租使用者層級使用 [[允許並封鎖](manage-apps.md#allow-and-block-apps)Teams系統管理中心的應用程式關閉。 如果在租使用者層級關閉此設定，即使已開啟使用者層級許可權，也會封鎖所有使用者。

您也可以在使用者層級使用管理Microsoft Teams[中的應用程式許可權原則](teams-app-permission-policies.md)來關閉家長 App。

## <a name="more-information"></a>詳細資訊

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
