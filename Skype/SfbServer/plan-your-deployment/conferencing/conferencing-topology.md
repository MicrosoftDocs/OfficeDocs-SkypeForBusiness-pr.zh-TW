---
title: 規劃商務用 Skype Server 的會議拓撲
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
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 摘要：閱讀此主題以瞭解如何在商務用 Skype Server 中規劃會議拓撲。
ms.openlocfilehash: 711db1309ce31838f02bd705252693a58992e2ee9a21e12931c8a9c5fe064d92
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54283105"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>規劃商務用 Skype Server 的會議拓撲
 
**摘要：** 閱讀此主題以瞭解如何在商務用 Skype Server 中規劃會議拓撲。
  
本主題說明商務用 Skype Server 中會議的拓撲基礎：
  
- 支援的拓撲
    
- 電話撥入式會議考慮
    
- Web 會議考慮
    
- 大型會議的需求
    
如需硬體和軟體需求的詳細資訊，請參閱[商務用 Skype Server 中會議的硬體和軟體需求](hardware-and-software-requirements.md)。
  
## <a name="supported-topologies"></a>支援的拓撲

在商務用 Skype Server 中，執行會議服務的伺服器一定會與前端伺服器或 Standard Edition 伺服器進行組合。 當您部署商務用 Skype Server 時，會自動部署 IM 會議功能。 您可以使用拓撲產生器，指定是否要部署 web、音訊和影片 (A/V) 和電話撥入式會議。 您也可以使用拓撲產生器，將會議新增至現有的部署。 如需拓撲基礎和組合案例的詳細資訊，請參閱[拓撲基礎的商務用 Skype Server](../../plan-your-deployment/topology-basics/topology-basics.md)。
  
您可以在下列拓撲和設定中部署會議：
  
- 商務用 Skype Server Standard Edition
    
- 商務用 Skype Server Enterprise Edition
    
- 包含或不企業語音
    
## <a name="dial-in-conferencing-considerations"></a>電話撥入式會議考慮

若要部署電話撥入式會議，您必須考慮下列事項：
  
- 電話撥入式會議需要一台轉送伺服器，以商務用 Skype Server 與 pstn 閘道之間的某些設定) 來轉譯信令 (和媒體，以及在轉送伺服器和 pstn 閘道之間轉譯信號和媒體的 PSTN 閘道。
    
   在設定電話撥入式會議之前，您必須先部署企業語音或轉送伺服器，並至少進行下列其中一項作業：
    
  - PSTN 閘道
    
  - IP-PBX
    
  - 透過設定 SIP 主幹) 所連接的網際網路電話語音服務提供者 (SBC)  (的會話邊界控制器
    
- 您可以在中央網站部署應用程式服務、會議語音應答應用程式和會議宣告應用程式，但不能在分支網站中部署。
    
- 您必須在每個部署商務用 Skype Server 會議的集區中部署電話撥入式會議。 您不需要在每個集區中指派存取號碼，但是您必須在每個集區中部署電話撥入式會議功能。 當使用者呼叫一個集區中的存取號碼，以在不同的集區加入商務用 Skype Server 會議時，此需求即支援記錄的名稱功能。 
    
如需詳細資訊，請參閱[商務用 Skype Server 中的計畫撥入式會議](dial-in-conferencing.md)。
  
## <a name="web-conferencing-considerations"></a>Web 會議考慮

Web 會議需要下列專案： 
  
- 存取檔案存放區，以用來儲存 Web 會議內容。
    
- 與 Office Web Apps Server/Office Online Server 整合，這是為了在會議期間共用 PowerPoint 檔案所需的。
    
> [!NOTE]
> Office Web Apps Server 的最新小小 Office Online Server 稱為「商務用 Skype Server 支援的]。 如需詳細資訊，請參閱[Office Online Server 檔](/officeonlineserver/office-online-server)。 
  
商務用 Skype Server 提供下列方式來設定 Office Web Apps Server/Office Online Server。 視您的需求而定，您可以：
  
- **在組織的防火牆之後和相同的網路區域中，同時安裝商務用 Skype Server 和 Office Web Apps Server/Office Online Server 內部部署。** 透過此拓撲，將會透過反向 proxy 伺服器提供對 Office Web Apps server/Office Online Server 的外部存取。 理想狀況下，您應該在與商務用 Skype Server 相同的網路區域中安裝 Office Web Apps Server/Office Online Server。
    
    外部商務用 Skype 用戶端可以使用反向 proxy 伺服器（該伺服器要求來自網際網路的要求，以及將郵件轉送至內部網路），連線至商務用 Skype Server 及 Office Web Apps server/Office Online Server。  (內部用戶端不需要使用反向 proxy 伺服器，因為他們可以直接連線到 Office Web apps server/Office Online Server。如果您想要使用僅供 Office 使用的專用 Office Online Server web apps server/商務用 Skype Server 伺服器陣列，則 ) 此拓撲會發揮最佳作用。
    
- **使用外部部署的 Office Web Apps Server/Office Online Server。** 在此拓撲中，會在內部部署商務用 Skype Server，並使用部署于商務用 Skype Server 網路區域以外的 Office Web Apps Server/Office Online Server。 當公司中的多個應用程式共用 Office Web Apps server/Office Online Server 時，可能會發生這種情況，而且部署于要求商務用 Skype Server 使用 Office Web Apps Server/Office Online Server 外部介面的網路上，反之亦然。
    
    您不需要安裝反向 proxy 伺服器;相反地，所有從 Office Web Apps server/Office Online Server 到商務用 Skype Server 的要求都透過您的 Edge Server 路由傳送。 您的內部和外部商務用 Skype 用戶端都使用外部 URL 連線至 Office Web Apps Server/Office Online Server。
    
    如果 Office web apps server/Office Online Server 部署在內部防火牆之外，請選取在拓撲產生器的 [周邊/網際網路) ] 中，將 **web apps server 部署在外部網路 (中** 的選項 Office。
    
如需詳細資訊，請參閱[Configure Office integration with 商務用 Skype Server 中的 Web Apps Server](../../deploy/deploy-conferencing/office-web-app-server.md)。 
  
不論您選取的拓撲為何，開啟正確的防火牆埠都很重要。 您必須確定 DNS 名稱、IP 位址及埠未受到 Office Web Apps Server/Office Online Server、負載平衡器或商務用 Skype Server 上的防火牆封鎖。
  
> [!NOTE]
> 在周邊網路中部署伺服器的另一個選項，可提供 Office Web Apps Server/Office Online Server 的外部存取權。 如果您選擇這麼做，請記住 Office Web Apps Server/Office Online Server 安裝程式需要伺服器電腦成為 Active Directory 網域的成員。 除非您的網路原則允許周邊網路中的電腦成為 Active Directory 網域成員，否則建議您不要在周邊網路中安裝 Office Web Apps Server/Office Online Server。 相反地，您應該在內部網路中安裝 Office Web Apps Server/Office Online Server，並透過您的反向 proxy 伺服器提供外部使用者存取。 
  
## <a name="topology-requirements-for-large-meetings"></a>大型會議的拓撲需求

單一大型會議需要至少一部前端伺服器和一部後端伺服器。 不過，為了提供高可用性，我們建議使用兩部前端伺服器集區和鏡像後端伺服器，如下圖所示：
  
**大型會議拓撲**

![大型會議拓撲](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
主控大型會議的使用者必須擁有位於前端集區中的使用者帳戶。 不過，我們不建議您在此集區中主控其他使用者帳戶。 而只是用於大型會議。 最佳作法是在此集區中建立特殊的使用者帳戶，僅供主控大型會議使用。 因為大型會議設定已經針對效能進行優化，所以以一般使用者的身分使用它時，可能會發生問題，例如，當涉及 PSTN 端點時，無法將 P2P 會話提升為會議。
  
若要管理恰好兩部前端伺服器的集區，需要一些特殊的考慮。 如需詳細資訊，請參閱[商務用 Skype Server 2015 的拓撲基礎](../../plan-your-deployment/topology-basics/topology-basics.md)和[商務用 Skype Server 2015 的參考拓撲](../../plan-your-deployment/topology-basics/reference-topologies.md)。
  
此外，如果您想要選擇性地為大型會議所用的集區提供嚴重損壞修復備份和容錯移轉，您可以將它與不同資料中心的專用集區配對。 如需詳細資訊，請參閱[在商務用 Skype Server 中規劃高可用性和嚴重損壞修復](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
拓撲的其他注意事項包括：
  
- 需要有檔案共用，才能儲存會議內容，以及在部署及啟用封存伺服器時儲存封存檔。 檔案共用可以專用於集區，也可以是部署集區之網站上其他集區所使用的相同檔案共用。 如需設定檔案共用的詳細資訊，請參閱[Create a file share in 商務用 Skype Server 2015](../../deploy/install/create-a-file-share.md)。
    
- 在大型會議中啟用 PowerPoint 簡報功能需要 Office Web Apps Server/Office Online Server。 Office web apps server/Office Online Server 可以專用於大型會議集區，也可以是部署專用集區之網站上其他集區所使用的相同 Office Web apps server/Office Online Server。 如需詳細資訊，請參閱[Configure Office integration with 商務用 Skype Server 中的 Web Apps Server](../../deploy/deploy-conferencing/office-web-app-server.md)。 
    
- 前端伺服器的負載平衡需要對 HTTP 流量 (例如「會議內容下載) 」的硬體負載平衡。 建議使用 DNS 負載平衡進行 SIP 流量。 如需詳細資訊，請參閱[商務用 Skype 的負載平衡需求](../../plan-your-deployment/network-requirements/load-balancing.md)。 
    
- 如果您想要對專用大型會議集區使用監控伺服器，我們建議使用監控伺服器及其在商務用 Skype Server 部署中所有前端伺服器集區間共用的資料庫。 如需詳細資訊，請參閱[Plan for monitoring in 商務用 Skype Server](../../plan-your-deployment/monitoring.md)。
