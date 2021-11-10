---
title: Microsoft EDU 家長應用程式在 Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams EDU 文章，記錄家長應用程式的先決條件和設定。
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9243dfedb11c9102673e821bd2fac9d06cf3c834
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "60887291"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>在 Microsoft Teams

家長應用程式可協助教師使用 Teams 聊天，安全地與班級團隊中的學生家長和監護人聯繫並互動，這將在教育者組織中進行縮放。 所有家長和監護人的資料都是使用學校資料同步處理，讓 IT 員工能夠順暢地設定專案。

## <a name="requirements"></a>需求

### <a name="school-data-sync"></a>學校資料同步處理

- 您需要學校資料同步處理 (SDS) ，以填入每個學生的家長和監護人 **相關連絡人** 資訊。
  - [部署SDS](/schooldatasync/how-to-deploy-sds-using-sds-v2.1-csv-files)

- 如果您需要協助為租使用者中的學生設定 SDS，以及填報家長和監護人相關連絡人，請聯絡 EDU 客戶成功小組：：
  - 在 FastTrack 完成[RFA FastTrack。](https://www.microsoft.com/fasttrack?rtc=1)
  - 在支援服務中 [開啟票證](https://aka.ms/sdssupport)。

### <a name="teams-admin-center---policies"></a>Teams系統管理中心 - 政策

- 課程團隊擁有者必須已啟用Teams聊天功能。
- 課程團隊擁有者必須擁有外部存取權，Teams **組織未管理的帳戶**。 
  - 您必須在租使用者層級和使用者層級啟用此功能。 租使用者層級設定可在系統管理中心的 **>外部存取** Teams找到。 您也可以透過 PowerShell 存取此設定。 使用者層級外部存取策略只能透過 PowerShell 存取。 請參閱下方的 PowerShell 命令以進一步提供指引。

## <a name="enabling-external-access-with-teams-accounts-not-managed-by-an-organization"></a>使用組織未管理Teams帳戶啟用外部存取

1. 安裝最新版 PowerShell 模組Microsoft Teams預覽版。

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
    
2. 使用具有系統管理員許可權的認證，執行下列命令：

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

系統預設會針對所有使用者層級的外部存取Teams使用者層級 () 帳戶啟用外部 `EnableTeamsConsumerAccess` 存取。 使用者必須同時啟用租使用者層級設定和使用者層級策略設定，使用者Teams未由組織管理的帳戶。 如果您不希望租使用者中的每個使用者都啟用此存取，您應該確定已停用租使用者層級設定、更新指派給使用者的使用者層級外部存取策略，然後啟用租使用者層級設定。

若要檢查哪些使用者層級的外部存取策略存在，以及指派給誰，您可以使用下列步驟：
    
3. 檢查存在哪些使用者層級的外部存取策略。

    ```powershell
    Get-CsExternalAccessPolicy -Include All
    ```

4. 針對 "Global" 策略外的其他每一個策略，檢查哪些使用者已指派該策略。 注意：任何未指派特定策略的使用者都會回到 '全域'政策。 新增到租使用者的任何新使用者都會有指派的 "Global" 策略。

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

由於所有使用者層級的外部存取策略預設都設為 True，如果您想要調整特定使用者的設定，您可以使用調整後的設定建立/修改現有的外部存取策略，以及/或使用下列 `EnableTeamsConsumerAccess` PowerShell Cmdlet 將使用者重新指派至新的或現有的 `EnableTeamsConsumerAccess` 策略：

- 建立新的外部存取策略 [：New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- 自訂現有的外部存取 (，包括"全域 [") ：Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> 下列訂閱預設政策無法修改：'FederationAndPICDefault'，'FederationOnly'，'NoFederationAndPIC'。 根據預設，會指派給所有使用者的'FederationAndPICDefault'政策，不過新使用者現在預設會指派'全域'政策。 如果您需要變更已指派這些訂閱預設策略的使用者之策略設定，請為這些使用者指派具有正確設定的不同策略。

- 指派外部存取策略給單一 [使用者：Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- 指派原則給一組使用者 [：New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

為租使用者中的使用者正確設定使用者層級的外部存取策略之後，您可以使用下列 Cmdlet 為租使用者啟用租使用者層級設定 () ： `AllowTeamsConsumer`

- 設定租使用者的聯盟設定設定 [：Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="disabling-the-parents-app"></a>停用家長應用程式

家長應用程式預設為啟用，因此所有班級團隊擁有者都會在班級團隊中看到該應用程式。 

您可以在租使用者層級使用允許並封鎖系統管理中心[](manage-apps.md#allow-and-block-apps)中的應用程式Microsoft Teams應用程式。 如果應用程式在租使用者層級停用，將會封鎖所有使用者，即使已啟用使用者層級許可權。

您也可以在使用者層級使用管理應用程式權限原則來停用[應用程式](teams-app-permission-policies.md)Microsoft Teams。

## <a name="more-information"></a>詳細資訊

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
