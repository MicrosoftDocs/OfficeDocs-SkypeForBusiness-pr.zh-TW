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
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 請閱讀本文，瞭解如何部署 Microsoft Teams 會議室，包括部署階段。
ms.openlocfilehash: 87ded33b464d6f5248fe1fb71d579d5f191bb6b6
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726304"
---
# <a name="deployment-overview"></a>部署概觀

Microsoft Teams 會議室的部署基本上分成階段：

- 確認您的部署位置 (聊天室) 部署相依性
- 建立 Microsoft Teams 或商務用 Skype 和 Exchange 帳戶，並將這些帳戶指派給主機 (請參閱設定 [Microsoft Teams 會議室](rooms-configure-accounts.md)) 
- 重新製作 Microsoft Surface 平板電腦以做為 Microsoft Teams 會議室主機 (請參閱設定 [Microsoft Teams 會議室](console.md) 主機或部署 Microsoft Teams [會議室大量](rooms-scale.md) 部署指南) 
-  (為) 設定 Microsoft Operations Management Suite 的選擇性選項 (請參閱使用 Azure 監視器部署 [Microsoft Teams 會議室管理](azure-monitor-deploy.md)
- 在會議室中設定主機，並連接您需要的 (裝置，請參閱適用于您裝置集合的 OEM 檔) 

AV 技術可用於最後一項工作，但貴組織的 IT 部門必須執行程式的其他部分。 


## <a name="site-readiness"></a>網站就緒 

當訂購的裝置送達貴組織時，請與網路和裝置及 AV 小組合作，以確保符合部署相依性，而且每個網站和空間在電源、網路和顯示方面已準備就緒。 此外，請確定符合實際安裝需求。 針對實際安裝考慮，請流覽廠商的網站，並運用 AV 小組在安裝和安裝螢幕及執行接線時的體驗。

您可以在下列規劃指引連結中，進一步瞭解這些相依性：

-   [檢查網路可用性](rooms-prep.md#check-network-availability)
-   [證書](rooms-prep.md#certificates)
-   [代理](rooms-prep.md#proxy)

**專業秘訣** - 如果您打算使用 Proxy 伺服器來提供 Teams 或商務用 Skype Online 的存取權，請先 [閱讀本文](../proxy-servers-for-skype-for-business-online.md)。 當涉及商務用 Skype 流量的 Proxy 伺服器時，建議您完全忽略 Proxy 伺服器。 商務用 Skype 流量已加密，因此 Proxy 伺服器不會使其更安全。 在較廣泛的部署中，我們建議您遵循 Teams 網路準備中的指引[](../prepare-network.md)，以規劃頻寬並評估您的網路是否適合即時流量。

|    |     |
|-----------|------------|
| ![確認網站](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>確認網站符合 Microsoft Teams 會議室的重要需求。</li><li>確認您針對每個網站都提供了足夠的頻寬。</li></ul>| 
| ![規劃裝置部署](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的裝置部署和組配置。</li></ul>| 

## <a name="service-readiness"></a>服務整備

若要準備您的 Microsoft Teams 會議室部署，請執行下列重要的中心工作：

-   定義 Microsoft Teams 會議室服務帳戶功能。
-   準備組織單位和 Active Directory 群組以保留您的 Microsoft Teams 會議室電腦和服務帳戶，並且準備群組原則物件 (GPO) 啟用 PowerShell 重算。

### <a name="define-microsoft-teams-rooms-service-account-features"></a>定義 Microsoft Teams 會議室服務帳戶功能 

根據您決定要啟用 Microsoft Teams 會議室部署的共同合作案例，您必須判斷您指派給每個 Microsoft Teams 會議室服務帳戶的功能。

| **案例** | **描述** | **Microsoft Teams 會議室服務帳戶功能** |
|---------- |------------- | --- |
| 互動式會議            | 使用語音、影片和螢幕畫面分享;將 Microsoft Teams 會議室製作為可預約的資源                     | 已啟用商務用 Skype，已啟用 Exchange (資源信箱)  |
| 電話撥入式會議            | 使用電話撥入 *式* 會議座標，直接從 Microsoft Teams 會議室主控台啟動會議 | 已啟用音訊會議                                          |
| 外發/內線 PSTN 通話 | 啟用 Microsoft Teams 會議室主機撥打和接聽 PSTN 電話                                         | 已啟用電話系統                                                |

有關 Microsoft Teams 會議室帳戶的資訊，請參閱 [設定 Microsoft Teams 會議室的帳戶](rooms-configure-accounts.md)。


|    |     |
|-----------|------------|
| ![案例支援](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定您將支援哪些案例，並找出 Microsoft Teams 會議室服務帳戶的授權需求。</li></ul>| 
| ![準備主機電腦](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>準備託管電腦和服務帳戶。</li></ul>| 


_範例 Microsoft Teams 會議室服務帳戶規劃資料表_

| **網站**  | **會議室名稱** | **會議室類型** | **未來的會議室功能**                                                 | **Microsoft Teams 會議室帳戶功能**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| 倫敦總部 | 居裡         | 中型        | 1 個螢幕、音訊和視音訊加簡報 <br>電話撥入式會議存取<br> PSTN 存取  | 已啟用商務用 Skype，已啟用 Exchange (資源信箱)  <br>已啟用音訊會議 <br>已啟用電話系統 |
| 雪梨總部 | 山          | 大型         | 2 螢幕、音訊和視視加簡報<br>電話撥入式會議存取<br> PSTN 存取  | 已啟用商務用 Skype，已啟用 Exchange (資源信箱) <br> 已啟用音訊會議 <br>已啟用電話系統 |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>準備託管 Microsoft Teams 會議室電腦和服務帳戶 (選) 

若要啟用您管理及報告 Microsoft Teams 會議室電腦和服務帳戶，請準備內部部署 Active Directory 或 Azure Active Directory (Azure AD) 。 

定義內部部署的 Active Directory 或 Azure AD 群組，以新增所有 Microsoft Teams 會議室服務 (使用者) 帳戶，然後在整個 Microsoft Teams 會議室部署使用 Get-CSUserSession PowerShell Cmdlet 來建立使用方式報告。 例如，建立名為 SkypeRoomSystemsv2-Service-Accounts 的群組。 


在內部部署 Active Directory 或 Azure AD 階層中定義一個組織單位，以保留所有 Microsoft Teams 會議室電腦帳戶 (如果他們已加入網域) ，以及一個組織單位來保存所有 Microsoft Teams 會議室使用者帳戶。 如果您為 Microsoft Teams 會議室電腦帳戶建立組織單位，請考慮停用繼承，以確保您只將您打算將原則適用于已加入網域的 Microsoft Teams 會議室。 

建立指派給包含 Microsoft Teams 會議室電腦帳戶的組織單位的群組原則物件。 請使用此功能： 

-   [設定電源和本地帳戶設定](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)。
-   啟用 Windows Update。
-   啟用 PowerShell 重處理。 您可以設定啟動腳本以執行腳本：Enable-PSRemoting -Force

您可以使用 PowerShell 執行數個遠端系統管理活動，包括取得和設定設定資訊。 PowerShell 重新管理必須先啟用，才能進行任何 PowerShell 遠端系統管理，且應視為部署程式一部分，或透過群組原則進行群組原則。 有關這些功能及啟用這些功能的資訊，請參閱 [維護與作業](rooms-operations.md#remote-management-using-powershell)。 


## <a name="configuration-and-deployment"></a>組配置與部署 

群組原則與部署規劃涵蓋下列重要領域：

-   帳戶設置
-   裝置軟體安裝
-   裝置部署
-   Microsoft Teams 會議室應用程式和周邊裝置組
-   測試
-   資產管理

### <a name="account-provisioning"></a>帳戶設置 

每個 Microsoft Teams 會議室裝置都需要專屬且唯一的資源帳戶，必須同時啟用 Microsoft Teams 或商務用 Skype 和 Exchange。 這個帳戶必須擁有託管在 Exchange 上的會議室信箱，而且要啟用為 Teams 或商務用 Skype 部署中的會議室。 在 Exchange 端，必須配置處理日曆，裝置才能自動接受傳入的會議邀請。 有關建立這些帳戶的資訊，請參閱設定 [Microsoft Teams 會議室的帳戶](rooms-configure-accounts.md)。 

**專業秘訣** – 讓這些帳戶的顯示名稱具有描述性且容易理解。 這些是使用者在搜尋並新增 Microsoft Teams 會議室系統至會議時會看到的名稱。 有些組織使用會議網站會議室名稱 (最大會議室容量) -RS，因此例如 Curie 這個倫敦 12 人的會議室，其顯示名稱可能是 - ** LON-CURIE (12) -RS。  

|    |     |
|-----------|------------|
| ![決定命名慣例](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定 Microsoft Teams 會議室帳戶的命名慣例。</li><li>決定是否要建立個別帳戶或使用大量配置腳本。</li></ul>| 
| ![下一個步驟](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的裝置部署。</li></ul>| 


### <a name="device-software-installation"></a>裝置軟體安裝 

規劃部署 Microsoft Teams 會議室時，有許多選項需要考慮安裝必要的軟體。 下表說明常見案例與方法。 

| **案例**            | **方法**         |
|-------------------------|-----------------------|   
|部署數個 Microsoft Teams 會議室裝置， (<10) 。 | 如果使用 Surface Pro 型 Microsoft Teams 會議室，請遵循每個 [裝置安裝的安裝指示](console.md)。 [這個便利的影片會逐步引導您完成此程式。](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) 如果使用整合式解決方案，請利用廠商映射進行部署，並設定必要的設定。 |
| 從單一廠商部署 10 到 50 部裝置。     | 建立 WIM 型影像、在指引中的步驟 [6](console.md)之後暫停，並拍攝發佈影像，以用於您的複製發佈技術。    |
| 部署超過 50 個 Microsoft Teams 會議室裝置、部署來自多個廠商的裝置，或要求組織特定的代理程式做為部署的一部分。 | 使用以工作順序器為基礎的軟體建立和發佈平臺，例如 [Microsoft 端點組態管理員](rooms-scale.md)。  |


**專業提示** - 每個 Microsoft Teams 會議室都必須有您網路上有效且唯一的機器名稱。 許多監控和警示系統將電腦名稱稱顯示為金鑰識別碼，因此，為 Microsoft Teams 會議室部署開發命名慣例非常重要，可讓支援人員輕鬆找到已標為需要採取行動的 Microsoft Teams 會議室。 例如，使用一種模式為 ：使用一種模式：使用一種由 1994 年 12 月 30 日 (- 的一個模式 ：一個使用 1993 年 4 月 31 日) 。 

在部署時，您也需要考慮管理及配置 Microsoft Teams 會議室應用程式安裝程式所建立之[](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts)本地帳戶的策略。

我們提供有關如何使用 Microsoft Azure [監視器](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) 監控 Microsoft Teams 會議室部署及報告可用性、硬體/軟體錯誤，以及 Microsoft Teams 會議室應用程式版本的指引。 如果您決定使用 Microsoft Operations Management Suite，您應該在軟體安裝程式中安裝 Operations Management Suite 代理程式，並設定工作區的工作區連接資訊。 

另一個考慮是 Microsoft Teams 會議室是否會加入網域。 有關網域加入優點的資訊，請參閱 Skype Room [System](domain-joining-considerations.md)網域加入考慮。 

|    |     |
|-----------|------------|
| ![決策點裝置命名](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定部署期間所使用的 Microsoft Teams 會議室裝置命名慣例。</li><li>決定是否要加入 Microsoft Teams 會議室裝置至您的網域，以及如何管理和設定本地帳戶。 </li><li>決定是否要使用 Operations Management Suite 監控 Microsoft Teams 會議室部署。</li><li>決定您將使用哪一種方法將軟體和代理程式部署到 Microsoft Teams 會議室系統，以準備裝置部署。 </li></ul>| 
| ![下一個步驟方案裝置](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的裝置部署方法。</li></ul>| 


### <a name="device-deployment"></a>裝置部署

將軟體部署到 Microsoft Teams 會議室單位之後，請建立計畫，將裝置及其指派的周邊裝置運送至您的會議室，然後繼續進行安裝和安裝。 


|    |     |
|-----------|------------|
| ![管理網站部署](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定將管理網站部署的人。</li><li> 找出將在網站安裝 Microsoft Teams 會議室裝置的資源，然後進行組配置和測試。</li></ul>| 
| ![開始裝置測試](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始裝置測試。</li></ul>| 

_範例部署資料表_

| **網站**  | **會議室名稱** | **會議室類型** | **Microsoft Teams 會議室系統**  | **周邊裝置**  | **Microsoft Teams 會議室電腦名稱稱**  | **Microsoft Teams 會議室資源帳戶**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| 倫敦總部 | 居裡         | 中型        |                                   |                  |                                          |                                             |
| 雪梨總部 | 山          | 大型         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft Teams 會議室應用程式和周邊裝置組 

在已實際部署每個 Microsoft Teams 會議室系統，並連接支援的周邊裝置之後，您必須設定 Microsoft Teams 會議室應用程式，以指派 Microsoft Teams 會議室資源帳戶和先前建立的密碼，以便 Microsoft Teams 會議室系統能夠登錄 Microsoft Teams 或商務用 Skype 和 Exchange。 運用檔中其他位置連結的經過認證的 USB 音訊和視音訊周邊設備，是一項關鍵。 否則可能會導致無法預測的行為。 

您可以手動設定每個 Microsoft Teams 會議室系統。 或者，您可以使用集中儲存的每一個 Microsoft Teams 會議室 XML 設定檔來管理應用程式設定，並運用啟動 GPO 腳本，每次 Microsoft Teams 會議室系統更新時，重新套用您想要的設定。 

有關如何使用 XML 設定檔之詳細資訊，請參閱使用 XML 設定檔遠端系統管理 [Microsoft Teams 會議室主控台設定](xml-config-file.md)。 

您可以使用遠端 [PowerShell](rooms-operations.md#remote-management-using-powershell) 來提取 Microsoft Teams 會議室的組式，以滿足報告需求。 

|    |     |
|-----------|------------|
| ![決策點設定](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定是否要手動設定每個 Microsoft Teams 會議室系統，或使用中央 XML 檔案， (每個 Microsoft Teams 會議室裝置裝置一) 。</li></ul>| 
| ![下一個步驟遠端方法](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>定義您的遠端系統管理方法。</li></ul>| 

### <a name="testing"></a>測試

部署 Microsoft Teams 會議室系統之後，您應該進行測試。 檢查 Microsoft [Teams 會議室](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) 中所列的功能在部署裝置上是否可正常使用。 強烈建議部署小組確認 Microsoft Teams 會議室已登 (Microsoft Operations Management Suite) 。 另外，請務必進行許多測試通話和會議，以檢查品質。 詳細資訊請參閱此實用的 [部署檢查清單](console.md#microsoft-teams-rooms-deployment-checklist)。

我們建議您在一般 Teams 或商務用 Skype 推出期間，為通話品質儀表板 (CQD) 設定建組檔案、監控品質趨勢，並參與經驗品質檢閱程式。 詳細資訊請參閱改善及 [監控 Teams 的通話品質](../monitor-call-quality-qos.md)。 

### <a name="asset-management"></a>資產管理

在部署時，您需要使用會議室名稱、Microsoft Teams 會議室裝置名稱、已登錄的 Microsoft Teams 會議室資源帳戶，以及指派的周邊裝置 (以及他們使用哪些 USB 埠來更新資產註冊) 。 

_資產表範例_

| **網站**  | **會議室名稱** | **會議室類型** | **Microsoft Teams 會議室序號。**  | **周邊裝置/序號/埠**  | **Microsoft Teams 會議室電腦名稱稱**  | **Microsoft Teams 會議室服務帳戶**  | **部署日期** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| 倫敦總部 | 居裡         | 中型        |                                          |                                          |                                          |                                            |                   |
| 雪梨總部 | 山          | 大型         |                                          |                                          |                                          |                                            |                   |


