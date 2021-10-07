---
title: 通過直接路由認證的工作階段邊界控制器
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: 了解哪些工作階段邊界控制器 (SBC) 已通過直接路由認證。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1d9859b15b881d53a2f1b3c5b39442331e51be2e
ms.sourcegitcommit: 74d3ab35c344d70b2399bc46a6ced3ab2762a470
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2021
ms.locfileid: "60138219"
---
# <a name="session-border-controllers-certified-for-direct-routing"></a>通過直接路由認證的工作階段邊界控制器

Microsoft 與選取的工作階段邊界控制器 (SBC) 廠商合作，以認證其 SBC 可搭配直接路由使用。

Microsoft 可與每個廠商合作，以：

- 共同處理 SIP 互相連線通訊協定。
- 使用協力廠商實驗室執行大量測試。 只有通過測試的裝置才會通過認證。
- 在生產與生產前環境中，使用所有通過認證的裝置執行每日測試。 在生產前環境中驗證裝置可確保雲端中新版本的直接路由程式碼可搭配認證的 SBC 使用。
- 與 SBC 廠商建立聯合支援流程。

  > [!NOTE]
  > Microsoft 只有在透過直接路由連接通過認證的裝置時，才支援電話系統。 Microsoft 保留拒絕非認證裝置透過直接路由連接到電話系統的支援案例的權利。 如果 Microsoft 判斷客戶的直接路由問題與廠商的 SBC 裝置有關，則客戶需要與 SBC 廠商聯繫以取得支援。

遵循經過直接路由認證之裝置清單的資料表。 (如需有關哪些 SBC 廠商支援本機媒體最佳化的資訊，請參閱[設定直接路由的本機媒體最佳化](direct-routing-media-optimization-configure.md))。

[深入了解直接路由](https://aka.ms/dr)。如果您對直接路由的 SBC 認證計畫有任何疑問，請連絡 drsbccertification@microsoft.com。 <br/>

## <a name="certified-sbc-vendors"></a>認證的 SBC 廠商

|                                                       廠商                                                        |       產品       | 非媒體旁路 | 媒體旁路 | 軟體版本 | 支援 911 服務提供者* | 支援 ELIN |  
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|  
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  支援 7.20A.258 (建議 7.40A.100)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  支援 7.20A.258 (建議 7.40A.100)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  支援 7.20A.258 (建議 7.40A.100)   |   &#10004;   |  &#10004;  |
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  支援 7.20A.258 (建議 7.40A.100)   |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 1000B  SBC  |     &#10004;     |   &#10004;     |  支援 7.20A.250 (建議 7.20A.258)  |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 9000  SBC  |     &#10004;     |   &#10004;     |  支援 7.20A.258 (建議 7.40A.100)   | &#10004;     |  &#10004;  |
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  支援 7.20A.258 (建議 7.40A.100) |  &#10004;    |  &#10004;  |   
|                                                                                                                     | Mediant Cloud Edition SBC  |     &#10004;     |   &#10004;     |  支援 7.20A.258 (建議 7.40A.100) |  &#10004;    |  &#10004;  |
|  [Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5100/5110       |     &#10004;     |   &#10004;    |       支援 8.2 和 7.2 (建議 9.2)       | &#10004;   |     |
|                                                                                                                     |      SBC 5200/5210       |     &#10004;     |  &#10004;    |       支援 8.2 和 7.2 (建議 9.2)       |   &#10004; |    |
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       支援 8.2 和 7.2 (建議 9.2)       |   &#10004;  | |
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       支援 8.2 和 7.2 (建議 9.2)       |    &#10004;  |  |
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       支援 8.2 和 7.2 (建議 9.2)          |  &#10004;    |    |
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.x 或 9.x     |   &#10004;  |  &#10004;     |
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.x 或 9.x     |   &#10004;   |     &#10004;     |
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.x 或 9.x    |   &#10004;    |     &#10004;     |
| | EdgeMarc 系列 |  &#10004; | | 15.6.1 | |  
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |           |       1.4       |     |    |
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   &#10004;    |  &#10004;  |
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   &#10004;   |  &#10004;  |
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   &#10004;   |  &#10004;  |
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      支援 3.20 (建議 4.0)        |  &#10004;    |  &#10004;   |
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   | &#10004; |      4.7 (4.9 用於媒體旁路)      | &#10004; | &#10004; |  
|                     [Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     適用於 1000 系列整合式服務路由器的 Cisco Unified Border Element (CUBE)        |     &#10004;   | &#10004; |      支援 IOS XE Amsterdam 17.2.1r (建議 17.6.1a)         |    &#10004;     |   |  
|                                   |     適用於 4000 系列整合式服務路由器的 Cisco Unified Border Element (CUBE)        |     &#10004;   | &#10004; |   支援 IOS XE Amsterdam 17.2.1r (建議 17.6.1a)         |   &#10004;      |    |  
|                                   |     適用於 1000V 系列雲端服務路由器的 Cisco Unified Border Element (CUBE)       |     &#10004;   | &#10004; |      支援 IOS XE Amsterdam 17.2.1r (建議 17.3.3)         |    &#10004;     |    |  
|                                 |     適用於 1000 系列彙總服務路由器的 Cisco Unified Border Element (CUBE)      |     &#10004;   | &#10004; |      支援 IOS XE Amsterdam 17.2.1r (建議 17.6.1a)         |    &#10004;     |    |
|                                 |     適用於 Catalyst 8000 邊緣平台的 Cisco Unified Border Element (CUBE)      |     &#10004;   | &#10004; |      支援 IOS XE Amsterdam 17.3.2 (建議 17.6.1a)      |    &#10004;     |    |
|                     [Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    Avaya Session Border Controller for Enterprise ( ASBCE)    |     &#10004;     |       &#10004;     |       8.1.1 版 (8.1.2 用於媒體旁路)      |     |    |
|                     [Nokia](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|    Nokia 工作階段邊界控制器    |     &#10004;     |           |       19.5 (1908)       |     |    |
|                     |    Nokia 工作階段邊界控制器    |     &#10004;     |           |       20.8       |      &#10004;        |    |
|                     [Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|    NetMatch-S CI     |     &#10004;     |           |       支援 5.0 (建議 5.1)     |     |    |
|                     [Ericsson](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|    vSBC 2.16     |     &#10004;     |           |              |     |    |
|                     [Cataleya](https://cataleya.com/orchidplatforms/)|    Orchid Link    |     &#10004;     |           |      3.1        |     |    |
|                     [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|    Teams SBC    |     &#10004;     |     &#10004;      |      1.6        |     |    |
|                     [Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|    Atos Unify OpenScape 工作階段邊界控制器   |     &#10004;     |          |      V10R1.2       |     |    |
|                     [Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|    vmVSXi   |     &#10004;     |     &#10004;     |      10.5.1.354-vm-S-x64      |     |    |
|                     [Enghouse Networks](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|    Dialogic BorderNet SBC   |     &#10004;     |     &#10004;     |      3.9.0-786      |     |    |
|                     [Patton Electronics Co.](https://www.patton.com/microsoft/)|    Patton SmartNode eSBC   |     &#10004;     |         |      3.19.x      |     |    |
|                     [M5 Technologies (先前稱為 Media5 Corporation)](https://www.m5t.com/solutions/sentinel-sbc-ms-teams-certified/)|    Mediatrix Sentinel 系列   |     &#10004;     |         |      DGW 48.0.2340 (建議 DGW 48.1.2503)      |     |    |
|                     [Ekinops](https://www.ekinops.com/solutions/voice-data-access/microsoft-direct-routing-sbc)|    Ekinops Session Border Controller (ONeSBC)   |     &#10004;     |     &#10004;     |      6.6.1m5ha1      |     |    |
|                     |    Ekinops Virtual Session Border Controller (ONEvSBC)   |     &#10004;     |    &#10004;      |      6.6.1m5ha1      |     |    |
|                     [46 Labs LLC](https://46labs.com/docs/hcvoice/teams/)|    Hyperconverged Voice   |     &#10004;     |     &#10004;      |      HCVoice 1.0.6       |     |    |

<br/>

\* **911 服務提供者**

- [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing/)
- [Intrado 緊急路由服務 (ERS)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Intrado 緊急閘道 (EGW)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Inteliquent](https://www.inteliquent.com/services/emergency-services/e911)

<br/>

## <a name="support-for-local-media-optimization"></a>支援本機媒體最佳化

下表說明哪些 SBC 廠商支援[支援本機媒體最佳化](direct-routing-media-optimization.md)。 

| 廠商 | 產品 |    軟體版本 |
|:------------|:-------|:-------|
| [AudioCodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    Mediant 500 SBC |   7.20A.256 | 
|            |  Mediant 800 SBC |   7.20A.258 | 
|            |  Mediant 2600 SBC |  7.20A.258 | 
|            |  Mediant 4000 SBC |  7.20A.258 | 
|            |  Mediant 1000B SBC | 7.20A.256 | 
|            |  Mediant 9000 SBC |  7.20A.258 | 
|            |  Mediant Virtual Edition SBC |   7.20A.258 | 
|            |  Mediant Cloud Edition SBC | 7.20A.258 |
| [Ribbon SBC Core](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  SBC 5110         | 8.2  |
|            |  SBC 5210         | 8.2  |
|            |  SBC 5400         | 8.2  |
|            |  SBC 7000         | 8.2  |
|            |  SBC SWe          | 8.2  |
| [Ribbon SBC Edge](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  SBC SWe Lite | 8.1.5 |
|               | SBC 1000 | 8.1.5  |
|               | SBC 2000 | 8.1.5  |
| [TE-SYSTEMS](https://www.anynode.de/local_media_optimization/) |  anynode          | 4.0.1+ |
| [Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | AP 1100 | 8.4.0.0.0 |
|        | AP 3900 | 8.4.0.0.0 |
|        | AP 4600 | 8.4.0.0.0 | 
|        | AP 6300 | 8.4.0.0.0 |
|        | AP 6350 | 8.4.0.0.0 | 
|        | VME     | 8.4.0.0.0 |




## <a name="direct-routing-and-analog-devices-interoperability"></a>直接路由和類比裝置互通性

下表列出已驗證直接路由和類比裝置之間互通性的裝置。

|                                                       廠商                                                        |       產品       | 已驗證
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     | 
| [Cisco](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html) |  ATA 191 Multiplatform Analog Telephone Adapter |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |   AP1100 軟體版本 8.3.0.1.2 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP3900 軟體版本 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP4600 軟體版本 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6300 軟體版本 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6350 軟體版本 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  VME 軟體版本 8.3.0.1.2 |     &#10004;     |
| [功能區](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000。軟體版本：8.1.1 (組建 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [功能區](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000。軟體版本：8.1.1 (組建 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [功能區](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 302。軟體版本: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [功能區](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 304。軟體版本: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [功能區](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 2900A。軟體版本: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [功能區](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 4806。軟體版本: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [功能區](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 4808。軟體版本: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [功能區](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 6000. Software version: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) |  具有 Grandstream GXW42xx 的 anynode (V1.0.7.10) |     &#10004;     |
  
若要向我們提供有關 Teams 的產品意見反應，例如新功能的想法，請參閱 [Uservoice](https://microsoftteams.uservoice.com)。


[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

記下授予主要版本的認證。 這表示支援主要版本之後的 SBC 韌體中，具有任何編號的韌體。
