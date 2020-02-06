---
title: 商務用 Skype Server 中的企業語音所需元件
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
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: 商務用 Skype Server 中的企業語音元件摘要。
ms.openlocfilehash: a2e32e2301a404afd06038d438fbb62a13235d65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803103"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>商務用 Skype Server 中的企業語音所需元件
 
商務用 Skype Server 中的企業語音元件摘要。
  
若要部署企業語音，您的拓撲中需要下列元件。 
  
- 一或多個轉送伺服器，可在部分設定中，在內部商務用 Skype Server、企業語音結構及公用交換電話網絡（PSTN）閘道或會話初始通訊協定之間轉換傳輸（SIP）主幹。 中繼伺服器是企業語音部署中最重要的元件。 如需詳細資訊，請參閱[商務用 Skype server 中的中繼伺服器元件](mediation-server.md)。
    
    轉送伺服器可以與前端伺服器 collocated，或安裝為獨立伺服器。
    
- PSTN 連線元件，其中可以包含 SIP trunks 或 PSTN 閘道。 如需詳細資訊，請參閱[商務用 Skype Server 中的 PSTN 連接元件](pstn-connectivity.md)。
    
- [邊緣伺服器]，可讓您的使用者在貴組織的防火牆以外時使用企業語音功能。 
    
    存取邊緣服務提供來自貴組織防火牆外部之商務用 Skype 使用者通話的 SIP 信號。 A/V 邊緣服務可讓您能夠遍歷 NAT 和防火牆。 使用來自企業防火牆外部之整合通訊（UC）用戶端的來電者，都依賴于個人和電話會議的 A/V 邊緣服務。
    
    A/V 驗證服務已 collocated，並為 A/V 邊緣服務提供驗證服務。 嘗試連線至 A/V 邊緣服務的外部使用者必須具備 A/V 驗證服務所提供的驗證權杖，才能進行呼叫。
    
- 此外，某些企業語音元件會在前端伺服器上執行。 如需這些元件的詳細資訊，請參閱[商務用 Skype server 的前端伺服器 VoIP 元件](front-end-server-voip.md)
    

