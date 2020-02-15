---
title: 設定用戶端啟動載入原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 摘要： 如何管理群組原則。
ms.openlocfilehash: 4db9becc32e8f9bca99f06ac4533d33e82666591
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029054"
---
# <a name="configure-client-bootstrapping-policies"></a>設定用戶端啟動載入原則
 
**摘要：** 如何管理群組原則。
  
群組原則管理主控台 (GPMC) 和群組原則物件編輯器是您用來管理群組原則工具。 隨附於 Office 群組原則系統管理範本是 lync16.admx (ADMX) 以及.adml (ADML) 系統管理範本，其中含有您設定網域中的群組原則物件的商務用 Skype 的登錄型原則設定。 ADML 檔案都是特定語言的互補 ADMX 檔案。 每個 ADMX 和 ADML 檔案包含單一 Office 應用程式的原則設定。 您可以免費從 Microsoft 下載中心[下載 Office 2016 系統管理範本檔案 (ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030) 。
  
商務用 skype，有幾個用戶端啟動載入原則，您應該考慮設定之前使用者登入伺服器第一次。 如範例、 預設伺服器和用戶端應該使用直到登入的安全性模式已完成。 您可以使用群組原則來建立使用者的電腦登錄中的這些設定之前他們登入，並開始接收來自伺服器的頻內佈建設定。 下表列出可用於商務用 Skype 的群組原則設定。
  
**Skype for Business 的群組原則設定**

|群組原則設定|描述|
|:-----|:-----|
|指定伺服器 (ConfigurationMode)  <br/> | 會指定如何商務用 Skype 識別 「 傳輸 」 和 「 登入期間所要使用的伺服器。 此設定，在您指定下列項目： <br/>  ServerAddressExternal： 指定伺服器名稱或 IP 位址供用戶端及同盟連絡人從外部防火牆連線時。 <br/>  ServerAddressInternal： 指定伺服器名稱或用戶端從組織防火牆內部連線時所使用的 IP 位址。 <br/>  Transport： 指定傳輸控制通訊協定 (TCP) 或傳輸層安全性 (TLS)。 <br/> |
|其他伺服器支援版本 (ConfiguredServerCheckValues)  <br/> |會指定以 Skype for Business Server 將登入，此外預設所支援的伺服器版本的分號分隔的伺服器版本名稱的清單。  <br/> |
|停用自動上傳的登入失敗記錄 (DisableAutomaticSendTracing)  <br/> |自動上傳登入失敗記錄至 Skype 商務伺服器進行分析。 如果登入成功自動上傳沒有記錄檔。 如果未設定此原則，會發生下列情況：  <br/> Skype 商務 Online 使用者： 登入失敗記錄會自動上傳。 為商務用 Skype 內部部署使用者： 上載之前對使用者顯示的確認對話方塊中，該資料。 停用此設定時，登入記錄檔自動上傳至 Skype for Business Server Skype for Business 內部部署與 Skype for Business Online 使用者。 啟用此設定時，登入記錄檔會永遠不會自動上載。  <br/> |
|停用 HTTP 後援 SIP 連線 (DisableHttpConnect)  <br/> |防止 Skype for Business Server 嘗試如果無法使用 TLS 或 TCP 使用 HTTP 連線至伺服器。 依預設，商務用 Skype 先嘗試使用 TLS 或 TCP 連線至伺服器，而且如果這些傳輸方法皆未成功，商務用 Skype 會嘗試使用 HTTP 連線。 使用此原則可停用後援 HTTP 連線嘗試。  <br/> |
|需要登入認證 (DisableNTCredentials)  <br/> |需要使用者提供登入認證 skype for Business，而非自動使用 Windows 認證登入 SIP 伺服器期間。  <br/> |
|停用伺服器版本檢查 (DisableServerCheck)  <br/> |如果您將此原則設定為 1 時，可防止商務用 Skype 登入前先檢查的伺服器名稱和版本。 根據預設，商務用 Skype 會使之前登入這類檢查。  <br/> |
|啟用使用位元下載通訊錄服務檔案 (EnableBitsForGalDownload)  <br/> |可讓使用背景智慧型傳送服務 (BITS) 下載通訊錄服務檔案的商務用 Skype。  <br/> |
|設定 SIP 安全性模式 (EnableSIPHighSecurityMode)  <br/> |可讓傳送和接收立即訊息更安全地商務用 Skype。 此原則具有不會影響 Windows.NET 或 Microsoft Exchange Server 服務。  <br/> 如果您未設定此原則，商務用 Skype 可以使用任何傳輸。 但如果它不會使用 TLS 和商務用 Skype 如果伺服器驗證的使用者，必須使用 NTLM 或 Kerberos 驗證。  <br/> |
|全域通訊錄下載初始延遲 (GalDownloadInitialDelay)  <br/> |指定的時間之前的全域通訊清單 (GAL) 下載，就會發生。 預設值為 60 分鐘，這表示伺服器延遲介於 0 到 60 分鐘的隨機期間 GAL 檔案下載。  <br/> |
|防止使用者執行 Skype for Business (PreventRun)  <br/> |防止使用者執行商務用 Skype。 您可在「電腦設定」和「使用者設定」中設定此原則設定，但系統會優先使用「電腦設定」中的原則設定。  <br/> |
|允許儲存使用者密碼 (SavePassword)  <br/> |可讓儲存密碼的商務用 Skype。  <br/> |
|設定 SIP 壓縮模式 (SipCompression)  <br/> |指定何時要開啟 [SIP 壓縮。 根據預設，會根據介面卡速度啟用 SIP 壓縮。 請注意，設定此原則可能導致登入時間變長。  <br/> |
|受信任的網域清單 (TrustModelData)  <br/> |列出受信任的網域，不會符合客戶 SIP 網域的前置詞。  <br/> |
   
在伺服器上設定的原則優先於群組原則設定和使用者設定的用戶端選項。下表摘要列出當衝突發生時，設定的優先順序。
  
**群組原則優先順序**

|**Precedence**|**設定的位置或方法**|
|:-----|:-----|
|1   <br/> |Skype 商務伺服器頻內佈建  <br/> |
|2   <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3   <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4   <br/> |在商務用 Skype 中的 [選項] 對話方塊  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>若要使用 Skype for Business 系統管理範本檔案定義群組原則設定

1. 建立包含所有的非語言相關 ADMX 檔案的根層級資料夾。 例如，您的網域控制站，這個位置上建立集中存放區的根資料夾：
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > 此程序假設您想要管理您網域中的多部電腦。 在此情況下，您可以儲存範本集中存放區中的主要網域控制站的 Sysvol 資料夾中。 此網域系統管理範本提供複製的中央儲存位置。 
  
2. 建立您要使用的每種語言的子資料夾。 這些子資料夾會包含語言專屬 ADML 資源檔案。 例如，在此位置建立美國英文 (EN-US) 的子資料夾：
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

