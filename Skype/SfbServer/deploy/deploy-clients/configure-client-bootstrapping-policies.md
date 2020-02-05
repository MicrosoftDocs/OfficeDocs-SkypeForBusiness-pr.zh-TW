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
description: 摘要：如何管理群組原則。
ms.openlocfilehash: 40b79c2be5713249df9f7e3061cb42d6be27f926
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769105"
---
# <a name="configure-client-bootstrapping-policies"></a>設定用戶端啟動載入原則
 
**摘要：** 如何管理群組原則。
  
群組原則管理主控台（GPMC）和群組原則物件編輯器是您用來管理群組原則的工具。 隨附于 Office 群組原則管理範本是 lync16 admx （ADMX）和 adml （ADML）管理範本，其中包含您針對網域中的 [群組原則] 物件所設定之商務用 Skype 的以註冊表為基礎的原則設定。 ADML 檔案是對 ADMX 檔案的語言特定補充。 每個 ADMX 與 ADML 檔案都包含單一 Office 應用程式的原則設定。 您可以從 Microsoft 下載中心免費[下載 Office 2016 管理範本檔案（ADMX/ADML）](https://www.microsoft.com/en-us/download/details.aspx?id=49030) 。
  
針對商務用 Skype 用戶端，在使用者第一次登入伺服器之前，您必須先考慮幾個用戶端引導原則。 例如，用戶端在登入完成之前應該要使用的預設伺服器和安全模式。 您可以使用群組原則在使用者的電腦註冊表中建立這些設定，然後再登入並開始從伺服器接收帶外的提供設定設定。 下表列出適用于商務用 Skype 的群組原則設定。
  
**商務用 Skype 的群組原則設定**

|群組原則設定|說明|
|:-----|:-----|
|指定伺服器（ConfigurationMode）  <br/> | 指定商務用 Skype 如何識別登入期間要使用的傳輸與伺服器。 在此設定中，您指定下列各項： <br/>  ServerAddressExternal：指定從外部防火牆外部連線時，用戶端和同盟連絡人所使用的伺服器名稱或 IP 位址。 <br/>  ServerAddressInternal：指定用戶端從組織的防火牆內連線時所使用的伺服器名稱或 IP 位址。 <br/>  傳輸：指定傳輸控制通訊協定（TCP）或傳輸層安全性（TLS）。 <br/> |
|支援的其他伺服器版本（ConfiguredServerCheckValues）  <br/> |指定伺服器版本名稱的清單，並以分號分隔，除了預設支援的伺服器版本之外，還會登入商務用 Skype 伺服器。  <br/> |
|停用登入失敗記錄的自動上傳（DisableAutomaticSendTracing）  <br/> |自動將登入失敗記錄上傳到商務用 Skype Server 以進行分析。 如果登入成功，則不會自動上傳任何記錄。 如果未設定此原則，就會發生下列情況：  <br/> 針對商務用 Skype Online 使用者：系統會自動上傳登入失敗記錄。 如果是商務用 Skype 內部部署使用者： [上傳] 之前，會向使用者顯示確認對話方塊。 停用此設定時，系統會自動將登入記錄上傳到商務用 Skype 內部部署和商務用 Skype Online 使用者的商務用 Skype 伺服器。 啟用此設定時，不會自動上傳登入記錄。  <br/> |
|停用 SIP 連線的 HTTP 回退（DisableHttpConnect）  <br/> |如果 TLS 或 TCP 無法使用，則會禁止商務用 Skype Server 嘗試使用 HTTP 連線到伺服器。 根據預設，商務用 Skype 會先嘗試使用 TLS 或 TCP 連線到伺服器，如果這些傳輸方法都沒有成功，商務用 Skype 會嘗試使用 HTTP 進行連線。 使用此原則來停用回退 HTTP 連線嘗試。  <br/> |
|需要登入認證（DisableNTCredentials）  <br/> |要求使用者供應商務用 Skype 的登入認證，而不是在登錄 SIP 伺服器期間自動使用 Windows 認證。  <br/> |
|停用伺服器版本檢查（DisableServerCheck）  <br/> |如果您將此原則設定為1，則會在登入之前，禁止商務用 Skype 檢查伺服器名稱和版本。 根據預設，商務用 Skype 會先進行這些檢查，然後才能登入。  <br/> |
|啟用 BITS 以下載通訊錄服務檔（EnableBitsForGalDownload）  <br/> |啟用商務用 Skype 使用背景智慧傳輸服務（BITS）來下載通訊錄服務檔案。  <br/> |
|設定 SIP 安全模式（EnableSIPHighSecurityMode）  <br/> |啟用商務用 Skype 以更安全地傳送和接收立即訊息。 此原則對 Windows .NET 或 Microsoft Exchange Server 服務沒有任何影響。  <br/> 如果您未設定此原則設定，商務用 Skype 可以使用任何傳輸。 但如果它不使用 TLS，且伺服器驗證使用者的身份，則商務用 Skype 必須使用 NTLM 或 Kerberos 驗證。  <br/> |
|全域通訊錄下載初始延遲（GalDownloadInitialDelay）  <br/> |指定在下載全域通訊清單（GAL）之前的時間週期。 預設值為60分鐘，表示伺服器會延遲下載 GAL 檔案，且隨機期間為0到60分鐘。  <br/> |
|防止使用者執行商務用 Skype （PreventRun）  <br/> |防止使用者執行商務用 Skype。 您可以在 [電腦設定] 和 [使用者設定] 底下設定此原則設定，但 [電腦設定] 底下的原則設定優先。  <br/> |
|允許儲存使用者密碼（SavePassword）  <br/> |讓商務用 Skype 儲存密碼。  <br/> |
|設定 SIP 壓縮模式（SipCompression）  <br/> |指定何時開啟 SIP 壓縮。 根據預設，SIP 壓縮會根據配接器速度而啟用。 請注意，設定此原則可能會增加登入時間。  <br/> |
|受信任的網域清單（TrustModelData）  <br/> |列出與客戶 SIP 網域的首碼不相符的信任網域。  <br/> |
   
在伺服器上設定的原則會優先于使用者設定的群組原則設定和用戶端選項。 下表摘要列出發生衝突時設定的優先順序順序。
  
**群組原則優先順序**

|**高於**|**設定的位置或方法**|
|:-----|:-----|
|1  <br/> |商務用 Skype 伺服器的內提供  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3  <br/> |HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4  <br/> |商務用 Skype 中的 [選項] 對話方塊  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>使用商務用 Skype 管理範本檔案來定義群組原則設定

1. 建立根層級資料夾，以包含所有語言中立的 ADMX 檔案。 例如，在以下位置為網網域控制站上的中央存放區建立根資料夾：
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > 這個程式假設您想要管理網域中的多部電腦。 在這種情況下，您會將範本儲存在主要網網域控制站上 Sysvol 資料夾中的中央存放區。 這會提供網域系統管理範本的複製中央儲存位置。 
  
2. 針對您要使用的每個語言建立子資料夾。 這些子資料夾將包含特定語言的 ADML 資源檔案。 例如，在此位置為美國英文（ZH-CN）建立子資料夾：
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

