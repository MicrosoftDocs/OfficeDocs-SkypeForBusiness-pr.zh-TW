---
title: EDU Microsoft 家長應用程式系統管理員設定
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams EDU 文章檔先決條件，以及家長應用程式 PowerShell 設定。
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ca2c252964f610ee13924f25f5d4ca8e31b9d59
ms.sourcegitcommit: 4a9ea18808d17e2eb6e4e2e7e3894e33c14e8631
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2021
ms.locfileid: "59475904"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>在 Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

在 Microsoft Teams 中啟用家長應用程式是一個簡單的程式，為教師提供安全的方法，讓學生與保持租使用者中的學生及其連絡人通訊，並在整個教育者組織中進行縮放。

## <a name="requirements"></a>需求

- SDS (學校資料同步處理) - 您必須使用 CSV 選項將與您的學生相關聯的相關連絡人上傳到 SDS。 請參閱設定 [CSV for SDS](/schooldatasync/set-up-your-sds-flow) 和更新 [相關的Contacts以](/graph/api/relatedcontact-update) 瞭解更多資訊。
- 在 Teams管理中心中，課程擁有者必須已啟用聊天功能，且與未由組織管理Teams **帳戶** 進行聯合聊天。 

如果您需要以每個使用者為基礎啟用聯合聊天，請執行下列步驟。

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>以每個使用者為基礎啟用聯合聊天

1. 安裝最新的 PowerShell 模組Microsoft Teams預覽版。

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force -AllowClobber
    ```
    
2. 使用具有系統管理員許可權的認證在命令視窗中執行。

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```
    
3. 在通用群組/使用者層級組組或租使用者層級組配置中關閉和開啟。

    ```powershell
    #Retrieves tenant level configuration
    Get-CsTenantFederationConfiguration
    #Turn OFF tenant level configuration
    Set-CsTenantFederationConfiguration -AllowTeamsConsumer $false
    #Turn ON tenant level configuration
    Set-CsTenantFederationConfiguration -AllowTeamsConsumer $true
    #Turn OFF Global GROUP/USER level configuration
    Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false
    #Turn ON Global GROUP/USER level configuration
    Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false
    ```
        
    > [!NOTE]
    > 當進行此 PowerShell 時，可能需要一小時或一小時以上才能完成變更。
    
## <a name="more-information"></a>詳細資訊

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [將策略指派給使用者](/powershell/module/skype/grant-csexternalaccesspolicy)
