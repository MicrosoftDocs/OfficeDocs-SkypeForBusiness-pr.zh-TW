---
title: 認證以直接路由的會話邊界控制器
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
description: 系統管理員可以瞭解 (SBCs) 已驗證直接路由的會話框線控制器。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 256451e778ed0e5864a7144003d44eb7ffc28767
ms.sourcegitcommit: b8e697d52dcedace66cec2a06a5bd9889a780623
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2021
ms.locfileid: "49782536"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>通過直接路由認證的工作階段邊界控制器清單

使用選取的會話邊界控制器 (SBC) 廠商認證的 Microsoft 合作夥伴，以驗證其 SBCs 與直接佈線搭配運作。 

Microsoft 與各個廠商搭配： 

- 共同處理 SIP 互連通訊協定。
- 使用協力廠商實驗來執行重要測試。 只有經過測試的裝置才經過認證。 
- 在生產及生產環境中，在所有認證的裝置上執行每日測試。 驗證預先生產環境中的裝置，可保證雲端中直接路由程式碼的新版本可以搭配經過驗證的 SBCs 運作。 
- 與 SBC 供應商建立共同支援流程。


  > [!NOTE]
  > 如果認證的裝置或裝置是透過直接路由連線，Microsoft 只支援電話系統。 Microsoft 保留拒絕支援案例的權利，在未驗證的裝置透過直接佈線連線至電話系統時。 如果 Microsoft 認為客戶的直接路由問題是供應商的 SBC 裝置，客戶將需要與 SBC 供應商聯繫以取得支援。

下表列出認證以直接路由的裝置。  (有關哪些 SBC 廠商支援本機媒體優化的資訊，請參閱 [設定直接路由的本機媒體優化](direct-routing-media-optimization-configure.md)。 ) 

[深入瞭解直接路由](https://aka.ms/dr)。 如果您有任何關於 SBC 認證計畫直接路由的問題，請與 drsbccertification@microsoft.com。
<br/>
<br/>

|                                                       那裡                                                        |       產品       | 非媒體旁路 | 媒體旁路 | 軟體版本 | 已使用 E911 提供者驗證 | 支援 ELIN
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|
| [Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  支援的 7.20 7.20 (建議 258)    | <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> [Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul> |  &#10004;  |
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  支援的 7.20 7.20 (建議 258)    | <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  支援的 7.20 7.20 (建議 258)    |   <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>  |  &#10004;  |    
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  支援的 7.20 7.20 (建議 258)    |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>  |  &#10004;  |    
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   擱置     |  支援的 7.20 7.20 (建議 258)   |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>  |  &#10004;  |    
|                                                                                                                     | Mediant 9000 SBC  |     &#10004;     |   &#10004;     |  支援的 7.20 7.20 (建議 258)    | <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>    |  &#10004;  |                                                                       
|                                                                                                                     | 虛擬版 SBC |     &#10004;     |   &#10004;     |  支援的 7.20 7.20 (建議 258)  |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>   |  &#10004;  |    
|  [功能區通訊](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5100/5110       |     &#10004;     |   &#10004;    |       支援的8.2 和 7.2 (建議的 9.2)        | <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul> |    |    
|                                                                                                                     |      SBC 5200/5210       |     &#10004;     |  &#10004;    |       支援的8.2 和 7.2 (建議的 9.2)        |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li></ul> |    |    
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       支援的8.2 和 7.2 (建議的 9.2)        |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li><li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li></ul>  ||    
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       支援的8.2 和 7.2 (建議的 9.2)        |   <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li></ul> |  |    
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       支援的8.2 和 7.2 (建議的 9.2)           |   <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul> |    |    
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      ∞或 9. x     |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> [Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> </ul>   |  &#10004;   |    
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     ∞或 9. x     |  <ul> <li>[頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> [Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> </ul>   |     &#10004;     |    
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      ∞或 9. x    |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> [Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> </ul>    |     &#10004;     |   
| | EdgeMarc 數列 |  &#10004; | | 15.6.1 | 
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    思考 365 SBC    |     &#10004;     |           |       1.4       |     |    |    
|                     [聯手](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>   |  &#10004;  |    
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |    
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |    
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>   |  &#10004;  |    
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |                                            
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |    
|                     [TE-系統](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      支援的 3.20 (建議的 4.0)         |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>   |    |    
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   |  |      4.7      |     |    |  
|                     [Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     Cisco 統一框線元素 () 系列整合式服務路由器1000的 CUBE        |     &#10004;   |  |      IOS XE 阿姆斯特丹 17.2.1 r      |    <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>    |   |  
|                                   |     Cisco 統一框線元素 () 系列整合式服務路由器4000的 CUBE        |     &#10004;   |  |      IOS XE 阿姆斯特丹 17.2.1 r      |   <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>     |    |  
|                                   |     Cisco 整合框線元素 ([立方體]) 1000V Series 雲端服務路由器       |     &#10004;   |  |      IOS XE 阿姆斯特丹 17.2.1 r      |    <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>    |    |  
|                                 |     1000系列匯總服務路由器 (CUBE) 的 Cisco 整合框線元素      |     &#10004;   |  |      IOS XE 阿姆斯特丹 17.2.1 r      |    <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務 (ERS) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道 (EGW) ](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>    |    |
|                     [Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    企業 ( ASBCE 的 Avaya 會話框線控制器)     |     &#10004;     |           |       發行8.1。1       |     |    | 
|                     [Networks](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|    Nokia 會話邊界控制器    |     &#10004;     |           |       19.5 (1908)        |     |    | 
|                     [Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|    NetMatch CI     |     &#10004;     |           |       5.0       |     |    | 
|                     [Ericsson](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|    vSBC 2.16     |     &#10004;     |           |              |     |    | 
|                     [Cataleya](https://cataleya.com/orchidplatforms/)|    蘭花連結    |     &#10004;     |           |      3.1        |     |    | 
|                     [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|    團隊 SBC    |     &#10004;     |     &#10004;      |      1.6        |     |    | 

<br/>
<br/>
下表列出在直接路由和類比裝置之間驗證互通性的裝置。

|                                                       那裡                                                        |       產品       | 驗證
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     |
| [敷設](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000。軟體版本： 8.1.1 (組建 527) ](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [敷設](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000。軟體版本： 8.1.1 (組建 527) ](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [聯手](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |   AP1100 軟體版本8.3.0.1。2 |     &#10004;     |
  | [聯手](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP3900 軟體版本8.3.0.1。2|     &#10004;     |
  | [聯手](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP4600 軟體版本8.3.0.1。2|     &#10004;     |
  | [聯手](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6300 軟體版本8.3.0.1。2|     &#10004;     |
  | [聯手](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6350 軟體版本8.3.0.1。2|     &#10004;     |
  | [聯手](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  VME 軟體版本8.3.0.1。2 |     &#10004;     |
  | [TE-系統](https://www.anynode.de/anynode-and-microsoft-teams/) |  anynode 與 Grandstream GXW42xx (V 1.0.7.10)  |     &#10004;     |

若要向我們的小組提供產品意見反應，例如新功能的想法，請參閱 [Uservoice](https://microsoftteams.uservoice.com)。
請注意授予主要版本的認證。 這表示支援在主要版本之後，在 SBC 固件中有任何數位的固件。
