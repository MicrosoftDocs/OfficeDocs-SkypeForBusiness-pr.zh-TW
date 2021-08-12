---
title: 刪除外部使用者存取的網站或使用者原則
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
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
description: 您可以刪除 [外部存取原則] 頁面的 [商務用 Skype Server 控制台] 中所列的任何網站或使用者原則。
ms.openlocfilehash: 79858592b8ba7dbcee692807bba3d2a472a8579cbc843ddeb96c25c811cc6df7
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848678"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>刪除外部使用者存取的網站或使用者原則

如果您已建立或設定不再想要使用的外部使用者存取原則，您可以執行下列方法：

  - 刪除任何已建立的網站或使用者原則。

  - 將全域原則重設為預設設定。預設全域原則設定拒絕任何外部使用者存取。全域原則無法刪除。


您可以刪除 [**外部存取原則**] 頁面的 [商務用 Skype Server 控制台] 中所列的任何網站或使用者原則。 刪除全域原則並不會實際將其刪除，但只會將其重設為預設設定，但不包括對任何外部使用者存取選項的支援。 如需重設全域原則的詳細資訊，請參閱 [重設外部使用者存取的全域原則](reset-the-global-policy-for-external-user-access.md)。


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>刪除外部使用者存取的網站或使用者原則

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  按一下 **[外部使用者存取]**，並按一下 **[外部存取原則]**。

4.  在 **[外部存取原則]** 索引標籤上，按一下想要刪除的網站或使用者原則，並按一下 **[編輯]**，然後按一下 **[刪除]**。

5.  系統提示確認刪除時，請按一下 **[確定]**。


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除 PIN 原則

您可以使用 Windows PowerShell 和 Remove-CsExternalAccessPolicy Cmdlet 刪除外部存取原則。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話執行此 Cmdlet。 


## <a name="to-remove-a-specific-external-access-policy"></a>移除特定的外部存取原則

  - 此命令會移除套用至 Redmond 網站的外部存取原則：<br/><br/>Remove-CsExternalAccessPolicy 身分識別 "site： Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>移除所有套用至個別使用者範圍的外部存取原則

  - 此命令會移除在個別使用者範圍內設定的外部存取原則：<br/><br/>Get-CsExternalAccessPolicy-Filter "tag： *" |Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>移除已停用外部使用者存取的所有外部存取原則

  - 此命令會刪除已停用外部使用者存取的所有外部存取原則：<br/><br/>Get-CsExternalAccessPolicy |Where-Object {$ _。EnableOutsideAccess-eq $False} |Remove-CsExternalAccessPolicy


如需詳細資訊，請參閱 [get-csexternalaccesspolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) Cmdlet 的 [說明] 主題。
