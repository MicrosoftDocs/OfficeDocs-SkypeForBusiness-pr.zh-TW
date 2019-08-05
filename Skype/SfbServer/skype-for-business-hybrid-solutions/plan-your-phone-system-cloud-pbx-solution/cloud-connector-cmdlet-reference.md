---
title: 雲端連接器 Cmdlet 參考
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: 下表列出 [商務用 Skype] 雲端連接器版本 Cmdlet 以及詳細資訊的連結。
ms.openlocfilehash: 58fed82857138bf9716db88648344e9140b29d6f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192598"
---
# <a name="cloud-connector-cmdlet-reference"></a>雲端連接器 Cmdlet 參考
 
下表列出 [商務用 Skype] 雲端連接器版本 Cmdlet 以及詳細資訊的連結。
  
> [!NOTE]
> 您必須在雲端連接器主機電腦上執行所有 Cmdlet, 而且您必須以系統管理員身分執行 PowerShell 會話。 
  
|**Cmdlet 名稱**|**說明**|
|:-----|:-----|
|[備份-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> 版本1.4.2 及更新版本  <br/> |將 [認證機構服務] 備份到檔案, 並將它儲存到 [網站共用目錄] 下的 [CA] 資料夾。     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |使用客戶提供的 Windows Server 2012 R2 ISO 檔案建立基本虛擬硬碟檔案 (VHDX)。 在部署 ofCloud 連接器期間, 將會使用 VHDX 檔案。  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |透過將雲端連接器主機伺服器置於維護模式, 來為更新程式做好準備。 裝置已 "排出";也就是說, 所有現有的呼叫都會完成, 但拒絕新的通話。  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |在雲端連接器主機伺服器上退出更新維護模式。  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | 將商務用 Skype 雲端連接器版本設定匯出到商務用 Skype 雲端連接器 Edition 主機伺服器上的本機檔案。 <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |將雲端連接器範例設定檔 (.ini) 匯出到雲端連接器裝置的裝置目錄。 您可以修改並重新命名檔案, 以用於您的部署。  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> 版本1.4.2 及更新版本  <br/> |將根 CA 憑證匯出到雲端連接器主機伺服器上的本機檔案。  <br/> |
|[CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |檢索雲端連接器主機伺服器上的工作目錄。 所有部署檔案都儲存在這個目錄中。  <br/> |
|[CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |顯示儲存雲端連接器裝置記錄的目前目錄。  <br/> |
|[CcApplianceStatus](get-ccappliancestatus.md) <br/> 版本2.1 及更新版本  <br/> |提供雲端連接器裝置的診斷資訊。  <br/> |
|[CcCredential](get-cccredential.md) <br/> |傳回目前雲端連接器部署的認證。  <br/> |
|[CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |傳回雲端連接器部署的外部憑證檔路徑。 使用者準備這個證書。  <br/> |
|[CcSiteDirectory](get-ccsitedirectory.md) <br/> |顯示網站層級配置檔案儲存位置的目前目錄。 該資料夾包含基本 VHD 和雲端連接器安裝檔案。 此資料夾應與雲端連接器網站的所有其他裝置共用。  <br/> |
|[CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |顯示儲存雲端連接器之網站層級記錄的目前目錄。  <br/> |
|[CcVersion](get-ccversion.md) <br/> 版本2.0 及更新版本  <br/> |傳回雲端連接器實例上的版本。 CCVersion 只能在雲端連接器的主機電腦中使用。  <br/> |
|[匯入-CcConfiguration](import-ccconfiguration.md) <br/> 版本2.0 及更新版本  <br/> |從本機檔案將商務用 Skype 雲端連接器版本設定匯入雲端連接器主機伺服器。  <br/> |
|[安裝-CcAppliance](install-ccappliance.md) <br/> |在主機伺服器上安裝雲端連接器裝置, 包括 AD、管理中心存儲區、中繼伺服器以及 Edge 伺服器虛擬機器。  <br/> |
|[發佈-CcAppliance](publish-ccappliance.md) <br/> | 從線上租使用者配置取得高可用性資訊, 並將其發佈至主機伺服器上的雲端連接器裝置。 <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | 在線上租使用者配置中, 將裝置資訊註冊到 PSTN 網站。 裝置必須先註冊, 才能由雲端連接器管理服務來部署和管理。 <br/> |
|[移除-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> 版本1.4.2 及更新版本  <br/> |在雲端連接器的 [網站共用目錄\<]\>下, 移除 [CA] 資料夾中的 [SiteRootDirectory \CA\SfB CCE Root. p12]。  <br/> |
|[移除-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> 版本1.4.2 及更新版本  <br/> |在您執行更新 CcCACertificate 或更新 CcServerCertificate Cmdlet 之後, 在中央管理儲存區、中繼伺服器和 Edge 伺服器上移除舊版伺服器憑證。  <br/> |
|[更新-CcCACertificate](renew-cccacertificate.md) <br/> 僅限版本1.4。2  <br/> |重新安裝憑證授權單位服務 AD Server 以建立新的根 CA 憑證。  <br/> |
|[更新-CcServerCertificate](renew-ccservercertificate.md) <br/> 僅限版本1.4。2  <br/> |當雲端連接器的憑證接近到期或已到期時, 會為它續約。  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> 版本1.4.2 及更新版本  <br/> |重設憑證授權單位伺服器以安裝新的憑證授權單位憑證。  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> 版本2.1 及更新版本  <br/> |清除認證, 並提示您重新輸入目前雲端連接器部署所使用的所有認證。  <br/> |
|[搜尋-CcLog](search-cclog.md) <br/> |在雲端連接器裝置的記錄目錄中搜尋來電記錄和撥出電話記錄  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |在雲端連接器主機伺服器上設定工作目錄。 所有部署檔案都儲存在這個目錄中。  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |設定目前雲端連接器部署的認證。  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |指定要儲存中繼伺服器或 Edge 伺服器憑證的路徑  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |設定雲端連接器的網站層級配置檔案將儲存在哪個目錄中。 該資料夾將會包含基本 VHD 和雲端連接器設定檔。  <br/> |
|[開始-CcDownload](start-ccdownload.md) <br/> |同步下載雲端連接器位與 msi 檔案。  <br/> |
|[開始-CcLogging](start-cclogging.md) <br/> |產生雲端連接器裝置的呼入和呼出通話記錄。  <br/> |
|[停止 CcLogging](stop-cclogging.md) <br/> |停止為雲端連接器裝置產生呼入和呼出通話記錄。  <br/> |
|[切換 CcVersion](switch-ccversion.md) <br/> |中斷正在執行的裝置的連線, 並切換到新部署或備份裝置。  <br/> |
|[卸載-CcAppliance](uninstall-ccappliance.md) <br/> |從主機伺服器卸載正在執行的雲端連接器裝置。  <br/> |
|[取消註冊-CcAppliance](unregister-ccappliance.md) <br/> |從線上租使用者配置中的 PSTN 網站登出目前的雲端連接器裝置。  <br/> |
|[更新-CcCACertificate](update-cccacertificate.md) <br/> 版本2.0 及更新版本  <br/> |重新安裝憑證授權單位服務 AD Server 以建立新的根 CA 憑證。  <br/> |
|[更新-CcServerCertificate](update-ccservercertificate.md) <br/> 版本2.0 及更新版本  <br/> |當雲端連接器的憑證接近到期或已到期時, 會為它續約。  <br/> |
   

