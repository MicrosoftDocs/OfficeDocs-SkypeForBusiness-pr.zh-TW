---
title: 會話邊界控制器已通過直接路由認證
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: 系統管理員可以瞭解哪些會話邊界控制器 (SBC) 直接路由認證。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 97a3c69f6fee5b14e5c2252b51b9b17d8a810799
ms.sourcegitcommit: 41e2e97b5856e727e42ebf5bfebceede9af56481
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53388658"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>通過直接路由認證的工作階段邊界控制器清單

Microsoft 與已選取的會話邊界控制器 (SBC) 廠商合作，以認證其 SBC 使用直接路由。

Microsoft 會與每個廠商合作，以：

- 共同處理 SIP 互連通訊協定。
- 使用協力廠商實驗室執行強烈的測試。 只有通過測試的裝置才通過認證。
- 在生產與生產前環境中，使用所有通過認證的裝置執行每日測試。 在生產前環境中驗證裝置，可確保雲端中新版本的直接路由程式碼可與認證 SBCs 一起使用。
- 與 SBC 廠商建立共同支援程式。

  > [!NOTE]
  > Microsoft 僅支援電話系統通過直接路由連結的裝置或裝置時，才能使用此連結。 Microsoft 保留拒絕未通過認證的裝置透過直接路由電話系統支援案例。 如果 Microsoft 判斷客戶的直接路由問題與廠商的 SBC 裝置有關，客戶將需要與 SBC 廠商聯繫以提供支援。

遵循已認證直接路由之清單裝置的資料表。  (有關哪些 SBC 廠商支援 Local Media 優化的資訊，請參閱設定直接路由的當地媒體優化[.) ](direct-routing-media-optimization-configure.md)

[深入瞭解直接路由](https://aka.ms/dr)。
如果您對直接路由的 SBC 認證計畫有任何疑問，請 drsbccertification@microsoft.com。
<br/>

## <a name="certified-sbc-vendors"></a>經過認證的 SBC 廠商

|                                                       供應商                                                        |       產品       | 非媒體旁路 | 媒體旁路 | 軟體版本 | 支援 911 服務提供者* | ELIN 支援
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|
| [音訊代碼](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  支援 7.20A.250 (建議使用 7.20A.258)    | &#10004;   |  &#10004;  |
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  支援 7.20A.250 (建議使用 7.20A.258)    | &#10004;   |  &#10004;  |
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  支援 7.20A.250 (建議使用 7.20A.258)    |   &#10004;   |  &#10004;  |    
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  支援 7.20A.250 (建議使用 7.20A.258)    |  &#10004;   |  &#10004;  |    
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   等待     |  支援 7.20A.250 (建議使用 7.20A.258)   |  &#10004;   |  &#10004;  |    
|                                                                                                                     | Mediant 9000 SBC  |     &#10004;     |   &#10004;     |  支援 7.20A.250 (建議使用 7.20A.258)    | &#10004;     |  &#10004;  |                                                                       
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  支援 7.20A.250 (建議使用 7.20A.258)  |  &#10004;    |  &#10004;  |    
|  [功能區通訊](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5100/5110       |     &#10004;     |   &#10004;    |       支援 8.2 和 7.2 (建議 9.2)        | &#10004;   |     |    
|                                                                                                                     |      SBC 5200/5210       |     &#10004;     |  &#10004;    |       支援 8.2 和 7.2 (建議 9.2)        |   &#10004; |    |    
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       支援 8.2 和 7.2 (建議 9.2)        |   &#10004;  ||    
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       支援 8.2 和 7.2 (建議 9.2)        |    &#10004;  |  |    
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       支援 8.2 和 7.2 (建議 9.2)           |  &#10004;    |    |    
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.x 或 9.x     |   &#10004;  |  &#10004;     |    
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.x 或 9.x     |   &#10004;   |     &#10004;     |    
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.x 或 9.x    |   &#10004;    |     &#10004;     |   
| | EdgeMarc 數列 |  &#10004; | | 15.6.1 | 
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    思考 365 SBC    |     &#10004;     |           |       1.4       |     |    |    
|                     [甲骨文](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   &#10004;    |  &#10004;  |    
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  &#10004;    |  &#10004;  |    
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |    
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |    
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   &#10004;   |  &#10004;  |                                            
|                                                                                                                    |      Vme           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   &#10004;   |  &#10004;  |    
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      支援 3.20 (建議 4.0)         |  &#10004;    |  &#10004;   |    
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   | &#10004; |      4.7 (4.9 適用于媒體旁路)       |     |    |  
|                     [思科](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     1000 系列整合式服務路由器 (CUBE) 整合的 Cisco Unified Border 元素        |     &#10004;   | &#10004; |      支援的 IOS XE Amsterdam 17.2.1r (建議 17.3.2)          |    &#10004;     |   |  
|                                   |     Cisco Unified Border Element (CUBE) 4000 系列整合式服務路由器        |     &#10004;   | &#10004; |   支援的 IOS XE Amsterdam 17.2.1r (建議 17.3.2)          |   &#10004;      |    |  
|                                   |     1000V 系列雲端服務路由器 (CUBE) 的 Cisco Unified Border 元素       |     &#10004;   | &#10004; |      支援的 IOS XE Amsterdam 17.2.1r (建議 17.3.2)          |    &#10004;     |    |  
|                                 |     適用于 1000 系列匯總服務路由器 (CUBE) 整合 Border 元素      |     &#10004;   | &#10004; |      支援的 IOS XE Amsterdam 17.2.1r (建議 17.3.2)          |    &#10004;     |    |
|                                 |     Cisco Unified Border Element (CUBE) 11000 Edge 平臺      |     &#10004;   | &#10004; |      IOS XE Amsterdam 17.3.2      |    &#10004;     |    |
|                     [Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    適用于 ASBCE Enterprise ( Avaya 會話) 控制器)     |     &#10004;     |       &#10004;     |       第 8.1.1 (8.1.2 版媒體旁路)       |     |    | 
|                     [諾基亞](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|    Nokia 會話邊界控制器    |     &#10004;     |           |       1908 (19.5)        |     |    | 
|                     |    Nokia 會話邊界控制器    |     &#10004;     |           |       20.8       |      &#10004;        |    | 
|                     [Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|    NetMatch-S CI     |     &#10004;     |           |       支援 5.0 (建議 5.1)      |     |    | 
|                     [愛立信](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|    vSBC 2.16     |     &#10004;     |           |              |     |    | 
|                     [Cataleya](https://cataleya.com/orchidplatforms/)|    蘭花連結    |     &#10004;     |           |      3.1        |     |    | 
|                     [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|    TeamsSbc    |     &#10004;     |     &#10004;      |      1.6        |     |    | 
|                     [Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|    Atos Unify OpenScape 會話邊界控制器   |     &#10004;     |          |      V10R1.2       |     |    | 
|                     [Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|    vmVSXi   |     &#10004;     |     &#10004;     |      10.5.1.354-vm-S-x64      |     |    |
|                     [Enghouse Networks](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|    對話方塊 BorderNet SBC   |     &#10004;     |     &#10004;     |      3.9.0-786      |     |    |
|                     [巴頓電子公司。](https://www.patton.com/microsoft/)|    巴頓 SmartNode eSBC   |     &#10004;     |         |      3.19.x      |     |    |
|                     [M5 技術 (先前稱為 Media5 Corporation) ](https://www.m5t.com/solutions/sentinel-sbc-ms-teams-certified/)|    Mediatrix Sentinel 系列   |     &#10004;     |         |      DGW 48.0.2340 (建議 DGW 48.1.2503)       |     |    |

<br/>
* 911 個服務提供者

- [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing/)
- [ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [內部緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
<br/>

## <a name="direct-routing-and-analog-devices-interoperability"></a>直接路由和類比裝置互通性

下表列出已驗證直接路由和類比裝置之間互通性的裝置。

|                                                       供應商                                                        |       產品       | 驗證
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [音訊代碼](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [音訊代碼](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     | 
| [思科](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html) |  ATA 191 多平臺類比電話配接器 |     &#10004;     |
| [甲骨文](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |   AP1100 軟體版本 8.3.0.1.2 |     &#10004;     |
| [甲骨文](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP3900 軟體版本 8.3.0.1.2|     &#10004;     |
| [甲骨文](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP4600 軟體版本 8.3.0.1.2|     &#10004;     |
| [甲骨文](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6300 軟體版本 8.3.0.1.2|     &#10004;     |
| [甲骨文](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6350 軟體版本 8.3.0.1.2|     &#10004;     |
| [甲骨文](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  VME 軟體版本 8.3.0.1.2 |     &#10004;     |
| [絲帶](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000。軟體版本：8.1.1 (527) ](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [絲帶](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000。軟體版本：8.1.1 (527) ](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) |  使用 Grandstream GXW42xx (V1.0.7.10)  |     &#10004;     |
  
若要針對新功能提供產品Teams，例如新功能的構想，請參閱[Uservoice](https://microsoftteams.uservoice.com)。


[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

請注意授予主要版本的認證。 這表示支援主要版本之後 SBC 中任何號碼的固件。
