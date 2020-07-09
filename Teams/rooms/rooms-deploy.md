---
title: 部署 Microsoft Teams 會議室
ms.author: v-lanac
author: lanachin
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
description: 閱讀本文以瞭解如何部署 Microsoft 團隊聊天室，包括部署階段。
ms.openlocfilehash: ee8ff755674828b4a2635316227f9cc27189a110
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085959"
---
# <a name="deployment-overview"></a>部署概觀

Microsoft 團隊聊天室的部署實質上會分解成幾個階段：

- 確認您的部署位置（會議室）符合部署相依性
- 建立 Microsoft 團隊或商務用 Skype 與 Exchange 帳戶，並將其指派給主控台裝置（請參閱[設定 Microsoft 團隊聊天室的帳戶](rooms-configure-accounts.md)）
- 重設 Microsoft Surface 平板電腦版，以做為 Microsoft 團隊聊天室主控台（請參閱[設定 Microsoft 團隊聊天室主控台](console.md)或[部署 microsoft 團隊聊天室大量部署指南](rooms-scale.md)）
- 可選為您的系統設定 Microsoft 作業管理套件（請參閱[使用 Azure 監視器部署 Microsoft 團隊聊天室管理](azure-monitor-deploy.md)
- 在會議室中設定主控台並連接您需要的週邊裝置（請參閱適用于您裝置的 OEM 檔）

[AV techs] 可用於最後一個工作，但貴組織的 IT 部門將需要執行此程式的其他部分。 


## <a name="site-readiness"></a>網站準備 

當已排序的裝置傳送給您的組織時，請與您的網路和設施和 AV 團隊共同作業，以確保已滿足部署相依性，且每個網站和會議室都已準備好使用 power、網路及顯示器。 此外，請確定符合物理安裝需求。 如需實際安裝的考慮，請造訪供應商的網站，並充分利用您的 AV 小組在安裝和安裝螢幕及執行佈線時的體驗。

您可以在下面的規劃指導方針連結中找到更多關於這些相依性的相關資訊：

-   [檢查網路可用性](rooms-prep.md#check-network-availability)
-   [證書](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Pro 提示**-如果您想要使用 proxy 伺服器來提供團隊或商務用 Skype Online 的存取權，請先[閱讀本文](../proxy-servers-for-skype-for-business-online.md)。 請注意，當您透過 proxy 伺服器上的商務用 Skype 流量時，我們建議您完全忽略 proxy 伺服器。 商務用 Skype 通訊已加密，所以 proxy 伺服器無法讓它更加安全。 我們建議您按照較廣的部署，在您的[網路上準備小組](../prepare-network.md)進行頻寬規劃，並評估您的網路對即時流量的適用性。

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>確認您的網站符合 Microsoft 團隊聊天室的主要需求。</li><li>確認您已為每個網站提供足夠的頻寬。</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的裝置部署和配置。</li></ul>| 

## <a name="service-readiness"></a>服務就緒性

若要準備您的 Microsoft 小組會議室部署，請執行下列重要的中央工作：

-   定義 Microsoft 團隊聊天室服務帳戶功能。
-   準備組織單位和 Active Directory 群組，以保留 Microsoft 團隊聊天室電腦和服務帳戶，以及（選擇性地）準備群組原則物件（Gpo）來啟用 PowerShell 遠端處理。

### <a name="define-microsoft-teams-rooms-service-account-features"></a>定義 Microsoft 團隊聊天室服務帳戶功能 

根據您針對 Microsoft 團隊聊天室部署所決定啟用的共同作業案例，您必須判斷您指派給您的每個 Microsoft 團隊聊天室服務帳戶所指派的功能和功能。

| **案例** | **描述** | **Microsoft 團隊聊天室服務帳戶功能** |
|---------- |------------- | --- |
| 互動式會議            | 使用語音、影片和螢幕共用;將 Microsoft 團隊會議室製作成 bookable 資源                     | 針對商務用 Skype 啟用，已啟用 Exchange （資源信箱） |
| 電話撥入式會議            | 使用電話撥入式會議座標，從 Microsoft 團隊聊天室主控台*直接*開始進行會議 | 已啟用音訊會議                                          |
| 輸出/進貨 PSTN 通話 | 啟用 Microsoft 團隊聊天室主控台來撥打和接聽 PSTN 通話                                         | 已啟用電話系統                                                |

如需 Microsoft 團隊聊天室帳戶的詳細資訊，請參閱[設定 Microsoft 團隊聊天室的帳戶](rooms-configure-accounts.md)。


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定您要支援哪些案例，並找出您的 Microsoft 團隊聊天室服務帳戶的授權需求。</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>準備主持電腦與服務帳戶。</li></ul>| 


_範例 Microsoft 團隊聊天室服務帳戶規劃表格_

| **網站**  | **會議室名稱** | **會議室類型** | **未來的空間功能**                                                 | **Microsoft 團隊聊天室帳戶功能**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| 倫敦總部 | Curie         | 中型        | 1畫面、音訊及影片加上簡報 <br>電話撥入式會議存取<br> PSTN 存取  | 針對商務用 Skype 啟用，已啟用 Exchange （資源信箱） <br>已啟用音訊會議 <br>已啟用電話系統 |
| 悉尼總部 | 峰          | 大型         | 2個畫面、音訊及影片加上簡報<br>電話撥入式會議存取<br> PSTN 存取  | 針對商務用 Skype 啟用，已啟用 Exchange （資源信箱）<br> 已啟用音訊會議 <br>已啟用電話系統 |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>準備主持 Microsoft 團隊聊天室電腦與服務帳戶（選用）

若要讓您管理並報告 Microsoft 團隊聊天室電腦和服務帳戶，請準備您的內部部署 Active Directory 或 Azure Active Directory （Azure AD）。 

定義內部部署的 Active Directory 或 Azure AD 群組，以將所有 Microsoft 團隊聊天室服務（使用者）帳戶新增至，然後使用 CSUserSession PowerShell Cmdlet 在您的 Microsoft 團隊聊天室部署中建立使用方式報告。 例如，建立名為 SkypeRoomSystemsv2-服務帳戶的群組。 


在您的內部部署 Active Directory 或 Azure AD 階層中定義一個組織單位，以保留所有 Microsoft 團隊聊天室電腦帳戶（如果它們已加入網域）和一個組織單位，以保留所有 Microsoft 團隊聊天室使用者帳戶。 如果您為 Microsoft 團隊聊天室電腦帳戶建立組織單位，請考慮停用繼承，以確保您只將所需的原則套用至加入網域的 Microsoft 團隊聊天室。 

建立指派給包含您 Microsoft 團隊聊天室電腦帳戶之組織單位的群組原則物件。 使用此功能可執行下列動作： 

-   [設定 [電源] 和 [本機帳戶] 設定](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)。
-   啟用 [Windows Update]。
-   啟用 PowerShell 遠端作業。 您可以設定啟動腳本來執行簡單的腳本： Enable-PSRemoting-Force

您可以使用 PowerShell 來執行許多遠端系統管理活動，包括取得和設定設定資訊。 必須先啟用 PowerShell remoting，*才能*進行任何 PowerShell 遠端系統管理，而且應該將它視為部署程式的一部分，或是透過群組原則進行設定。 如需這些功能的詳細資訊並啟用這些功能，請參閱[維護與作業](rooms-operations.md#remote-management-using-powershell)。 


## <a name="configuration-and-deployment"></a>配置和部署 

規劃配置和部署涵蓋下列主要區域：

-   帳戶預配
-   裝置軟體安裝
-   裝置部署
-   Microsoft 團隊聊天室應用程式和週邊裝置設定
-   正在
-   資產管理

### <a name="account-provisioning"></a>帳戶預配 

每個 Microsoft 團隊機房裝置都需要具備專用且唯一的資源帳戶，才能在 Microsoft 團隊或商務用 Skype 和 Exchange 中啟用。 此帳戶必須擁有 Exchange 託管的聊天室信箱，並在團隊或商務用 Skype 部署中啟用為會議室。 在 Exchange 端，您必須設定行事曆處理，才能讓裝置自動接受傳入的會議邀請。 如需建立這些帳戶的詳細資訊，請參閱[設定 Microsoft 團隊聊天室的帳戶](rooms-configure-accounts.md)。 

**Pro 提示**：讓這些帳戶的顯示名稱具描述性且易於理解。 這些是使用者在搜尋並新增 Microsoft 團隊聊天室系統至會議時所看到的名稱。 有些組織會使用 [公約]*網站*的 - *聊天室名稱*（*最大房間容量*）-RS （例如 Curie），在倫敦有12個人員的會議室，可能會有顯示名稱 LON-Curie （12）-RS。 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>針對您的 Microsoft 團隊聊天室帳戶決定命名慣例。</li><li>決定您要建立個別帳戶或使用大量提供腳本。</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的裝置部署。</li></ul>| 


### <a name="device-software-installation"></a>裝置軟體安裝 

規劃部署 Microsoft 團隊聊天室時，您有幾個選項可考慮安裝必要的軟體。 下表說明常見的案例及方法。 

| **案例**            | **手段**         |
|-------------------------|-----------------------|   
|部署少量的 Microsoft 團隊會議室裝置（<10）。 | 如果您使用的是 Surface Pro 的 Microsoft 團隊聊天室，請遵循[針對每個裝置安裝的安裝指示進行](console.md)。 [這個方便的影片會逐步引導您完成整個程式。](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) 如果您使用的是整合解決方案，請使用 [廠商] 影像來部署，並視需要設定設定。 |
| 從單一供應商的10與50裝置進行部署。     | 建立 WIM 的映射，[在指南中的步驟 6](console.md)之後暫停，並捕獲與您的仿製發佈技術搭配使用的發佈影像。    |
| 部署50以上的 Microsoft 團隊會議室裝置、從多個供應商部署裝置，或需要組織特定的代理程式作為部署的一部分。 | 使用以任務排序器為基礎的軟體組建與發佈平臺，例如[Microsoft 端點建構管理員](rooms-scale.md)。  |


**Pro 提示**-每個 Microsoft 團隊聊天室都必須在您的網路上擁有有效且唯一的電腦名稱稱。 許多監視及觸發系統會將電腦名稱稱顯示為金鑰識別碼，因此請務必開發 Microsoft 團隊聊天室部署的命名慣例，以讓支援人員輕鬆找出已標記為需要動作的 Microsoft 團隊聊天室。 範例可能是使用 MTR-*網站* - *房間名稱*（MTR-CURIE）的模式。 

在部署過程中，您也需要考慮管理和設定由 Microsoft 小組聊天室應用程式安裝程式所建立的[本機帳戶](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts)的方案。

我們提供有關如何使用[Microsoft Azure 監視器](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor)來監視 Microsoft 團隊會議室部署並報告可用性、硬體/軟體錯誤及 Microsoft 團隊聊天室應用程式版本的指導方針。 如果您決定使用 Microsoft Operations Management Suite，請在軟體安裝程式中安裝作業管理套件代理程式，並設定工作區的工作區連線資訊。 

另一個考慮是，是否要考慮將 Microsoft 團隊聊天室加入網域。 您可以在[Skype 會議室系統網域加入考慮](domain-joining-considerations.md)中找到有關網域加入的好處資訊。 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定要在您的部署期間使用的 Microsoft 團隊會議室裝置命名慣例。</li><li>決定您是否要將 Microsoft 團隊聊天室裝置加入您的網域，以及如何管理和設定本機帳戶。 </li><li>決定您是否要使用 Operations Management Suite 來監視 Microsoft 團隊聊天室部署。</li><li>決定您要使用哪種方法將軟體和代理程式部署到 Microsoft 團隊聊天室系統，以準備進行裝置部署。 </li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的裝置部署做法。</li></ul>| 


### <a name="device-deployment"></a>裝置部署

在您將軟體部署到 Microsoft 團隊會議室之後，請建立您的方案，將裝置及其指派的週邊裝置傳送到您的聊天室，然後繼續進行安裝與設定。 


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定誰能管理網站的網站部署。</li><li> 找出將在網站上安裝 Microsoft 團隊聊天室裝置的資源，並進行設定及測試。</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>啟動裝置測試。</li></ul>| 

_範例部署資料表_

| **網站**  | **會議室名稱** | **會議室類型** | **Microsoft 團隊聊天室系統**  | **週邊裝置**  | **Microsoft 團隊聊天室電腦名稱稱**  | **Microsoft 團隊聊天室資源帳戶**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| 倫敦總部 | Curie         | 中型        |                                   |                  |                                          |                                             |
| 悉尼總部 | 峰          | 大型         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft 團隊聊天室應用程式和週邊裝置設定 

在每個 Microsoft 團隊會議室系統都已實際部署且已連接支援的週邊裝置之後，您必須設定 Microsoft 團隊聊天室應用程式，將其指派給舊版的 Microsoft 團隊聊天室資源帳戶和密碼，以讓 Microsoft 團隊聊天室系統登入 Microsoft 團隊或商務用 Skype 和 Exchange。 在檔中的其他位置，充分利用連結的已認證 USB 音訊及視頻週邊設備的金鑰。 如果不這麼做，可能會導致無法預料的行為。 

您可以手動設定每個 Microsoft 團隊會議室系統。 或者，您也可以使用集中式儲存的每個 Microsoft 團隊會議室 XML 配置檔案來管理應用程式設定，並利用啟動 GPO 腳本，在每次 Microsoft 小組聊天室系統啟動時，重新套用您想要的設定。 

如需有關如何使用 XML 設定檔的詳細資訊，請參閱[使用 xml 設定檔遠端系統管理 Microsoft 球隊聊天室主控台設定](xml-config-file.md)。 

您可以使用[遠端 PowerShell](rooms-operations.md#remote-management-using-powershell)來拉入 Microsoft 團隊聊天室設定，以取得報告需求。 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定是否要手動設定每個 Microsoft 團隊聊天室系統，或使用中央 XML 檔案（每個 Microsoft 團隊會議室裝置一個）。</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>定義您的遠端系統管理做法。</li></ul>| 

### <a name="testing"></a>正在

部署 Microsoft 團隊聊天室系統之後，您應該進行測試。 檢查[Microsoft 團隊聊天室](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)中所列的功能是否可協助您在已部署的裝置上運作。 我們強烈建議部署小組驗證 Microsoft [小組] 會議室是否已記錄到 Microsoft 作業管理套件（如果使用）。 您也必須進行一些測試通話和會議，才能檢查品質。 如需詳細資訊，請參閱此[實用的部署檢查清單](console.md#microsoft-teams-rooms-deployment-checklist)。

我們建議您做為 [一般小組] 或 [商務用 Skype] 推出的一部分，您可以設定為通話品質儀表板（CQD）建立檔案、監控品質趨勢，以及參與經驗檢查的品質。 如需詳細資訊，請參閱[改善及監視團隊的通話品質](../monitor-call-quality-qos.md)。 

### <a name="asset-management"></a>資產管理

在部署過程中，您會想要使用房間名稱、Microsoft 團隊聊天室裝置名稱、登入的 Microsoft 團隊聊天室資源帳戶和指派的週邊裝置（以及它們所使用的 USB 埠）來更新資產登記簿。 

_[資產] 資料表範例_

| **網站**  | **會議室名稱** | **會議室類型** | **Microsoft 團隊聊天室序號**  | **週邊裝置/串列 nos （埠）**  | **Microsoft 團隊聊天室電腦名稱稱**  | **Microsoft 團隊聊天室服務帳戶**  | **部署日期** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| 倫敦總部 | Curie         | 中型        |                                          |                                          |                                          |                                            |                   |
| 悉尼總部 | 峰          | 大型         |                                          |                                          |                                          |                                            |                   |


