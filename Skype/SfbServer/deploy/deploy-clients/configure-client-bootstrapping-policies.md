---
title: 設定用戶端啟動載入原則
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 摘要：如何管理群組原則。
ms.openlocfilehash: 073bd23219b3fa0a39ed06a94a5ef0586a740e6d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831647"
---
# <a name="configure-client-bootstrapping-policies"></a>設定用戶端啟動載入原則
 
**摘要：** 如何管理群組原則。
  
群組原則管理主控台 (GPMC) ，而群組原則物件編輯器是您用來管理群組原則的工具。 包含在 Office 群組原則系統管理範本中的 adml (adml) )  (系統管理範本，包含您為網域中的群組原則物件所設定的商務用 Skype 登錄型原則設定。 ADML 檔案是特定語言對 ADMX 檔案的補充。 每個 ADMX 和 ADML 檔案都包含單一 Office 應用程式的原則設定。 您可以從 Microsoft 下載中心[下載 Office 2016 系統管理範本檔案 (ADMX/ADML) ](https://www.microsoft.com/download/details.aspx?id=49030) 。
  
針對商務用 Skype 用戶端，您應該考慮在使用者第一次登入伺服器之前，先考慮一些用戶端引導原則。 例如，用戶端應使用的預設伺服器及安全性模式，直到登入完成為止。 您可以使用群組原則在使用者的電腦登錄中建立這些設定，然後再登入，並開始從伺服器接收帶內布建設定。 下表列出可用於商務用 Skype 的群組原則設定。
  
**商務用 Skype 的群組原則設定**

|群組原則設定|描述|
|:-----|:-----|
|指定伺服器 (ConfigurationMode)   <br/> | 指定商務用 Skype 如何識別登入期間要使用的傳輸和伺服器。 在此設定中，您可以指定下列專案： <br/>  ServerAddressExternal：指定從外部防火牆外部連線時，用戶端和同盟連絡人所使用的伺服器名稱或 IP 位址。 <br/>  ServerAddressInternal：指定用戶端從組織防火牆內部連線時所使用的伺服器名稱或 IP 位址。 <br/>  Transport：指定傳輸控制通訊協定 (TCP) 或傳輸層安全性 (TLS) 。 <br/> |
| (ConfiguredServerCheckValues) 支援的其他伺服器版本  <br/> |指定伺服器版本名稱的清單，該清單是由商務用 Skype Server 會登入的分號分隔，除了預設支援的伺服器版本之外。  <br/> |
|停用自動上傳失敗記錄 (DisableAutomaticSendTracing)   <br/> |自動將登入失敗記錄上傳至商務用 Skype Server 以進行分析。 登入成功時，不會自動上傳記錄。 若未設定此原則，則會發生下列情況：  <br/> 針對商務用 Skype 線上使用者：會自動上傳登入失敗記錄。 若為商務用 Skype 內部部署使用者：上傳之前會向使用者顯示確認對話方塊。 停用此設定時，會自動將登錄記錄上傳至商務用 Skype 內部部署和商務用 Skype 線上使用者的商務用 Skype Server。 啟用此設定時，將不會自動上傳登入記錄。  <br/> |
|停用 SIP 連線的 HTTP 回退 (DisableHttpConnect)   <br/> |當 TLS 或 TCP 無法使用時，禁止商務用 Skype Server 嘗試使用 HTTP 連接至伺服器。 根據預設，商務用 Skype 第一次嘗試使用 TLS 或 TCP 連線至伺服器，但如果兩個傳輸方法都沒有成功，則商務用 Skype 會嘗試使用 HTTP 進行連線。 使用此原則可停用後援 HTTP 連線嘗試。  <br/> |
|需要登入認證 (DisableNTCredentials)   <br/> |要求使用者在登入 SIP 伺服器期間，為商務用 Skype 提供登入認證，而非自動使用 Windows 認證。  <br/> |
|停用伺服器版本檢查 (DisableServerCheck)   <br/> |如果將此原則設為1，則在登入前，避免商務用 Skype 檢查伺服器名稱及版本。 根據預設，商務用 Skype 會在登入之前進行這些檢查。  <br/> |
|啟用 BITS 以下載通訊錄服務檔案 (EnableBitsForGalDownload)   <br/> |可讓商務用 Skype 使用背景智慧轉接服務 (BITS) 下載通訊錄服務檔案。  <br/> |
|設定 SIP 安全性模式 (EnableSIPHighSecurityMode)   <br/> |可讓商務用 Skype 更安全地傳送和接收立即訊息。 這個原則對 Windows .net 或 Microsoft Exchange Server 服務沒有任何作用。  <br/> 如果您未設定此原則設定，商務用 Skype 可以使用任何傳輸。 不過，如果它不使用 TLS，而且伺服器驗證使用者，商務用 Skype 必須使用 NTLM 或 Kerberos 驗證。  <br/> |
|全域通訊錄下載初始延時 (GalDownloadInitialDelay)   <br/> |會指定在 (GAL) 中下載全域通訊清單之前的時間週期。 預設值為60分鐘，這表示伺服器會延遲下載 GAL 檔案，其隨機期限介於0到60分鐘之間。  <br/> |
|防止使用者執行商務用 Skype (PreventRun)   <br/> |防止使用者執行商務用 Skype。 您可在「電腦設定」和「使用者設定」中設定此原則設定，但系統會優先使用「電腦設定」中的原則設定。  <br/> |
|允許儲存使用者密碼 (SavePassword)   <br/> |可讓商務用 Skype 儲存密碼。  <br/> |
|設定 SIP 壓縮模式 (SipCompression)   <br/> |指定何時開啟 SIP 壓縮。 根據預設，以配接器速度啟用 SIP 壓縮。 請注意，設定此原則可能導致登入時間變長。  <br/> |
|受信任的網域清單 (TrustModelData)   <br/> |列出不符合客戶 SIP 網域首碼的信任網域。  <br/> |
   
在伺服器上設定的原則優先於群組原則設定和使用者設定的用戶端選項。下表摘要列出當衝突發生時，設定的優先順序。
  
**群組原則優先順序**

|**Precedence**|**設定的位置或方法**|
|:-----|:-----|
|1  <br/> |商務用 Skype Server 頻帶內布建  <br/> |
|第  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3   <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4   <br/> |商務用 Skype 中的 [選項] 對話方塊  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>若要使用商務用 Skype 系統管理範本檔案來定義群組原則設定

1. 建立根層級的資料夾，以包含所有語言中立的 ADMX 檔案。 例如，在此位置的網域控制站上建立中央存放區的根資料夾：
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > 此程式假設您要管理網域中的多部電腦。 在此情況下，您可以將範本儲存在網域主控站的 Sysvol 資料夾中的中央存放區。 這會為網域系統管理範本提供複製的中央儲存位置。 
  
2. 為您要使用的每一種語言建立子資料夾。 這些子資料夾將會包含特定語言的 ADML 資源檔。 例如，在此位置，為美國英文 (EN-US) 建立子資料夾：
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

