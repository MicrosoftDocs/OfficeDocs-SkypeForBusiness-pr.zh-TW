---
title: 在 Android 上部署 Microsoft Teams 會議室
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
description: 請閱讀本文以瞭解在 Android 上部署 Microsoft Teams 會議室。
ms.openlocfilehash: bb02ff59eb473d0db276fd773e9f1ff3f1ae0007
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875003"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>在 Android 上部署 Microsoft Teams 會議室

Android 版 Microsoft Teams 會議室的部署可以分成下列階段：

- **網站準備就緒** 確認您的會議室 (位置) 部署需求。
- **服務就緒** 建立資源帳戶並指派給裝置 (請參閱使用 [Microsoft 365](resource-account-ui.md) 系統管理中心建立資源) 。 雖然我們建議您使用專用會議室授權，但擁有適當授權的使用者帳戶也可以登錄 Android 上的 Teams 會議室。
- **組配置與部署** 設定 Teams 會議室並連接您需要的 (請參閱製造商的檔，以) 。

若要管理 Teams 會議室，您必須是全域系統管理員、Teams 服務系統管理員或 Teams 裝置系統管理員。有關系統管理員角色的資訊，請參閱使用 [Microsoft Teams 系統管理員角色來管理 Teams](../using-admin-roles.md)。

## <a name="site-readiness"></a>網站準備就緒

當訂購的裝置傳送給貴組織時，請與網路、設施及音訊-視覺小組合作，以確保符合部署需求，且每個網站和會議室在電源、網路和顯示方面已準備就緒。

我們針對共同合作欄網站的建議為：

- 會議室大小最多 5 人
- 專用資源帳戶
- 啟用觸控功能的顯示器
- 乙太網路纜線連接
- Microsoft Teams 媒體 (網路上) QoS 的服務品質

針對實體安裝考慮，請參閱製造商的檔，如果您有相關檔，請利用音訊-視覺小組的經驗，然後再安裝及安裝螢幕，然後執行纜線連接。

> [!TIP]
> 請務必查看為 [Teams](../prepare-network.md) 準備您的網路以規劃頻寬，並評估您的網路是否適合即時流量。
>
> 我們不建議您在 Teams 裝置與網際網路之間放置 Proxy 伺服器。 有關 Proxy 伺服器和 Teams 的資訊，請參閱 [Teams 的 Proxy 伺服器](../proxy-servers-for-skype-for-business-online.md)。

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>確認您的網站符合 Microsoft Teams 共同合作條的網站就緒需求。</li><li>確認您為每個網站提供了足夠的頻寬。</li></ul>|
| ![描述下一個步驟的圖示](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的共同資料條部署和組組。</li></ul>|

## <a name="service-readiness"></a>服務整備

部署 Teams 會議室之前，您必須決定是否要使用 Microsoft 365 資源帳戶、使用者帳戶，或兩者混合使用。 Microsoft 365 資源帳戶是專用於特定資源的信箱和 Teams 帳戶，例如會議室、投影機等。 這些資源帳戶可以使用您建立會議邀請時定義的規則，自動回應會議邀請。 除非 Teams 會議室專門供特定個人私人使用，否則我們建議您為它設定 Microsoft 365 資源帳戶。

### <a name="using-a-resource-account"></a>使用資源帳戶

如果您決定設定 Microsoft 365 資源帳戶，您必須購買會議室授權。 會議室授權包含資源信箱，可讓貴組織人員透過 Outlook 或 Teams 預約會議室。 授權也會啟用視音訊會議，以及會議參與者之間的螢幕共用。

如果您需要接聽或撥打外部電話號碼，您可能需要通話方案或 Microsoft 365 商務語音 [附加元件授權](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business)。 如果您的組織中已啟用直接路由，則只需要會議室 SKU。

當您建立資源帳戶時，您可以選擇是否要讓帳戶自動接受或拒絕會議邀請、允許週期性會議、指定人員可以預先預約資源多遠等等。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

有關 Microsoft 365 資源帳戶的資訊，請參閱使用 [Microsoft 365](resource-account-ui.md)系統管理中心建立資源帳戶 。

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定是否要撥打或接聽外部電話，並確定資源帳戶的授權需求。</li></ul>|
| ![描述下一個步驟的圖示](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>準備資源帳戶。</li></ul>|

## <a name="configuration-and-deployment"></a>組配置與部署

組配置與部署規劃涵蓋下列主要領域：

- 資源帳戶資源配置
- 裝置部署
- Teams 會議室應用程式和周邊裝置組
- 測試
- 資產管理

### <a name="account-provisioning"></a>帳戶資源配置

如果您打算使用 Microsoft 365 資源帳戶讓使用者預約共同合作橫條圖，請遵循使用 [Microsoft 365](resource-account-ui.md) 系統管理中心建立資源帳戶中的指示，為每個需要共同合作欄的 Microsoft 365 資源帳戶建立一個 Microsoft 365 資源帳戶。 這也是您需要在資源帳戶新增會議室授權的地方，如果您想要撥打或接聽來自外部電話號碼的通話，請加入通話方案或商務語音授權，如果貴組織並未使用直接路由。

如果您想要將 Teams 會議室指派給個別使用者供其私人使用，則不需要設定任何其他帳戶。 使用者可以使用個人帳戶來登錄共同合作橫條圖。

> [!TIP]
> 讓 Microsoft 365 資源帳戶的顯示名稱具有描述性且容易理解。 這些是使用者在搜尋和新增 Teams 會議室至會議時會看到的名稱。 您可以使用網站會議室名稱 (最大會議室容量) 等慣例，例如倫敦 4 人會議室的 Curie，其顯示名稱為 - ** LON-CURIE (4) 。 

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定專屬資源帳戶的命名慣例。</li><li>決定是否要建立個別帳戶或使用大量置備腳本。</li></ul>|
| ![描述下一個步驟的圖示](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始規劃您的裝置部署。</li></ul>|

### <a name="device-deployment"></a>裝置部署

接下來，您需要建立方案，將裝置及其指派的周邊裝置傳送至您的會議室，然後繼續進行安裝和安裝。

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](../media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定誰將管理網站部署。</li><li> 找出將現場安裝 Teams 會議室的資源，並負責進行組組和測試。</li></ul>|
| ![描述下一個步驟的圖示](../media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>開始裝置測試。</li></ul>|

### <a name="testing"></a>測試

部署 Teams 會議室之後，您應該測試它們。 請登錄 Teams 會議室，並檢查預期功能是否正常。 我們強烈建議您確認它們會顯示在 Microsoft Teams 系統管理中心的裝置標籤下的共同合作列區段。 您還必須進行數次測試通話和會議，以檢查品質與績效。

我們建議您在 Microsoft Teams 的一般推出中，設定通話品質儀表板 (CQD) 的建建檔案、監控品質趨勢，以及參與體驗品質檢閱程式。 詳細資訊，請參閱體驗 [品質檢閱指南](https://aka.ms/qerguide)。

### <a name="asset-management"></a>資產管理

在部署中，您想要使用會議室名稱、已登錄的資源帳戶和指派的周邊裝置來更新資產註冊。

## <a name="related-topics"></a>相關主題

[使用 Microsoft Teams 系統管理中心設定 Microsoft Teams 會議室的帳戶](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
