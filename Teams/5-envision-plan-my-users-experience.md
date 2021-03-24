---
title: 規劃使用者對 Microsoft Teams 的體驗
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 選擇 Teams 用戶端應用程式、規劃端點品質、取得部署端點Wi-Fi以及選擇音訊裝置的建議。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d20d914ab6ceca1d264a23662c9c8a067798a82
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094731"
---
# <a name="plan-my-users-experience"></a>規劃使用者的體驗

本文提供正確識別雲端語音服務部署元素的需求概觀，這些元素會直接影響使用者的體驗。 在部署前準備這些專案，將提高您成功為使用者提供高品質、可靠體驗的機會。 

## <a name="client-deployment"></a>用戶端部署

Microsoft Teams 提供適用于 Android 和 iOS (Windows 和 Mac) 和行動 (用戶端) 。 請參閱取得 Microsoft Teams 的用戶端 (Windows 和 Mac) 和行動用戶端的其他 [詳細資料](./get-clients.md)。

## <a name="client-updates"></a>用戶端更新

Teams 的主要優點之一是用戶端會自動保持在最新狀態。 PC 和 Mac 上的用戶端會使用背景程式進行更新，此程式會檢查新建立，並下載應用程式閒置時的新用戶端。

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>規劃端點品質

如下圖所示，端點是為使用者提供品質體驗的重要建組塊。

![描述品質三個要素的圖表](media/plan-my-users-experience-image1.png "描述品質的三個元件，以及服務管理如何與這三個元件重迭的圖表。將焦點放在端點上。")

Teams 端點可在許多裝置上執行，包括 PC、Mac、平板電腦和行動裝置。 部分體驗不僅包含裝置，還包括使用者如何連接到裝置，例如使用裝置內建的麥克風/喇叭、耳塞或優化的耳機。 使用優化的耳機可豐富整體使用者體驗。

下列端點規劃指南可協助確保貴組織在 Teams 中順利上線。

## <a name="endpoint-capability"></a>端點功能

規劃的第一部分，是為了確保貴組織的所有電腦和其他裝置都可以執行 Teams。 這不只涉及查看硬體需求，還涉及瞭解電腦在背景中執行哪些其他操作。 許多組織會執行其他軟體，包括入侵偵測系統和反惡意軟體，這可能會影響裝置的基本性能。

有關每個平臺上 Teams 用戶端的軟體需求 (Web、桌面及行動) ，請參閱取得 [Microsoft Teams](./get-clients.md)的用戶端。

## <a name="endpoint-firewalls"></a>端點防火牆

用戶端防火牆會對使用者體驗有重大的影響。
除了防止建立通話之外，用戶端防火牆也會影響通話品質。 根據 [Microsoft 365 或 Office 365 URL](/microsoft-365/enterprise/urls-and-ip-address-ranges)和 IP 位址範圍的資訊，在用戶端防火牆上設定適當的排除專案。 您的協力廠商廠商將擁有如何建立排除專案的特定指引。

>[!NOTE]
> Microsoft Teams 會以適當的防火牆組組自動更新 Windows 防火牆。

## <a name="wi-fi-recommendations-for-endpoints"></a>Wi-Fi端點的建議

部署優化的Wi-Fi網路，以支援 Microsoft Teams 中的即時工作負載，需要經過重大規劃。 下列各節提供一些一般指南，可協助避免規劃端點時常見的錯誤。

### <a name="wi-fi-drivers"></a>Wi-Fi驅動程式

某些Wi-Fi驅動程式可能會有問題。 例如，驅動程式在訪問點之間可能具有非常積極的漫遊行為，導致通話品質不佳。
這不是很常見的情況，但一Wi-Fi部署前，請確保已更新並測試 PC 上的驅動程式。

### <a name="wi-fi-bands"></a>Wi-Fi帶

現今在設備中使用的頻帶Wi-Fi種，2.4 GHz 和 5.0 GHz。 如果貴組織同時提供這兩個頻帶，您應該設定驅動程式設定，以偏好 5.0 GHz 頻帶。 此頻帶在輸送量方面密度更高，且受到 2.4 GHz 頻帶的干擾影響較小。
此建議假設您已正確優化 5.0 GHz 網路帶。

### <a name="wi-fi-radio-type"></a>Wi-Fi廣播類型

規劃支援較新廣播類型的Wi-Fi裝置。 如果您在您撥備的裝置Wi-Fi 802.11ac 或更新版本，就可以獲得很好的提升使用效果。

### <a name="wireless-avoidance"></a>無線避免

有些組織偏好完全避免Wi-Fi問題。 有時候，這項指引會透過建議提供給使用者，讓使用者直接連接到有線網路。 在某些情況下，網路綁定順序可能偏好使用無線網路連接，即使電腦已連接到有線連接，仍繼續使用該連接。 若要避免此非預期行為，請設定綁定順序以避免此情況。

### <a name="80211-power-save-protocol"></a>802.11 Power Save 通訊協定

如果貴組織使用不支援 802.11 Power Save 通訊協定的無線訪問點或路由器，您可能會在 Windows 裝置上運行的 Microsoft Teams 中遇到通話中斷或通話品質不佳的問題。 如果無法升級無線存取點或路由器，您應該更新以電池電力執行之裝置上的 Windows Power Plan 設定。 下列支援文章提供進一步的詳細資料及組 [組指引](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>貴組織中將會部署哪些 Teams 用戶端？</li><li>您一開始會如何將 Teams 用戶端部署到您的使用者？</li><li>誰負責評估端點和裝置，以驗證它們符合 Teams 品質體驗的需求？</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>記錄部署 Teams 用戶端所遵循的流程。</li><li>評估端點和裝置，並需要執行及補救。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Teams 的裝置

Microsoft Teams 可用於會議或電話系統。 使用這些功能時，Teams 所使用的介面裝置在使用者體驗中會扮演重要角色。

使用內建電腦喇叭和麥克風可能聽起來對擁有該組式的使用者來說可以接受。 但一般來說，這些裝置未針對雜訊消除進行優化，而且任何類型的環境雜訊會對通話中的其他人造成下游影響。 運用針對這些案例優化的裝置，有助於確保高品質的體驗。

每個裝置都必須符合使用者的需求。 您需要為貴組織中不同的角色和使用案例量身打造裝置，例如耳機。
在規劃程式過程中，應完成人員對裝置映射練習。

選取裝置之後，請將其納入試驗測試計劃，以完成驗證。 在試驗期間運用問卷收集意見，以確保您的裝置策略最佳。

> [!NOTE]
> 目前，我們建議您使用透過商務用 Skype 認證計畫認證的音訊裝置。 若要尋找在此計畫下通過認證的裝置，請參閱 [Microsoft Teams](https://products.office.com/microsoft-teams/across-devices/devices) 裝置和 [USB 音訊和視像裝置](/SkypeForBusiness/certification/devices-usb-devices)。



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>決定貴組織的使用者和會議室體驗的整體裝置策略。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>為貴組織完成人員對裝置映射練習。</li><li>記錄使用者和會議室取得裝置的過程。</li><li>記錄使用者和會議室的部署和組組裝置程式。</li><li>購買初始裝置以開始部署。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->