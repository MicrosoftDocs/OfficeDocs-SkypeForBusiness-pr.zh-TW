---
title: 在商務用 Skype Server 中包含安全性桌面
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: 規劃如何在 E9-1-1 部署中將組織的安全性服務台納入商務用 Skype Server 企業語音中。
ms.openlocfilehash: 4d69d02c985588726df449e749380db5aa728855
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831897"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a>在商務用 Skype Server 中包含安全性桌面
 
規劃如何在 E9-1-1 部署中將組織的安全性服務台納入商務用 Skype Server 企業語音中。
  
您的公司可能需要警衛室介入處理緊急通話。為了協助決定如何將警衛室整合至 E9-1-1 部署，您應該回答下列問題。
  
**您是否希望在有人撥打緊急通話時通知警衛室？**
  
您可以設定位置原則，讓商務用 Skype Server 將立即訊息 (IM) 警示傳送至一或多個安全性人員的商務用 Skype SIP 位址。 這些通知包含撥打緊急電話的人員名稱、號碼及位置，以加速安全人員協助處理緊急狀況。
    
**您想要針對每一通緊急通話都邀請警衛室參加會議嗎？**
  
只要緊急服務服務提供者有支援，您可以設定位置原則，以隨每通緊急通話附上回撥號碼。然後提供者就會針對緊急電話，使用此號碼來召集您組織的安全人員開會。此會議可在位置原則中設定為單向 (只能聆聽) 或雙向。
    
> [!NOTE]
> 必要時，您可以為每個位置原則設定不同的緊急人員。這樣可讓您針對公司內的不同區域自訂回應，或針對來自網路內部和外部的緊急電話分別建立不同的行為。您可以使用通訊群組來指定想要通知的人員。 
  

