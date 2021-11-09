---
title: 在商務用 Skype Server 中規劃立即訊息和目前狀態
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
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 摘要：瞭解如何在商務用 Skype Server 中規劃立即訊息和目前狀態。
ms.openlocfilehash: b81da143bf7b8d917d88939d8b28261910bb8f5a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835081"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>在商務用 Skype Server 中規劃立即訊息和目前狀態
 
**摘要：** 瞭解如何在商務用 Skype Server 中規劃立即訊息和目前狀態。
  
在商務用 Skype Server 中規劃立即訊息和目前狀態。 若要瞭解特定的部署選項，例如啟用或停用離線立即訊息 (IM) ，請參閱[Deploy 商務用 Skype Server 中的立即訊息與顯示狀態](../deploy/im-and-presence/im-and-presence.md)。
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>在商務用 Skype Server 中規劃立即訊息和目前狀態

前端伺服器提供核心商務用 Skype Server 功能，例如立即訊息 (IM) 和目前狀態，並包含在每個商務用 Skype Server 部署中。 有兩種可供使用的版本：商務用 Skype Server Enterprise Edition （主要為大型組織設計）和商務用 Skype Server Standard Edition，其主要是針對需要較小硬體投資且不需要較小的組織進行設計。需要完整的高可用性選項。 這兩種版本都支援所有商務用 Skype Server 工作負載，包括 IM、顯示狀態、會議及企業語音。
  
立即訊息 (IM) 可讓使用者在電腦上使用文字訊息，與其他使用者進行即時溝通。同時支援雙方或多方 IM 工作階段。雙方 IM 交談中的參與者可以隨時將第三個參與者加入交談中。若發生這種情況，[交談] 視窗會變更成可支援會議功能。
  
目前狀態為使用者提供有關網路上其他人狀態的資訊。 使用者的目前狀態提供的資訊可協助其他人決定是否應該嘗試聯繫使用者，以及是否使用立即訊息、電話或電子郵件。 目前狀態會促進立即通訊，但也會提供使用者正在開會中或不在辦公室的資訊，指出無法進行立即通訊。 這種目前狀態會顯示為商務用 Skype 及其他存在狀態的應用程式中的目前狀態圖示，包括 microsoft Outlook 訊息和共同作業用戶端、microsoft SharePoint 技術及 Microsoft Office。 目前狀態圖示代表使用者的目前可用性和溝通意願。 
  
### <a name="technical-requirements"></a>技術需求

立即訊息 (IM) 和目前狀態，一定要在 Enterprise Edition 前端集區和 Standard Edition 伺服器上執行。 如需支援的硬體、作業系統及資料庫軟體的資訊，請參閱[認證閘道](../../SfbPartnerCertification/certification/infra-gateways.md)、[商務用 Skype 2015 環境的需求](requirements-for-your-environment/requirements-for-your-environment.md)，以及[商務用 Skype Server 2019 的基礎結構需求](../../SfBServer2019/plan/system-requirements.md)。
  
### <a name="enabling-communication-with-external-users"></a>啟用與外部使用者的通訊

您可以讓您的使用者與外部使用者通訊，以大幅增加您在商務用 Skype Server 中的投資效益。 外部使用者包括：
  
- 遠端使用者：貴組織自身的使用者、在防火牆外工作時使用的膝上型電腦或其他商務用 Skype Server 裝置。
    
- 同盟使用者：來自公司的使用者，您也可以使用商務用 Skype Server 的使用者。 為了方便您的使用者輕鬆連絡這些使用者，您可以和這些公司建立同盟關係。 
    
- Skype 使用者：商務用 Skype 使用者可以使用 IM、語音和影片，在 Skype 上抵達數百萬使用者。
    
> [!NOTE]
> 已不再支援 AOL、Yahoo 和 Google 交談。 
  
> [!NOTE]
> 若要啟用任何或所有上述案例，您必須部署 Edge Server，以協助啟用商務用 Skype Server 部署與外部使用者之間的安全通訊。 貴組織的遠端使用者和同盟組織的使用者，將能夠看到彼此的目前狀態，並使用 IM 進行通訊。 
  
> [!NOTE]
> 只有整合功能共同作業平臺 (UCCP (XMPP) 支援 [可延伸的訊息和顯示狀態通訊協定]，) 協同互通性測試命令 (JITC) 認證案例。 
  
### <a name="archiving-im-content"></a>封存 IM 內容

商務用 Skype Server 提供您的組織必須遵循合規性法規時可使用的功能。 您可以使用封存為組織中的所有使用者或您指定的特定使用者封存 IM 訊息的內容。 如需詳細資訊，請參閱[Plan for 封存 in 商務用 Skype Server](archiving/archiving.md)。 
  
如果您也已部署 Microsoft Exchange Server 2013，您可以將 Exchange 資料封存與商務用 Skype Server 資料的封存整合，並使用單一工具來搜尋這兩種類型的封存資料。 如需詳細資訊，請參閱[Configure 商務用 Skype Server to use Exchange Server](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)封存。
  
### <a name="topologies-and-components"></a>拓撲和元件

立即訊息 (IM) 和目前狀態所需的元件包括：
  
- 組織的前端伺服器 (稱為集區) 或 Standard Edition 伺服器。 IM 和目前狀態功能在這些伺服器上一定會啟用。 如需前端集區拓撲和管理的詳細資訊，請參閱 [前端集區高可用性和管理](high-availability-and-disaster-recovery/high-availability.md)。
    
- 負載平衡器（如果您有 Enterprise Edition 前端集區）。
    
### <a name="supported-collocation"></a>支援的組合

組合定義為具有已安裝多個角色的單一伺服器或伺服器群組。 如需組合的詳細資訊，請參閱[拓撲基礎的商務用 Skype Server](topology-basics/topology-basics.md)。 
  

