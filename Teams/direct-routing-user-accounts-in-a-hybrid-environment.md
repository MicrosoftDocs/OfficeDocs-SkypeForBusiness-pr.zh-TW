---
title: 具有 PSTN 連接的混合式環境中的使用者帳戶
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: 瞭解使用者建立的不同組合，以及支援或不受支援的組合。
ms.openlocfilehash: bf2fee0646e5230964673af4dbfa4fed22086cdc
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572110"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>具有 PSTN 連接的混合式環境中的使用者帳戶

## <a name="about-the-environment"></a>關於環境

本文適用于您擁有下列各項的環境： 
 
- 商務用 Skype Server 或 Lync Server 2013 
- Office 365 租使用者 
- 在商務用 Skype Server 與商務用 Skype Online 或 Microsoft 團隊租使用者之間設定混合式連接 
- 已啟用並從用戶端撥打和接聽公用交換電話網絡（PSTN）通話的使用者

 
如果您使用的是不同的環境（例如商務用 Skype 雲端連接器版本）、混合式未設定，或者您的使用者未啟用 PSTN 通話，則支援矩陣會有所不同。  

## <a name="about-the-combinations-and-the-supportability-statement"></a>關於組合和支援性語句  

具有 PSTN 連線的商務用 Skype 混合式環境可提供使用者服務的提供位置，以及如何調配及管理使用者帳戶的彈性。 但豐富的選項可能會產生一些不受支援的組合。 本節說明使用者建立的不同組合，後面接著可支援的語句。


**碼**   
- **企業語音：** 此選項可為使用內部部署商務用 Skype 使用者帳戶的使用者提供對 PSTN 的存取權。 內部部署商務用 Skype 轉送伺服器提供 interconnectivity 到 PSTN。  
- **混合式語音連線：** 提供對使用商務用 Skype Online 帳戶的使用者存取 PSTN 的選項。 內部部署商務用 Skype 轉送伺服器提供 interconnectivity 到 PSTN。 
- **直接路由：** 提供使用 Microsoft 團隊用戶端的線上商務用 Skype 帳戶、Microsoft 團隊授權的使用者存取 PSTN 的選項。 SBC 已連線到 Office 365 中的 SIP Proxy，而不需要 Microsoft 的任何內部部署軟體。

  
**此環境支援下列組合：**
- **案例1：** 商務用 Skype 內部部署中的使用者帳戶，將會使用商務用 Skype 用戶端與企業語音
- **案例2：** 商務用 Skype online 中的使用者帳戶，且會使用商務用 Skype 用戶端搭配混合式語音連接
- **案例3：** 商務用 Skype online 中使用 Microsoft 團隊授權的使用者帳戶，並將使用團隊用戶端
 
### <a name="supportability-matrix"></a>支援矩陣


|**中建立的使用者物件**  |**使用者的商務用 Skype 服務提供者**|**使用者的用戶端**|**語音選項**|**受**|
| ------------ | --------- | --------- | --------- | -------- |
|內部部署廣告| 內部部署 |商務用 Skype   | 企業語音   |是的|
|內部部署廣告|Online| 商務用 Skype  | 混合式語音連接   |是的 |
|內部部署廣告|Online |Microsoft 團隊 |直接路由  |是的 |
|**不支援的組合**    | |         |         |      |
|Azure AD| 內部部署/線上 | 商務用 Skype/Microsoft 團隊|企業語音/混合式語音連接/直接路由  |否，您必須先在內部部署 AD 中建立使用者物件 |
|內部部署廣告  |內部部署| Microsoft 團隊| 企業語音/混合式語音連接/直接路由   |否，內部部署商務用 Skype 不支援 Microsoft 團隊用戶端 |     
|內部部署廣告  |Online |商務用 Skype  | 直接路由  |否，商務用 Skype 用戶端不支援直接傳送，且在商務用 Skype 中必須啟用使用者的企業語音功能  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>包含 PSTN 之混合式環境的可支援性聲明

針對所有使用者，您**必須**在內部部署的 AD 中建立使用者物件，然後使用 Azure ad Connect 工具將其同步處理到 Azure AD。 如果使用者物件是在混合式設定中直接在 Azure AD 中建立，則**不支援**針對團隊/商務用 Skype 使用者啟用使用者。 針對新的使用者（例如新員工），會直接為團隊啟用該使用者，必須針對使用內部部署商務用 Skype 管理工具的商務用 Skype 啟用該使用者。 在線上商務用 Skype 或團隊中建立使用者，但不需要先在**不支援**企業語音的內部部署池中啟用這些使用者。 如需此功能的詳細資訊，請參閱在[商務用 Skype Server 中使用內部部署 PSTN 連線來規劃 Office 365 中的電話系統](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)。
