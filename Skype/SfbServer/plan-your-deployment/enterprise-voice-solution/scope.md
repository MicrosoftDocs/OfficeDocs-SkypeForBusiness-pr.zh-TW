---
title: 在商務用 Skype Server 中定義 E9-1-1 部署的範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: 規劃商務用 Skype Server Enterprise Voice 中的 E9-1-1 部署所需的決策。
ms.openlocfilehash: fa300ac2f4ba1c0d847abec138b6882e4f240831
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802463"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>在商務用 Skype Server 中定義 E9-1-1 部署的範圍

規劃商務用 Skype Server Enterprise Voice 中的 E9-1-1 部署所需的決策。

在您設定 E9 的商務用 Skype-1-1 之前，您必須先規劃 E9-1-1 部署。 需要考慮的一些問題包括：

 **貴組織的原則與 E9-1-1 的法律義務為何？**

 E9-1-1-1-1-1-1 parlance）中的 Pbx 法律需求（在 E9-1-1 中稱為多行電話系統，或 MLTS）與狀態不同。 您應該向法律小組請教，瞭解在您的相關地域中部署商務用 Skype 的義務。

 **貴企業中需要為 E9 的哪些區域啟用-1-1？**

 您可以為整個企業或選取的位置啟用 E9-1-1。 例如，您可能會在不同狀態的辦公室中有不同的 E9-1 需求，或者您可能想要排除美國以外的網站

 **如何將 E9-1-1 部署到分支網站？**

 語音復原是您在分支網站部署 E9-1-1 時，必須瞭解的重要概念。 如果您使用的是集中式電子 9-1-1 SIP trunks，且發生 WAN 中斷，則登入的用戶端可能無法從位置資訊服務取得位置，或無法連線到緊急服務服務提供者。 商務用 Skype 提供幾項策略，可處理分支辦公室中的語音復原，包括：具備彈性資料網路、在每個分支部署 SIP 幹線，或在中斷期間將緊急呼叫推出到本機閘道。 如需詳細資訊，請參閱[規劃分支網站語音復原](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx)。

 **您是否要為在網路外部工作的使用者啟用 E9-1-1？**

 自動位置採集只適用于組織網路內部的客戶，所以您的組織必須決定是否支援 E9-1-1-從商務用 Skype 用戶端，而不是在內部部署進行的通話。 例如，如果使用者是在家中或從客戶的網站工作，您是否能讓他們放入緊急通話？ 如果用戶端位於商業網路之外，則可將用戶端設定為提示使用者輸入位置。 不過，因為這些使用者提供的位置無法依據主要街道位址指南（MSAG） prevalidated，所以緊急服務服務提供者發送器必須在路由前確認與來電者 verbally 位置的有效性。公用安全應答點（PSAP）的呼叫。

> [!NOTE]
> 使用 VPN 連線到貴組織網路的使用者的商務用 Skype 用戶端可以挑選內部 IP 位址資訊，但因為這些位址無法用來識別使用者的實際位置，所以必須排除 VPN 子網。從位置資訊服務。

 **您想要提供緊急呼叫路由至美國以外的網站嗎？**

 您可能會想要提供緊急路由至您公司不是由緊急服務服務提供者所提供的區域（例如，國際位置）。 若要這樣做，請建立新的網站，然後將語音原則指派給參照 PSTN 使用狀況的網站，以透過本機 PSTN 閘道路由通話。


