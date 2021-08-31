---
title: 部署 Microsoft Teams 會議室
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 請閱讀本文，瞭解如何部署Microsoft Teams 會議室，包括部署階段。
ms.openlocfilehash: 3c7420880bd36d1ebacd778d623da14e1705e324
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730402"
---
# <a name="deployment-overview"></a>部署概觀

部署Microsoft Teams 會議室階段：

- 確認您的會議室 (位置) 部署相依性
- 建立Microsoft Teams或商務用 Skype Exchange帳戶，並將這些帳戶指派給主機裝置 (請參閱設定帳戶[Microsoft Teams 會議室) ](rooms-configure-accounts.md)
- 重新映射 Microsoft Surface 平板電腦以在主機Microsoft Teams 會議室使用 (請參閱設定Microsoft Teams 會議室主機或[](console.md)部署 Microsoft Teams 會議室[大量](rooms-scale.md)部署指南) 
-  (選) 為系統設定 Microsoft Operations Management Suite (請參閱使用 Azure[監視器](azure-monitor-deploy.md)部署Microsoft Teams 會議室管理
- 在會議室中設定主機，並連接您所需的 (請參閱您裝置集的 OEM 檔) 

AV 技術可用於上一個工作，但貴組織的 IT 部門必須執行程式的其他部分。 


## <a name="site-readiness"></a>網站準備就緒 

當訂購的裝置傳送給貴組織時，請與網路和裝置及 AV 小組合作，以確保符合部署相依性，且每個網站和會議室在電源、網路和顯示方面已準備就緒。 此外，請確定符合實體安裝需求。 針對實體安裝考慮，請流覽廠商的網站，並運用 AV 小組在安裝和安裝螢幕及執行纜線連接時的體驗。

您可以在下列規劃指南連結中，進一步瞭解這些相依性：

-   [檢查網路可用性](rooms-prep.md#check-network-availability)
-   [證書](rooms-prep.md#certificates)
-   [代理](rooms-prep.md#proxy)

**Pro提示**- 如果您打算使用 Proxy 伺服器提供連線或 Teams 或 商務用 Skype的存取權，請首先閱讀 [本文](../proxy-servers-for-skype-for-business-online.md)。 當涉及 proxy 伺服器商務用 Skype流量時，建議您完全忽略 Proxy 伺服器。 商務用 Skype流量已加密，因此 Proxy 伺服器不會使其更安全。 在更廣泛的部署中，建議您遵循準備網路Teams以規劃頻寬，並[](../prepare-network.md)評估網路是否適合即時流量。

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![確認網站。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>確認網站符合您網站Microsoft Teams 會議室。</li><li>確認您為每個網站提供了足夠的頻寬。</li></ul>| 
| ![規劃裝置部署。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的裝置部署和組組。</li></ul>| 

## <a name="service-readiness"></a>服務整備

若要準備您的Microsoft Teams 會議室部署，請執行下列重要、集中的工作：

-   定義Microsoft Teams 會議室服務帳戶功能。
-   準備組織單位和 Active Directory 群組以保留您的 Microsoft Teams 會議室 電腦和服務帳戶，以及準備群組原則物件 (GPO) 以啟用 PowerShell 重算。

### <a name="define-microsoft-teams-rooms-service-account-features"></a>定義Microsoft Teams 會議室服務帳戶功能 

根據您決定使用 Microsoft Teams 會議室 部署啟用的共同合作案例，您必須判斷您指派給每個 Microsoft Teams 會議室 服務帳戶的功能。

| **案例** | **描述** | **Microsoft Teams 會議室服務帳戶功能** |
|---------- |------------- | --- |
| 互動式會議            | 使用語音、視像和螢幕畫面共用;將Microsoft Teams 會議室成為可預約的資源                     | 已針對 商務用 Skype 啟用，Exchange (資源信箱)  |
| 電話撥入式會議            | 使用電話撥入 *式會議* 座標Microsoft Teams 會議室從主機啟動會議 | 已啟用音訊會議                                          |
| 外發/內入 PSTN 通話 | 啟用Microsoft Teams 會議室主機撥打和接聽 PSTN 通話                                         | 已啟用電話系統                                                |

若要進一Microsoft Teams 會議室帳戶，請參閱[設定帳戶Microsoft Teams 會議室。](rooms-configure-accounts.md)


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![案例支援。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定您將支援哪些案例，並確定您服務帳戶Microsoft Teams 會議室需求。</li></ul>| 
| ![準備主機。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>準備主機和服務帳戶。</li></ul>| 


_範例 Microsoft Teams 會議室服務帳戶規劃資料表_

| **網站**  | **會議室名稱** | **會議室類型** | **未來的會議室功能**                                                 | **Microsoft Teams 會議室帳戶功能**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| 倫敦總部 | 居裡         | 中型        | 1 個螢幕、音訊和視音訊加簡報 <br>電話撥入式會議存取<br> PSTN 存取  | 已針對 商務用 Skype 啟用，Exchange (資源信箱)  <br>已啟用音訊會議 <br>已啟用電話系統 |
| 雪梨總部 | 山          | 大型         | 2 螢幕、音訊和視像加簡報<br>電話撥入式會議存取<br> PSTN 存取  | 已針對 商務用 Skype 啟用，Exchange (資源信箱) <br> 已啟用音訊會議 <br>已啟用電話系統 |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>準備Microsoft Teams 會議室電腦和服務帳戶 (選項) 

若要在電腦和服務帳戶上管理Microsoft Teams 會議室報表，請準備內部部署 Active Directory 或 Azure Active Directory (Azure AD) 。 

定義內部部署 Active Directory 或 Azure AD 群組，以新增所有 Microsoft Teams 會議室 服務 (使用者) 帳戶，然後在整個 Microsoft Teams 會議室 部署中使用 Get-CSUserSession PowerShell Cmdlet 來建立使用方式報告。 例如，建立名為 SkypeRoomSystemsv2-Service-Accounts 的群組。 


在內部部署 Active Directory 或 Azure AD 階層中定義一個組織單位，以保留所有 Microsoft Teams 會議室 電腦帳戶 (如果他們已加入網域) ，另一個組織單位則保留所有 Microsoft Teams 會議室 使用者帳戶。 如果您為 Microsoft Teams 會議室 電腦帳戶建立組織單位，請考慮停用繼承，以確保您只將您打算適用于已加入網域Microsoft Teams 會議室。 

建立指派給包含您帳戶之組織單位的群組原則Microsoft Teams 會議室物件。 請使用這個功能： 

-   [設定 Power 和 local account 設定](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)。
-   啟用Windows更新。
-   啟用 PowerShell 重處理。 您可以設定啟動腳本以執行腳本：Enable-PSRemoting -Force

您可以使用 PowerShell 來執行數個遠端系統管理活動，包括取得和設定設定資訊。 PowerShell 遠端系統管理必須先啟用，才能進行任何 PowerShell 遠端系統管理，並視為部署程式或透過群組原則進行配置的一部分。 有關這些功能及啟用這些功能的資訊，請參閱 [維護與作業](rooms-operations.md#remote-management-using-powershell)。 


## <a name="configuration-and-deployment"></a>組組和部署 

組組和部署規劃涵蓋下列主要領域：

-   帳戶資源配置
-   裝置軟體安裝
-   裝置部署
-   Microsoft Teams 會議室應用程式和周邊裝置組組
-   測試
-   資產管理

### <a name="account-provisioning"></a>帳戶資源配置 

每個Microsoft Teams 會議室裝置都需要一個專用且唯一的資源帳戶，且必須同時為Microsoft Teams或商務用 Skype Exchange。 此帳戶必須在 Exchange 上託管會議室信箱，並啟用為部署Teams或商務用 Skype會議室。 在Exchange，必須配置處理日曆，讓裝置能夠自動接受傳入的會議邀請。 有關建立這些帳戶的資訊，請參閱[設定帳戶Microsoft Teams 會議室。](rooms-configure-accounts.md) 

**Pro提示**： 讓這些帳戶的顯示名稱具有描述性且容易理解。 這些是使用者在搜尋及將系統新加入會議時Microsoft Teams 會議室的名稱。 有些組織使用會議網站會議室名稱 (最大會議室容量) -RS，例如 Curie ，即倫敦的 12 人會議室，其顯示名稱為 - ** LON-CURIE (12) -RS。  

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![決定命名慣例。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定您帳戶的命名Microsoft Teams 會議室慣例。</li><li>決定是否要建立個別帳戶或使用大量置備腳本。</li></ul>| 
| ![下一個步驟。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的裝置部署。</li></ul>| 


### <a name="device-software-installation"></a>裝置軟體安裝 

規劃部署Microsoft Teams 會議室時，有許多選項可考慮安裝所需的軟體。 下表說明常見案例與方法。 

| **案例**            | **方法**         |
|-------------------------|-----------------------|   
|在 10 Microsoft Teams 會議室部署 (<數) 。 | 如果您使用Surface Pro型Microsoft Teams 會議室，請遵循每個裝置安裝的[安裝指示](console.md)。 [這段實用影片會引導您完成此程式。](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) 如果使用整合式解決方案，請使用廠商映射進行部署，並設定必要的設定。 |
| 從單一廠商部署 10 到 50 個裝置。     | 建立 WIM 型影像、在指南步驟 [6](console.md)之後暫停，並捕獲要與複製發佈技術一起使用的發佈影像。    |
| 部署超過 50 Microsoft Teams 會議室裝置、部署來自多個廠商的裝置，或需要組織專用代理程式做為部署的一部分。 | 使用以工作順序程式為基礎的軟體建立和發佈平臺，例如[Microsoft Endpoint Configuration Manager。](rooms-scale.md)  |


**Pro提示**- Microsoft Teams 會議室網路上必須有有效且唯一的機器名稱。 許多監控和警示系統將電腦名稱稱顯示為金鑰識別碼，因此必須針對 Microsoft Teams 會議室 部署開發命名慣例，讓支援人員輕鬆找到已標為需要動作的 Microsoft Teams 會議室。 範例可能是使用一種模式，即使用一種由一種模式所建立 - ** (-LON-CURIE) 。 

在部署中，您也需要考慮管理及配置由應用程式安裝程式所建立之Microsoft Teams 會議室策略。 [](/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts)

我們提供有關如何使用 Microsoft Azure 監視器來[](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor)監控 Microsoft Teams 會議室部署，並報告可用性、硬體/軟體錯誤，以及Microsoft Teams 會議室版本。 如果您決定使用 Microsoft Operations Management Suite，您應該在軟體安裝過程中安裝營運管理套件代理程式，並設定工作區的工作區連接資訊。 

另一個考慮是Microsoft Teams 會議室是否加入網域。 有關網域加入優點的資訊，請參閱會議室Skype[網域加入考慮。](domain-joining-considerations.md) 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![決策點裝置命名。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定Microsoft Teams 會議室部署期間所使用的裝置命名慣例。</li><li>決定是否要將裝置Microsoft Teams 會議室網域，以及如何管理及設定本地帳戶。 </li><li>決定是否要使用營運管理套件來監控Microsoft Teams 會議室部署。</li><li>決定您將使用哪一種方法將軟體和代理程式部署到 Microsoft Teams 會議室系統，以準備裝置部署。 </li></ul>| 
| ![下一個步驟方案裝置。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的裝置部署方法。</li></ul>| 


### <a name="device-deployment"></a>裝置部署

將軟體部署到 Microsoft Teams 會議室 裝置之後，請建立您的方案，將裝置及其指派的周邊裝置運送到您的會議室，然後繼續進行安裝和安裝。 


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![管理網站部署。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定誰將管理網站部署。</li><li> 找出將安裝裝置Microsoft Teams 會議室的資源，然後進行組組和測試。</li></ul>| 
| ![啟動裝置測試。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始裝置測試。</li></ul>| 

_範例部署資料表_

| **網站**  | **會議室名稱** | **會議室類型** | **Microsoft Teams 會議室系統**  | **周邊裝置**  | **Microsoft Teams 會議室電腦名稱稱**  | **Microsoft Teams 會議室資源帳戶**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| 倫敦總部 | 居裡         | 中型        |                                   |                  |                                          |                                             |
| 雪梨總部 | 山          | 大型         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft Teams 會議室應用程式和周邊裝置組組 

每個 Microsoft Teams 會議室 系統已實際部署並連接支援的周邊裝置之後，您必須設定 Microsoft Teams 會議室 應用程式，以指派先前建立之 Microsoft Teams 會議室 資源帳戶和密碼，讓 Microsoft Teams 會議室 系統能夠登錄 Microsoft Teams 或 商務用 Skype 和 Exchange。 利用檔其他位置連結的經過認證的 USB 音訊和視像周邊設備是一項關鍵。 否則可能會導致無法預測的行為。 

您可以手動設定每個Microsoft Teams 會議室系統。 或者，您也可以使用集中儲存的 xml 設定檔來管理應用程式設定，並運用啟動 GPO 腳本，每次 Microsoft Teams 會議室 系統啟動時重新套用您想要的設定。 Microsoft Teams 會議室 

若要瞭解如何使用 XML 設定檔，請參閱使用 XML 組Microsoft Teams 會議室遠端系統管理主機[設定](xml-config-file.md)。 

您可以使用遠端[PowerShell](rooms-operations.md#remote-management-using-powershell)來針對報告需求Microsoft Teams 會議室資料配置。 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![決策點設定。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定是否要手動設定每個Microsoft Teams 會議室，或使用中央 XML 檔案 (每個裝置Microsoft Teams 會議室一) 。</li></ul>| 
| ![下一個步驟遠端方法。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>定義遠端系統管理方法。</li></ul>| 

### <a name="testing"></a>測試

系統Microsoft Teams 會議室之後，您應該測試。 檢查已部署Microsoft Teams 會議室[中所列的](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)功能是否正常。 我們強烈建議部署小組確認Microsoft Teams 會議室已記錄至 Microsoft Operations Management Suite (是否) 。 此外，您還必須進行數次測試通話和會議，以檢查品質。 詳細資訊，請參閱此 [實用的部署檢查清單](console.md#microsoft-teams-rooms-deployment-checklist)。

我們建議您在一般 Teams 或 商務用 Skype 推出時，設定通話品質儀表板 (CQD) 的建庫檔案、監控品質趨勢，以及參與體驗品質檢閱程式。 詳細資訊，請參閱改善及[監控通話品質Teams。](../monitor-call-quality-qos.md) 

### <a name="asset-management"></a>資產管理

在部署中，您需要使用會議室名稱、Microsoft Teams 會議室 裝置名稱、已登錄 Microsoft Teams 會議室 資源帳戶，以及指派的周邊裝置 (，以及他們使用哪些 USB 埠) 來更新資產註冊。 

_範例資產資料表_

| **網站**  | **會議室名稱** | **會議室類型** | **Microsoft Teams 會議室序號。**  | **周邊裝置/串口編號/埠**  | **Microsoft Teams 會議室電腦名稱稱**  | **Microsoft Teams 會議室服務帳戶**  | **部署日期** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| 倫敦總部 | 居裡         | 中型        |                                          |                                          |                                          |                                            |                   |
| 雪梨總部 | 山          | 大型         |                                          |                                          |                                          |                                            |                   |