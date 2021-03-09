---
title: 通過直接路由認證的會話邊界控制器
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
description: 系統管理員可以瞭解哪些會話邊界控制器 (SBC) 通過直接路由認證。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 31a9003015fc9f9d6f12595e313022c305faab8a
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568929"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>通過直接路由認證的工作階段邊界控制器清單

Microsoft 與選取的會話邊界控制器 (SBC) 廠商合作，以認證其 SBC 能使用直接路由。 

Microsoft 會與每個廠商合作，以：

- 共同處理 SIP 互連通訊協定。
- 使用協力廠商實驗室執行強度測試。 只有通過測試的裝置才通過認證。 
- 在生產與生產前環境中，使用所有通過認證的裝置執行每日測試。 在生產前環境中驗證裝置，可確保雲端中新版直接路由代碼可與通過認證的 SBC 一起使用。 
- 與 SBC 廠商建立共同支援程式。


  > [!NOTE]
  > Microsoft 只有在通過認證的裝置或裝置透過直接路由進行連接時，才支援電話系統。 Microsoft 保留拒絕未通過認證的裝置透過直接路由連接至電話系統的支援案例的權利。 如果 Microsoft 判斷客戶的直接路由問題與廠商的 SBC 裝置有關，客戶將需要與 SBC 廠商聯繫以提供支援。

下表列出通過直接路由認證的裝置。  (哪些 SBC 廠商支援本地媒體優化， [請參閱設定直接](direct-routing-media-optimization-configure.md)路由 .) 

[深入瞭解直接路由](https://aka.ms/dr)。 如果您對直接路由的 SBC 認證計畫有任何疑問，請drsbccertification@microsoft.com。
<br/>
<br/>

|                                                       供應商                                                        |       產品       | 非媒體旁路 | 媒體旁路 | 軟體版本 | 已與 E911 提供者驗證 | 支援 ELIN
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  支援 7.20A.250 (7.20A.258)    | <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> [ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul> |  &#10004;  |
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  支援 7.20A.250 (7.20A.258)    | <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  支援 7.20A.250 (7.20A.258)    |   <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>  |  &#10004;  |    
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  支援 7.20A.250 (7.20A.258)    |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>  |  &#10004;  |    
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   等待     |  支援 7.20A.250 (7.20A.258)   |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>  |  &#10004;  |    
|                                                                                                                     | Mediant 9000 SBC  |     &#10004;     |   &#10004;     |  支援 7.20A.250 (7.20A.258)    | <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>    |  &#10004;  |                                                                       
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  支援 7.20A.250 (7.20A.258)  |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>   |  &#10004;  |    
|  [功能區通訊](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5100/5110       |     &#10004;     |   &#10004;    |       支援 8.2 和 7.2 (建議 9.2)        | <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul> |    |    
|                                                                                                                     |      SBC 5200/5210       |     &#10004;     |  &#10004;    |       支援 8.2 和 7.2 (建議 9.2)        |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li></ul> |    |    
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       支援 8.2 和 7.2 (建議 9.2)        |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li><li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li></ul>  ||    
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       支援 8.2 和 7.2 (建議 9.2)        |   <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li></ul> |  |    
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       支援 8.2 和 7.2 (建議 9.2)           |   <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul> |    |    
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.x 或 9.x     |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> [ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> </ul>   |  &#10004;   |    
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.x 或 9.x     |  <ul> <li>[頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> [ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> </ul>   |     &#10004;     |    
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.x 或 9.x    |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> [ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> </ul>    |     &#10004;     |   
| | EdgeMarc 數列 |  &#10004; | | 15.6.1 | 
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |           |       1.4       |     |    |    
|                     [甲骨文](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>   |  &#10004;  |    
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |    
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |    
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>   |  &#10004;  |    
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |                                            
|                                                                                                                    |      Vme           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |    
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      支援 3.20 (建議 4.0)         |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>   |  &#10004;   |    
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   |  |      4.7      |     |    |  
|                     [思科](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     Cisco Unified Border Element (CUBE) 1000 系列整合式服務路由器        |     &#10004;   | &#10004; |      支援的 IOS XE 周遊 17.2.1r (建議 17.3.2)          |    <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>    |   |  
|                                   |     Cisco Unified Border Element (CUBE) 4000 系列整合式服務路由器        |     &#10004;   | &#10004; |   支援的 IOS XE 周遊 17.2.1r (建議 17.3.2)          |   <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>     |    |  
|                                   |     Cisco Unified Border Element (CUBE) 1000V 系列雲端服務路由器       |     &#10004;   | &#10004; |      支援的 IOS XE 周遊 17.2.1r (建議 17.3.2)          |    <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>    |    |  
|                                 |     Cisco Unified Border Element (CUBE) 1000 系列匯總服務路由器      |     &#10004;   | &#10004; |      支援的 IOS XE 周遊 17.2.1r (建議 17.3.2)          |    <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>    |    |
|                                 |     Cisco Unified Border Element (Cube) 8000 Edge 平臺      |     &#10004;   | &#10004; |      IOS XE 周遊 17.3.2      |    <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>    |    |
|                     [Avya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    Avya 會話 Border Controller for Enterprise ( ASBCE)     |     &#10004;     |           |       版本 8.1.1       |     |    | 
|                     [諾基亞](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|    Nokia 會話邊界控制器    |     &#10004;     |           |       1908 (19.5)        |     |    | 
|                     |    Nokia 會話邊界控制器    |     &#10004;     |           |       20.8       |      <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[ERS (內緊急路由服務) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[EGW (內緊急閘道) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>       |    | 
|                     [Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|    NetMatch-S CI     |     &#10004;     |           |       支援 5.0 (建議 5.1)      |     |    | 
|                     [愛立信](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|    vSBC 2.16     |     &#10004;     |           |              |     |    | 
|                     [Cataleya](https://cataleya.com/orchidplatforms/)|    Orchid Link    |     &#10004;     |           |      3.1        |     |    | 
|                     [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|    Teams SBC    |     &#10004;     |     &#10004;      |      1.6        |     |    | 
|                     [Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|    Atos Unify OpenScape 會話邊界控制器   |     &#10004;     |          |      V10R1.2       |     |    | 
|                     [San用 Inc.](https://www.sansay.com/solutions/microsoft-teams/)|    vmVSXi   |     &#10004;     |     &#10004;     |      10.5.1.354-vm-S-x64      |     |    |

<br/>
<br/>
下表列出已驗證直接路由與類比裝置之間互通性的裝置。

|                                                       供應商                                                        |       產品       | 驗證
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     |
| [絲帶](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000。軟體版本：8.1.1 (527) ](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [絲帶](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000。軟體版本：8.1.1 (527) ](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [甲骨文](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |   AP1100 軟體版本 8.3.0.1.2 |     &#10004;     |
  | [甲骨文](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP3900 軟體版本 8.3.0.1.2|     &#10004;     |
  | [甲骨文](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP4600 軟體版本 8.3.0.1.2|     &#10004;     |
  | [甲骨文](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6300 軟體版本 8.3.0.1.2|     &#10004;     |
  | [甲骨文](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6350 軟體版本 8.3.0.1.2|     &#10004;     |
  | [甲骨文](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  VME 軟體版本 8.3.0.1.2 |     &#10004;     |
  | [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) |  使用 Grandstream GXW42xx (V1.0.7.10)  |     &#10004;     |
  | [思科](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html) |  ATA 191 多平臺類比電話轉接器 |     &#10004;     |
  
若要提供有關 Teams 的產品意見，例如新功能的構想，請參閱[Uservoice。](https://microsoftteams.uservoice.com)
請注意，授予主要版本的認證。 這表示支援主要版本之後 SBC 中任何號碼的內建。
