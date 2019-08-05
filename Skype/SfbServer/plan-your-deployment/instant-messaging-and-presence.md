---
title: 在商務用 Skype Server 中規劃立即訊息和目前狀態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: '摘要: 瞭解如何在商務用 Skype Server 中規劃立即訊息和目前狀態。'
ms.openlocfilehash: 29026a0b4ef7cce55f155f024efc9ccc84457906
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192990"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>在商務用 Skype Server 中規劃立即訊息和目前狀態
 
**摘要:** 瞭解如何在商務用 Skype Server 中規劃立即訊息和目前狀態。
  
規劃商務用 Skype Server 中的立即訊息和目前狀態。 若要瞭解特定的部署選項 (例如啟用或停用離線立即訊息 (IM)), 請參閱[在商務用 Skype Server 中部署立即訊息和目前狀態](../deploy/im-and-presence/im-and-presence.md)。
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>在商務用 Skype Server 中規劃立即訊息和目前狀態

前端伺服器提供核心的商務用 Skype 伺服器功能, 例如立即訊息 (IM) 和目前狀態, 且包含在每個商務用 Skype Server 部署中。 有兩種版本可供使用: 商務用 Skype Server Enterprise Edition, 主要針對較大型的組織和商務用 Skype Server Standard Edition 設計, 主要針對需要較小單位的較小組織。硬體投資且不需要完整的高可用性選項。 這兩種版本都支援所有商務用 Skype 伺服器工作負載, 包括 IM、目前狀態、會議和企業語音。
  
[立即訊息 (IM)] 可讓您的使用者在電腦上使用文字型郵件即時相互通訊。 支援兩方和多方 IM 會話。 在雙方的 IM 交談中, 參與者可以隨時新增協力廠商參與者加入交談。 發生這種情況時, 交談視窗會變更以支援會議功能。
  
[目前狀態] 會提供資訊給使用者, 瞭解網路上其他人的狀態。 使用者的目前狀態會提供資訊, 協助其他人決定是否應該嘗試與使用者聯繫, 以及是否要使用立即訊息、電話或電子郵件。 如果可能的話, 目前狀態會鼓勵立即通訊, 但它也會提供使用者是否在會議中或不在辦公室的相關資訊, 指出無法進行立即通訊。 在商務用 Skype 和其他存在感知的應用程式 (包括 Microsoft Outlook 訊息與共同作業用戶端、Microsoft SharePoint 技術及 Microsoft Office) 中, 此目前狀態會顯示為「目前狀態」圖示。 [目前狀態] 圖示代表使用者目前的可用性和溝通意願。 
  
### <a name="technical-requirements"></a>技術需求

[立即訊息 (IM)] 和 [目前狀態] 都是在企業版前端池和標準版伺服器上執行。 如需支援的硬體、作業系統及資料庫軟體的相關資訊, 請參閱[認證閘道](../../SfbPartnerCertification/certification/infra-gateways.md)、[商務用 skype 2015 環境的需求](requirements-for-your-environment/requirements-for-your-environment.md), 以及[商務用 Skype Server 2019 的基礎結構需求](../../SfBServer2019/plan/system-requirements.md).
  
### <a name="enabling-communication-with-external-users"></a>啟用與外部使用者的通訊

您可以讓您的使用者與外部使用者通訊, 大幅提高您在商務用 Skype Server 中投資的益處。 外部使用者可以包括:
  
- 遠端使用者: 貴組織自己的使用者、在防火牆外工作, 且正在使用其膝上型電腦或其他商務用 Skype 伺服器裝置。
    
- 同盟使用者: 您與其他人同時執行商務用 Skype Server 的公司使用者。 若要讓您的使用者能夠輕鬆地與這些使用者聯繫, 您可以建立與這些公司的聯盟關聯。 
    
- Skype 使用者: 商務用 Skype 使用者可以使用 IM、語音和影片, 在 Skype 中與成百上千的使用者取得聯繫。
    
> [!NOTE]
> 已不再支援 AOL、Yahoo 和 Google 交談。 
  
> [!NOTE]
> 若要啟用任何一種或所有案例, 您必須部署邊緣伺服器, 以協助您在商務用 Skype Server 部署與外部使用者之間進行安全通訊。 貴組織的遠端使用者和聯盟組織中的使用者將能夠彼此查看其目前狀態並使用 IM 進行通訊。 
  
> [!NOTE]
> 只有整合功能共同作業平臺 (UCCP) 聯合互通性測試命令 (JITC) 認證案例, 才能支援可擴展訊息與目前狀態通訊協定 (XMPP)。 
  
### <a name="archiving-im-content"></a>封存 IM 內容

如果您的組織必須遵循合規性規範, 商務用 Skype Server 提供您可以使用的功能。 您可以使用 [封存] 來封存貴組織中所有使用者的 IM 訊息內容, 或只針對您指定的特定使用者封存 IM 訊息的內容。 如需詳細資訊, 請參閱[在商務用 Skype 伺服器中規劃](archiving/archiving.md)封存。 
  
如果您也已部署 Microsoft Exchange Server 2013, 您可以將 Exchange 資料的存檔與商務用 Skype 伺服器資料進行整合, 然後使用單一工具來搜尋這兩種類型的已歸檔資料。 如需詳細資訊, 請參閱[設定商務用 Skype 伺服器以使用 Exchange 伺服器](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)封存。
  
### <a name="topologies-and-components"></a>拓撲與元件

立即訊息 (IM) 與目前狀態所需的元件如下:
  
- 貴組織的前端伺服器 (稱為「池」) 或標準版伺服器。 在這些伺服器上, 系統永遠都能啟用 IM 和目前狀態功能。 如需前端池拓撲與管理的詳細資訊, 請參閱[前端池高可用性和管理](high-availability-and-disaster-recovery/high-availability.md)。
    
- [負載平衡器] (如果您有企業版的 [前端] 池)。
    
### <a name="supported-collocation"></a>支援的 collocation

Collocation 定義為安裝了多個角色的單一伺服器或一組伺服器。 如需 collocation 的詳細資訊, 請參閱[商務用 Skype Server 的拓撲基礎](topology-basics/topology-basics.md)。 
  

