---
title: 重設外部使用者存取的全域原則
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
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
description: 您無法完全刪除全域原則。使用全域原則的 **[刪除]** 選項只會將全域原則重設為預設設定，而預設設定不包含對任何外部使用者存取選項的支援。
ms.openlocfilehash: acb275ac924dbb5b7e9ad377ab4d287a0734f752
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043655"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Skype 中的外部使用者存取的全域原則重設為企業伺服器 

如果您已建立或設定不想再使用的外部使用者存取原則，則可以執行下列動作：

  - 刪除任何已建立的網站或使用者原則。

  - 將全域原則重設為預設設定。預設全域原則設定拒絕任何外部使用者存取。全域原則無法刪除。

您無法完全刪除全域原則。使用全域原則的 **[刪除]** 選項只會將全域原則重設為預設設定，而預設設定不包含對任何外部使用者存取選項的支援。

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>若要將全域原則重設為預設設定

1.  從使用者帳戶是 RTCUniversalServerAdmins 群組成員 （或具有相等使用者權限），或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，，，然後輸入 Admin URL 以開啟 Skype for Business Server Control Panel。

3.  在左導覽列中，依序按一下 **[外部使用者存取]** 和 **[外部存取原則]**。

4.  在 **[外部存取原則]** 索引標籤上，依序按一下全域原則、**[編輯]** 和 **[刪除]**。

5.  系統提示確認刪除時，請按一下 [確定] ****。頁面頂端會出現一則訊息，通知您已將全域原則重設。


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 重設全域外部存取原則

使用 Windows PowerShell 和 Remove-csexternalaccesspolicy cmdlet 可以重設全域外部存取原則。 可以執行此 cmdlet，從 Skype for Business Server 管理命令介面或 Windows PowerShell 的遠端工作階段。 

## <a name="to-reset-the-global-external-access-policy"></a>若要重設全域外部存取原則

  - 這個命令可重設全域外部存取原則：
    
        Remove-CsExternalAccessPolicy -Identity "global"

如需詳細資訊，請參閱[Remove-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的說明主題。


