---
title: 使用承租人參數的商務用 Skype Online 中的 Cmdlet
description: 使用承租人參數的商務用 Skype Online 中的 Cmdlet。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff2b8053dd855a854fa26699770d3dafaa0dcbd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546799"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a>使用承租人參數的商務用 Skype Online 中的 Cmdlet

 


修改您的公用提供者設定時，您必須提供承租人身分識別;即使您只有一個承租人，也是如此。 例如，此命令會將 Windows Live 設定為您的使用者可與之通訊的唯一公開提供者：

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

幸運的是，您不需要輸入承租人識別碼 (例如，bf19b7db-6960-41e5-a139-2aa373474354) 每次您執行其中一個 Cmdlet。 相反地，您可以執行 [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) Cmdlet，將租使用者識別碼儲存在變數中，然後在呼叫另一個 Cmdlet 時使用該變數，以取得租使用者識別碼。 例如：

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

或者，您可以在單一命令中執行這項作業，方法是檢索租使用者識別碼，然後將此值管線傳送至 Set-CsTenantPublicProvider Cmdlet：

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

呼叫 **Get-CsTenant** Cmdlet 時，不需要指定租使用者識別碼。 此命令會傳回您租使用者的相關資訊：

    Get-CsTenant

下列 Cmdlet 會接受租使用者身分識別。 不過，在這種情況下，此參數是選用的，而且不需要在呼叫 Cmdlet 時輸入。 相反地，Windows PowerShell 會根據您目前連線的商務用 Skype Online 租使用者，為您輸入承租人身分識別：

  - [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))

  - [CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))

  - [CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))

  - [CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

例如，您可以使用下列命令呼叫 **CsTenantFederationConfiguration** Cmdlet：

    Get-CsTenantFederationConfiguration

您可以在呼叫 Get-CsTenantFederationConfiguration 時加入租使用者參數，但這不是必要的：

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a>另請參閱


[商務用 Skype Online 中的身分識別、範圍和承租人](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[商務用 Skype Online Cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

