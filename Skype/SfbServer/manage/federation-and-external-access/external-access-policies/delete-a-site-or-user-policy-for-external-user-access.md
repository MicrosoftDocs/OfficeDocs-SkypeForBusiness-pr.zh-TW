---
title: 刪除外部使用者存取的網站或使用者原則
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
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
description: 您可以刪除 skype for Business Server Control Panel 列在 [外部存取原則] 頁面上任何網站或使用者原則。
ms.openlocfilehash: ae0a0499e7497c4d62884860a2730960e5070ac8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041232"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>刪除外部使用者存取的網站或使用者原則

如果您已建立或設定不想再使用的外部使用者存取原則，則可以執行下列動作：

  - 刪除任何已建立的網站或使用者原則。

  - 將全域原則重設為預設設定。預設全域原則設定拒絕任何外部使用者存取。全域原則無法刪除。


您可以刪除 skype for Business Server Control Panel 列在 [**外部存取原則**] 頁面上任何網站或使用者原則。 刪除全域原則並不是實際加以刪除，只是將它重設為不支援任何外部使用者存取選項的預設設定。 如需重設全域原則的詳細資訊，請參閱[重設外部使用者存取的全域原則](reset-the-global-policy-for-external-user-access.md)。


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>刪除外部使用者存取的網站或使用者原則

1.  從使用者帳戶是 RTCUniversalServerAdmins 群組成員 （或具有相等使用者權限），或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，，，然後輸入 Admin URL 以開啟 Skype for Business Server Control Panel。 

3.  按一下 **[外部使用者存取]**，並按一下 **[外部存取原則]**。

4.  在 **[外部存取原則]** 索引標籤上，按一下想要刪除的網站或使用者原則，並按一下 **[編輯]**，然後按一下 **[刪除]**。

5.  系統提示確認刪除時，請按一下 **[確定]**。


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除 PIN 原則

使用 Windows PowerShell 和 Remove-csexternalaccesspolicy cmdlet 可刪除外部存取原則。 可以執行此 cmdlet，從 Skype for Business Server 管理命令介面或 Windows PowerShell 的遠端工作階段。 


## <a name="to-remove-a-specific-external-access-policy"></a>若要移除的特定外部存取原則

  - 此命令會移除套用至 Redmond 網站的外部存取原則：
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>若要移除所有外部存取原則套用至個別使用者範圍

  - 此命令會移除在個別使用者範圍內設定的外部存取原則：
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>若要移除其中已停用外部使用者存取的所有外部存取原則

  - 此命令會刪除已停用外部使用者存取的所有外部存取原則：
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


如需詳細資訊，請參閱[Remove-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的說明主題。
