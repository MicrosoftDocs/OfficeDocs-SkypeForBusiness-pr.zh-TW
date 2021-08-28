---
title: Cloud Connector Cmdlet 參考
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: 下表列出具有簡短描述的商務用 Skype Cloud Connector Edition Cmdlet，以及詳細資訊的連結。
ms.openlocfilehash: 19fc33912075e7737a4fa7fc242e74dd1de92289
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583727"
---
# <a name="cloud-connector-cmdlet-reference"></a>Cloud Connector Cmdlet 參考
 
> [!Important]
> 雲端連接器 Edition 會在2021年7月31日和商務用 Skype 線上時終止。 當您的組織升級至 Teams 後，請瞭解如何使用[直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話網絡連線至 Teams。

下表列出具有簡短描述的商務用 Skype Cloud Connector Edition Cmdlet，以及詳細資訊的連結。
  
> [!NOTE]
> 您必須在雲端連接器主機機器上執行所有 Cmdlet，而且必須以系統管理員身分執行 PowerShell 會話。 
  
|**Cmdlet 名稱**|**描述**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> 版本1.4.2 和更新版本  <br/> |將憑證授權單位服務備份至檔案，並將其儲存至網站共用目錄下的 CA 資料夾。     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |使用客戶提供 Windows Server 2012 R2 ISO 檔案，建立基本虛擬硬碟檔案 (VHDX) 。 在部署 ofCloud 連接器期間，將會使用 VHDX 檔案。  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |以維護模式來準備更新程式的雲端連接器主機伺服器。 裝置已「耗盡」;也就是說，所有的現有呼叫都會完成，但拒絕新來電。  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |在雲端連接器主機伺服器上退出更新維護模式。  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | 將商務用 Skype Cloud Connector Edition 設定匯出至商務用 Skype Cloud Connector Edition 主伺服器上的本機檔案。 <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |匯出雲端連接器範例設定檔 (.ini) 雲端連接器裝置的裝置目錄。 您可以修改和重新命名檔案，以用於部署。  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> 版本1.4.2 和更新版本  <br/> |將根 CA 憑證匯出至雲端連接器主機伺服器上的本機檔案。  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |在雲端連接器主機伺服器上檢索工作目錄。 所有部署檔案都會儲存在這個目錄中。  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |顯示儲存雲端連接器裝置記錄檔的目前目錄。  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> 版本2.1 和更新版本  <br/> |提供雲端連接器裝置的診斷資訊。  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |傳回目前 Cloud Connector 部署的認證。  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |傳回雲端連接器部署的外部憑證檔案路徑。 使用者準備此憑證。  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |顯示存放網站層級設定檔的目前目錄。 資料夾包含基本 VHD 和 Cloud Connector 安裝檔案。 此資料夾應與雲端連接器網站的所有其他裝置共用。  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |顯示儲存雲端連接器之網站層級記錄的目前目錄。  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> 版本2.0 和更新版本  <br/> |傳回雲端連接器實例上的版本。 Get-CCVersion 只能用於 Cloud Connector 的主機電腦。  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> 版本2.0 和更新版本  <br/> |將本機檔案的商務用 Skype Cloud Connector Edition 設定匯入雲端連接器主機伺服器。  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |在主伺服器上安裝 Cloud Connector 裝置（包括 AD、中央管理存放區、轉送伺服器和 Edge Server 虛擬機器）。  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | 從線上承租人設定取得高可用性資訊，並將其發佈至主伺服器上的雲端連接器裝置。 <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | 在線上承租人設定中向 PSTN 網站註冊裝置資訊。 裝置必須先註冊，雲連接器管理服務才能部署及管理。 <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> 版本1.4.2 和更新版本  <br/> |將 CA 資料夾中的憑證授權單位服務備份檔案「 \<SiteRootDirectory\> \CA\SFB CCE 根類」移除在雲端連接器的網站共用目錄下。  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> 版本1.4.2 和更新版本  <br/> |在執行 Renew-CcCACertificate 或更新 CcServerCertificate Cmdlet 後，在中央管理存放區、轉送伺服器和 Edge Server 上移除舊版伺服器憑證。  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> 僅限版本1.4。2  <br/> |重新安裝憑證授權單位服務 AD Server，以建立新的根 CA 憑證。  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> 僅限版本1.4。2  <br/> |當 Cloud Connector 的憑證接近到期或已到期時，會進行續訂。  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> 版本1.4.2 和更新版本  <br/> |重設憑證授權單位伺服器以安裝新的憑證授權憑證。  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> 版本2.1 和更新版本  <br/> |清除認證，並提示您重新輸入目前雲端連接器部署所使用的所有認證。  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |在雲端連接器裝置記錄目錄中搜尋傳入和撥出電話記錄檔  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |設定雲端連接器主機伺服器上的工作目錄。 所有部署檔案都會儲存在這個目錄中。  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |設定目前 Cloud Connector 部署的認證。  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |指定用於儲存轉送伺服器或 Edge Server 之憑證的路徑  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |設定用來儲存雲端連接器之網站層級設定檔的目錄。 資料夾將會包含基本 VHD 和雲端連接器設定檔。  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |同步下載雲端連接器 bits 和 msi 檔案。  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |產生雲端連接器裝置的內送和撥出電話記錄。  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |停止為雲端連接器裝置產生傳入和傳出通話記錄。  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |中斷執行中的裝置，並切換至新部署或備份裝置。  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |從主機伺服器卸載正在執行的雲端連接器裝置。  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |在線上租使用者設定中從 PSTN 網站登出目前的雲端連接器裝置。  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> 版本2.0 和更新版本  <br/> |重新安裝憑證授權單位服務 AD Server，以建立新的根 CA 憑證。  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> 版本2.0 和更新版本  <br/> |當 Cloud Connector 的憑證接近到期或已到期時，會進行續訂。  <br/> |
