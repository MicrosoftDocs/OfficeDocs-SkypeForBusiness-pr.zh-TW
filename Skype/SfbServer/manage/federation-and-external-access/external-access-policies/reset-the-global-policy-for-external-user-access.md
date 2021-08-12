---
title: 重設外部使用者存取的全域原則
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
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
description: 您無法完全刪除全域原則。 在全域原則上使用 [ **刪除** ] 選項，只會將全域原則重設為預設設定，但不包括對任何外部使用者存取選項的支援。
ms.openlocfilehash: ebdd18d85570156a00cb4b31d36ec5660365223318ed748b799e9100c1deaaa5
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848668"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>在商務用 Skype Server 中重設外部使用者存取的全域原則 

如果您已建立或設定不再想要使用的外部使用者存取原則，您可以使用下列方法：

  - 刪除任何已建立的網站或使用者原則。

  - 將全域原則重設為預設設定。 預設全域原則設定拒絕任何外部使用者存取。 無法刪除全域原則。

您無法完全刪除全域原則。 全域原則上的 **Delete** 選項只會將全域原則重設為預設設定，但不包括對任何外部使用者存取選項的支援。

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>若要將全域原則重設為預設設定

1.  從屬於 RTCUniversalServerAdmins 群組成員或具有同等使用者權限的使用者帳戶，或是指派給 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。

3.  在左導覽列中，依序按一下 **[外部使用者存取]** 和 **[外部存取原則]**。

4.  在 **[外部存取原則]** 索引標籤上，依序按一下全域原則、**[編輯]** 和 **[刪除]**。

5.  系統提示確認刪除時，請按一下 [確定] 。頁面頂端會出現一則訊息，通知您已將全域原則重設。


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 重設全域外部存取原則

您可以使用 Windows PowerShell 和 Remove-CsExternalAccessPolicy Cmdlet 來重設全域外部存取原則。 您可以從商務用 Skype Server 管理命令介面或從遠端會話 Windows PowerShell 執行此 Cmdlet。 

## <a name="to-reset-the-global-external-access-policy"></a>重設全域外部存取原則

  - 這個命令可重設全域外部存取原則：<br/><br/>Remove-CsExternalAccessPolicy 身分識別 "global"

如需詳細資訊，請參閱 [get-csexternalaccesspolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) Cmdlet 的 [說明] 主題。
