---
title: 在商務用 Skype Server 中管理 Web 服務配置設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: '摘要: 管理商務用 Skype Server 中的 Web 服務配置設定。'
ms.openlocfilehash: b2a7f287c9386c89d132e03e96aa25e9472f7008
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193006"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中管理 Web 服務配置設定
 
**摘要:** 管理商務用 Skype Server 中的 Web 服務配置設定。
  
您可以使用 [ **Web 服務**] 頁面來設定存取商務用 Skype Server 相關 web 伺服器與 web 服務的驗證方法。
  
請按照這些步驟建立新的 Web 服務原則。
  
### <a name="to-create-new-web-service-configuration-settings"></a>若要建立新的 web 服務設定

1.  從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
    
2. 開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。  
    
3. 在左側導覽列中, 按一下 [**安全性**], 然後按一下 [ **Web 服務**]。
    
4. 在 [ **Web 服務**] 頁面上, 按一下 [**新增**], 然後執行下列其中一項操作:
    
   - 若要設定網站的 Web 服務, 請按一下 [**網站**設定]。 在 [**選取網站**] 中, 按一下要將 Web 服務原則套用到哪個網站, 然後按一下 **[確定]**。
    
   - 若要設定文件庫的 Web 服務, 請按一下 [**池配置**]。 在 [**選取服務**] 中, 按一下將套用 Web 服務原則的服務, 然後按一下 **[確定]**。 
    
5. 在 [**新增 Web 服務**] 中, 在**整合的 windows 驗證**中, 選取 [**協商**]、[**整合式 windows 驗證**] 或 [**無**]。
    
6. 根據您的環境中用戶端和支援的功能, 選取下列一或多個專案:
    
   - **啟用 Pin 驗證**, 讓用戶端使用 pin 碼進行驗證。
    
   - **啟用憑證驗證**, 將池中的伺服器頒發憑證給用戶端。
    
   - **啟用憑證連結下載**, 讓伺服器提供驗證憑證下載該憑證的憑證鏈。
    
7. 按一下 [認可]****。
    
## <a name="modify-existing-web-service-configuration-settings"></a>修改現有的 Web 服務設定

您可以使用 [ **Web 服務**] 頁面來設定存取商務用 Skype Server 相關 web 伺服器與 web 服務的驗證方法。
  
請依照這些步驟來修改現有的 Web 服務原則。
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>修改現有的 Web 服務設定

1.  從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
    
2. 開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。  
    
3. 在左側導覽列中, 按一下 [**安全性**], 然後按一下 [ **Web 服務**]。
    
4. 在 [ **Web 服務**] 頁面上, 按一下 [設定], 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。
    
5. 在 [**編輯 Web 服務**] 中, 在**整合的 windows 驗證**中, 選取 [**協商**]、[**整合式 windows 驗證**] 或 [**無**]。
    
6. 根據您的環境中用戶端和支援的功能, 選取下列一或多個專案:
    
   - **啟用 Pin 驗證**, 讓用戶端使用 pin 碼進行驗證。
    
   - **啟用憑證驗證**, 將池中的伺服器頒發憑證給用戶端。
    
   - **啟用憑證連結下載**, 讓伺服器提供驗證憑證下載該憑證的憑證鏈。
    
7. 按一下 [認可]****。
    
## <a name="delete-existing-web-service-configuration-settings"></a>刪除現有的 Web 服務設定設定

請依照下列步驟刪除 web 服務設定。
  
### <a name="to-delete-web-service-configuration-settings"></a>刪除 web 服務配置設定

1.  從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
    
2. 開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。  
    
3. 在左側導覽列中, 按一下 [**安全性**], 然後按一下 [ **Web 服務**]。
    
4. 在 [ **Web 服務**] 頁面上, 于 [搜尋] 欄位中, 輸入您要刪除之原則的全部或部分名稱。
    
5. 在原則清單中, 按一下您想要的原則, 按一下 [**編輯**], 然後按一下 [**刪除**]。
    
6. 按一下 [確定]****。
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 刪除 Web 服務配置設定

您可以使用 Windows PowerShell 與**Remove CsWebServiceConfiguration** Cmdlet 來刪除 web 服務設定設定。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料, 請參閱博客文章[: 「快速入門: 使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 在商務用 Skype 伺服器中, 程式是一樣的。
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>刪除 web 服務設定的特定集合

- 下列命令會移除套用至雷德蒙網站的 Web 服務安全性設定:
    
  ```
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>若要刪除所有套用至網站範圍的 web 服務設定設定

下列命令會移除所有套用至服務範圍的 Web 服務安全性設定:
    
  ```
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>若要刪除所有允許憑證驗證的 web 服務設定設定

下列命令會移除所有允許使用憑證驗證的 Web 服務安全性設定:
    
  ```
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

如需詳細資訊, 請參閱[移除-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps)。
  

