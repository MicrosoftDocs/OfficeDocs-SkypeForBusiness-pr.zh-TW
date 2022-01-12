---
title: 使用通話方案檢查Teams 電話網際網路連接
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f28350c2ae0487ed62d55bbd99d6a731a7bfac0
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766916"
---
# <a name="check-your-internet-connection-for-teams-phone"></a>檢查您的網際網路Teams 電話

Teams 電話 Microsoft 的技術，可于雲端Microsoft Teams內Microsoft 365功能。 每個使用Microsoft Teams Teams 電話裝置都需要網際網路連接。

若要獲得最佳Teams 電話，您需要寬頻網際網路連接，可支援貴組織可能隨時撥打的電話上限。 您也需要確定網路上的電腦可以與Microsoft 365聯繫。

您不需要授權Teams 電話執行這些步驟。

## <a name="check-your-internet-connection-speed"></a>檢查網際網路連線速度

本文可協助判斷您的網際網路連線速度是否夠快，適合需要撥打電話的人。 您將提供有關貴組織的資訊，並取得一份報表，其中顯示您的網際網路連接會由Teams Teams 電話。

### <a name="gather-information-about-your-internet-connection-and-users"></a>收集您的網際網路連接和使用者相關資訊

開始之前，您需要下列資訊：

* 網際網路連接的速度
* 有多少人會使用您的Teams 電話主要來自您的辦公室
* 主要從遠端Teams 電話，例如家用辦公室使用

### <a name="enter-your-information-into-the-network-planner"></a>將您的資訊輸入網路規劃中心

請遵循下列步驟：

1. 在瀏覽器中，前往 [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com) 。 使用具備全域系統管理員權限的帳戶登入。 您用來註冊 Microsoft 365 或 Office 365 的帳戶具備這些權限。
2. 開啟 **[規劃]**，並選取 **[網路規劃中心]**。
3. 在 **[網路規劃]** 底下，選取 **[新增]**。 為您的規劃輸入名稱，然後選取 **[套用]**。
4. 選取網路規劃名稱。
5. 在下一頁，於 **[網站]** 索引標籤底下選取 **[新增網路站台]**。
6. 填寫網路網站 **名稱**、 **網路使用者** 和 **網際網路連結容量欄位** ，然後選取 **儲存**。 讓這個畫面上的其他欄位保留空白，且不要選取 **[ExpressRoute]** 或 **[連線至 WAN]** 選項。
7. 在 **[報告]** 索引標籤，選取 **[開始報告]**。
8. 輸入 **報表名稱，** 以及網路使用者 (Office遠端) ，然後選取產生報表以建立報表，顯示 Teams。   我們將在下一節中告訴您如何閱讀報告。

### <a name="find-your-minimum-internet-connection-speed"></a>尋找最低網際網路連線速度

當您選取產生 **報表** 時，Microsoft 365或Office 365建立報表。

此數位 **會顯示** 您的網際網路Office 365欄和Teams Teams 電話。 我們建議您此數位不超過您網際網路總連線速度的 30%。 例如，如果您的網際網路連接是 *60 Mbps，Teams* Teams 電話使用不超過 *18 Mbps*。

使用此等式來判斷您的最低網際網路連線速度：<*影響> / 0.3*。  

假設影響數位是 *4.6875 Mbps。* 尋找最低網際網路連線速度的計算為 *4.6875 / 0.3 = 15.6*。 在這種情況下，網際網路連線速度至少應為 *15.6Mbps*。

如果Teams Teams 電話超過網際網路總連線速度的 30%，則 **影響號碼會顯示** 為紅色。 在這種情況下，您可能需要升級網際網路連接。

![連線速度警告。](../media/network-planner-report-speed-warning.png)

>[!NOTE]
> 網路規劃工具所提供的頻寬影響只是預估值。 建議您使用通話[品質儀表板](../cqd-what-is-call-quality-dashboard.md)，主動監控與組織內部人員進行音訊Microsoft Teams通話的使用者體驗。

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>確定您網路上的電腦和裝置能夠連線至 Microsoft 365

使用網路的電腦Teams 電話必須使用特定的網路埠來與Microsoft 365通訊。 這些埠基本上就是裝置透過網路或網際網路彼此交談的門。 您的防火牆需要允許您網路上的裝置透過下列 *輸出* 網路連接埠來連線至 Microsoft 365：

* **TCP 連接埠** 80 和 443
* **UDP 連接埠** 3478、3479、3480 和 3481

檢查防火牆是否允許在這些網路埠上通訊最簡單的方法是使用 Microsoft 365[網路](/microsoft-365/enterprise/office-365-network-mac-perf-onboarding-tool)連接工具，從您想要測試的辦公室位置執行連接測試。 完成測試後，請確認結果和建議。
