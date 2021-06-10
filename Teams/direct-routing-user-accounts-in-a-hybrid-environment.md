---
title: 在混合式環境中使用 PSTN 的使用者帳戶
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
f1.keywords:
- NOCSH
description: 瞭解使用者建立的不同組合，以及支援或不受支援的組合。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d55f72bc9b22a3bb1e1ba889f24cf7a7ea0cbb53
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096323"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>含有 PSTN 連線功能的混合式環境中的使用者帳戶

## <a name="about-the-environment"></a>關於環境

本文適用于您擁有下列所有專案的環境： 
 
- 商務用 Skype Server Lync Server 2013 
- 組織Microsoft 365或Office 365組織 
- 在線上或租使用者商務用 Skype Server商務用 Skype之間Microsoft Teams連線 
- 已啟用撥打和接收公用交換電話網絡的使用者 (PSTN) 用戶端或用戶端的通話

 
如果您有不同的環境，例如 (、商務用 Skype Cloud Connector Edition) 未針對 PSTN 通話啟用混合式，或您的使用者未啟用 PSTN 通話，則支援矩陣會有所不同。  

## <a name="about-the-combinations-and-the-supportability-statement"></a>關於組合和可支援性聲明  

具有 pstN 商務用 Skype的混合式環境，可提供提供使用者服務位置，以及使用者帳戶的部署和管理方式的彈性。 但豐富的選項可能會建立一些不支援的組合。 本節說明使用者建立的不同組合，後面接著可支援性聲明。


**定義：**   
- **企業語音：** 為擁有內部部署或使用者帳戶的使用者提供 PSTN 商務用 Skype選項。 內部部署和商務用 Skype伺服器提供 PSTN 的互連。  
- **混合式語音連接：** 為擁有線上帳戶的使用者提供 PSTN 商務用 Skype選項。 內部部署和商務用 Skype伺服器提供 PSTN 的互連。 
- **直接路由：** 使用用戶端，為擁有線上帳戶商務用 Skype PSTN Microsoft Teams選項Microsoft Teams PSTN。 SBC 已連接到 Microsoft 365 或 Office 365的 SIP Proxy，而不需要 Microsoft 的任何內部部署軟體。

  
**環境支援下列組合：**
- **案例 1：** 內部商務用 Skype中的使用者帳戶，並且會使用 商務用 Skype 用戶端企業語音
- **案例 2：** 商務用 Skype 中的使用者帳戶，且會使用 商務用 Skype 用戶端與混合式語音連線
- **案例 3：** 線上的使用者帳戶商務用 Skype授權Microsoft Teams，並且會Teams用戶端
 
### <a name="supportability-matrix"></a>可支援性矩陣


|**在**  |**使用者商務用 Skype服務提供者**|**使用者的用戶端**|**語音選項**|**支援**|
| ------------ | --------- | --------- | --------- | -------- |
|內部部署 AD| 內部部署 |商務用 Skype   | 企業語音   |是|
|內部部署 AD|線上| 商務用 Skype  | 混合式語音連接   |是 |
|內部部署 AD|線上 |Microsoft Teams |直接路由  |是 |
|**不支援的組合**    | |         |         |      |
|Azure AD| 內部部署/線上 | 商務用 Skype/Microsoft Teams|企業語音/混合式語音連接/直接路由  |否，使用者物件必須先在內部部署 AD 中建立 |
|內部部署 AD  |內部部署| Microsoft Teams| 企業語音/混合式語音連接/直接路由   |否，Microsoft Teams用戶端不支援內部部署商務用 Skype |     
|內部部署 AD  |線上 |商務用 Skype  | 直接路由  |否，用戶端不支援直接商務用 Skype路由  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>使用 PSTN 的混合式環境支援性聲明

對於所有使用者，使用者物件必須在內部部署 AD 中建立，然後使用 Azure AD 連線同步處理至 Azure AD。 如果使用者物件是直接在混合式Teams Azure AD 中建立，則不支援啟用 Teams/商務用 Skype 的使用者。  對於新使用者 ，例如新進人員 ，他們將會直接為 Teams 啟用，使用者必須啟用商務用 Skype內部部署商務用 Skype管理工具。 不支援在線上商務用 Skype或Teams中建立使用者，而不先在內部部署企業語音 **中啟用使用者**。 有關此詳細資訊，請參閱在 電話系統 中使用內部部署[PSTN](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)商務用 Skype Server。