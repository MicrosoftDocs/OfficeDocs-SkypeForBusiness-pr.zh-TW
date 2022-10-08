---
title: 檢查 Teams Phone System 的網際網路連線
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: 檢查您的網際網路是否已準備好使用 Teams Phone System
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 7cef6f8b9a3bfa6aa99fe342f8d1abf66f7c6594
ms.sourcegitcommit: fc87f4300f53abf7a049936944abb21d0cade0d9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2022
ms.locfileid: "68480933"
---
# <a name="check-your-internet-connection-for-teams-phone-system"></a>檢查 Teams Phone System 的網際網路連線

Teams Phone System 是 Microsoft 的技術，可在 Microsoft Teams 中使用 Microsoft 365 雲端啟用手機功能。 使用 Microsoft Teams 和手機系統的每個裝置都需要連線到網際網路。

若要獲得最佳的電話系統體驗，您需要寬頻網際網路連線，以支援貴組織可隨時撥打的最大通話數目。 您也必須確定您網路上的電腦可以連線到 Microsoft 365 服務。

## <a name="check-your-internet-connection-speed"></a>檢查您的網際網路連線速度

本文可協助判斷您的網際網路連線是否夠快，以容納需要撥打電話的人數。 您將提供組織的相關資訊，並取回一份報告，顯示 Teams 和電話系統將使用多少網際網路連線。

### <a name="gather-information-about-your-internet-connection-and-users"></a>收集您的網際網路連線和使用者的相關資訊

開始之前，您需要下列資訊：

* 網際網路連線的速度
* 有多少人主要從您的辦公室使用電話系統
* 有多少人主要從遠端位置使用電話系統，例如家庭辦公室

### <a name="enter-your-information-into-the-network-planner"></a>將您的資訊輸入網路規劃中心

請遵循下列步驟：

1. 在瀏覽器中，移至 [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com) 。 使用具備全域系統管理員權限的帳戶登入。 您用來註冊 Microsoft 365 的帳戶具有這些許可權。
2. 開啟 **[規劃]**，並選取 **[網路規劃中心]**。
3. 在 **[網路規劃]** 底下，選取 **[新增]**。 為您的規劃輸入名稱，然後選取 **[套用]**。
4. 選取網路規劃名稱。
5. 在下一頁，於 **[網站]** 索引標籤底下選取 **[新增網路站台]**。
6. 填寫 **[網路] 網站名稱**、[ **網路使用者**] 和 [ **網際網路連結] 容量** 欄位，然後選取 [ **儲存]**。 讓這個畫面上的其他欄位保留空白，且不要選取 **[ExpressRoute]** 或 **[連線至 WAN]** 選項。
7. 在 **[報告]** 索引標籤，選取 **[開始報告]**。
8. 在 **[報告名稱**] 及 [Office **] 和 [****遠端**)  (**的網路使用者** 數目中輸入，然後選取 [**產生報** 表] 以建立顯示 Teams 頻寬需求的報告。 我們會告訴您如何在下一節閱讀報告。

### <a name="find-your-minimum-internet-connection-speed"></a>尋找最低網際網路連線速度

當您選取 **[產生報表**] 時，Microsoft 365 會建立報表。

在 [**影響**] 欄和 **Office 365** 列中，此數位會顯示 Teams 和手機系統將使用多少網際網路連線。 我們建議此數位不超過您網際網路總連線速度的 30%。 例如，如果您的網際網路連線為 *60 Mbps*，Teams 和手機系統應該使用不超過 *18 Mbps*。

使用此方程式來判斷最低網際網路連線速度：<*影響號碼> / 0.3*。  

假設 [影響] 數位為 *4.6875 Mbps*。 尋找最低網際網路連線速度的計算方式是 *4.6875 / 0.3 = 15.6*。 在此情況下，網際網路連線速度至少應為 *15.6 Mbps*。

如果 Teams 和手機系統會使用超過您網際網路總連線速度的 30%， **影響** 號碼會顯示為紅色。 在這種情況下，您可能需要升級網際網路連線。

![連線速度警告。](../media/network-planner-report-speed-warning.png)

>[!NOTE]
> Network Planner 提供的頻寬影響僅為估計值。 建議您使用 [通話品質儀表板](../cqd-what-is-call-quality-dashboard.md) ，在組織內部使用 Microsoft Teams 主動監控使用者的音訊和視訊通話體驗。

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>確定您網路上的電腦和裝置能夠連線至 Microsoft 365

使用電話系統的電腦和裝置必須使用特定的網路埠，才能與 Microsoft 365 服務通訊。 這些埠基本上是裝置透過網路或網際網路互相交談的門。 您的防火牆需要允許您網路上的裝置透過下列 *輸出* 網路連接埠來連線至 Microsoft 365：

* **TCP 連接埠** 80 和 443
* **UDP 連接埠** 3478、3479、3480 和 3481

檢查防火牆是否允許在這些網路埠上進行通訊的最簡單方式，就是使用 [Microsoft 365 網路連線工具](/microsoft-365/enterprise/office-365-network-mac-perf-onboarding-tool) ，從您要測試的辦公室執行連線測試。 完成測試後，確認結果和建議。
