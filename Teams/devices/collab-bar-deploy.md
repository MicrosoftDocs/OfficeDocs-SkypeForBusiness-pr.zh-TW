---
title: 在 Android 上部署Microsoft Teams 會議室
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 請閱讀本文以瞭解如何在 Android 上部署Microsoft Teams 會議室。
ms.openlocfilehash: 52b865879db3941b5631d7b22c25bd8f6e4d3ce6
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438411"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>在 Android 上部署Microsoft Teams 會議室

在 Android 上部署Microsoft Teams 會議室可以分成下列階段：

- **網站整備** 確認您的部署位置 (會議室) 符合部署需求。
- **服務整備** 建立資源帳戶並將它們指派給裝置 (請參 [閱使用Microsoft 365 系統管理中心) 建立資源帳戶](resource-account-ui.md)。 雖然我們建議使用專用的會議室授權，但擁有適當授權的使用者帳戶也可以在 Android 上登入Teams 會議室。
- **設定與部署** 設定Teams 會議室並連接您需要的周邊裝置， (查看製造商的檔以取得詳細資料) 。

若要管理Teams 會議室，您必須是全域系統管理員、Teams 服務系統管理員或 Teams 裝置系統管理員。如需系統管理員角色的詳細資訊，請參[閱使用 Microsoft Teams 系統管理員角色來管理 Teams](../using-admin-roles.md)。

## <a name="site-readiness"></a>網站整備

當已訂購的裝置傳遞給貴組織時，請與您的網路、設施和音訊視覺小組合作，以確保符合部署需求，而且在電源、網路和顯示方面，每個網站和會議室都已準備就緒。

我們在 Android 網站上Teams 會議室的建議如下：

- 最多 5 人大小的會議室
- 專用資源帳戶
- 啟用觸控功能的顯示器
- 乙太網路分機
- 在網路上針對 Microsoft Teams 媒體啟用的服務品質 (QoS) 

如需實際安裝考慮，請參閱製造商的檔，如果有的話，請先利用音訊視覺小組的體驗，再安裝和掛接螢幕並執行分機。

> [!TIP]
> 請務必查看 [準備 Teams 的網路，](../prepare-network.md) 以進行頻寬規劃，並評估網路是否適合即時流量。
>
> 我們不建議在 Teams 裝置和網際網路之間放置 Proxy 伺服器。 如需 Proxy 伺服器和 Teams 的詳細資訊，請參閱 [Teams 的 Proxy 伺服器](../proxy-servers-for-skype-for-business-online.md)。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![描繪決策點的圖示。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>確認您的網站符合 Android 上Teams 會議室的網站整備需求。</li><li>確認您已為每個網站提供足夠的頻寬。</li></ul>|
| ![描述後續步驟的圖示。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始在 Android 部署和設定上規劃您的Teams 會議室。</li></ul>|

## <a name="service-readiness"></a>服務整備

部署Teams 會議室之前，您必須先決定這些帳戶是否要使用 Microsoft 365 資源帳戶、使用者帳戶或兩者混合使用。 Microsoft 365 資源帳戶是專屬於特定資源的信箱和 Teams 帳戶，例如會議室、投影機等等。 這些資源帳戶可以使用您在建立時定義的規則自動回應會議邀請。 除非Teams 會議室專用於特定個人供其私人使用，我們建議為其設定Microsoft 365 資源帳戶。

### <a name="using-a-resource-account"></a>使用資源帳戶

如果您決定設定Microsoft 365 資源帳戶，您將需要為該帳戶購買會議室授權。 會議室授權包含資源信箱，可讓貴組織中的人員透過 Outlook 或 Teams 預約會議室。 該授權也可在會議參與者之間進行視訊和音訊會議及螢幕共用。

如果您需要接收或撥打外部電話號碼或從外部電話號碼撥打電話，您可能需要通話方案或Microsoft 365 商務語音附加元件[授權](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business)。 如果您已在組織中啟用直接路由，則只需要會議室 SKU。

當您建立資源帳戶時，您可以選擇讓帳戶自動接受或拒絕會議邀請、允許週期性會議、指定人員可以提前多久預約資源等等。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

如需Microsoft 365 資源帳戶的詳細資訊，請參閱[使用Microsoft 365 系統管理中心建立資源帳戶](resource-account-ui.md)。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![描繪決策點的圖示。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定您要撥打或接聽外部電話，以及識別資源帳戶的授權需求。</li></ul>|
| ![描述後續步驟的圖示。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>準備資源帳戶。</li></ul>|

## <a name="configuration-and-deployment"></a>設定與部署

設定和部署的規劃涵蓋下列重要領域：

- 資源帳戶布建
- 裝置部署
- Teams 會議室應用程式和周邊裝置設定
- 測試
- 資產管理

### <a name="account-provisioning"></a>帳戶布建

如果您打算使用 Microsoft 365 資源帳戶讓使用者在 Android 裝置上預約Teams 會議室，請依照[使用Microsoft 365 系統管理中心建立資源帳戶](resource-account-ui.md)中的指示，針對 Android 裝置上需要的每個Teams 會議室建立Microsoft 365 資源帳戶一個。 您也需要將會議室授權新增至資源帳戶，如果您想要撥打或接聽外部電話號碼或外部電話號碼的來電，如果您的組織不是使用直接路由，請使用通話方案或商務語音授權。

如果您想要將Teams 會議室指派給個別使用者供其私人使用，則不需要設定任何其他帳戶。 使用者可以在 Android 裝置上使用個人帳戶登入Teams 會議室。

> [!TIP]
> 讓 Microsoft 365 資源帳戶的顯示名稱具有描述性且易於理解。 這些是使用者在搜尋並將Teams 會議室新增至會議時會看到的名稱。 您可以使用「*網站* - *會議室名稱*」之類的慣例 (*最大會議室容量*) ，例如，倫敦 4 人制會議室 Curie 的顯示名稱可能為 LON-CURIE (4) 。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![描繪決策點的圖示。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定專用資源帳戶的命名慣例。</li><li>決定您要建立個別帳戶或使用大量布建腳本。</li></ul>|
| ![描述後續步驟的圖示。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的裝置部署。</li></ul>|

### <a name="device-deployment"></a>裝置部署

接下來，您需要建立計畫，將裝置及其指派的周邊裝置傳送到您的會議室，然後繼續安裝和設定。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![描繪決策點的圖示。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定誰將管理網站的網站部署。</li><li> 找出要在網站上安裝Teams 會議室的資源，並負責設定和測試。</li></ul>|
| ![描述後續步驟的圖示。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始裝置測試。</li></ul>|

### <a name="testing"></a>測試

部署Teams 會議室之後，您應該測試它們。 登入Teams 會議室，並檢查預期的功能是否正常運作。 強烈建議您確認它們出現在 **Android 版 [** Teams **裝置**] 索引標籤Microsoft Teams 系統管理中心的 [Teams 會議室] 區段中。 此外，也請務必進行數次測試通話和會議，以檢查品質和效能。

我們建議您在 Teams 推出一般Microsoft中，設定「通話品質儀表板」的建置檔案 (CQD) 、監控品質趨勢，以及參與體驗品質檢閱程式。 如需詳細資訊，請參閱 [體驗品質檢閱指南](../quality-of-experience-review-guide.md)。

### <a name="asset-management"></a>資產管理

在部署中，您需要使用聊天室名稱、登入資源帳戶，以及指派的周邊裝置來更新資產註冊。

## <a name="related-topics"></a>相關主題

[建立會議室和共用 Teams 裝置的資源帳戶](../rooms/with-office-365.md)