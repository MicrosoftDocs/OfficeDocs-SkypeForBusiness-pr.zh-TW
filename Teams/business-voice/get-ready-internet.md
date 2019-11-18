---
title: 檢查您的網際網路連線
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19f26c0bd7ab4fe89770909d81d60abc97aaa8b0
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653549"
---
# <a name="check-your-internet-connection"></a>檢查您的網際網路連線

Business Voice 位於 Microsoft 365 的雲端中。 使用 Microsoft Teams 和 Business Voice 的每一部電腦和裝置都需要連線至網際網路。 若要獲得 Business Voice 的最佳體驗，您需要可支援每次撥打預期的電話數量所需的寬頻網際網路連線。 您也需要確定您網路上的電腦能夠連線至 Microsoft 365 伺服器。

若要執行這些步驟，您必須有具備下列其中一項訂閱的租用戶：

* Office 365 商務基本版
* Office 365 商務進階版
* Office 365 E1
* Office 365 E3
* Office 365 F1
* Microsoft 365 A1
* Microsoft 365 A3
* Microsoft 365 E3
* Microsoft 365 商務版

您不需要 Business Voice 授權就可以執行這些步驟。

## <a name="check-your-internet-connection-speed"></a>檢查您的網際網路連線速度

本文可協助判斷您的網際網路連線速度，對於撥打電話、主持視訊會議等等所需的人數來說是否足夠快。 您會輸入一些關於組織的資訊，並取得 Teams 和 Business Voice 將使用您的網際網路連線量的報告。

### <a name="get-information-about-your-internet-connection-and-users"></a>取得有關您的網際網路連線和使用者的資訊

開始之前，您需要知道下列資訊：

* 您的網際網路連線速度。
* 將主要透過您的辦公室使用 Business Voice 的人數。
* 將主要透過遠端位置 (例如家庭辦公室) 使用 Business Voice 的人數。

### <a name="enter-your-information-into-the-network-planner"></a>將您的資訊輸入網路規劃中心

以下是您需要執行的操作：

1. 開啟瀏覽器，然後移至 https://admin.teams.microsoft.com，並使用具備全域系統管理員權限的帳戶登入。 您用來註冊 Office 365 的帳戶具備這些權限。
1. 開啟 [規劃]**** 然後選取 [網路規劃中心]****。
1. 在 [網路規劃]**** 底下，選取 [新增]****。 為您的規劃命名，然後選取 [套用]****。 您的網路規劃應看起來如下：

    ![網路規劃中心主畫面](../media/network-planner-main.png)
1. 按一下您的網路規劃名稱 (上圖中的**主辦公室**)。
1. 在下一頁上，於 [網站]**** 索引標籤底下選取 [新增網路站台]****。
1. 只填寫以下螢幕擷取畫面中所指定的欄位，然後選取 [儲存] ****。 讓這個畫面上的其他欄位保留空白，且不要選取 [ExpressRoute]**** 或 [連線至 WAN]**** 選項。

    ![網路規劃中心網站資訊](../media/network-planner-site-info.png)
1. 在 [報告]**** 索引標籤下，選取 [開始報告]****。
1. 填寫下列資訊，然後選取 [產生報告]****，以建立顯示 Teams 頻寬需求的報告。 我們會在下一節中示範如何顯示報告。

    ![網路規劃中心報告資訊](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a>找到您的最低網際網路連線速度

選取 [產生報告]**** 時，Office 365 會建立一個看起來如下的報告：

![網路規劃中心報告詳細資料](../media/network-planner-report.png)

強調顯示的數字會顯示 Teams 和 Business Voice 使用您的網際網路連線量。 建議這個數字不要超過網際網路連線速度總計的 30%。 例如，如果您的網際網路連線是60 Mbps，則 Teams 和 Business Voice 不應佔用超過 18 Mbps。

您可以執行以下計算來找出您的最低網際網路連線速度：`<highlighted number> / .3`。 使用上圖中強調顯示的數字，此計算會是 `4.6875 / .3 = 15.6`。 這表示您的最低網際網路連線速度必須至少為 15.6 Mbps。

如果 Teams 和 Business Voice 將使用超過網際網路連線速度總計的 30%，則強調顯示的數字會以紅色顯示。 如果發生這種情況，您可能需要將網際網路連線升級。

![連線速度警告](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>確定您網路上的電腦和裝置能夠連線 Microsoft 365

若要正常運作，您要搭配 Business Voice 使用的電腦和裝置必須使用特定網路連接埠與 Microsoft 365 伺服器通訊。 網路連接埠本質上是門戶，電腦和裝置可以經由它透過網路或網際網路彼此交談。 您的防火牆需要允許您網路上的電腦和裝置能夠使用下列輸出網路連接埠來連線 Microsoft 365：

* **TCP 連接埠** 80 和 443
* **UDP 連接埠** 3478、3479、3480 和 3481

檢查您的防火牆是否允許網路連接埠通訊的最簡單方法是使用 Teams 進行測試通話。 若要進行測試通話，請執行下列動作：

1. 在您網路的電腦上移至 https://aka.ms/getteams，以安裝 Teams。 確定喇叭和麥克風已連線至此電腦。
2. 使用 Microsoft 365 帳戶開啟 Teams 並登入
3. 在 Teams 中，選取您的個人檔案圖片，然後選取 [設定]****  >  [裝置]****
4. 選擇 [音訊裝置]**** 下的 [音訊裝置]****
5. 遵循提示留下訊息並讓訊息向您播放

* 如果通話可連線，且您可以聽見您的訊息向您播放，您的防火牆即已正確設定。
* 如果通話可連線，但您無法聽見提示或聽見您的訊息向您播放，請確定您的喇叭和麥克風已正確設定，且電腦可以偵測到。 請再試一次。
* 如果通話未連線，或如果通話可連線但您無法聽見您的訊息向您播放，則可能需要更新您的防火牆，以允許以上所列的網路連接埠。 查看您的防火牆文件，了解如何允許網路連接埠連線網際網路，或與 IT 專家連絡以協助您。

如果您是 IT 專業人員，想要深入了解如何準備更大型或更複雜的網路來支援 Business Voice 的資訊，請參閱[評估我的環境](../3-envision-evaluate-my-environment.md)。 [評估我的環境](../3-envision-evaluate-my-environment.md)文章提供關於頻寬、Proxy 和防火牆需求，以及如何使用[網路評估工具](../3-envision-evaluate-my-environment.md#test-the-network)測試網路的更多資訊。
