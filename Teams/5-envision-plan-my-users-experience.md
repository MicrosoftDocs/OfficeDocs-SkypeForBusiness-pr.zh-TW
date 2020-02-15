---
title: 規劃使用者對 Microsoft 團隊的體驗
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 選擇 [團隊用戶端應用程式]，規劃端點品質，取得部署 Wi-fi 端點及選擇音訊裝置的建議。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77a325fbe8cacb3b2760f5b3034dee0e16695278
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42021594"
---
# <a name="plan-my-users-experience"></a>規劃我的使用者體驗

本文概述正確識別您的雲端語音服務部署元素的需求，這些專案會直接影響您的使用者體驗。 在部署之前先準備好這些專案，就能增加成功為使用者提供高品質、可靠體驗的機會。 

## <a name="client-deployment"></a>用戶端部署

Microsoft 團隊擁有可供 web、桌面（Windows 和 Mac）及行動裝置（Android 與 iOS）使用的用戶端。 如需如何安裝桌面（Windows 和 Mac）與行動用戶端的其他詳細資料，請參閱[取得 Microsoft 團隊的用戶端](https://docs.microsoft.com/microsoftteams/get-clients)。

## <a name="client-updates"></a>用戶端更新

團隊的其中一個主要優點是，用戶端會自動保持為最新狀態。 PC 和 Mac 上的用戶端會使用背景處理常式來更新，在 app 空閒時檢查新的組建並下載新的用戶端。

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>規劃端點品質

在下圖中您可以看到，端點是提供使用者品質體驗的重要組建區塊。

![描述三個品質元件的圖表](media/plan-my-users-experience-image1.png "描述三個品質元件的圖表，以及服務管理如何與所有三個元件重迭。將焦點放在端點上。")

團隊端點可以在許多裝置上執行，包括 Pc、Mac、平板電腦和行動裝置。 部分體驗不僅包括裝置，而且使用者如何連線到裝置，例如使用裝置內建的麥克風/喇叭、earbuds 或優化的耳機。 使用優化的耳機可豐富整體使用者體驗。

下列針對端點規劃的指導方針可協助您確保貴組織成功地使用團隊加入了您的組織。

## <a name="endpoint-capability"></a>端點功能

規劃中的第一個部分是確保貴組織中的所有電腦和其他裝置都能執行團隊。 這涉及不只是查看硬體需求，還需要瞭解電腦在背景執行的其他動作。 許多組織會執行其他軟體，包括入侵偵測系統和反惡意程式碼，這可能會影響裝置的基本效能。

如需每個平臺（網頁、桌面及行動裝置）上團隊用戶端軟體需求的相關資訊，請參閱[取得 Microsoft 團隊的用戶端](https://docs.microsoft.com/microsoftteams/get-clients)。

## <a name="endpoint-firewalls"></a>端點防火牆

用戶端防火牆對使用者體驗的影響可能會有很大的影響。
用戶端防火牆可能會影響通話品質，除了可防止通話的建立。 根據[Office 365 url 和 IP 位址範圍](https://aka.ms/o365ips)中的資訊，在用戶端防火牆上設定適當的排除。 您的協力廠商廠商將提供有關如何建立排除項的特定指導方針。

>[!NOTE]
> Microsoft 團隊會自動使用適當的防火牆設定來更新 Windows 防火牆。

## <a name="wi-fi-recommendations-for-endpoints"></a>端點的 wi-fi 建議

需要進行大量規劃，才能部署已優化的 Wi-fi 網路，以支援 Microsoft 團隊中的即時工作負載。 下列各節提供一些一般指導方針，可協助您在規劃端點時避免常見的錯誤。

### <a name="wi-fi-drivers"></a>Wi-fi 驅動程式

某些 Wi-fi 驅動程式可能會造成問題。 例如，驅動程式在存取點之間可能會有非常嚴格的漫遊行為，導致通話品質不佳。
這不是常見的情況，但請務必確保電腦上的 Wi-fi 驅動程式已在部署之前更新並經過測試。

### <a name="wi-fi-bands"></a>Wi-fi 區段

目前在 Wi-fi 裝置、2.4 GHz 和 5.0 GHz 中，主要使用兩種類型的區段。 如果您的組織同時提供兩個頻帶，您應該將您的驅動程式設定設定為優先使用 5.0 GHz 區段。 此區段在輸送量方面是很大的 denser，而且受到 2.4 GHz 區段干擾的影響較小。
此建議假設您已正確優化 5.0 GHz 網路區段。

### <a name="wi-fi-radio-type"></a>Wi-fi 無線電類型

規劃支援新版 Wi-fi 無線電類型的裝置。 如果您在您所設定的裝置上，利用 802.11 ac 或更新版本，就能取得良好的 Wi-fi 效能。

### <a name="wireless-avoidance"></a>無線回避

有些組織傾向于完全避免使用 Wi-fi。 在某些情況下，此指導方針是透過將使用者直接連線至有線網路的建議提供的。 在某些情況下，網路系結順序可能會有最佳的無線連線，而且即使電腦已連接至有線連線，仍會繼續使用該連線。 若要避免此意外行為，請設定系結順序來避免這種情況。

### <a name="80211-power-save-protocol"></a>802.11 省電通訊協定

如果您的組織使用的無線存取點或路由器不支援802.11 節能通訊協定，在 Windows 裝置上執行的 Microsoft 團隊中，您可能會遇到通話中斷或太差的通話品質。 如果無法升級您的無線存取點或路由器，您應該在以電池電源執行的裝置上更新 Windows 電源配置設定。 下列[支援文章](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)中提供了進一步的詳細資訊和設定指導方針。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>貴組織中將部署哪些團隊用戶端？</li><li>您要如何開始將團隊用戶端部署到您的使用者？</li><li>誰負責評估端點和裝置，以驗證他們是否符合品質體驗的小組需求？</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>記錄部署團隊用戶端所遵循的步驟。</li><li>評估端點和裝置，並需要執行與修正。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>團隊裝置

Microsoft 團隊可以用於會議或作為電話系統。 使用這些功能時，小組所用的介面裝置在使用者體驗中起著重要的作用。

如果您使用的是內建電腦喇叭和麥克風，擁有該設定的使用者就可能會聽到聲音。 但一般來說，這些裝置並未針對雜訊取消進行優化，而且任何類型的環境干擾都可能對通話中其他人產生下游影響。 利用針對這些案例優化的裝置將有助於確保高品質的體驗。

每個裝置都必須符合您的使用者需求。 您必須針對貴組織中的不同角色和使用案例，調整裝置（例如耳機）。
在規劃程式中應完成角色對裝置的對應練習。

選取裝置之後，請將它們包含在最終驗證的試驗測試方案中。 在試驗期間利用調查來收集意見反應，以確保您的裝置策略是最佳的。

> [!NOTE]
> 目前，我們建議使用透過商務用 Skype 認證計畫認證的音訊裝置。 若要尋找此程式下認證的裝置，請參閱[Microsoft 團隊裝置](https://products.office.com/microsoft-teams/across-devices/devices)和[USB 音訊與視頻裝置](https://docs.microsoft.com/SkypeForBusiness/certification/devices-usb-devices)。



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>決定您組織的整體裝置策略，以取得使用者和會議室的體驗。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>針對您的組織完成角色對裝置對應練習。</li><li>記錄為使用者和會議室取得裝置的程式。</li><li>為使用者和會議室的部署和設定裝置記錄程式。</li><li>購買初始裝置以開始您的部署。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
