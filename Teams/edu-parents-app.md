---
title: EDU Microsoft 家長應用程式系統管理員設定
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams EDU 文章檔先決條件和家長應用程式 PowerShell 設定。
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8cd05f6ad2b238b4db2d611a6fc00e5f8a57189f
ms.sourcegitcommit: 6da1531dda6a0a3eecdca40e682783cc81c0d3e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60785146"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>在 Microsoft Teams

家長應用程式可協助授課者使用聊天功能，安全地與班級中的學生家長和監護人Teams互動，這將會在整個授課者組織中進行縮放。 所有家長和監護人的資料都是使用學校資料同步處理，讓教育者和 IT 員工能夠順暢地設定專案。

## <a name="requirements"></a>需求

### <a name="school-data-sync"></a>學校資料同步處理

- 您需要學校資料同步處理 (SDS) ，以填入每個 **學生的相關連絡人** 資訊。
  - [部署SDS](/schooldatasync/how-to-deploy-sds-using-sds-v2.1-csv-files)

- 如果您需要協助，在租使用者中設定 SDS 及啟用父連絡人，請聯絡 EDU 客戶成功小組：：
  - 在 FastTrack 完成[RFA 程式](https://www.microsoft.com/fasttrack?rtc=1)。
  - 在支援服務中 [開啟票證](https://aka.ms/sdssupport)。

### <a name="teams-admins-center---policies"></a>Teams系統管理中心 - 政策

- 課程擁有者必須已啟用聊天功能
- 課程擁有者必須擁有外部存取，Teams **組織未管理的帳戶**。 
  - 您可以在租使用者層級的 >外部 Access 中找到這項設定，或者如果您想要為一組使用者啟用，請參閱下方的 PowerShell。

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>以每個使用者為基礎啟用聯合聊天

1. 安裝最新版 PowerShell 模組Microsoft Teams預覽版。

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
    
2. 使用具有系統管理員許可權的認證，在命令視窗中執行下列命令：

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

根據預設Teams使用者層級的外部存取 (EnableTeamsConsumerAccess) 啟用消費者外部存取。 使用者必須啟用 (AllowTeamsConsumer) 的租使用者層級設定和使用者層級策略設定，使用者Teams外部存取。 如果您不希望租使用者中的每個人都啟用 Teams 消費者外部存取，您應該先更新指派給使用者的使用者層級外部存取策略，再啟用租使用者層級設定。

如果您需要檢查哪些使用者層級的外部存取策略存在，以及指派給誰，您可以使用下列步驟：
    
3. 檢查存在哪些使用者層級的外部存取策略。

    ```powershell
    Get-CsExternalAccessPolicy -Include All
    ```

4. 針對 "Global" 策略外的其他每一個策略，檢查哪些使用者已指派該策略。 注意：任何未指派特定策略的使用者都會回到 '全域'政策

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

### <a name="further-powershell-options"></a>進一步 PowerShell 選項

由於所有使用者層級的外部存取策略預設都會設定為 True，如果您想要更新其中任何一個策略來調整 EnableTeamsConsumerAcces 設定，您可以透過下列 PowerShell 建立具有調整設定的新外部存取策略，或重新指派使用者至新的或現有的策略：

- 建立新的外部存取 (建立新的外部存取策略，並定義以下 [) ：New-CsExternalAccesSPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- 自訂現有的外部存取 (修改現有外部存取策略的設定，包括全域原則 [) ) ：Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> 無法修改下列訂閱預設值：「FederationAndPICDefault」、「FederationOnly」、「NoFederationAndPIC」。 如果您需要為已指派這些策略的使用者變更其策略設定，請指派具有正確設定的不同策略給這些使用者。

- 指派外部存取策略給單一 [使用者：Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- 指派原則給一組使用者 [：New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

一旦確定所有使用者的使用者層級外部存取策略已正確設定，就可以啟用租使用者層級設定，使用下列 Cmdlet 控制租使用者Teams消費者外部存取：

- 將租使用者的聯 (設定設為 true [) ：Set-CsTenantFederationConfiguration (SkypeForBusiness](/powershell/module/skype/set-cstenantfederationconfiguration)) 

### <a name="disabling-the-parents-app"></a>停用家長應用程式

家長應用程式預設為啟用，因此所有課程擁有者都會在班級團隊中看到該應用程式。 您可以在租使用者層級使用允許並封鎖系統管理中心[](manage-apps.md#allow-and-block-apps)中的應用程式Microsoft Teams應用程式。 如果在租使用者層級停用此功能，將會封鎖所有使用者，即使已啟用使用者層級許可權。

您也可以在使用者層級使用 [在 Microsoft Teams 中管理應用程式許可權 (teams-app-permission-policies.md) 。

## <a name="more-information"></a>詳細資訊

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [將策略指派給使用者](/powershell/module/skype/grant-csexternalaccesspolicy)
