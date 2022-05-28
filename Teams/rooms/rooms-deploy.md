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
description: 請閱讀本文以瞭解如何部署Microsoft Teams 會議室，包括部署階段。
ms.openlocfilehash: 0111e8723d70b753c2d8de64350387252db8f8f7
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2022
ms.locfileid: "65760915"
---
# <a name="deployment-overview"></a>部署概觀

部署Microsoft Teams 會議室基本上分成多個階段：

- 確認您的部署位置 (空格) 符合部署相依性
- 建立Microsoft Teams或商務用 Skype及Exchange帳戶，並將它們指派給Teams 會議室 (請參閱[設定帳戶Microsoft Teams 會議室) ](rooms-configure-accounts.md)
-  (選擇性) 為系統設定 Azure 監視器 (請參閱[使用 Azure 監視器部署Microsoft Teams 會議室管理](azure-monitor-deploy.md)
- 在會議空間中設定Teams 會議室，以及連接您需要的周邊裝置， (查看您一組裝置的 OEM 檔) 

## <a name="site-readiness"></a>網站整備 

當已訂購的裝置傳遞給貴組織時，請與您的網路、設施和 AV 小組合作，以確保符合部署相依性，而且在電源、網路和顯示方面，每個網站和空間都已準備就緒。 此外，請確定符合實體安裝需求。 如需實際安裝考慮，請洽詢您的廠商，並利用 AV 小組在安裝及安裝螢幕及執行駕駛線時的體驗。

您可以在下列規劃指導方針連結中深入瞭解這些相依性：

-   [檢查網路可用性](rooms-prep.md#check-network-availability)
-   [證書](rooms-prep.md#certificates)
-   [代理](rooms-prep.md#proxy)

**Pro提示**- 如果您必須使用 Proxy 伺服器來提供Teams的存取權，請先 [檢閱本文](../proxy-servers-for-skype-for-business-online.md)。 若要透過 Proxy 伺服器Microsoft Teams即時媒體流量，建議您略過 Proxy 伺服器。 Microsoft Teams流量已加密，因此 Proxy 伺服器不會使其更安全，而且會為即時流量增加延遲。 做為您更廣泛部署的一部分，我們建議您遵循[準備您的網路以進行Teams](../prepare-network.md)的指導方針，以進行頻寬規劃，並評估網路是否適合即時流量。

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![確認網站。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>確認您的網站符合Microsoft Teams 會議室的重要需求。</li><li>確認您已為每個網站提供足夠的頻寬。</li></ul>| 
| ![規劃裝置部署。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的裝置部署和設定。</li></ul>| 

## <a name="service-readiness"></a>服務整備

若要準備您的Microsoft Teams 會議室部署，請執行下列關鍵、中心工作：

-   定義Microsoft Teams 會議室資源帳戶。
-   如果加入 Teams 會議室 以Azure Active Directory，請準備具有動態成員資格的 Azure AD 群組，以保留所有Teams 會議室資源帳戶。 這將會簡化未來的管理，例如套用條件式存取原則。 為了最輕鬆地運用 Azure AD 動態群組，請決定命名慣例，以唯一方式識別您的Teams 會議室資源帳戶。
-   如果加入 Teams 會議室 至 Active Directory，請準備組織單位和 Active Directory 群組以保留您的Microsoft Teams 會議室電腦和資源帳戶，並選擇性地準備群組原則物件 (GPO) 啟用 PowerShell 重新傳送。

### <a name="define-microsoft-teams-rooms-resource-account-features"></a>定義Microsoft Teams 會議室資源帳戶功能 

根據您決定透過Microsoft Teams 會議室部署啟用的共同作業案例而定，您必須決定指派給您所啟用之每個Microsoft Teams 會議室的功能。

| **案例** | **描述** | **Microsoft Teams 會議室服務帳戶功能** |
|---------- |------------- | --- |
| 互動式會議            | 使用語音、視訊和螢幕畫面分享;將Microsoft Teams 會議室設定為可預約的資源                     | 已啟用Microsoft Teams或商務用 Skype;已啟用Exchange (資源信箱)  |
| 電話撥入式會議            | 點選主機上的 [新增會議] 時，有音訊會議電話號碼 | 已啟用 音訊會議                                          |
| 輸出/輸入 PSTN 通話 | 啟用Microsoft Teams 會議室主機撥打和接聽 PSTN 通話                                         | 已啟用 電話系統                                                |

如需Microsoft Teams 會議室帳戶的詳細資訊，請參閱[設定Microsoft Teams 會議室帳戶](rooms-configure-accounts.md)。


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![案例支援。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定您將支援哪些案例，並識別Microsoft Teams 會議室資源帳戶的授權需求。</li></ul>| 
| ![準備主機。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>準備託管電腦和資源帳戶。</li></ul>| 


_Microsoft Teams 會議室資源帳戶規劃資料表範例_

| **網站**  | **會議室名稱** | **會議室類型** | **未來會議室功能**                                                 | **Microsoft Teams 會議室帳戶功能**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| 倫敦 HQ | 居裡         | 中型        | 1 個螢幕、音訊和視訊加上簡報 <br>電話撥入式會議存取權<br> PSTN 存取權  | 已啟用Exchange (資源信箱)  <br>已啟用 音訊會議 <br>已啟用 電話系統 |
| 雪梨 HQ | 山          | 大型         | 2 個螢幕、音訊和視訊加上簡報<br>電話撥入式會議存取權<br> PSTN 存取權  | 已啟用 商務用 Skype <br>已啟用Exchange (資源信箱) <br> 已啟用 音訊會議 <br>已啟用 電話系統 |


### <a name="prepare-to-host-microsoft-teams-rooms-and-resource-accounts-optional"></a>準備 (選擇性) 託管Microsoft Teams 會議室和資源帳戶

若要讓您管理及報告Microsoft Teams 會議室和資源帳戶，請準備您的內部部署的 Active Directory或Azure Active Directory (Azure AD) 。 

定義內部部署的 Active Directory或Azure Active Directory群組以新增所有Microsoft Teams 會議室資源帳戶。 如果使用Azure Active Directory，請考慮使用動態群組來自群組自動新增和移除資源帳戶。

定義內部部署的 Active Directory階層中的一個組織單位，以保留所有Microsoft Teams 會議室電腦帳戶 (如果他們已加入網域) ，以及一個組織單位來保留所有Microsoft Teams 會議室使用者帳戶。 停用群組原則繼承，以確保您只套用您打算套用至加入網域Microsoft Teams 會議室的原則。

建立指派給組織單位的群組原則物件，其中包含您的Microsoft Teams 會議室電腦帳戶。 使用此功能： 

-   [設定電源和本機帳戶設定](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)。
-   啟用Windows Update。
-   啟用 PowerShell 重新模式。 您可以設定啟動腳本以執行腳本：Enable-PSRemoting -強制

您可以使用 PowerShell 來執行數個遠端系統管理活動，包括取得和設定設定資訊。 PowerShell 重新排序 *必須先啟* 用，才能進行任何 PowerShell 遠端系統管理，並且應視為部署程式的一部分，或透過群組原則設定。 如需有關這些功能並啟用這些功能的詳細資訊，請參閱 [維護和作業](rooms-operations.md#remote-management-using-powershell)。 


## <a name="configuration-and-deployment"></a>設定與部署 

設定和部署的規劃涵蓋下列重要領域：

-   資源帳戶布建
-   裝置軟體安裝
-   裝置部署
-   Microsoft Teams 會議室應用程式和周邊裝置設定
-   測試
-   資產管理

### <a name="resource-account-provisioning"></a>資源帳戶布建 

每個Microsoft Teams 會議室裝置都需要專屬且唯一的資源帳戶，Microsoft Teams或商務用 Skype都必須啟用該帳戶，Exchange。 此帳戶必須在Exchange主控會議室信箱。 行事曆處理必須設定好，裝置才能自動接受傳入的會議邀請。 如需建立這些帳戶的詳細資訊，請參閱[設定Microsoft Teams 會議室帳戶](rooms-configure-accounts.md)。 

**Pro提示**- 每個Microsoft Teams 會議室在您的網路上都必須有有效且唯一的電腦名稱稱。 許多監控和警示系統會將電腦名稱稱顯示為金鑰識別碼，因此請務必針對Microsoft Teams 會議室部署開發命名慣例，讓支援人員能夠輕鬆找到已標幟為需要採取動作的Microsoft Teams 會議室。 例如，使用 *MTR-Site* - *Room Name* (MTR-LON-CURIE) 模式。 

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![決定命名慣例。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定Microsoft Teams 會議室資源帳戶的命名慣例。</li><li>決定您要建立個別帳戶或使用大量布建腳本。</li></ul>| 
| ![後續步驟。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的裝置部署。</li></ul>| 


### <a name="device-software-installation"></a>裝置軟體安裝 

Teams 會議室是由原始設備製造商 (OEM) 預先安裝。

我們提供如何使用[Microsoft Azure 螢幕監控Microsoft Teams 會議室](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor)部署的指導方針，並報告可用性、硬體/軟體錯誤及Microsoft Teams 會議室應用程式版本。 如果您決定使用 Microsoft Operations Management Suite，您應該安裝 Operations Management Suite 代理程式做為軟體安裝程式的一部分，並為您的工作區設定工作區連線資訊。 

另一個考慮是Microsoft Teams 會議室是否會加入網域。 在設定網域加入的[群組原則](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)Microsoft Teams 會議室中，可以找到加入網域之優點的相關資訊。 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![決策點裝置命名。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定部署期間要使用的Microsoft Teams 會議室資源帳戶命名慣例。</li><li>決定是否要加入Microsoft Teams 會議室裝置到您的網域。 </li><li>決定是否要使用 Azure 監視器監視Microsoft Teams 會議室部署。</li> 
| ![後續步驟規劃裝置。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的裝置部署方法。</li></ul>| 


### <a name="device-deployment"></a>裝置部署

決定如何建立和管理Microsoft Teams 會議室資源帳戶之後，請建立計畫，將裝置及其指派的周邊裝置運送到您的會議室，然後繼續安裝和設定。


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![管理逐網站部署。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定誰將管理網站的網站部署。</li><li> 找出要在網站上安裝Microsoft Teams 會議室的資源，並負責設定和測試。</li></ul>| 
| ![啟動裝置測試。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始裝置測試。</li></ul>| 

_範例部署資料表_

| **網站**  | **會議室名稱** | **會議室類型** | **Microsoft Teams 會議室系統**  | **周邊裝置**  | **Microsoft Teams 會議室電腦名稱稱**  | **Microsoft Teams 會議室資源帳戶**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| 倫敦 HQ | 居裡         | 中型        |                                   |                  |                                          |                                             |
| 雪梨 HQ | 山          | 大型         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft Teams 會議室應用程式和周邊裝置設定 

在每個Microsoft Teams 會議室系統實際部署並連接支援的周邊裝置之後，您將需要設定Microsoft Teams 會議室應用程式，以指派Microsoft Teams 會議室資源帳戶和密碼，以便Teams 會議室登入Microsoft Teams或商務用 Skype，然後Exchange。

您可以手動設定每個Microsoft Teams 會議室系統。 或者，您可以使用集中儲存的 xML 設定檔，Teams 會議室 XML 組態檔來管理應用程式設定。

如需有關如何使用 XML 組態檔的詳細資訊，請參閱使用[XML 組態檔從遠端系統管理Microsoft Teams 會議室主機設定](xml-config-file.md)。 

您可以使用[遠端 PowerShell](rooms-operations.md#remote-management-using-powershell)來提取報告需求Microsoft Teams 會議室設定。 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![決策點設定。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定您要手動設定每個Microsoft Teams 會議室系統，還是使用中央 XML 檔案 (每個Microsoft Teams 會議室裝置) 一個。</li></ul>| 
| ![後續步驟遠端方法。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>定義您的遠端系統管理方法。</li></ul>| 

### <a name="testing"></a>測試

部署Teams 會議室之後，您應該測試。 檢查Microsoft Teams 會議室[說明](https://support.microsoft.com/en-us/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2?ui=en-us&rs=en-us&ad=us)中列出的功能是否可在已部署的裝置上運作。 我們強烈建議部署小組確認Microsoft Teams 會議室出現在Teams系統管理中心。 此外，也請務必進行數次測試通話和會議來檢查品質。 如需詳細資訊，請參閱這個 [實用的部署檢查清單](console.md#microsoft-teams-rooms-deployment-checklist)。

我們建議您在一般Teams或商務用 Skype推行中，設定「通話品質儀表板」 (CQD) 的建置檔案，監控品質趨勢，並參與體驗品質檢閱程式。 如需詳細資訊，請參閱[改善及監控Teams的通話品質](../monitor-call-quality-qos.md)。 

### <a name="asset-management"></a>資產管理

在部署中，您會想要更新資產註冊的聊天室名稱、Microsoft Teams 會議室名稱、Microsoft Teams 會議室資源帳戶，以及指派的周邊裝置。 

_資產資料表範例_

| **網站**  | **會議室名稱** | **會議室類型** | **Microsoft Teams 會議室序號。**  | **周邊裝置/序號。/ 埠**  | **Microsoft Teams 會議室電腦名稱稱**  | **Microsoft Teams 會議室服務帳戶**  | **部署日期** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| 倫敦 HQ | 居裡         | 中型        |                                          |                                          |                                          |                                            |                   |
| 雪梨 HQ | 山          | 大型         |                                          |                                          |                                          |                                            |                   |
