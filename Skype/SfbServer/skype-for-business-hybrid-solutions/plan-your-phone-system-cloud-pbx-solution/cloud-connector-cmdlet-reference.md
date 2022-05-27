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
description: 下表列出商務用 Skype Cloud Connector Edition Cmdlet，其中包含簡短的描述和詳細資訊的連結。
ms.openlocfilehash: efe4a048e939b6491acc93b7ccd4717ffc9aca8b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676165"
---
# <a name="cloud-connector-cmdlet-reference"></a>Cloud Connector Cmdlet 參考

> [!Important]
> Cloud Connector Edition 將于 2021 年 7 月 31 日與 商務用 Skype Online 一起淘汰。 一旦您的組織升級至Teams，請瞭解如何使用[直接路由](/MicrosoftTeams/direct-routing-landing-page)將內部部署電話語音網路連線到Teams。

下表列出商務用 Skype Cloud Connector Edition Cmdlet，其中包含簡短的描述和詳細資訊的連結。
  
> [!NOTE]
> 您必須在 Cloud Connector 主機電腦上執行所有 Cmdlet，而且必須以系統管理員身分執行 PowerShell 會話。 
  
|Cmdlet 名稱**|描述|
|---|---|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <p> 1.4.2 版和更新版本|將憑證授權單位單位服務備份至檔案，並將它儲存至網站共用目錄下的 CA 資料夾。|
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md)|使用客戶提供的 Windows Server 2012 R2 ISO 檔案， (VHDX) 建立基底虛擬硬碟檔案。 VHDX 檔案將在部署雲端連接器期間使用。|
|[Enter-CcUpdate](enter-ccupdate.md)|將 Cloud Connector 主機伺服器置於維護模式，以準備更新程式。 設備已「清空」;也就是說，所有現有的呼叫都會完成，但會拒絕新的呼叫。|
|[Exit-CcUpdate](exit-ccupdate.md)|結束 Cloud Connector 主機伺服器上的更新維護模式。|
|[Export-CcConfiguration](export-ccconfiguration.md)|將商務用 Skype Cloud Connector Edition組態匯出至商務用 Skype Cloud Connector Edition主機伺服器上的本機檔案。|
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md)|將 Cloud Connector 範例組態檔 (.ini) 匯出至 Cloud Connector 設備的設備目錄。 您可以修改並重新命名要用於部署的檔案。|
|[Export-CcRootCertificate](export-ccrootcertificate.md) <p> 1.4.2 版和更新版本|將根 CA 憑證匯出至 Cloud Connector 主機伺服器上的本機檔案。|
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md)|擷取 Cloud Connector 主機伺服器上的工作目錄。 所有部署檔案都會儲存在此目錄中。|
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md)|顯示儲存雲端連接器設備記錄檔的目前目錄。|
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <p> 2.1 版和更新版本|提供 Cloud Connector 設備的診斷資訊。|
|[Get-CcCredential](get-cccredential.md)|傳回目前 Cloud Connector 部署的認證。|
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)|傳回 Cloud Connector 部署的外部憑證檔案路徑。 使用者準備此憑證。|
|[Get-CcSiteDirectory](get-ccsitedirectory.md)|顯示儲存月臺層級組態檔的目前目錄。 資料夾包含基底 VHD 和 Cloud Connector 安裝檔案。 此資料夾應該與 Cloud Connector 網站的所有其他設備共用。|
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md)|顯示目前目錄，其中儲存 Cloud Connector 的月臺層級記錄。|
|[Get-CcVersion](get-ccversion.md) <p> 2.0 版和更新版本|傳回 Cloud Connector 實例上的版本。 Get-CCVersion只能在 Cloud Connector 的主機電腦中使用。|
|[Import-CcConfiguration](import-ccconfiguration.md) <p> 2.0 版和更新版本|將商務用 Skype Cloud Connector Edition組態從本機檔案匯入至 Cloud Connector 主機伺服器。|
|[Install-CcAppliance](install-ccappliance.md)|在主機伺服器上安裝雲端連接器設備，包括 AD、中央管理Microsoft Store、轉送伺服器和 Edge Server 虛擬機器。|
|[Publish-CcAppliance](publish-ccappliance.md)|從線上租使用者組態取得高可用性資訊，並將其發佈至主機伺服器上的 Cloud Connector 設備。|
|[Register-CcAppliance](register-ccappliance.md)|在線上租使用者設定中向 PSTN 網站註冊設備資訊。 設備必須先註冊，才能由 Cloud Connector 管理服務進行部署和管理。|
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <p> 1.4.2 版和更新版本|移除 Cloud Connector 網站共用目錄下 CA 資料夾中的憑證授權單位單位服務備份檔案 「 \<SiteRootDirectory\> \CA\SfB CCE Root.p12」。|
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <p> 1.4.2 版和更新版本|在您執行 Renew-CcCACertificate 或更新 CcServerCertificate Cmdlet 之後，移除中央管理Microsoft Store、轉送伺服器和 Edge Server 上的舊版伺服器憑證。|
|[Renew-CcCACertificate](renew-cccacertificate.md) <p> 僅限 1.4.2 版|重新安裝憑證授權單位單位服務 AD 伺服器，以建立新的根 CA 憑證。|
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <p> 僅限 1.4.2 版|當 Cloud Connector 的憑證即將到期或已過期時，請更新這些憑證。|
|[Reset-CcCACertificate](reset-cccacertificate.md) <p> 1.4.2 版和更新版本|重設憑證授權單位單位伺服器以安裝新的憑證授權單位單位憑證。|
|[Restore-CcCredentials](restore-cccredentials.md) <p> 2.1 版和更新版本|清除認證，並提示您重新輸入用於目前 Cloud Connector 部署的所有認證。|
|[Search-CcLog](search-cclog.md)|在 Cloud Connector 設備記錄目錄中搜尋連入和傳出通話記錄|
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md)|設定 Cloud Connector 主機伺服器上的工作目錄。 所有部署檔案都會儲存在此目錄中。|
|[Set-CcCredential](set-cccredential.md)|設定目前 Cloud Connector 部署的認證。|
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)|指定儲存轉送伺服器或 Edge Server 憑證的路徑|
|[Set-CcSiteDirectory](set-ccsitedirectory.md)|設定將儲存 Cloud Connector 月臺層級組態檔的目錄。 此資料夾將包含基底 VHD 和 Cloud Connector 組態檔。|
|[Start-CcDownload](start-ccdownload.md)|同步下載 Cloud Connector 位和 msi 檔案。|
|[Start-CcLogging](start-cclogging.md)|產生雲端連接器設備的連入和傳出通話記錄。|
|[Stop-CcLogging](stop-cclogging.md)|停止產生 Cloud Connector 設備的連入和傳出通話記錄。|
|[Switch-CcVersion](switch-ccversion.md)|中斷執行中設備的連線，並切換至新部署的或備份裝置。|
|[Uninstall-CcAppliance](uninstall-ccappliance.md)|從主機伺服器卸載執行中的 Cloud Connector 設備。|
|[Unregister-CcAppliance](unregister-ccappliance.md)|從線上租使用者設定中的 PSTN 網站取消註冊目前的 Cloud Connector 設備。|
|[Update-CcCACertificate](update-cccacertificate.md) <p> 2.0 版和更新版本|重新安裝憑證授權單位單位服務 AD 伺服器，以建立新的根 CA 憑證。|
|[Update-CcServerCertificate](update-ccservercertificate.md) <p> 2.0 版和更新版本|當 Cloud Connector 的憑證即將到期或已過期時，請更新這些憑證。|
