---
title: 商務用 Skype Online 中使用租使用者參數的 Cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 40f325c55415f97822b1e8c9d21a6d2e80e27273
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728013"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a>商務用 Skype Online 中使用租使用者參數的 Cmdlet

 


修改公用提供者設定時，您必須提供租使用者身分識別;即使您只有單一租使用者，也是如此。 例如，這個命令會將 Windows Live 設為您的使用者可與之通訊的唯一公用提供者：

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

幸運的是，您不需要在每次執行其中一個 Cmdlet 時輸入租使用者識別碼（例如，bf19b7db-6960-41e5-a139-2aa373474354）。 相反地，您可以執行[CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) Cmdlet、儲存變數中的租使用者識別碼，然後在您呼叫其中一個其他 Cmdlet 時使用該變數，以取得租使用者識別碼。 例如：

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

或者，您也可以在單一命令中執行這項操作，方法是檢索租使用者識別碼，然後將該值 CsTenantPublicProvider Cmdlet：

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

在呼叫**CsTenant** Cmdlet 時，您不需要指定租使用者識別碼。 這個命令會傳回您租使用者的相關資訊：

    Get-CsTenant

下列 Cmdlet 接受租使用者身分識別。 不過，在這些情況下，參數是選擇性的，而且不需要在呼叫 Cmdlet 時輸入。 相反地，Windows PowerShell 會根據您目前連線至的商務用 Skype Online 租使用者，有效地輸入您的租使用者身分識別：

  - [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))

  - [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))

  - [Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))

例如，您可以使用此命令呼叫**CsTenantFederationConfiguration** Cmdlet：

    Get-CsTenantFederationConfiguration

雖然不必要，但您可以在呼叫 CsTenantFederationConfiguration 時包含租使用者參數：

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a>請參閱


[商務用 Skype Online 中的身分識別、範圍和租使用者](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

