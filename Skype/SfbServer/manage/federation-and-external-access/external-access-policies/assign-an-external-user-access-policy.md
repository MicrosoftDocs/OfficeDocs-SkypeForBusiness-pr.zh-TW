---
title: 指派外部使用者存取原則
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果已為使用者啟用商務用 Skype Server，您可以將適當的原則套用至特定使用者，以在商務用 Skype Server 控制台中設定 SIP 同盟、遠端使用者存取及公用立即訊息 (IM) 連線能力。
ms.openlocfilehash: d53840f1abd13b504916340b585aa53ee7324330c2fe34c463e66c54dc180417
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/11/2021
ms.locfileid: "57849558"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>將外部使用者存取原則指派給已啟用商務用 Skype 使用者

如果已為使用者啟用商務用 Skype Server，您可以將適當的原則套用至特定使用者，以在商務用 Skype Server 控制台中設定 SIP 同盟、遠端使用者存取及公用立即訊息 (IM) 連線能力。 例如，如果您建立一個原則來支援遠端使用者存取，您必須先將它套用至使用者，使用者才能從遠端位置連接至商務用 Skype Server，並從遠端位置與內部使用者共同作業。


> [!NOTE]  
> 若要支援外部使用者存取，您必須啟用想要支援之每種外部使用者存取類型的支援，以及設定適當原則及其他控制使用的選項。 如需詳細資訊，請參閱[管理同盟與外部存取商務用 Skype Server](../managing-federation-and-external-access.md)。


使用本主題中的程序，將先前建立的外部使用者存取原則套用至一或多個使用者帳戶。


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>將外部使用者原則套用至使用者帳戶

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 **[使用者]**，然後搜尋想要設定的使用者帳戶。

4.  在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。

5.  在 [**外部存取原則**] 底下的 [**編輯商務用 Skype Server 使用者**] 中，選取您要套用的使用者原則。
     
> [!NOTE]  
> 設定會套用 **\<Automatic>** 預設伺服器或全域原則設定。


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指派 Per-User 外部存取原則

您可以使用 Windows PowerShell 和 Grant-CsExternalAccessPolicy Cmdlet 指派每個使用者的外部存取原則。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話執行此 Cmdlet。 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>將個別使用者外部存取原則指派給單一使用者

  - 此命令可將個別使用者外部存取原則 RedmondExternalAccessPolicy 指派給使用者 Ken Myer。<br/><br/>Grant-CsExternalAccessPolicy-Identity "Ken Myer"-PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>將個別使用者外部存取原則指派給多個使用者

  - 此命令可將個別使用者外部存取原則 USAExternalAccessPolicy，指派給所有具有 Active Directory 中之 UnitedStates OUto 帳戶的使用者。 如需此命令中所使用之 OU 參數的詳細資訊，請參閱 [Get-CsUser](/powershell/module/skype/Get-CsUser) Cmdlet 的檔。<br/><br/>Get-CsUser-OU "OU = 美國，dc = litwareinc，dc = com" |Grant-CsExternalAccessPolicy PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>取消指派個別使用者外部存取原則

  - 此命令可將任何先前指派給 Ken Myer 的個別使用者外部存取原則予以解除指派。一旦解除指派個別使用者原則，即會自動使用全域原則或其本機網站原則 (如果存在的話) 來管理 Ken Myer。網站原則的優先順序高於全域原則。<br/><br/>Grant-CsExternalAccessPolicy-Identity 「Ken Myer」-PolicyName $Null


如需詳細資訊，請參閱 [get-csexternalaccesspolicy](/powershell/module/skype/Grant-CsExternalAccessPolicy) Cmdlet 的 [說明] 主題。
