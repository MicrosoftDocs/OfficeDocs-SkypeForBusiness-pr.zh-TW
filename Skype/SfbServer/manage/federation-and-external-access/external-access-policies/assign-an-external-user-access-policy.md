---
title: 指派外部使用者存取原則
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果使用者已啟用商務用 Skype Server 的功能，您可以在商務用 Skype Server 控制台中設定 SIP 同盟、遠端使用者存取及公用立即訊息（IM）連線，方法是將適當的原則套用至特定的使用者。
ms.openlocfilehash: b87eb377b23063dbcdfd9562a99533da230a8f30
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818324"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>將外部使用者存取原則指派給商務用 Skype 啟用的使用者

如果使用者已啟用商務用 Skype Server 的功能，您可以在商務用 Skype Server 控制台中設定 SIP 同盟、遠端使用者存取及公用立即訊息（IM）連線，方法是將適當的原則套用至特定的使用者。 例如，如果您建立了支援遠端使用者存取的原則，您必須先將其套用至使用者，才能讓使用者從遠端位置連線到商務用 Skype Server，並從遠端位置與內部使用者共同作業。


> [!NOTE]  
> 若要支援外部使用者存取，您必須針對您要支援的每個外部使用者存取類型啟用支援，然後設定適當的原則和其他選項來控制其用途。 如需詳細資訊，請參閱[管理商務用 Skype Server 的同盟和外部存取](../managing-federation-and-external-access.md)。


使用本主題中的程式，將先前建立的外部使用者存取原則套用至一或多個使用者帳戶。


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>將外部使用者原則套用到使用者帳戶

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左導覽列中，按一下 [使用者]****，然後搜尋想要設定的使用者帳戶。

4.  在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]**** 及 [顯示詳細資料]****。

5.  在 [在**外部存取原則****編輯商務用 Skype 伺服器使用者**] 底下，選取您要套用的使用者原則。
     
> [!NOTE]  
> [ ** \<自動>** 設定] 會套用 [預設伺服器] 或 [全域原則設定]。


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指派每個使用者的外部存取原則

您可以使用 Windows PowerShell 和 Grant CsExternalAccessPolicy Cmdlet 來指派每個使用者的外部存取原則。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>將每個使用者的外部存取原則指派給單一使用者

  - 這個命令會將每個使用者的外部存取原則 RedmondExternalAccessPolicy 指派給使用者 Ken Myer。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>將每個使用者的外部存取原則指派給多個使用者

  - 這個命令會將每個使用者的外部存取原則 USAExternalAccessPolicy 指派給在 Active Directory 中的美國組織單位中擁有帳戶的所有使用者。 如需此命令中使用的 OU 參數的詳細資訊，請參閱[move-csuser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) Cmdlet 的相關檔。
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>若要取消指派每個使用者的外部存取原則

  - 這個命令會會先前指派給 Ken Myer 的任何每使用者外部存取原則。 未指派每個使用者原則時，會使用全域原則（如果有的話）自動管理 Ken Myer，或在其本機網站原則中使用。 網站原則的優先順序高於全域原則。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



如需詳細資訊，請參閱[Grant CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) Cmdlet 的說明主題。


