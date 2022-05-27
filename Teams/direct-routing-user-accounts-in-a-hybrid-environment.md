---
title: 在混合式環境中使用 PSTN 的使用者帳戶
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解使用者建立的不同組合，以及支援或不支援的組合。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e97d1a3ac433db78792ca3cc512d32c5a8fec243
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676415"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>含有 PSTN 連線功能的混合式環境中的使用者帳戶

## <a name="about-the-environment"></a>關於環境

本文適用于您擁有下列所有功能的環境：

- 商務用 Skype Server 或 Lync Server 2013
- Microsoft 365或Office 365組織
- 在 商務用 Skype Server 與 商務用 Skype Online 或 Microsoft Teams 租使用者之間設定的混合式連線
- 能夠撥打和接收公用交換電話網路 (PSTN 的使用者，) 用戶端和用戶端的通話


如果您的環境 (如商務用 Skype Cloud Connector Edition) 、未設定混合式，或您的使用者未啟用 PSTN 通話，則支援矩陣會有所不同。

## <a name="about-the-combinations-and-the-supportability-statement"></a>關於組合與支援聲明

具有 PSTN 連線能力的商務用 Skype混合式環境可在提供使用者服務的位置以及使用者帳戶的布建與管理方式上提供彈性。 但選項的豐富性可能會建立一些不支援的組合。 本節說明使用者建立的不同組合，後面接著支援聲明。

**定義：**

- **企業語音：** 為擁有內部部署商務用 Skype使用者帳戶的使用者提供 PSTN 存取權的選項。 內部部署商務用 Skype中送伺服器提供 PSTN 的互連性。
- **混合式語音連線：** 為擁有 商務用 Skype Online 帳戶的使用者提供 PSTN 存取權的選項。 內部部署商務用 Skype中送伺服器提供 PSTN 的互連性。
- **直接路由：** 為使用Microsoft Teams用戶端的線上商務用 Skype帳戶、Microsoft Teams授權的使用者提供 PSTN 存取權的選項。 SBC 已連線至 Microsoft 365 或 Office 365 中的 SIP Proxy，而不需要任何來自 Microsoft 的內部部署軟體。

**環境支援下列組合：**

- **案例 1：** 商務用 Skype內部部署中的使用者帳戶，並將商務用 Skype用戶端搭配企業語音
- **案例 2：** 商務用 Skype Online 中的使用者帳戶，並將商務用 Skype用戶端搭配混合式語音連線使用
- **案例 3：** 商務用 Skype線上且擁有Microsoft Teams授權的使用者帳戶，且會使用Teams用戶端

### <a name="supportability-matrix"></a>支援矩陣

|在下列位置建立的使用者物件|使用者的商務用 Skype服務提供者|使用者的用戶端|語音選項|支援|
|---|---|---|---|---|
|內部部署 AD|內部部署|商務用 Skype|企業語音|是|
|內部部署 AD|線上|商務用 Skype|混合式語音連線|是|
|內部部署 AD|線上|Microsoft Teams|直接路由|是|
|**不支援的組合**|||||
|Azure AD|內部部署/線上|商務用 Skype/Microsoft Teams|企業語音/混合式語音連線/直接路由|否，必須先在內部部署 AD 中建立使用者物件|
|內部部署 AD|內部部署|Microsoft Teams|企業語音/混合式語音連線/直接路由|否，內部部署商務用 Skype不支援Microsoft Teams用戶端|
|內部部署 AD|線上|商務用 Skype|直接路由|否，商務用 Skype用戶端不支援直接路由|

### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>含 PSTN 之混合式環境的支援聲明

對於所有使用者，**使用者物件必須在** 內部部署 AD 中建立，並使用 Azure AD 連線工具同步處理至 Azure AD。 如果在混合式組態中直接在 Azure AD 中建立使用者物件，**則不支援** 啟用使用者Teams/商務用 Skype。 對於新進使用者，例如將直接為Teams啟用的新進人員，使用者必須啟用商務用 Skype使用內部部署商務用 Skype管理工具。 **不支援** 在線上商務用 Skype或Teams中建立使用者，但不先在內部部署集區中使用企業語音啟用使用者。 如需詳細資訊，請參閱[在 商務用 Skype Server 中使用內部部署 PSTN 連線來規劃電話系統](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)。
