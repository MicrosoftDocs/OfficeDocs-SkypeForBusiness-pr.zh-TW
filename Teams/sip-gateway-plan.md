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
description: 深入瞭解 SIP 閘道，例如需求和優點。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: f20c26d07bbfb0eebef9b46cbc1db85ad9f4d341
ms.sourcegitcommit: 30429a67cf477afa97fb09aa3b301443d989f8eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/04/2022
ms.locfileid: "68384739"
---
# <a name="plan-for-sip-gateway"></a>規劃 SIP 閘道

SIP 閘道可讓貴組織使用任何與 Microsoft Teams 相容的 SIP 裝置，以保留您在 SIP 裝置上的投資。 現在您可以使用公司認證登入 Teams，並使用相容的 SIP 裝置撥打和接聽電話。 相容裝置可商務用 Skype具有標準 SIP 韌體的 IP 手機、具有多重格式 SIP 韌體的 Cisco IP 手機，或來自 Poly、Yealink 和 AudioCode 等廠商的 SIP 裝置。 若要瞭解如何為 SIP 閘道設定 SIP 裝置，請參閱 [設定 SIP 閘道](sip-gateway-configure.md)。

## <a name="benefits-of-sip-gateway"></a>SIP 閘道的優點

SIP 閘道會將相容的 SIP 裝置連線到 Teams，協助使用者順暢地移轉到 Teams 電話語音。 使用 SIP 閘道，您的使用者可以執行下列所有動作：

- **撥打電話：** SIP 裝置使用者可以撥打公用交換電話網路 (PSTN) 、其他 SIP 裝置以及 Teams 和商務用 Skype使用者。 SIP 裝置使用者只能撥打有電話號碼的使用者。
- **接聽來電：** SIP 裝置使用者可以從 PSTN、Teams 或商務用 Skype擁有 SIP 裝置的使用者，以及來自 Teams 和商務用 Skype用戶端應用程式的來電。 SIP 裝置可做為 Teams 端點。 輸入電話也會指派給使用者的 SIP 裝置。
- **多個同時通話：** 通話中的 SIP 裝置使用者可以保留通話，以便撥打或接聽其他通話。 SIP 裝置使用者也可以進行兩次電話會議。
- **請勿打擾：** SIP 裝置使用者可以在裝置上設定請勿打擾，讓裝置不會撥打來電。 這不會影響使用者在所有其他 Teams 端點上的狀態。
- **保留/繼續和靜音/取消靜音：** SIP 裝置使用者可以使用裝置上這些動作的功能，來保留通話並繼續通話，或將通話設為靜音和取消靜音。
- **語音 信箱：** SIP 裝置使用者可以聆聽來電者為其保留的電子儲存語音訊息。
- **訊息等待指標：** SIP 裝置使用者可以在有新的語音信箱訊息時收到通知。
- **登入和登出：** SIP 裝置使用者可以在裝置上登入並登出 Teams。
- **雙音調多頻：** SIP 裝置使用者可以在互動式語音回應通話期間按下數位鍵來提供輸入。
- **Teams 會議：** SIP 裝置使用者可以撥打會議存取號碼來加入 Teams 會議。 會議參與者可以透過撥號至使用者的電話號碼將 SIP 裝置使用者新增至會議，或只要按一下 [要求加入] 新增參與者，也會警示使用者的 SIP 裝置。 其他組織的來賓使用者可由撥號至來賓使用者號碼以加入該來賓的參與者新增到 Teams 會議。
- **來電轉接：** SIP 裝置使用者可以轉接來電。 SIP 閘道支援盲眼和傳送傳輸。
- **當地來電轉接：** SIP 裝置使用者可以隨時 (設定裝置的轉寄規則、逾時和忙碌) 。 如果裝置已連線至 SIP 閘道，則通話將會根據裝置使用者設定的規則重新導向至目標位址。 若要讓本機來電轉接運作，系統管理員必須將屬性設 `AllowCallRedirect` 為 `Set-CsTeamsCallingPolicy` `Enabled` 。
- **已過舊的裝置：** SIP 閘道支援針對租使用者布建的過舊裝置自動登出。 配對 (登入) 裝置若 30 天未連線，則會關閉配對，並在 14 天后) 裝置解除配對 (登出。 離線裝置可以在重設出廠之後重新上線。

## <a name="requirements-to-use-sip-gateway"></a>使用 SIP 閘道的需求

Teams 使用者必須有已啟用 PSTN 通話的電話號碼，才能使用 SIP 閘道。

> [!NOTE]
> SIP 閘道不適用於 GCC、GCC High 和 DoD)  (政府環境。

### <a name="hardware-software-and-licenses"></a>硬體、軟體和授權

如果您有 3PIP 或 SIP 裝置，您必須具備：

- Microsoft Teams、商務用 Skype Online 方案 2 和 Microsoft 365 手機系統透過 E5 或獨立授權 (的授權) 
- PSTN 啟用 (，也即透過 Microsoft Teams 通話方案、直接路由或運算子連線) 電話號碼
- 任何通用區域裝置的通用區域電話授權

## <a name="compatible-devices"></a>相容的裝置

|廠商    |模型      |最小韌體版本|已核准韌體版本|備註|連結|
|----------|-----------|------------|-----------|------------|------------|
|**Cisco** |           |            |           |執行企業韌體的裝置必須轉換成多重格式韌體。 請閱讀右側的指南以瞭解做法。|[Cisco 韌體轉換指南](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)|
|          |8832       |11.3.5MPP   |11-3-7MPP  |   |   |
|          |6821       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |7811       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |7821       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |7841       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |7861       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8811       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8841       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8845       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8851       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8861       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8865       |11.1.1MPP   |11-3-7MPP  |   |   |
|**聚**  |           |            |           |裝置會自動重新開機並安裝選取的韌體。|   |
|          |Trio 8500  |5.9.5.3182  |7.2.2.1094 |   |   |
|          |Trio 8800  |5.9.5.3182  |7.2.2.1094 |   |   |
|          |VVX150<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX201<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX250<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX300     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX301<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX310     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX311<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX350<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX400     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX401<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX410     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX411<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX450<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX500     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX501<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX600     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX601<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |Rove B2    |8.0.3.0010  |8.0.3.0010 |   |   |
|          |Rove B4    |8.0.3.0010  |8.0.3.0010 |   |   |
|          |Rove 30    |8.0.3.0010  |8.0.3.0010 |   |   |
|          |Rove 40    |8.0.3.0010  |8.0.3.0010 |   |   |
|**Yealink**|          |            |           |   |[Yealink 支援](https://support.yealink.com/)|
|          |T21P       |83          |34.72.0.75 |   |   |
|          |T21P_E2    |83          |52.84.0.125|   |   |
|          |T23G       |83          |44.84.0.140|   |   |
|          |T27G<sup>1</sup>      |83          |69.86.0.15 |   |   |
|          |T29G       |83          |46.83.0.130|   |   |
|          |T30<sup>1</sup>       |83          |124.86.0.40|   |   |
|          |T30P<sup>1</sup>      |83          |124.86.0.40|   |   |
|          |T31G<sup>1</sup>      |83          |124.86.0.40|   |   |
|          |T31P<sup>1</sup>      |83          |124.86.0.40|   |   |
|          |T33G<sup>1</sup>      |83          |124.86.0.40|   |   |
|          |T40G       |83          |76.84.0.125|   |   |
|          |T40P       |83          |54.84.0.125|   |   |
|          |T41P       |83          |36.83.0.120|   |   |
|          |T41S<sup>1</sup>      |83          |66.86.5.1  |   |   |
|          |T42G       |83          |29.83.0.130|   |   |
|          |T42S<sup>1</sup>      |83          |66.86.5.1  |   |   |
|          |T42U<sup>1</sup>      |83          |108.86.5.1 |   |   |
|          |T43U<sup>1</sup>      |83          |108.86.5.1 |   |   |
|          |T46G       |83          |28.83.0.130|   |   |
|          |T46S<sup>1</sup>      |83          |66.86.5.1  |   |   |
|          |T46U<sup>1</sup>      |83          |108.86.5.1 |   |   |
|          |T48G       |83          |35.83.0.130|   |   |
|          |T48S<sup>1</sup>      |83          |66.86.5.1  |   |   |
|          |T48U<sup>1</sup>      |83          |108.86.5.1 |   |   |
|          |T53<sup>1</sup>       |83          |96.86.5.1  |   |   |
|          |T53W<sup>1</sup>      |83          |96.86.5.1  |   |   |
|          |T54W<sup>1</sup>      |83          |96.86.5.1  |   |   |
|          |T57W<sup>1</sup>      |83          |96.86.5.1  |   |   |
|**AudioCodes**|       |            |           |某些 AudioCodes SIP 裝置需要布建 URL 設定。 在右側下載並安裝受影響之 AudioCodes 裝置的升級檔案。 |[在 AudioCodes 為受影響裝置下載的檔案](https://audiocodes.sharefile.com/share/view/sc9cdf17f9ec45d09/fo7914a2-4f3a-4000-8957-47bd6f35a3a5)|
|          |405<sup>1</sup>        |2.2.8      |2.2.16.589 |   |   |
|          |405HD<sup>1</sup>      |3.2.1      |2.2.16.589 |   |   |
|          |405HDG<sup>1</sup>     |3.2.1      |2.2.16.589 |   |   |
|          |420HD<sup>1</sup>      |3.2.1      |2.2.16.589 |   |   |
|          |420HDG<sup>1</sup>     |3.2.1      |2.2.16.589 |   |   |
|          |430HD<sup>1</sup>      |3.2.1      |2.2.16.589 |   |   |
|          |430HDG<sup>1</sup>     |3.2.1      |2.2.16.589 |   |   |
|          |440HD<sup>1</sup>      |3.2.1      |2.2.16.589 |   |   |
|          |445HD<sup>1</sup>      |3.2.1      |3.4.6.704 |   |   |
|          |445HDG<sup>1</sup>     |3.2.1      |3.4.6.704 |   |   |
|          |450HD<sup>1</sup>      |3.2.1      |3.4.6.704  |   |   |
|          |C450HD<sup>1</sup>     |3.2.1      |3.4.6.704  |   |   |
|          |445HD<sup>1</sup>      |3.2.1      |3.4.6.704  |   |   |
|          |RX50<sup>1</sup>       |3.2.1      |3.4.6.704  |   |   |
|**Spectralink**|       |           |           |   |[Spectralink 支援](https://support.spectralink.com)|
|          |7202        |PCS22B     |PCS22B     |手機 |   |
|          |7212        |PCS22B     |PCS22B     |手機 |   |
|          |7502        |PCS22B     |PCS22B     |手機 |   |
|          |7522        |PCS22B     |PCS22B     |手機 |   |
|          |7532        |PCS22B     |PCS22B     |手機 |   |
|          |7622        |PCS22B     |PCS22B     |手機 |   |
|          |7642        |PCS22B     |PCS22B     |手機 |   |
|          |7722        |PCS22B     |PCS22B     |手機 |   |
|          |7742        |PCS22B     |PCS22B     |手機 |   |
|          |IP-DECT Server 200 |PCS22Ab |PCS22Ab |IP-DECT Server |   |
|          |IP-DECT Server 400 |PCS22Ab |PCS22Ab |IP-DECT Server |   |
|          |IP-DECT Server 6500 |PCS22Ab |PCS22Ab |IP-DECT Server |   |
|          |虛擬 IP-DECT Server One |PCS22Ab |PCS22Ab |IP-DECT Server |   |
|          |IP-DECT 基座 |PCS22Ab |PCS22Ab |IP-DECT Server |   |
|**Ascom**|       |           |           |   |[Ascom 支援](https://www.ascom.com/products-and-services/services/support-and-maintenance/)|
|          |Ascom d43        |2.11.4     |2.11.4     |手機 |   |
|          |Ascom d63        |2.11.4     |2.11.4     |手機 |   |
|          |Ascom d81        |4.13.1     |4.13.1     |手機 |   |
|          |Ascom d83        |4.13.1     |4.13.1     |手機 |   |
|          |Ascom Myco 3 DECT        |3.4.1     |3.4.1     |手機 |   |
|          |IP-DECT 存取點 IPBSx        |11.8.8     |11.8.8     |IP-DECT 存取點 |   |
|          |IP-DECT 閘道 IPBL     |11.8.8     |11.8.8     |IP-DECT 閘道 |   |
|          |TDM 基座        |R3N     |R3N     |IP-DECT 基座 |   |
|          |IP-DECT 虛擬裝置 IPVM        |11.8.8     |11.8.8     |IP-DECT Server |   |

<sup>1</sup> 裝置支援使用 SIP 閘道的動態緊急呼叫 (E911) 。

> [!NOTE]
> 客戶可以分別使用 AudioCodes OVOC 和 Poly Lens 管理其 AudioCode 400 系列和 Poly VVX/Trio 裝置的裝置側邊設定。

> [!NOTE]
> Spectralink 聽筒會透過 Air 從 Spectralink IP-DECT 伺服器接收韌體更新。

> [!NOTE]
> Ascom 聽筒會從 Ascom IP-DECT 伺服器透過空中接收韌體更新。

> [!NOTE]
> 針對支援查詢，搭配 Teams SIP 閘道使用 IP-DECT 系統的客戶應連絡其 DECT 製造商或其實作通道合作夥伴。

> [!NOTE]
> 對於某些裝置，最小韌體版本會大於核准的韌體版本。 這是因為 3.X 版本是 商務用 Skype 版本。 我們會更新 SIP 版本，也就是 2.X。
