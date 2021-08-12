---
title: 商務用 Skype Server 中企業語音所需的元件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: 商務用 Skype Server 中企業語音元件的摘要。
ms.openlocfilehash: e07c075fad0dcbad8fecfc9183b6ab1a4a1901d848d072a893444c295e56a59d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54333095"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>商務用 Skype Server 中企業語音所需的元件
 
商務用 Skype Server 中企業語音元件的摘要。
  
若要部署企業語音，您的拓撲需要下列元件。 
  
- 一或多部轉送伺服器，可在某些設定中，在內部商務用 Skype Server、企業語音基礎結構和公用交換電話網路 (PSTN) 閘道或會話初始通訊協定（ (SIP) 主幹）間，轉換信號和設定的媒體。 在您的企業語音部署中，轉送伺服器是最重要的元件。 如需詳細資訊，請參閱[商務用 Skype Server 中的轉送伺服器元件](mediation-server.md)。
    
    轉送伺服器可以與前端伺服器組合，也可以安裝成獨立伺服器。
    
- PSTN 連線元件，其中可以包含 SIP 主幹或 PSTN 閘道。 如需詳細資訊，請參閱[商務用 Skype Server 中的 PSTN 連接元件](pstn-connectivity.md)。
    
- Edge server，可讓您的使用者在組織防火牆之外時使用企業語音功能。 
    
    Access Edge service 提供來自組織防火牆外商務用 Skype 使用者呼叫的 SIP 信號。 A/V Edge Service 可以讓媒體周遊 NAT 和防火牆。 從公司防火牆外使用整合通訊 (UC) 用戶端的來電者，會依賴 A/V Edge Service 來進行個別通話和電話會議。
    
    A/V 驗證服務會和 A/V Edge Service 配置在一起，並為後者提供驗證服務。嘗試連接至 A/V Edge Service 的外部使用者，需要 A/V 驗證服務提供的驗證 Token 才能接通電話。
    
- 此外，一些企業語音元件會在前端伺服器上執行。 如需這些元件的詳細資訊，請參閱[Front End Server VoIP 元件商務用 Skype Server](front-end-server-voip.md)
    

