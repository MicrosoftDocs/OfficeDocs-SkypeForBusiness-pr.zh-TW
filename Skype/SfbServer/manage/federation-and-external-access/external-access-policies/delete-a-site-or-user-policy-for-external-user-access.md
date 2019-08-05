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
localization_priority: Normal
description: 您可以刪除 [外部存取原則] 頁面上的 [商務用 Skype Server] 控制台中所列的任何網站或使用者原則。
ms.openlocfilehash: 615df309088a329e07f5417dce16e98366a371c7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188812"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>刪除外部使用者存取的網站或使用者原則

如果您已建立或設定您不想再使用的外部使用者存取原則, 您可以執行下列動作:

  - 刪除您建立的任何網站或使用者原則。

  - 將全域原則重設為預設設定。 預設全域原則設定會拒絕任何外部使用者存取。 無法刪除全域原則。


您可以刪除 [**外部存取原則**] 頁面上的 [商務用 Skype Server] 控制台中所列的任何網站或使用者原則。 刪除全域原則並不會真正將它刪除, 但只會將其重設為預設設定, 而不包含任何外部使用者存取選項的支援。 如需重設全域原則的詳細資訊, 請參閱[重設外部使用者存取的全域原則](reset-the-global-policy-for-external-user-access.md)。


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>刪除網站或使用者原則供外部使用者存取

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。 

3.  按一下 [**外部使用者存取**], 然後按一下 [**外部存取原則**]。

4.  在 [**外部存取原則**] 索引標籤上, 按一下您要刪除的網站或使用者原則, 按一下 [**編輯**], 然後按一下 [**刪除**]。

5.  當系統提示您確認刪除時, 請按一下 **[確定]**。


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除 PIN 原則

您可以使用 Windows PowerShell 與 Remove CsExternalAccessPolicy Cmdlet 來刪除外部存取原則。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 


## <a name="to-remove-a-specific-external-access-policy"></a>移除特定外部存取原則

  - 這個命令會移除已套用至雷德蒙者網站的外部存取原則:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>若要移除所有套用至每個使用者範圍的外部存取原則

  - 這個命令會移除在每個使用者作用中設定的所有外部存取原則:
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>若要移除所有外部存取原則 (在禁止外部使用者存取的情況下)

  - 這個命令會刪除已停用使用者存取的所有外部存取原則:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


如需詳細資訊, 請參閱[Remove CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) Cmdlet 的說明主題。
