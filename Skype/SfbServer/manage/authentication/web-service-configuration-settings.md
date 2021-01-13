---
title: 在商務用 Skype Server 中管理 Web 服務設定
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
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 摘要：管理商務用 Skype Server 中的 Web 服務設定。
ms.openlocfilehash: 68abe01614902d5e6f4c58040b30b6afbd475df8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806493"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中管理 Web 服務設定
 
**摘要：** 在商務用 Skype Server 中管理 Web 服務設定。
  
您可以使用 [ **Web 服務** ] 頁面來設定驗證方法，以存取用來存取商務用 Skype Server 相關的網頁伺服器和 web 服務。
  
請遵循下列步驟建立新的 Web 服務原則。
  
### <a name="to-create-new-web-service-configuration-settings"></a>若要建立新的 web 服務設定

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。  
    
3. 在左導覽列中，按一下 [ **安全性** ]，然後按一下 [ **Web 服務**]。
    
4. 在 [ **Web 服務** ] 頁面上，按一下 [ **新增**]，然後執行下列其中一項動作：
    
   - 若要設定網站的 Web 服務，請按一下 [ **網站** 設定]。 在 [ **選取網站**] 中，按一下要套用 Web 服務原則的網站，然後按一下 **[確定]**。
    
   - 若要設定集區的 Web 服務，請按一下 [ **集** 區設定]。 在 [ **選取服務**] 中，按一下將套用 Web 服務原則的服務，然後按一下 **[確定]**。 
    
5. 在 **[新的 Web 服務設定**] 的 **整合式 windows 驗證** 中，選取 [ **協商**]、[ **整合式 windows 驗證**] 或 [ **無**]。
    
6. 根據用戶端的功能和您環境中的支援，選取下列其中一項或多項：
    
   - **啟用 Pin 驗證** ，以允許使用 pin 碼驗證用戶端。
    
   - [**啟用憑證驗證**] 以讓集區中的伺服器對用戶端發出憑證。
    
   - [**啟用憑證鏈下載**] 可讓顯示驗證憑證的伺服器下載該憑證的憑證鏈。
    
7. 按一下 **[認可]**。
    
## <a name="modify-existing-web-service-configuration-settings"></a>修改現有的 Web 服務設定

您可以使用 [ **Web 服務** ] 頁面來設定驗證方法，以存取用來存取商務用 Skype Server 相關的網頁伺服器和 web 服務。
  
請遵循下列步驟來修改現有的 Web 服務原則。
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>修改現有的 Web 服務設定

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。  
    
3. 在左導覽列中，按一下 [ **安全性** ]，然後按一下 [ **Web 服務**]。
    
4. 在 [ **Web 服務** ] 頁面上，按一下設定，然後按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。
    
5. 在 [ **編輯 Web 服務] 設定** 的 **整合式 windows 驗證** 中，選取 [ **協商**]、[ **整合式 windows 驗證**] 或 [ **無**]。
    
6. 根據用戶端的功能和您環境中的支援，選取下列其中一項或多項：
    
   - **啟用 Pin 驗證** ，以允許使用 pin 碼驗證用戶端。
    
   - [**啟用憑證驗證**] 以讓集區中的伺服器對用戶端發出憑證。
    
   - [**啟用憑證鏈下載**] 可讓顯示驗證憑證的伺服器下載該憑證的憑證鏈。
    
7. 按一下 **[認可]**。
    
## <a name="delete-existing-web-service-configuration-settings"></a>刪除現有的 Web 服務設定

請遵循下列步驟刪除 web 服務設定。
  
### <a name="to-delete-web-service-configuration-settings"></a>若要刪除 web 服務設定設定

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。  
    
3. 在左導覽列中，按一下 [ **安全性** ]，然後按一下 [ **Web 服務**]。
    
4. 在 [ **Web 服務** ] 頁面上的搜尋欄位中，輸入您要刪除之原則的全部或部分名稱。
    
5. 在原則清單中，按一下您要的原則，再按一下 **[編輯]**，然後按一下 **[刪除]**。
    
6. 按一下 **[確定]**。
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 刪除 Web 服務設定設定

您可以使用 Windows PowerShell 和 **Remove-CsWebServiceConfiguration** Cmdlet 刪除 web 服務設定設定。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端工作階段執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 商務用 Skype Server 中的程式相同。
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>刪除特定的 web 服務設定集合集合

- 下列命令會移除套用至 Redmond 網站的 Web 服務安全性設定：
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>若要刪除所有套用至網站範圍的 web 服務設定設定

下列命令會移除套用至服務範圍的所有 Web 服務安全性設定：
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>若要刪除所有允許憑證驗證的 web 服務設定

下列命令會移除所有允許使用憑證驗證的 Web 服務安全性設定：
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

如需詳細資訊，請參閱 [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps)。
  

