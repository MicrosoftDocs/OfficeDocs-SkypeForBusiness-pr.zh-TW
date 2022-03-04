---
title: 家長在 Teams 教育版
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft TeamsTeams 教育版，
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8d1b84fc78558fcbb1945cbc56b311b5e06234a5
ms.sourcegitcommit: e97c981489ff1f02674df57426da3b22cc6d68c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2022
ms.locfileid: "63062527"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>在中設定父Microsoft Teams 教育版

Teams 教育版中的家長關係可協助教師使用 Teams 聊天，安全地與班級團隊中的學生家長和監護人聯繫並互動，這將在教育者組織中進行縮放。 所有家長和監護人的資料都是使用學校資料同步處理，讓 IT 員工能夠順暢地設定專案。

一旦設定好教育者和監護人，他們就可以使用聊天Teams聊天。 

若要取得與教師聯繫家長和監護人的指引，請參閱連線[與Teams](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960)。

若要取得讓教育者設定與家長和監護人通訊的指引，請參閱在 Microsoft Teams 中[與監護人Microsoft Teams](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e?ui=en-us&rs=en-us&ad=us)。

家長也可以使用監督聊天。 家長和監護人沒有完整的Teams許可權，這表示他們無法開始與學生交談，或移除使用者的完整許可權 (例如教育) 聊天。 有關監看聊天的資訊[，請參閱在](supervise-chats-edu.md)聊天中Microsoft Teams。

## <a name="requirements"></a>需求

### <a name="school-data-sync"></a>學校資料同步處理

- 您需要學校資料同步處理 (SDS) ，以填入每個學生的家長和監護人 **相關連絡人** 資訊。
  - [部署SDS](/schooldatasync/parents-and-guardians-in-sds)

- 如果您需要協助為租使用者中的學生設定 SDS，以及填報家長和監護人相關連絡人，請聯絡 EDU 客戶成功小組：：
  - 在 FastTrack 完成[RFA 程式](https://www.microsoft.com/fasttrack?rtc=1)。
  - 在支援服務中開啟 [票證](https://aka.ms/sdssupport)。

- 目前，SDS 僅支援父連絡人的 CSV 資料輸入功能;不過，您可以針對所有名冊資料使用 [PowerSchool API 同步](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) 處理或 [OneRoster API 同步](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) 處理，只要使用 CSV 新增父連絡人。
  - 使用 [SDS v1 CSV](/schooldatasync/school-data-sync-format-csv-files-for-sds)同步格式建立第二個同步設定檔。
  - 將兩個填滿的 [父](/schooldatasync/parent-contact-sync-file-format) 檔案，將 v1 檔案的其餘部分清空， (頁) 。
    - User.csv
    - Guardianrelationship.csv
  - 若要查看 v1 CSV 檔案的範例集，請參閱檔案的最小值GitHub[屬性](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes)。
  - 如果您想要在初始同步處理之後自動提取 CSV 檔案，請閱讀 [我們的 CSV 檔案同步處理自動化檔](/schooldatasync/csv-file-sync-automation)。
  - 若要取得設定 SDS 資料同步處理之協助，請與我們的客戶成功小組聯繫[，或](https://www.microsoft.com/fasttrack?rtc=1)[開啟支援票證](https://edusupport.microsoft.com/support?product_id=data_sync)。

### <a name="teams-admin-center---policies"></a>Teams系統管理中心 - 政策

- 課程團隊擁有者必須Teams開啟聊天。
- 課程團隊擁有者必須擁有外部存取權，Teams **組織未** 管理的帳戶。
  - 您必須在租使用者層級和使用者層級開啟此功能。 租使用者層級設定可在系統管理中心的 **>外部存取** Teams找到。 您也可以透過 PowerShell 存取此設定。 使用者層級外部存取策略只能透過 PowerShell 存取。 請參閱下方的 PowerShell 命令以進一步提供指引。

> [!NOTE]
>家長和監護人在家長功能中會歸類為外部使用者，這表示他們沒有完整的租使用者權利。 他們只能存取新加入的聊天或聊天，以及檔案、影像，以及聊天中共用的其他內容。
>
>此外，外部使用者 (離線、可用、忙碌等 ) ，但您可以使用 PowerShell 來關閉此功能，以保護使用者的隱私權。 在 PowerShell 中，使用 [Set-CsPrivacyConfiguration 和](/powershell/module/skype/set-csprivacyconfiguration) set ``EnablePrivacyMode=true`` 。
>
>即使家長和監護人是外部使用者，他們對於聊天的貢獻還是可以探索的。 瞭解如何在 Teams中執行電子檔探索調查，以執行電子檔探索[Microsoft Teams](ediscovery-investigation.md)。

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>允許外部存取Teams組織未管理的帳戶

若要允許教育人員與 Teams 中的家長和監護人通訊，教育租使用者 IT 系統管理員必須更新租使用者的政策，才能允許租使用者Teams帳戶的外部存取權。 有關管理外部存取的資訊，請參閱管理[外部](manage-external-access.md)存取Microsoft Teams。

以下是為家長和監護人開啟外部存取權的步驟。

1. 安裝最新版 PowerShell Microsoft Teams預覽版。

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```

2. 使用具有系統管理員許可權的認證，執行下列命令：

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

    系統預設會針對所有使用者層級的外部存取策略開啟 Teams 帳戶，而組織未在使用者層級管理 (`EnableTeamsConsumerAccess`) 帳戶開啟外部存取。 使用者必須同時開啟租使用者層級設定和使用者層級策略設定，使用者Teams非組織管理的帳戶進行外部存取。 如果您不希望租使用者中的每個使用者都開啟此存取，您應該確定已關閉租使用者層級設定、更新指派給使用者的使用者層級外部存取策略，然後開啟租使用者層級設定。

    若要檢查哪些使用者層級的外部存取策略存在，以及指派給誰，您可以使用下列步驟：

3. 檢查使用者層級的外部存取策略是否存在。

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. 針對 "Global" 策略外的其他每一個策略，檢查哪些使用者已指派該策略。

   > [!NOTE]
   > 任何未指派特定策略的使用者都會回到 '全域'政策。 新增到租使用者的任何新使用者都會有指派的 "Global" 策略。

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

由於所有使用者層級 `EnableTeamsConsumerAccess` 的外部存取策略預設都設為 True `EnableTeamsConsumerAccess` ，如果您想要調整特定使用者的設定，您可以使用調整後的設定來建立/修改現有的外部存取策略，以及/或使用下列 PowerShell Cmdlet 將使用者重新指派至新的或現有的策略：

- 建立新的外部存取策略： [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- 自訂現有的外部存取 (，包括"全域") ： [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> 下列訂閱預設政策無法修改：'FederationAndPICDefault'，'FederationOnly'，'NoFederationAndPIC'。 根據預設，會指派給所有使用者的'FederationAndPICDefault'政策，不過新使用者現在預設會指派'全域'政策。 如果您需要變更已指派這些訂閱預設策略的使用者之策略設定，請為這些使用者指派具有正確設定的不同策略。

- 指派外部存取策略給單一 [使用者：Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- 指派原則給一組使用者： [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

為租使用者中的使用者正確設定使用者層級的外部存取策略之後，您可以使用下列 Cmdlet 為租使用者開啟租使用者層級設定 () `AllowTeamsConsumer` ：

- 設定租使用者的聯盟設定設定： [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>在系統管理中心開啟家長Teams應用程式

家長應用程式預設為關閉，因此課程團隊擁有者不會在班級團隊中看到它，除非課程管理中心允許Teams應用程式。 家長應用程式在系統管理中心Teams使用[允許發行者封鎖的應用程式。](manage-apps.md#apps-blocked-by-publishers)

您隨時都可以使用允許和封鎖系統管理中心中的應用程式，在租使用者[](manage-apps.md#allow-and-block-apps)層級Teams應用程式。 如果在租使用者層級關閉，將會封鎖所有使用者，即使使用者層級許可權已開啟也一樣。

您也可以在使用者層級使用管理應用程式許可權政策來關閉家長[Microsoft Teams](teams-app-permission-policies.md)。

## <a name="more-information"></a>詳細資訊

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
