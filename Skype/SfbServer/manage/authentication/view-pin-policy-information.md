---
title: 在商務用 Skype Server 中查看 PIN 原則資訊
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
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 摘要：為商務用 Skype Server 查看使用者的 PIN 原則資訊。
ms.openlocfilehash: 4c223d5736df7f5f8ee1dbee11401a9fef2237cb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806523"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>在商務用 Skype Server 中查看 PIN 原則資訊
 
**摘要：** 為商務用 Skype Server 查看使用者的 PIN 原則資訊。
  
您可以使用 [ **PIN 原則** ] 索引標籤來查看個人識別碼 (PIN) 驗證使用 IP 電話連線至商務用 Skype 的使用者。 若要使用 PIN 驗證，請確定已在 Web 服務設定中選取了 [啟用 PIN 驗證]。
  
請遵循下列步驟來修改使用者層級或網站層級的 PIN 原則。 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>在商務用 Skype Server 控制台中查看 PIN 原則的相關資訊

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。  
    
3. 在左導覽列中，依序按一下 [安全性] 和 [PIN 原則]。
    
4. 在「PIN 原則」 頁面上，依序按一下原則、[編輯] 和 [顯示詳細資料]。
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看 PIN 原則

您也可以使用 Windows PowerShell 和 Get-CsPinPolicy Cmdlet 來查看 PIN 原則。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 商務用 Skype Server 中的程式相同。
  
### <a name="to-view-pin-policies"></a>若要查看 PIN 碼原則

若要查看所有 PIN 原則的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
  ```PowerShell
  Get-CsPinPolicy
  ```

如此將傳回類似如下的資訊：

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

如需詳細資訊，請參閱 [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) Cmdlet 的 [說明] 主題。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中建立新的 PIN 原則](create-a-new-pin-policy.md)
