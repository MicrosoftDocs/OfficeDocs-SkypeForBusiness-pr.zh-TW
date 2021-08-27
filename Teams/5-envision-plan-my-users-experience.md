---
title: 規劃使用者使用Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 選擇 Teams應用程式、規劃端點品質、取得部署端點Wi-Fi建議，以及選擇音訊裝置。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f6482baa6738d4f7c3495085f86ae9b9a054d0eb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624835"
---
# <a name="plan-my-users-experience"></a>規劃使用者的體驗

本文提供正確識別雲端語音服務部署元素的需求概觀，這些元素會直接影響使用者的體驗。 在部署前準備這些專案，會增加成功為使用者提供高品質、可靠體驗的機會。 

## <a name="client-deployment"></a>用戶端部署

Microsoft Teams Android 和 iOS (Windows Mac) ，以及行動 (用戶端) 。 有關如何安裝桌上型電腦 (Windows Mac) 手機用戶端的其他詳細資料，請參閱取得用戶端[Microsoft Teams。](./get-clients.md)

## <a name="client-updates"></a>用戶端更新

其中一個Teams優點就是用戶端會自動保持在最新狀態。 PC 和 Mac 上的用戶端會使用背景程式進行更新，此程式會檢查新建立，並下載應用程式閒置時的新用戶端。

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>規劃端點品質

如下圖所示，端點是為使用者提供品質體驗的重要建組塊。

![描述品質三個要素的圖表](media/plan-my-users-experience-image1.png "描述品質的三個元件，以及服務管理如何與這三個元件重迭的圖表。將焦點放在端點上。")

Teams端點可以在許多裝置上執行，包括電腦、Mac、平板電腦和行動裝置。 部分體驗不僅包含裝置，還包括使用者如何連接到裝置，例如，使用裝置內建的麥克風/喇叭、耳塞或優化的耳機。 使用優化的耳機可豐富整體使用者體驗。

以下端點規劃指南可協助確保貴組織擁有成功與 Teams。

## <a name="endpoint-capability"></a>端點功能

規劃的第一部分，是為了確保貴組織的所有電腦和其他裝置都可以Teams。 這不只涉及查看硬體需求，也涉及瞭解電腦在背景中執行哪些其他操作。 許多組織會執行其他軟體，包括入侵偵測系統和反惡意軟體，這可能會影響裝置的基本性能。

有關 Web、桌面Teams行動 (每個平臺用戶端的軟體需求) ，請參閱取得用戶端[Microsoft Teams。](./get-clients.md)

## <a name="endpoint-firewalls"></a>端點防火牆

用戶端防火牆會對使用者體驗有重大的影響。
除了防止建立通話之外，用戶端防火牆也會影響通話品質。 根據 URL 或 IP 位址範圍中Microsoft 365或Office 365防火牆上設定適當的[排除。](/microsoft-365/enterprise/urls-and-ip-address-ranges) 您的協力廠商廠商將擁有如何建立排除專案的特定指引。

>[!NOTE]
> Microsoft Teams會以適當的防火牆Windows自動更新防火牆。

## <a name="wi-fi-recommendations-for-endpoints"></a>Wi-Fi端點的建議

部署優化的網路需要Wi-Fi規劃，以支援即時工作負載Microsoft Teams。 下列各節提供一些一般指南，可協助避免規劃端點時常見的錯誤。

### <a name="wi-fi-drivers"></a>Wi-Fi驅動程式

某些Wi-Fi驅動程式可能會有問題。 例如，驅動程式在訪問點之間可能具有非常積極的漫遊行為，導致通話品質不佳。
這不是很常見的情況，但一Wi-Fi部署前，請確保已更新並測試 PC 上的驅動程式。

### <a name="wi-fi-bands"></a>Wi-Fi帶

現今在設備中使用的頻帶Wi-Fi種，2.4 GHz 和 5.0 GHz。 如果貴組織同時提供這兩個頻帶，您應該設定驅動程式設定，以偏好 5.0 GHz 頻帶。 此頻帶在輸送量方面密度更高，且受 2.4 GHz 頻帶的干擾影響較小。
此建議假設您已正確優化 5.0 GHz 網路帶。

### <a name="wi-fi-radio-type"></a>Wi-Fi單選類型

規劃支援較新無線Wi-Fi裝置。 如果您在您撥備的裝置Wi-Fi 802.11ac 或更新版本，就可以獲得很好的使用效果。

### <a name="wireless-avoidance"></a>無線避免

有些組織偏好完全避免Wi-Fi使用。 有時候，這項指引會透過建議提供給使用者，讓使用者直接連接到有線網路。 在某些情況下，網路綁定順序可能偏好使用無線網路連接，即使電腦已連接到有線連接，仍繼續使用該連接。 若要避免此非預期行為，請設定綁定順序以避免此情況。

### <a name="80211-power-save-protocol"></a>802.11 Power Save 通訊協定

如果貴組織使用不支援 802.11 Power Save 通訊協定的無線訪問點或路由器，您可能會在 Windows 裝置上Microsoft Teams通話品質不佳。 如果無法升級您的無線存取點或路由器，您應該更新Windows電池電力的裝置上的 Power Plan 設定。 下列支援文章提供進一步的詳細資料及組 [組指引](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>哪些Teams用戶端會部署在貴組織中？</li><li>您一開始要如何Teams用戶端？</li><li>神秘負責評估端點和裝置，以驗證它們符合Teams品質體驗的需求嗎？</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>記錄部署用戶端時Teams程式。</li><li>評估端點和裝置，並需要執行及補救。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>適用于 Teams

Microsoft Teams會議或電話系統。 使用這些功能時，用於Teams介面裝置在使用者體驗中會扮演重要角色。

使用內建電腦喇叭和麥克風可能聽起來對擁有該組式的使用者來說可以接受。 但一般來說，這些裝置未針對雜訊消除進行優化，而且任何類型的環境雜訊會對通話中的其他人造成下游影響。 運用針對這些案例優化的裝置，有助於確保高品質的體驗。

每個裝置都必須符合使用者的需求。 您需要為貴組織中不同的角色和使用案例量身打造裝置，例如耳機。
在規劃程式過程中，應完成人員對裝置映射練習。

選取裝置之後，請將其納入試驗測試計劃，以完成驗證。 在試驗期間運用問卷收集意見，以確保您的裝置策略最佳。

> [!NOTE]
> 目前，我們建議您使用通過認證計畫商務用 Skype裝置。 若要尋找此計畫所認證的裝置，請參閱[Microsoft Teams裝置和](https://products.office.com/microsoft-teams/across-devices/devices)USB[音訊與視音訊裝置](/SkypeForBusiness/certification/devices-usb-devices)。



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>決定貴組織的使用者和會議室體驗的整體裝置策略。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>為貴組織完成人員對裝置映射練習。</li><li>記錄取得使用者和會議室裝置的過程。</li><li>記錄使用者和會議室的部署和組組裝置程式。</li><li>購買初始裝置以開始部署。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->