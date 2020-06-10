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
description: 系統管理員可以瞭解哪個會話邊界控制器（SBCs）已認證以進行直接路由。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 35ce7be2c99ad0de9da3d397c8b6aed28a3634bc
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666095"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>通過直接路由認證的工作階段邊界控制器清單

Microsoft 合作夥伴與選取的會話邊界控制器（SBC）廠商確認其 SBCs 可搭配直接佈線。 

Microsoft 與各個廠商搭配： 

- 共同處理 SIP 互連通訊協定。
- 使用協力廠商實驗來執行重要測試。 只有經過測試的裝置才經過認證。 
- 在生產及生產環境中，在所有認證的裝置上執行每日測試。 驗證預先生產環境中的裝置，可保證雲端中直接路由程式碼的新版本可以搭配經過驗證的 SBCs 運作。 
- 與 SBC 供應商建立共同支援流程。


  > [!NOTE]
  > 如果認證的裝置或裝置是透過直接路由連線，Microsoft 只支援電話系統。 Microsoft 保留拒絕支援案例的權利，在未驗證的裝置透過直接佈線連線至電話系統時。 

下表列出認證以直接路由的裝置。 

[深入瞭解直接路由](https://aka.ms/dr)。 如果您對用於直接路由的 SBC 認證程式有任何疑問，請與 drsbccertification@microsoft.com。


|                                                       那裡                                                        |       產品       | 非媒體旁路 | 媒體旁路 | 軟體版本 | 已使用 E911 提供者驗證 | 支援 ELIN
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|
| [Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  支援的7.20 為250（建議7.20）   | <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> [Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul> |  &#10004;  |
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  支援的7.20 為250（建議7.20）   | <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  支援的7.20 為250（建議7.20）   |   <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>  |  &#10004;  |    
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  支援的7.20 為250（建議7.20）   |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>  |  &#10004;  |    
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   擱置     |  支援的7.20 為250（建議7.20）  |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>  |  &#10004;  |    
|                                                                                                                     | Mediant 9000 SBC  |     &#10004;     |   &#10004;     |  支援的7.20 為250（建議7.20）   | <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>    |  &#10004;  |                                                                       
|                                                                                                                     | 虛擬版 SBC |     &#10004;     |   &#10004;     |  支援的7.20 為250（建議7.20） |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>   |  &#10004;  |    
|  [功能區通訊](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5110       |     &#10004;     |   &#10004;    |       支援的7.2 （建議的8.2）       | <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul> |    |    
|                                                                                                                     |      SBC 5210       |     &#10004;     |  &#10004;    |       支援的7.2 （建議的8.2）       |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li></ul> |    |    
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       支援的7.2 （建議的8.2）       |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li><li>[Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li></ul>  ||    
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       支援的7.2 （建議的8.2）       |   <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li></ul> |  |    
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       支援的7.2 （建議的8.2）       |   <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul> |    |    
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.0.3 （組建537）     |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> [Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> </ul>   |  &#10004;   |    
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.0.3 （組建537）     |  <ul> <li>[頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> [Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> </ul>   |     &#10004;     |    
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.0.3 （組建216）    |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> [Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> </ul>    |     &#10004;     |   
| | EdgeMarc 數列 |  &#10004; | | 15.6.1 | 
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    思考 365 SBC    |     &#10004;     |           |       1.4       |     |    |    
|                     [聯手](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>   |  &#10004;  |    
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |    
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |    
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li> </ul>   |  &#10004;  |    
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |                                            
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   <ul> <li> [頻寬動態位置路由](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>[Intrado 緊急路由服務（ERS）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/) </li> <li>[Intrado 緊急閘道（EGW）](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)</li>  </ul>  |  &#10004;  |    
|                     [TE-系統](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      支援的3.20 （建議的4.0）        |     |    |    
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   |  |      4.7      |     |    |    

下表列出在直接路由和類比裝置之間驗證互通性的裝置。

|                                                       那裡                                                        |       產品       | 驗證
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     |
| [敷設](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000。軟體版本：8.1.1 （組建527）](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [敷設](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000。軟體版本：8.1.1 （組建527）](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |


若要向我們的小組提供產品意見反應，例如新功能的想法，請參閱[Uservoice](https://microsoftteams.uservoice.com)。
請注意授予主要版本的認證。 這表示支援在主要版本之後，在 SBC 固件中有任何數位的固件。
