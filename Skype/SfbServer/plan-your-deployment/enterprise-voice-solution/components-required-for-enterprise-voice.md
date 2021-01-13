---
title: 商務用 Skype Server 中的 Enterprise Voice 所需元件
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
description: 商務用 Skype Server 中的 Enterprise Voice 元件摘要。
ms.openlocfilehash: 1a7f13cc171af44ecbd0f48706ec12d882e50b33
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825823"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>商務用 Skype Server 中的 Enterprise Voice 所需元件
 
商務用 Skype Server 中的 Enterprise Voice 元件摘要。
  
若要部署 Enterprise Voice，您的拓撲中需要有下列元件。 
  
- 一或多個轉送伺服器，可在內部商務用 Skype 伺服器、企業語音基礎結構和公用交換電話網路 (PSTN) 閘道或會話初始通訊協定 (SIP) 主幹之間，轉譯信號，並在某些設定中使用媒體。 轉送伺服器是企業語音部署中最重要的元件。 如需詳細資訊，請參閱 [在商務用 Skype server 中的轉送伺服器元件](mediation-server.md)。
    
    轉送伺服器可以與前端伺服器組合，也可以安裝成獨立伺服器。
    
- PSTN 連線元件，其中可以包含 SIP 主幹或 PSTN 閘道。 如需詳細資訊，請參閱 [在商務用 Skype Server 中的 PSTN 連線元件](pstn-connectivity.md)。
    
- Edge Server，可讓您的使用者在組織防火牆之外時使用企業語音功能。 
    
    Access Edge service 提供來自組織防火牆外之商務用 Skype 使用者呼叫的 SIP 信號。 A/V Edge Service 可以讓媒體周遊 NAT 和防火牆。 從公司防火牆外使用整合通訊 (UC) 用戶端的來電者，會依賴 A/V Edge Service 來進行個別通話和電話會議。
    
    A/V 驗證服務會和 A/V Edge Service 配置在一起，並為後者提供驗證服務。嘗試連接至 A/V Edge Service 的外部使用者，需要 A/V 驗證服務提供的驗證 Token 才能接通電話。
    
- 此外，一些 Enterprise Voice 元件會在前端伺服器上執行。 如需這些元件的詳細資訊，請參閱 [適用于商務用 Skype server 的前端伺服器 VoIP 元件](front-end-server-voip.md)
    

