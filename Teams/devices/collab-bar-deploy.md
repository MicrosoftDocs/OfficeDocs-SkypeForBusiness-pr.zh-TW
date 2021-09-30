---
title: 在 Android Microsoft Teams 會議室部署應用程式
ms.author: mitressl
author: flinchbot
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
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 請閱讀本文以瞭解在 Android Microsoft Teams 會議室部署應用程式。
ms.openlocfilehash: 4ac068e008b53882dceba5f4ceef6e730a47b3f3
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011707"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>在 Android Microsoft Teams 會議室部署應用程式

Android 上的 Microsoft Teams 會議室部署可以分成下列階段：

- **網站準備就緒** 確認您的會議室 (位置) 部署需求。
- **服務就緒** 建立資源帳戶並指派給裝置 (請參閱使用資源帳戶 [Microsoft 365 系統管理中心) 。](resource-account-ui.md) 雖然我們建議您使用專用聊天室授權，但擁有適當授權的使用者帳戶也可以在 Android 上Teams 會議室帳戶。
- **組組和部署** 設定Teams 會議室並連接您需要的 (請參閱製造商的檔，以) 。

若要管理Teams 會議室，您必須是全域系統管理員、Teams系統管理員，或Teams系統管理員。有關系統管理員角色的資訊，請參閱使用 Microsoft Teams[系統管理員角色來管理Teams。](../using-admin-roles.md)

## <a name="site-readiness"></a>網站準備就緒

當訂購的裝置傳送給貴組織時，請與網路、設施及音訊-視覺小組合作，以確保符合部署需求，且每個網站和會議室在電源、網路和顯示方面已準備就緒。

我們針對共同合作欄網站的建議為：

- 會議室大小最多 5 人
- 專用資源帳戶
- 啟用觸控功能的顯示器
- 乙太網路纜線連接
- 針對媒體 (啟用) QoS Microsoft Teams服務品質

針對實體安裝考慮，請參閱製造商的檔，如果您有相關檔，請利用音訊-視覺小組的經驗，然後再安裝及安裝螢幕，然後執行纜線連接。

> [!TIP]
> 請務必查看準備您的網路，Teams頻寬規劃，並評估您的網路是否適合即時流量。 [](../prepare-network.md)
>
> 我們不建議您在裝置和網際網路Teams Proxy 伺服器。 有關 Proxy 伺服器和伺服器Teams，請參閱[Proxy 伺服器Teams。](../proxy-servers-for-skype-for-business-online.md)

|&nbsp;|&nbsp;|
|-----------|------------|
| ![描繪決策點的圖示。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>確認您的網站符合共同Microsoft Teams的網站Microsoft Teams。</li><li>確認您為每個網站提供了足夠的頻寬。</li></ul>|
| ![描述下一個步驟的圖示。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的共同資料條部署和組組。</li></ul>|

## <a name="service-readiness"></a>服務整備

在部署Teams 會議室，您必須決定他們是否Microsoft 365資源帳戶、使用者帳戶，或兩者混合使用。 Microsoft 365資源帳戶為Teams專用帳戶，例如會議室、投影機等。 這些資源帳戶可以使用您建立會議邀請時定義的規則，自動回應會議邀請。 除非Teams 會議室專屬於特定個人供其私人使用，否則我們建議您為Microsoft 365設定資源帳戶。

### <a name="using-a-resource-account"></a>使用資源帳戶

如果您決定設定Microsoft 365帳戶，您必須購買會議室授權。 授權會議室資源信箱，可讓貴組織人員透過 Outlook 或 Teams。 授權也會在會議參與者之間啟用視像和音訊會議及螢幕畫面共用。

如果您需要接聽或撥打外部電話號碼，您可能需要通話方案或Microsoft 365 商務語音[附加元件授權](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business)。 如果您的組織中已啟用直接路由，則只需要會議室 SKU。

當您建立資源帳戶時，您可以選擇是否要讓帳戶自動接受或拒絕會議邀請、允許週期性會議、指定人員可以預先預約資源多遠等等。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

若要進一Microsoft 365資源帳戶，請參閱使用 Microsoft 365 系統管理中心 建立[資源Microsoft 365 系統管理中心。](resource-account-ui.md)

|&nbsp;|&nbsp;|
|-----------|------------|
| ![描繪決策點的圖示。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定是否要撥打或接聽外部電話，並確定資源帳戶的授權需求。</li></ul>|
| ![描述下一個步驟的圖示。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>準備資源帳戶。</li></ul>|

## <a name="configuration-and-deployment"></a>組配置與部署

組組和部署規劃涵蓋下列主要領域：

- 資源帳戶資源配置
- 裝置部署
- Teams 會議室應用程式和周邊裝置組
- 測試
- 資產管理

### <a name="account-provisioning"></a>帳戶資源配置

如果您打算使用 Microsoft 365 資源帳戶讓使用者預約共同合作橫條圖，請遵循使用[Microsoft 365 系統管理中心](resource-account-ui.md)建立資源帳戶中的指示，為每個需要共同Microsoft 365的協作資料組建立 Microsoft 365 資源帳戶。 這也是您需要新增 會議室 授權至資源帳戶的地方，如果您想要撥打或接聽來自外部電話號碼的通話，請加入通話方案或商務語音授權，如果貴組織並未使用直接路由。

如果您想要將帳戶Teams 會議室個別使用者供其私人使用，則不需要設定任何其他帳戶。 使用者可以使用個人帳戶來登錄共同合作橫條圖。

> [!TIP]
> 讓資源帳戶的顯示名稱Microsoft 365描述性且容易理解。 這些是使用者在搜尋及新增會議Teams 會議室的名稱。 您可以使用網站會議室名稱 (最大會議室容量) 等慣例，例如倫敦 4 人會議室的 Curie，其顯示名稱為 - ** LON-CURIE (4) 。 

|&nbsp;|&nbsp;|
|-----------|------------|
| ![描繪決策點的圖示。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定專屬資源帳戶的命名慣例。</li><li>決定是否要建立個別帳戶或使用大量置備腳本。</li></ul>|
| ![描述下一個步驟的圖示。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的裝置部署。</li></ul>|

### <a name="device-deployment"></a>裝置部署

接下來，您需要建立方案，將裝置及其指派的周邊裝置傳送至您的會議室，然後繼續進行安裝和組組。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![描繪決策點的圖示。](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定誰將管理網站部署。</li><li> 找出將安裝網站Teams 會議室資源，並承擔組組和測試。</li></ul>|
| ![描述下一個步驟的圖示。](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始裝置測試。</li></ul>|

### <a name="testing"></a>測試

部署之後，Teams 會議室測試它們。 請Teams 會議室並檢查預期功能是否正常。 強烈建議您確認它們出現在系統管理中心的 Teams **裝置** Microsoft Teams區段。 您還必須進行數次測試通話和會議，以檢查品質與績效。

我們建議您在推出一般 Microsoft Teams 時，為通話品質儀表板 (CQD) 設定建房檔案、監控品質趨勢，以及參與體驗品質檢閱程式。 詳細資訊，請參閱體驗 [品質檢閱指南](../quality-of-experience-review-guide.md)。

### <a name="asset-management"></a>資產管理

在部署中，您想要使用會議室名稱、已登錄的資源帳戶和指派的周邊裝置更新資產註冊。

## <a name="related-topics"></a>相關主題

[使用系統管理中心Microsoft Teams 會議室帳戶Microsoft Teams帳戶](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->