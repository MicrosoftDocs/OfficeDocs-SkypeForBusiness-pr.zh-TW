---
title: 為 Microsoft 團隊部署共同作業橫條圖
ms.author: mitressl
author: flinchbot
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 閱讀本文以瞭解如何針對 Microsoft 團隊部署共同作業條。
ms.openlocfilehash: 4593d6b42e61efbd7d57f27fd0a10ed8f97b82f5
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268030"
---
# <a name="deploy-collaboration-bars-for-microsoft-teams"></a>為 Microsoft 團隊部署共同作業橫條圖

Microsoft 團隊的共同作業橫條圖部署可分為下列階段：

- **網站準備**確認您的部署位置（會議室）符合部署需求。
- **服務就緒**性建立資源帳戶並將其指派給裝置（[請參閱使用 Microsoft 365 系統管理中心建立資源帳戶](resource-account-ui.md)）。 雖然我們建議使用專用的聊天室授權，但授權的最終使用者帳戶也可以登入共同作業條。
- **配置和部署**在會議室中設定共同作業橫條圖，並連接您所需的週邊裝置（請參閱您的共同作業條的製造商檔）。

## <a name="site-readiness"></a>網站準備

當訂購的裝置傳送給您的組織時，請與您的網路、設施和音訊視覺團隊共同作業，以確保符合部署需求，且每個網站和會議室都已準備好使用 power、網路及顯示器。

我們針對共同作業條網站的建議如下：

- 最多4個人員的會議室大小
- 專用資源帳戶
- 支援觸控的顯示器
- 乙太網佈線
- 在網路上為 Microsoft 團隊媒體啟用的服務品質（QoS）

如需實際安裝的考慮，請參閱製造商的檔，如果有的話，請在安裝並安裝螢幕並執行佈線前，先利用音訊視覺小組的體驗。

> [!TIP]
> 請務必參閱[準備您的網路供小組](../prepare-network.md)進行頻寬規劃，並評估您的網路對即時流量的適用性。
>
> 我們不建議您將 proxy 伺服器放在團隊裝置與網際網路之間。 如需 proxy 伺服器與團隊的詳細資訊，請參閱[小組的 proxy 伺服器](../proxy-servers-for-skype-for-business-online.md)。

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>確認您的網站符合 Microsoft 團隊共同作業列的網站準備情況需求。</li><li>確認您已為每個網站提供足夠的頻寬。</li></ul>|
| ![描述後續步驟的圖示](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的共同作業條部署與設定。</li></ul>|

## <a name="service-readiness"></a>服務就緒性

在您部署共同作業橫條圖前，您必須決定是否要使用 Microsoft 365 資源帳戶、使用者帳戶或兩者的混合。 Microsoft 365 資源帳戶是專門用於特定資源（例如房間、投影機等）的信箱和小群組帳戶。 這些資源帳戶可以使用您在建立規則時所定義的規則，自動回應會議邀請。 除非共同作業列專用於特定個人供其私人使用，否則我們建議您為它設定 Microsoft 365 資源帳戶。

### <a name="using-a-resource-account"></a>使用資源帳戶

如果您決定要設定 Microsoft 365 資源帳戶，您必須為其購買會議室授權。 [會議室授權] 包含的資源信箱可讓貴組織中的人員透過 Outlook 或團隊預訂會議室。 授權也能在會議參與者之間啟用影片和音訊會議以及螢幕共用。

如果您需要接收或撥打電話給外部電話號碼，您也需要 Microsoft 365 手機系統或 Microsoft 365 商務語音授權。

當您建立資源帳戶時，您可以選擇是否要讓帳戶自動接受或拒絕會議邀請、允許週期性會議，指定提前的人員預訂資源的進度。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

如需 Microsoft 365 資源帳戶共同作業列的詳細資訊，請參閱[使用 microsoft 365 系統管理中心建立資源帳戶](resource-account-ui.md)。

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定您要撥打或接聽外部電話，以及找出您資源帳戶的授權需求。</li></ul>|
| ![描述後續步驟的圖示](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>準備資源帳戶。</li></ul>|

## <a name="configuration-and-deployment"></a>配置和部署

規劃配置和部署涵蓋下列主要區域：

- 資源帳戶預配
- 裝置部署
- Microsoft 團隊應用程式和週邊裝置設定的共同作業條
- 正在
- 資產管理

### <a name="account-provisioning"></a>帳戶預配

如果您打算使用 Microsoft 365 資源帳戶來讓使用者預訂共同作業列，請依照[使用 microsoft 365 系統管理中心建立資源帳戶](resource-account-ui.md)中的指示，為每一個需要的共同作業列建立 Microsoft 365 資源帳戶。 您也可以將會議室授權新增至資源帳戶，如果您想要撥打或接聽外部電話號碼（電話系統或商務語音授權）撥打電話或接聽電話。

如果您想要將共同作業條指派給個別的使用者，您不需要設定任何其他帳戶。 使用者可以使用個人帳戶登入共同作業列。

> [!TIP]
> 讓您的 Microsoft 365 資源帳戶顯示名稱具描述性且易於理解。 這些是使用者在搜尋並新增 Microsoft 團隊共同作業橫條圖時所看到的名稱。 您可以使用諸如*網站* - *會議室名稱*（*最大房間容量*）等慣例，例如 Curie，倫敦的4人會議室，可能會有顯示名稱 LON-Curie （4）。

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>針對您的專用資源帳戶決定命名慣例。</li><li>決定您要建立個別帳戶或使用大量提供腳本。</li></ul>|
| ![描述後續步驟的圖示](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的裝置部署。</li></ul>|

### <a name="device-deployment"></a>裝置部署

接著，您需要建立您的方案，以將裝置及其指派的週邊裝置傳送到您的聊天室，然後繼續進行安裝與設定。

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定誰能管理網站的網站部署。</li><li> 找出將針對網站上的 Microsoft 團隊安裝共同作業橫條圖的資源，並執行設定及測試。</li></ul>|
| ![描述後續步驟的圖示](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>啟動裝置測試。</li></ul>|

### <a name="testing"></a>正在

在已部署 Microsoft 團隊的共同作業條之後，您應該測試它們。 登入裝置，並檢查所需的功能是否在已部署的裝置上運作。 我們強烈建議您確認裝置出現在 Microsoft 團隊系統管理中心的 [**裝置**] 索引標籤底下的 [共同作業**條**] 區段中。 您也必須進行一些測試通話和會議，才能檢查品質與效能。

我們建議您做為 [一般 Microsoft 團隊推出] 的一部分，您可以設定為通話品質儀表板（CQD）建立檔案、監控品質趨勢，以及參與經驗審查程式的品質。 如需詳細資訊，請參閱[體驗檢查指南的品質](https://aka.ms/qerguide)。

### <a name="asset-management"></a>資產管理

在部署過程中，您會想要使用房間名稱、登入資源帳戶和指派的週邊裝置來更新資產登記簿。

## <a name="related-topics"></a>相關主題

[使用 Microsoft 團隊系統管理中心針對 Microsoft 團隊設定共同作業橫條圖的帳戶](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
