---
title: 在商務用 Skype Server 中刪除 PIN 原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 摘要：針對商務用 Skype Server，刪除使用者的電話撥入式會議 PIN。
ms.openlocfilehash: c496c8b1966ad16ba63b3320b373d3c9ca27dd20
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818795"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>在商務用 Skype Server 中刪除 PIN 原則
 
**摘要：** 針對商務用 Skype Server，刪除使用者的電話撥入式會議 PIN。
  
請依照下列步驟刪除個人識別碼（PIN）原則。
  
> [!NOTE]
> 您無法刪除全域 PIN 原則。 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>在商務用 Skype Server [控制台] 中刪除 PIN 原則

1.  從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。  
    
3. 在左側導覽列中，按一下 [**安全性**]，然後按一下 [ **PIN 規則**]。
    
4. 在 [ **PIN 原則**] 頁面上，于 [搜尋] 欄位中，輸入您要刪除之原則的全部或部分名稱。
    
5. 在原則清單中，按一下您想要的原則，按一下 [**編輯**]，然後按一下 [**刪除**]。
    
6. 按一下 [確定]****。
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除 PIN 原則

您可以使用 Windows PowerShell 與 Remove CsPinPolicy Cmdlet 來刪除 PIN 原則。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 在商務用 Skype 伺服器中，程式是一樣的。
  
### <a name="to-remove-a-specific-pin-policy"></a>移除特定的 PIN 原則

- 這個命令會移除具有身分識別 RedmondPinPolicy 的 PIN 原則：
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>若要移除所有套用至網站範圍的 PIN 原則

- 這個命令會移除在網站範圍中設定的所有 PIN 原則：
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>若要移除所有允許使用常見模式的 PIN 原則

- 如此一來，會移除所有允許使用常見模式的 PIN 原則： G
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

如需詳細資訊，請參閱[Remove CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) Cmdlet 的說明主題。
  

