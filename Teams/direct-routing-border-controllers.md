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
ms.openlocfilehash: 4c3d4f3b10d2e0e4fb70db1ab7f8eb0fccc8c3d6
ms.sourcegitcommit: e9718ad7e23317d490b238b3801267cb2e6b26e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2022
ms.locfileid: "69176700"
---
# <a name="session-border-controllers-certified-for-direct-routing"></a>通過直接路由認證的工作階段邊界控制器

Microsoft 與選取的工作階段邊界控制器 (SBC) 廠商合作，以認證其 SBC 可搭配直接路由使用。

Microsoft 可與每個廠商合作，以：

- 共同處理 SIP 互相連線通訊協定。
- 使用協力廠商實驗室執行大量測試。 只有通過測試的裝置才會通過認證。
- 在生產與生產前環境中，使用所有通過認證的裝置執行每日測試。 在生產前環境中驗證裝置可確保雲端中新版本的直接路由程式碼可搭配認證的 SBC 使用。
- 與 SBC 廠商建立聯合支援流程。

  > [!NOTE]
  > 與認證裝置一起使用時，Microsoft 僅支援具有直接路由的電話系統。 如果發生問題，您必須先與您的 SBC 廠商的客戶支援聯繫。 如有必要，SBC 廠商會透過內部管道將問題呈報給 Microsoft。 Microsoft 保留拒絕非認證裝置透過直接路由連接到電話系統的支援案例的權利。 如果 Microsoft 判斷客戶的直接路由問題與廠商的 SBC 裝置有關，則客戶需要與 SBC 廠商重新聯繫以尋求支援。
  >
  > 認證會授予特定 SBC 韌體版本。 以下記載的任何 SBC 韌體版本都經過認證且受支援。 只要主要、次要版本相同，就支援高於所記載的韌體版本。
  >
  > 範例：
  >
  > - 支援的 6.10.258 - 在此案例中，Microsoft 支援 6.10 版的韌體。(258 或更高)。
  > - 建議版本 6.20.100 - 在此案例中，Microsoft 建議使用 6.20 版。(100 或更高)。
  > - 有關特定版本的支援問題，請與 SBC 廠商聯繫。

遵循經過直接路由認證之裝置清單的資料表。 (如需有關哪些 SBC 廠商支援本機媒體最佳化的資訊，請參閱[設定直接路由的本機媒體最佳化](direct-routing-media-optimization-configure.md))。

[深入了解直接路由](https://aka.ms/dr)。

請注意，在進一步通知之前，我們不會接受新的認證提名。

## <a name="certified-sbc-vendors"></a>認證的 SBC 廠商

|廠商|產品|非媒體旁路|媒體旁路|軟體版本|支援 911 服務提供者*|支援 ELIN|
|---|---|---|---|---|---|---|
|[AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)|Mediant 500 SBC|&#10004;|&#10004;|支援 7.20A.258 (建議 7.40A.250 或 7.40A.300) |&#10004;|&#10004;|
||Mediant 800 SBC|&#10004;|&#10004;|支援 7.20A.258 (建議 7.40A.250 或 7.40A.300) |&#10004;|&#10004;|
||Mediant 2600 SBC|&#10004;|&#10004;|支援 7.20A.258 (建議 7.40A.250 或 7.40A.300) |&#10004;|&#10004;|
||Mediant 4000 SBC|&#10004;|&#10004;|支援 7.20A.258 (建議 7.40A.250 或 7.40A.300) |&#10004;|&#10004;|
||Mediant 1000B  SBC|&#10004;|&#10004;|支援 7.20A.258 (建議 7.40A.250 或 7.40A.300) |&#10004;|&#10004;|
||Mediant 9000  SBC|&#10004;|&#10004;|支援 7.20A.258 (建議 7.40A.250 或 7.40A.300) |&#10004;|&#10004;|
||Virtual Edition SBC|&#10004;|&#10004;|支援 7.20A.258 (建議 7.40A.250 或 7.40A.300) |&#10004;|&#10004;|
||Mediant Cloud Edition SBC|&#10004;|&#10004;|支援 7.20A.258 (建議 7.40A.250 或 7.40A.300) |&#10004;|&#10004;|
|[Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)|SBC 5100/5110|&#10004;|&#10004;|支援 10.1、9.2、8.2 和 7.2 的所有版本 (建議最新版本的 10.1) |&#10004;||
||SBC 5200/5210|&#10004;|&#10004;|支援 10.1、9.2、8.2 和 7.2 的所有版本 (建議最新版本的 10.1) |&#10004;||
||SBC 5400|&#10004;|&#10004;|支援 10.1、9.2、8.2 和 7.2 的所有版本 (建議最新版本的 10.1) ) |&#10004;||
||SBC 7000|&#10004;|&#10004;|支援 10.1、9.2、8.2 和 7.2 的所有版本 (建議最新版本的 10.1) |&#10004;||
||所有 SBC SWe 變體，包括託管優惠|&#10004;|&#10004;|支援 10.1、9.2、8.2 和 7.2 的所有版本 (建議最新版本的 10.1) |&#10004;||
||SBC 1000|&#10004;|&#10004;|8.x、9.x 或 11.x|&#10004;|&#10004;|
||SBC 2000|&#10004;|&#10004;|8.x、9.x 或 11.x|&#10004;|&#10004;|
||SBC SWe Edge (舊稱 SWe Lite) |&#10004;|&#10004;|8.x、9.x 或 11.x|&#10004;|&#10004;|
||EdgeMarc 系列|&#10004;|&#10004;|16.3.2||
|[Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)|Think 365 SBC|&#10004;||1.4|||
|[Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)|AP 1100|&#10004;|&#10004;|支援  8.3.0.0.1 和建議使用 8.4.x & 9.x|&#10004;|&#10004;|
||AP 3900|&#10004;|&#10004;|支援  8.3.0.0.1 和建議使用 8.4.x & 9.x|&#10004;|&#10004;|
||AP 4600|&#10004;|&#10004;|支援  8.3.0.0.1 和建議使用 8.4.x & 9.x|&#10004;|&#10004;|
||AP 6300|&#10004;|&#10004;|支援  8.3.0.0.1 和建議使用 8.4.x & 9.x|&#10004;|&#10004;|
||AP 6350|&#10004;|&#10004;|支援  8.3.0.0.1 和建議使用 8.4.x & 9.x|&#10004;|&#10004;|
||VME|&#10004;|&#10004;|支援  8.3.0.0.1 和建議使用 8.4.x & 9.x|&#10004;|&#10004;|
||AP 3950|&#10004;|&#10004;|支援 9.x|&#10004;|&#10004;|
||AP 4900|&#10004;|&#10004;|支援 9.x|&#10004;|&#10004;|
|[TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)|anynode|&#10004;|&#10004;|支援 3.20 (建議 4.0)|&#10004;|&#10004;|
|[Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)|Perimeta SBC|&#10004;|&#10004;|4.7 (4.9 用於媒體旁路)|&#10004;|&#10004;|
|[Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)|適用於 1000 系列整合式服務路由器的 Cisco Unified Border Element (CUBE)|&#10004;|&#10004;|支援 IOS XE Amsterdam 17.2.1r (建議 17.6.1a)|&#10004;||
||適用於 4000 系列整合式服務路由器的 Cisco Unified Border Element (CUBE)|&#10004;|&#10004;|支援 IOS XE Amsterdam 17.2.1r (建議 17.6.1a)|&#10004;||
||適用於 1000V 系列雲端服務路由器的 Cisco Unified Border Element (CUBE)|&#10004;|&#10004;|支援 IOS XE Amsterdam 17.2.1r (建議 17.3.3)|&#10004;||
||適用於 1000 系列彙總服務路由器的 Cisco Unified Border Element (CUBE)|&#10004;|&#10004;|支援 IOS XE Amsterdam 17.2.1r (建議 17.6.1a)|&#10004;||
||適用於 Catalyst 8000 邊緣平台的 Cisco Unified Border Element (CUBE)|&#10004;|&#10004;|支援 IOS XE Amsterdam 17.3.2 (建議 17.6.1a)|&#10004;||
|[Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|Avaya Session Border Controller for Enterprise (ASBCE)|&#10004;|&#10004;|8.1.1 版 (8.1.2 用於媒體旁路)|||
|[Nokia](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|Nokia 工作階段邊界控制器|&#10004;|&#10004;|22.0|&#10004;||
|[Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|NetMatch-S CI|&#10004;|&#10004;|支援 5.0、5.1 (建議 5.3)|||
|[Ericsson](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|vSBC 2.16|&#10004;|||||
|[Cataleya](https://cataleya.com/orchidplatforms/)|Orchid Link|&#10004;||3.1|||
|[ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|Teams SBC|&#10004;|&#10004;|1.6|||
|[Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|Atos Unify OpenScape 工作階段邊界控制器|&#10004;|&#10004;|V10R2.2.0|||
|[Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|vmVSXi|&#10004;|&#10004;|10.5.1.354-vm-S-x64|&#10004;||
|[Enghouse Networks](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|Dialogic BorderNet SBC|&#10004;|&#10004;|3.9.x|||
|[Patton Electronics Co.](https://www.patton.com/microsoft/)|Patton SmartNode eSBC|&#10004;||3.19.x|||
|[M5 Technologies (先前稱為 Media5 Corporation)](https://www.m5t.com/solutions/sentinel-sbc-ms-teams-certified/)|Mediatrix Sentinel 系列|&#10004;||DGW 48.0.2340 (建議 DGW 48.1.2503)|||
|[Ekinops](https://www.ekinops.com/solutions/voice-data-access/microsoft-direct-routing-sbc)|Ekinops Session Border Controller (ONeSBC)|&#10004;|&#10004;|支援的 6.8.x (建議使用 6.9.x) |||
||Ekinops Virtual Session Border Controller (ONEvSBC)|&#10004;|&#10004;|支援 6.6.1m5ha1 (建議 6.8.x)|||
|[46 Labs LLC](https://46labs.atlassian.net/wiki/spaces/peeredge/pages/61603842/Microsoft+Teams+Implementation+Guide+v1.0)|Peeredge Orchestrator|&#10004;|&#10004;|1.0.6|||
|[Frafos](https://www.frafos.com/ms-teams-abc-sbc)|ABC SBC|&#10004;||4.6|||

<br/>

\* **911 服務提供者**

- [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing/)
- [Intrado 緊急路由服務 (ERS)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Intrado 緊急閘道 (EGW)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Inteliquent](https://www.inteliquent.com/services/emergency-services/e911)

## <a name="support-for-local-media-optimization"></a>支援本機媒體最佳化

下表說明哪些 SBC 廠商支援[支援本機媒體最佳化](direct-routing-media-optimization.md)。

|廠商|產品|軟體版本|
|:---|:---|:---|
|[AudioCodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)|Mediant 500 SBC|7.20A.256|
||Mediant 800 SBC|支援 7.20A.258 (建議 7.40A.100)|
||Mediant 2600 SBC|支援 7.20A.258 (建議 7.40A.100)|
||Mediant 4000 SBC|支援 7.20A.258 (建議 7.40A.100)|
||Mediant 1000B SBC|支援 7.20A.258 (建議 7.40A.100)|
||Mediant 9000 SBC|支援 7.20A.258 (建議 7.40A.100)|
||Mediant Virtual Edition SBC|支援 7.20A.258 (建議 7.40A.100)|
||Mediant Cloud Edition SBC|支援 7.20A.258 (建議 7.40A.100)|
|[Ribbon SBC Core](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)|SBC 5110|8.2 或更新版本的 SW|
||SBC 5210|8.2 或更新版本的 SW|
||SBC 5400|8.2 或更新版本的 SW|
||SBC 7000|8.2 或更新版本的 SW |
||SBC SWe|8.2 或更新版本的 SW|
|[Ribbon SBC Edge](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)|SBC SWe Edge (舊稱 SWe Lite) |8.1.5 或更新版本的 SW|
||SBC 1000|8.1.5 或更新版本的 SW|
||SBC 2000|8.1.5 或更新版本的 SW|
|[TE-SYSTEMS](https://www.anynode.de/local_media_optimization/)|anynode|4.0.1+|
|[Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html)|AP 1100|8.4.0.0.0|
||AP 3900|8.4.0.0.1 和  9.x|
||AP 4600|8.4.0.0.1 和  9.x|
||AP 6300|8.4.0.0.1 和  9.x|
||AP 6350|8.4.0.0.1 和  9.x|
||VME|8.4.0.0.1 和  9.x|
||AP 3950|9.x|
||AP 4900|9.x|
|[Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|Avaya Session Border Controller for Enterprise (ASBCE)|10.1.2|

## <a name="direct-routing-and-analog-devices-interoperability"></a>直接路由和類比裝置互通性

下表列出已驗證直接路由和類比裝置之間互通性的裝置。

|廠商|產品|已驗證
|---|---|---|
|[AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)|[ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)|&#10004;|
|[AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)|[ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)|&#10004;|
|[Cisco](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html)|ATA 191 Multiplatform Analog Telephone Adapter|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 1100 軟體版本支援 8.3.0.1.2 和建議使用 8.4.x 或 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 3900 軟體版本支援 8.3.0.1.2 和建議使用 8.4.x 或 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 4600 軟體版本支援 8.3.0.1.2 和建議使用 8.4.x 或 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 6300 軟體版本支援 8.3.0.1.2 和建議使用 8.4.x 或 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 6350 軟體版本支援 8.3.0.1.2 和建議使用 8.4.x 或 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|VME 軟體版本支援 8.3.0.1.2 和建議使用 8.4.x 或  9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 3950 軟體版支援 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 4900 軟體版支援 9.x|&#10004;|
|[功能區](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[SBC 1000。軟體版本：8.1.1 (組建 527) 或更新版本的 SW 版本](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)|&#10004;|
|[功能區](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[SBC 2000。軟體版本：8.1.1 (組建 527) 或更新版本的 SW 版本](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)|&#10004;|
|[功能區](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 302。軟體版本：16.1.1 或更新版本的 SW 版本](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[功能區](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 304。軟體版本：16.1.1 或更新版本的 SW 版本](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[功能區](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 2900A。軟體版本：16.1.1 或更新版本的 SW 版本](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[功能區](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 4806。軟體版本：16.1.1 或更新版本的 SW 版本](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[功能區](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 4808。軟體版本：16.1.1 或更新版本的 SW 版本](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[功能區](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 6000。軟體版本：16.1.1 或更新版本的 SW 版本](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)|具有 Grandstream GXW42xx 的 anynode (V1.0.7.10)|&#10004;|

記下授予主要版本的認證。 這表示支援主要版本之後的 SBC 韌體中，具有任何編號的韌體。

如需提供有關 Teams 的產品意見反應，例如新功能的想法，請參閱 [Microsoft 意見反應入口網站](https://feedbackportal.microsoft.com/)。

> [!NOTE]
> 不支援媒體重新設定目標。 在直接路由通話期間，如果 SBC 傳送新的媒體 IP 至 Teams 直接路由，雖然是在 SIP 訊號中交涉，但媒體永遠不會從 Teams 直接路由傳送至新的 IP 位址。
