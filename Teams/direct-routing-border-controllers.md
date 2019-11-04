---
title: 通過直接路由認證的工作階段邊界控制器清單
ms.author: crowe
ms.reviewer: NMuravlyannikov
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
description: Microsoft 合作夥伴與所選的 SBC 廠商合作，利用直接佈線來認證其 SBCs。
ms.openlocfilehash: 5fa0cb728beed0f308a4d168cd149ef1e75e2809
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "37572242"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>通過直接路由認證的工作階段邊界控制器清單

Microsoft 合作夥伴與選取的會話邊界控制器（SBC）廠商確認其 SBCs 可搭配直接佈線。 

針對每個供應商，Microsoft： 

- 在 SIP 互連通訊協定上與 SBC 供應商共同合作。
- 透過協力廠商實驗來執行重要測試;只有經過測試的裝置才經過認證。 
- 在生產及生產環境中，在所有認證的裝置上執行每日測試。 驗證預先生產環境中的裝置，可保證雲端中直接路由程式碼的新版本可以搭配經過驗證的 SBCs 運作。 
- 提供與 SBC 供應商的聯合支援流程。


  > [!NOTE]
  > 如果認證的裝置或裝置是透過直接路由來連接，Microsoft 只支援電話系統。 Microsoft 保留拒絕支援案例的權利，在未驗證的裝置透過直接佈線連線至電話系統時。 

下表列出認證以直接路由的裝置。 

[深入瞭解直接路由](https://aka.ms/dr)。 如果您對用於直接路由的 SBC 認證程式有任何問題，請傳送電子郵件給 drsbccertification@microsoft.com


|                                                       那裡                                                        |       產品       | 非媒體旁路 | 媒體旁路 | 軟體版本 |
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|
| [Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  7.20. 250   |
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  7.20. 250   |
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  7.20. 250   |
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  7.20. 250   |
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   擱置     |  7.20. 250  |
|                                                                                                                     | Mediant 9000 SBC  |     &#10004;     |   &#10004;     |  7.20. 250   |                                                                       
|                                                                                                                     | 虛擬版 SBC |     &#10004;     |   &#10004;     |  7.20. 250 |
|  [功能區通訊](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5110       |     &#10004;     |   &#10004;    |       V 6。2       |
|                                                                                                                     |      SBC 5210       |     &#10004;     |  &#10004;    |       V 6。2       |
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       V 6。2       |
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       V 6。2       |
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       V 6。2       |
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      v.. 8.0。1     |
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     v.. 8.0。1     |
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      v.. 8.0。1    |
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    思考 365 SBC    |     &#10004;     |   擱置    |       V 1。4       |
|                     [聯手](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |
|                                                                                                                    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  | 
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |                                             
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |
|                     [TE-系統](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      v 3.16。2      |

若要向我們的小組提供產品意見反應（例如新功能的想法），請造訪[Uservoice](https://microsoftteams.uservoice.com)記下授予主要版本的認證。 這表示支援在主要版本之後，在 SBC 固件中有任何數位的固件。
