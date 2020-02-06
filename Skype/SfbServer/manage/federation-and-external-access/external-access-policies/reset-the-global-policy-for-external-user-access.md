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
description: 您無法完全刪除全域原則。 在全域原則上使用 [**刪除**] 選項時，只會將全域原則重設為預設設定，而不包含任何外部使用者存取選項的支援。
ms.openlocfilehash: e0e59c4de1b7a4bacbef30b4caa3d26c29b81e84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818264"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>在商務用 Skype Server 中重設外部使用者存取的全域原則 

如果您已建立或設定您不想再使用的外部使用者存取原則，您可以執行下列動作：

  - 刪除您建立的任何網站或使用者原則。

  - 將全域原則重設為預設設定。 預設全域原則設定會拒絕任何外部使用者存取。 無法刪除全域原則。

您無法完全刪除全域原則。 在全域原則上使用 [**刪除**] 選項時，只會將全域原則重設為預設設定，而不包含任何外部使用者存取選項的支援。

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>將全域原則重設為預設設定

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。

3.  在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**外部存取原則**]。

4.  在 [**外部存取原則**] 索引標籤上，按一下 [全域原則]，按一下 [**編輯**]，然後按一下 [**刪除**]。

5.  當系統提示您確認刪除時，請按一下 **[確定]**。 頁面頂端會出現一則訊息，通知您全域原則已重設。


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來重設全域外部存取原則

您可以使用 Windows PowerShell 和 CsExternalAccessPolicy Cmdlet 來重設全域外部存取原則。 此 Cmdlet 可從商務用 Skype Server Management 命令介面或從遠端會話 Windows PowerShell 執行。 

## <a name="to-reset-the-global-external-access-policy"></a>若要重設全域外部存取原則

  - 這個命令會重定全域外部存取原則：
    
        Remove-CsExternalAccessPolicy -Identity "global"

如需詳細資訊，請參閱[Remove CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) Cmdlet 的說明主題。


