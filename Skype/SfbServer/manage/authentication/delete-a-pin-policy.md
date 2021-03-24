---
title: 在商務用 Skype Server 中刪除 PIN 原則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 摘要：為商務用 Skype Server 刪除使用者的電話撥入式會議 PIN。
ms.openlocfilehash: b85d2bb29f8a1a28279a59f72957d201886d1dc4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096789"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>在商務用 Skype Server 中刪除 PIN 原則
 
**摘要：** 為商務用 Skype Server 刪除使用者的電話撥入式會議 PIN。
  
遵循下列步驟，可刪除個人識別碼 (PIN) 原則。
  
> [!NOTE]
> 您無法刪除全域 PIN 原則。 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>在商務用 Skype Server 控制台中刪除 PIN 原則

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。  
    
3. 在左導覽列中，依序按一下 **[安全性]** 和 **[PIN 原則]**。
    
4. 在 **[PIN 原則]** 頁面的搜尋欄位中，輸入您要刪除之原則的完整或部分名稱。
    
5. 在原則清單中，按一下您要的原則，再按一下 **[編輯]**，然後按一下 **[刪除]**。
    
6. 按一下 **[確定]**。
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除 PIN 原則

您可以使用 Windows PowerShell 和 Remove-CsPinPolicy Cmdlet 來刪除 PIN 原則。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 商務用 Skype Server 中的程式相同。
  
### <a name="to-remove-a-specific-pin-policy"></a>移除特定 PIN 原則

- 這個命令將移除含有 Identity RedmondPinPolicy 的 PIN 原則：
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>若要移除所有套用至網站範圍的 PIN 原則

- 這個命令將移除網站範圍設定的所有 PIN 原則：
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>移除允許使用共同模式的所有 PIN 原則

- 而且，這個將移除允許使用共同模式的所有 PIN 原則：G
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

如需詳細資訊，請參閱 [get-cspinpolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) Cmdlet 的 [說明] 主題。
