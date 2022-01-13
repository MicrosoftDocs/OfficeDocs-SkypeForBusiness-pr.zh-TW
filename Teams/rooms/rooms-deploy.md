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
description: 請閱讀本文，瞭解如何部署Microsoft Teams 會議室部署階段。
ms.openlocfilehash: 1f9edd4ccd2c0de00c91b99cef4f3f27b081b9ab
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015233"
---
# <a name="deployment-overview"></a>部署概觀

部署Microsoft Teams 會議室階段：

- 確認您的部署位置 (符合) 相依性
- 建立Microsoft Teams或商務用 Skype Exchange帳戶，並將這些帳戶指派Teams 會議室 (請參閱設定帳戶[Microsoft Teams 會議室) ](rooms-configure-accounts.md)
-  (為) 系統設定 Azure 監視器的選擇性 (請參閱使用 Azure 監視器部署Microsoft Teams 會議室[管理](azure-monitor-deploy.md)
- 在會議Teams 會議室中設定裝置並連接您所需的 (請參閱一組裝置之 OEM 檔) 

## <a name="site-readiness"></a>網站準備就緒 

當訂購的裝置傳送到貴組織時，請與網路、設施及 AV 小組合作，以確保符合部署相依性，且每個網站和空間在電源、網路和顯示方面已準備就緒。 此外，請確定符合實體安裝需求。 針對實體安裝考慮，請詢問您的廠商，並運用 AV 小組在安裝和安裝螢幕及執行纜線連接時的體驗。

您可以在下列規劃指南連結中，進一步瞭解這些相依性：

-   [檢查網路可用性](rooms-prep.md#check-network-availability)
-   [證書](rooms-prep.md#certificates)
-   [代理](rooms-prep.md#proxy)

**Pro提示**- 如果您必須使用 Proxy 伺服器提供存取權Teams，請首先 [閱讀本文](../proxy-servers-for-skype-for-business-online.md)。 當要處理Microsoft Teams伺服器即時媒體流量時，建議您完全忽略 Proxy 伺服器。 Microsoft Teams流量已加密，因此 Proxy 伺服器不會使其更安全，而且會為即時流量增加延遲。 在更廣泛的部署中，建議您遵循準備網路Teams以規劃頻寬，並[](../prepare-network.md)評估網路是否適合即時流量。

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![確認網站。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>確認網站符合重要需求，Microsoft Teams 會議室。</li><li>確認您為每個網站提供了足夠的頻寬。</li></ul>| 
| ![規劃裝置部署。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的裝置部署和組組。</li></ul>| 

## <a name="service-readiness"></a>服務整備

若要準備部署Microsoft Teams 會議室，請執行下列重要、集中的工作：

-   定義Microsoft Teams 會議室資源帳戶。
-   如果加入 Teams會議室Azure Active Directory，請準備Azure AD動態成員資格的群組，以保留所有 Teams 會議室 資源帳戶。 這將會簡化未來的管理，例如適用條件式 Access 原則。 若要最輕鬆地利用動態群組Azure AD，請決定一個命名慣例，以唯一識別您的Teams 會議室帳戶。
-   如果加入 Teams 會議室至 Active Directory，請準備組織單位和 Active Directory 群組以保留您的 Microsoft Teams 會議室 電腦和資源帳戶，以及準備群組原則物件 (GPO) 以啟用 PowerShell 重算。

### <a name="define-microsoft-teams-rooms-resource-account-features"></a>定義Microsoft Teams 會議室帳戶功能 

根據您決定使用 Microsoft Teams 會議室 部署啟用的共同合作案例，您必須判斷您指派給每個 Microsoft Teams 會議室的功能。

| **案例** | **描述** | **Microsoft Teams 會議室服務帳戶功能** |
|---------- |------------- | --- |
| 互動式會議            | 使用語音、視像和螢幕畫面共用;將 Microsoft Teams 會議室成為可預約的資源                     | 已針對 Microsoft Teams 或 商務用 Skype 啟用;Exchange (信箱)  |
| 電話撥入式會議            | 在主機上點一下「新會議」時，有音訊會議電話號碼 | 已啟用音訊會議                                          |
| 外發/內入 PSTN 通話 | 啟用Microsoft Teams 會議室主機撥打和接聽 PSTN 通話                                         | 已啟用電話系統                                                |

若要進一Microsoft Teams 會議室帳戶，請參閱[設定帳戶Microsoft Teams 會議室。](rooms-configure-accounts.md)


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![案例支援。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定您將支援哪些案例，並確定您資源帳戶的授權Microsoft Teams 會議室需求。</li></ul>| 
| ![準備主機。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>準備主機和資源帳戶。</li></ul>| 


_資源Microsoft Teams 會議室規劃資料表的範例_

| **網站**  | **會議室名稱** | **會議室類型** | **未來的會議室功能**                                                 | **Microsoft Teams 會議室帳戶功能**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| 倫敦總部 | 居裡         | 中型        | 1 個螢幕、音訊和視音訊加簡報 <br>電話撥入式會議存取<br> PSTN 存取  | 已啟用資源Exchange (信箱)  <br>已啟用音訊會議 <br>已啟用電話系統 |
| 雪梨總部 | 山          | 大型         | 2 螢幕、音訊和視像加簡報<br>電話撥入式會議存取<br> PSTN 存取  | 已啟用商務用 Skype <br>已啟用資源Exchange (信箱) <br> 已啟用音訊會議 <br>已啟用電話系統 |


### <a name="prepare-to-host-microsoft-teams-rooms-and-resource-accounts-optional"></a>準備託管Microsoft Teams 會議室資源帳戶 (選項) 

若要啟用管理及報告您的 Microsoft Teams 會議室 和資源帳戶，請準備您的內部部署 Active Directory 或 Azure Active Directory (Azure AD) 。 

定義內部部署 Active Directory 或 Azure Active Directory群組，以新增Microsoft Teams 會議室資源帳戶。 如果您使用 Azure Active Directory，請考慮使用動態群組來自動新增和移除群組中的資源帳戶。

在內部部署 Active Directory 階層中定義一個組織單位，以保留所有 Microsoft Teams 會議室 電腦帳戶 (如果他們已加入網域) ，以及一個組織單位來保留所有 Microsoft Teams 會議室 使用者帳戶。 停用群組原則繼承，以確保您只將您打算適用于已加入網域Microsoft Teams 會議室。

建立指派給包含您帳戶之組織單位的群組原則Microsoft Teams 會議室物件。 請使用這個功能： 

-   [設定 Power 和 Local 帳戶設定](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)。
-   啟用Windows更新。
-   啟用 PowerShell 重處理。 您可以設定啟動腳本以執行腳本：Enable-PSRemoting -Force

您可以使用 PowerShell 來執行數個遠端系統管理活動，包括取得和設定設定資訊。 PowerShell 遠端系統管理必須先啟用，才能進行任何 PowerShell 遠端系統管理，並視為部署程式或透過群組原則進行配置的一部分。 有關這些功能及啟用這些功能的資訊，請參閱 [維護與作業](rooms-operations.md#remote-management-using-powershell)。 


## <a name="configuration-and-deployment"></a>組配置與部署 

組配置與部署規劃涵蓋下列主要領域：

-   資源帳戶資源配置
-   裝置軟體安裝
-   裝置部署
-   Microsoft Teams 會議室應用程式和周邊裝置組
-   測試
-   資產管理

### <a name="resource-account-provisioning"></a>資源帳戶資源配置 

每個Microsoft Teams 會議室裝置都需要一個專用且唯一的資源帳戶，且必須同時為 Microsoft Teams 或 商務用 Skype 啟用Exchange。 此帳戶必須在 Exchange。 必須配置處理日曆，讓裝置能夠自動接受傳入的會議邀請。 有關建立這些帳戶的資訊，請參閱[設定帳戶Microsoft Teams 會議室。](rooms-configure-accounts.md) 

**Pro提示**- Microsoft Teams 會議室網路上必須有有效且唯一的機器名稱。 許多監控和警示系統將電腦名稱稱顯示為金鑰識別碼，因此必須針對 Microsoft Teams 會議室 部署開發命名慣例，讓支援人員輕鬆找到已標為需要動作的 Microsoft Teams 會議室。 範例可能是使用一種模式，即使用一種由一種模式所建立 - ** (-LON-CURIE) 。 

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![決定命名慣例。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定您資源帳戶的命名Microsoft Teams 會議室慣例。</li><li>決定是否要建立個別帳戶或使用大量置備腳本。</li></ul>| 
| ![下一個步驟。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的裝置部署。</li></ul>| 


### <a name="device-software-installation"></a>裝置軟體安裝 

Teams 會議室原始設備製造商或 OEM (預) 。

我們提供有關如何使用監視器Microsoft Azure監控部署[](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor)Microsoft Teams 會議室，並報告可用性、硬體/軟體錯誤，以及Microsoft Teams 會議室版本。 如果您決定使用 Microsoft Operations Management Suite，您應該在軟體安裝過程中安裝營運管理套件代理程式，並設定工作區的工作區連接資訊。 

另一個考慮是Microsoft Teams 會議室是否加入網域。 有關網域加入優點的資訊，請參閱為[Microsoft Teams 會議室。](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms) 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![決策點裝置命名。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定Microsoft Teams 會議室部署期間使用的資源帳戶命名慣例。</li><li>決定是否要將裝置Microsoft Teams 會議室網域。 </li><li>決定是否要使用 Azure 監視器來監控Microsoft Teams 會議室部署。</li> 
| ![下一個步驟方案裝置。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的裝置部署方法。</li></ul>| 


### <a name="device-deployment"></a>裝置部署

決定如何建立及管理您的 Microsoft Teams 會議室 資源帳戶之後，請建立您的方案，將裝置及其指派的周邊設備出貨到您的會議室，然後繼續進行安裝和配置。


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![管理網站部署。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定誰將管理網站部署。</li><li> 找出將安裝網站Microsoft Teams 會議室資源，並承擔組組和測試。</li></ul>| 
| ![啟動裝置測試。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始裝置測試。</li></ul>| 

_範例部署資料表_

| **網站**  | **會議室名稱** | **會議室類型** | **Microsoft Teams 會議室系統**  | **周邊裝置**  | **Microsoft Teams 會議室電腦名稱稱**  | **Microsoft Teams 會議室資源帳戶**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| 倫敦總部 | 居裡         | 中型        |                                   |                  |                                          |                                             |
| 雪梨總部 | 山          | 大型         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft Teams 會議室應用程式和周邊裝置組 

每個 Microsoft Teams 會議室 系統已實際部署並連接支援的周邊裝置之後，您必須設定 Microsoft Teams 會議室 應用程式來指派 Microsoft Teams 會議室 資源帳戶和密碼，才能啟用 Teams 會議室 以登錄Microsoft Teams或商務用 Skype，然後Exchange。

您可以手動設定每個Microsoft Teams 會議室系統。 或者，您可以使用集中儲存的 xml 設定檔Teams 會議室管理應用程式設定。

若要瞭解如何使用 XML 設定檔，請參閱使用 XML 組Microsoft Teams 會議室遠端系統管理主機[設定](xml-config-file.md)。 

您可以使用遠端[PowerShell](rooms-operations.md#remote-management-using-powershell)來針對報告需求Microsoft Teams 會議室資料配置。 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![決策點設定。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定是否要手動設定每個Microsoft Teams 會議室，或使用每個裝置 (一個Microsoft Teams 會議室 XML) 。</li></ul>| 
| ![下一個步驟遠端方法。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>定義遠端系統管理方法。</li></ul>| 

### <a name="testing"></a>測試

部署Teams 會議室之後，您應該測試它。 檢查已部署Microsoft Teams 會議室[中所列的](https://support.microsoft.com/en-us/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2?ui=en-us&rs=en-us&ad=us)功能是否可正常使用。 我們強烈建議部署小組確認系統Microsoft Teams 會議室系統管理中心Teams顯示。 您還必須進行數次測試通話和會議，以檢查品質。 詳細資訊，請參閱此 [實用的部署檢查清單](console.md#microsoft-teams-rooms-deployment-checklist)。

我們建議您在一般 Teams 或 商務用 Skype 推出時，設定通話品質儀表板 (CQD) 的建庫檔案、監控品質趨勢，以及參與體驗品質檢閱程式。 詳細資訊，請參閱改善及[監控通話品質Teams。](../monitor-call-quality-qos.md) 

### <a name="asset-management"></a>資產管理

在部署中，您想要使用會議室名稱、Microsoft Teams 會議室名稱、Microsoft Teams 會議室帳戶和指派的周邊裝置來更新資產註冊。 

_範例資產資料表_

| **網站**  | **會議室名稱** | **會議室類型** | **Microsoft Teams 會議室序號。**  | **周邊裝置/串口編號/埠**  | **Microsoft Teams 會議室電腦名稱稱**  | **Microsoft Teams 會議室服務帳戶**  | **部署日期** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| 倫敦總部 | 居裡         | 中型        |                                          |                                          |                                          |                                            |                   |
| 雪梨總部 | 山          | 大型         |                                          |                                          |                                          |                                            |                   |
