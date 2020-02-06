---
title: 在商務用 Skype Server 中查看 PIN 原則資訊
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
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 摘要：針對商務用 Skype Server 查看使用者的 PIN 原則資訊。
ms.openlocfilehash: 57a54e960a0c89408f173567a78449cad21de9ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818695"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>在商務用 Skype Server 中查看 PIN 原則資訊
 
**摘要：** 針對商務用 Skype Server，查看使用者的 PIN 原則資訊。
  
您可以使用 [**釘選原則**] 索引標籤來查看使用 IP 電話連線至商務用 Skype 的使用者個人識別碼（pin）驗證。 若要使用 PIN 驗證，請確認已在 [Web 服務設定] 中選取 [**啟用 Pin 驗證**]。
  
請依照這些步驟來修改使用者層級或網站層級的 PIN 原則。 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>若要在商務用 Skype Server [控制台] 中查看 PIN 原則的相關資訊

1.  從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。  
    
3. 在左側導覽列中，按一下 [**安全性**]，然後按一下 [ **PIN 規則**]。
    
4. 在 [ **PIN 原則**] 頁面上，按一下原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看 PIN 原則

您也可以使用 Windows PowerShell 和 CsPinPolicy Cmdlet 來查看 PIN 原則。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 在商務用 Skype 伺服器中，程式是一樣的。
  
### <a name="to-view-pin-policies"></a>若要查看 PIN 原則

若要查看所有 PIN 原則的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER：
    
  ```PowerShell
  Get-CsPinPolicy
  ```

這會傳回如下所示的資訊：

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

如需詳細資訊，請參閱[CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) Cmdlet 的說明主題。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中建立新的 PIN 原則](create-a-new-pin-policy.md)
