---
title: 規劃 SIP 閘道
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 深入瞭解 SIP 閘道，例如需求與權益。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e59f219d24f6441615d794f23e73274e817f6a3b
ms.sourcegitcommit: 2aae13454178dc2e2cbc8cca967cd181c5f9d044
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/06/2021
ms.locfileid: "61314245"
---
# <a name="plan-for-sip-gateway"></a>規劃 SIP 閘道

SIP 閘道可讓您的組織使用任何相容的 SIP 裝置Microsoft Teams SIP 裝置中的投資。 現在，您可以使用公司認證Teams，然後使用相容的 SIP 裝置撥打和接聽電話。 相容裝置可以是具有標準 SIP 商務用 Skype的 IP 電話、具有多平臺 SIP 固件的 Cisco IP 電話，或來自 Poly、Yealink 和 AudioCodes 等廠商的 SIP 裝置。 若要瞭解如何設定 SIP 閘道的 SIP 裝置，請參閱 [設定 SIP 閘道](sip-gateway-configure.md)。

## <a name="benefits-of-sip-gateway"></a>SIP 閘道的好處

SIP 閘道可將相容的 SIP 裝置連接到Teams，協助使用者順暢地Teams電話。 使用 SIP 閘道，您的使用者可以執行下列所有操作：

- **撥打電話：** SIP 裝置使用者可以撥打公用交換電話網絡 (PSTN) 、其他 SIP 裝置，以及Teams商務用 Skype使用者。 SIP 裝置使用者只能打電話給有電話號碼的使用者。
- **接聽電話：** SIP 裝置使用者可以從 PSTN、Teams 或 商務用 Skype 擁有 SIP 裝置的使用者，以及 Teams 和 商務用 Skype 用戶端應用程式商務用 Skype來電。 SIP 裝置會做為Teams端點。 輸入通話也會分叉到使用者的 SIP 裝置。
- **多個同時通話：** 通話中的 SIP 裝置使用者可以保留通話，以撥打或接聽其他通話。 SIP 裝置使用者也可以召開兩次電話會議。
- **請勿打擾：** SIP 裝置使用者可以在裝置上設定請勿打擾，讓裝置不會響鈴接聽來電。 這不會影響使用者在其他所有端點Teams狀態。
- **保留/繼續和靜音/取消靜音：** SIP 裝置使用者可以在裝置上使用這些動作的功能，來保留或繼續通話，或將通話設為靜音和取消靜音。
- **語音 信箱：** SIP 裝置使用者可以聆聽來電者留給他們的電子儲存語音訊息。
- **訊息等待指示器：** SIP 裝置使用者可以收到通知，當他們有新的語音信箱訊息時，會收到通知。
- **登錄和登出：** SIP 裝置使用者可以在裝置上Teams並登出。
- **雙音多頻率：** SIP 裝置使用者可以在互動式語音回應通話期間按數位鍵提供輸入。
- **Teams：SIP** 裝置使用者Teams會議存取號碼加入會議。 目前不支援撥出到同一個組織使用者的電話號碼。 不過，另一個組織的來賓使用者Teams撥入來賓使用者號碼以包含該來賓的參與者加入會議。 **注意：** 透過「Teams加入」新增會議參與者目前不會通知 SIP 裝置。
- **通話轉接：** SIP 裝置使用者可以轉接通話。 SIP 閘道同時支援視盲和諮詢傳輸。
- **本地呼叫轉轉：** SIP 裝置使用者可以針對裝置設定 (、超時和忙碌) 轉轉規則。 如果裝置已連接到 SIP 閘道，則通話會依據裝置使用者設定的規則重新導向至目標位址。 若要讓本地呼叫轉轉工作，系統管理員必須將 `AllowCallRedirect` 屬性設定為 `Set-CsTeamsCallingPolicy` `Enabled` 。 


## <a name="requirements-to-use-sip-gateway"></a>使用 SIP 閘道的需求

Teams啟用 PTSN 通話的電話號碼，使用者必須使用 SIP 閘道。

### <a name="hardware-software-and-licenses"></a>硬體、軟體和授權

如果您有 3PIP 或 SIP 裝置，您必須有： 
- 透過 E5 電話系統 (授權或獨立授權) 
- PTSN 啟用 (，即透過) 通話方案、Microsoft Teams路由或接線連線
- 任何共同電話裝置的共同區域授權

## <a name="compatible-devices"></a>相容裝置

|廠商    |模型      |最小固件版本|核准的固件版本|備註|連結|
|----------|-----------|------------|-----------|------------|------------|
|**Cisco** |           |            |           |執行企業固件的裝置必須轉換成多平臺的固件。 請閱讀右側指南以瞭解如何操作。|[Cisco 固件轉換指南](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)|
|          |6821       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7811       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7821       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7841       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7861       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8811       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8841       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8845       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8851       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8861       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8865       |11.1.1MPP   |11-3-3MPP  |   |   |
|**聚**  |           |            |           |裝置會自動重新開機並安裝選取的固件。|   |
|          |VVX150     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX201     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX250     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX300     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX301     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX310     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX311     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX350     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX400     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX401     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX410     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX411     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX450     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX500     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX501     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX600     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX601     |5.9.5       |6.3.1.8427 |   |   |
|**Yealink**|          |            |           |   |[Yealink 支援](https://support.yealink.com/)|
|          |T40P       |83          |54.84.0.125|   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T42G       |83          |29.83.0.130|   |   |
|          |T42S       |83          |66.85.0.5  |   |   |
|          |T42U       |83          |108.86.0.20|   |   |
|          |T43U       |83          |108.86.0.20|   |   |
|          |T46S       |83          |66.85.0.5  |   |   |
|          |T46U       |83          |108.86.0.20|   |   |
|          |T48S       |83          |66.85.0.5  |   |   |
|          |T48G       |83          |35.83.0.130|   |   |
|          |T48U       |83          |108.86.0.20|   |   |
|          |T53        |83          |96.85.0.5  |   |   |
|          |T53W       |83          |96.85.0.5  |   |   |
|          |T54W       |83          |96.85.0.5  |   |   |
|          |T57W       |83          |96.85.0.5  |   |   |
|          |T21P       |83          |52.84.0.140|   |   |
|          |T23G       |83          |44.84.0.140|   |   |
|          |T27G       |83          |69.85.0.5  |   |   |
|          |T29G       |83          |46.83.0.130|   |   |
|          |T30        |83          |124.85.0.40|   |   |
|          |T30P       |83          |124.85.0.40|   |   |
|          |T31G       |83          |124.85.0.40|   |   |
|          |T33G       |83          |124.85.0.40|   |   |
|          |T40G       |83          |76.84.0.125|   |   |
|          |T41P       |83          |36.83.0.120|   |   |
|          |T46G       |83          |28.83.0.130|   |   |
|**AudioCodes**|       |            |           |某些 AudioCodes SIP 裝置需要設定設定 URL。 在右側下載並安裝受影響的 AudioCodes 裝置升級檔案。 |[在 AudioCodes 下載受影響裝置檔案](https://audiocodes.sharefile.com/share/view/sc9cdf17f9ec45d09/fo19ecda-cf14-4a53-842b-5eab33a0b9b0)|
|          |405         |2.2.8      |2.2.16.525 |   |   |
|          |405HD       |3.2.1      |2.2.16.525 |   |   |
|          |420HD       |3.2.1      |2.2.16.525 |   |   |
|          |430HD       |3.2.1      |2.2.16.525 |   |   |
|          |440HD       |3.2.1      |2.2.16.525 |   |   |
|          |450HD       |3.2.1      |3.4.6.558  |   |   |
|          |C450HD      |3.2.1      |3.4.6.558  |   |   |
|          |445HD       |3.2.1      |3.4.6.558  |   |   |
