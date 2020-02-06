---
title: 規劃商務用 Skype Server 的會議拓撲
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
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 摘要：請閱讀本主題，瞭解如何在商務用 Skype Server 中規劃會議拓撲。
ms.openlocfilehash: 1b9d9024d90b4bd847c763747dad7a5f96616aa3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816012"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>規劃商務用 Skype Server 的會議拓撲
 
**摘要：** 若要瞭解如何在商務用 Skype Server 中規劃會議拓撲，請閱讀本主題。
  
本主題說明商務用 Skype Server 中的會議拓撲基礎：
  
- 支援的拓撲
    
- 電話撥入式會議考慮
    
- 網路會議考慮
    
- 大型會議的需求
    
如需硬體和軟體需求的詳細資訊，請參閱[商務用 Skype Server 中的會議硬體和軟體需求](hardware-and-software-requirements.md)。
  
## <a name="supported-topologies"></a>支援的拓撲

在商務用 Skype Server 中，執行會議服務的伺服器總是與前端伺服器或標準版伺服器 collocated。 當您部署商務用 Skype Server 時，IM 會議功能會自動部署。 您可以使用 [拓撲建立器] 來指定是否要部署 web、音訊和影片（A/V）和電話撥入式會議。 您也可以使用拓撲建立器，將會議新增至現有的部署。 如需有關拓撲基礎與 collocation 案例的詳細資料，請參閱[商務用 Skype Server 的拓撲基礎](../../plan-your-deployment/topology-basics/topology-basics.md)。
  
您可以在下列拓撲和配置中部署會議：
  
- 商務用 Skype Server 標準版
    
- 商務用 Skype Server Enterprise Edition
    
- 具備或不使用企業語音
    
## <a name="dial-in-conferencing-considerations"></a>電話撥入式會議考慮

如果您要部署電話撥入式會議，您必須考慮下列事項：
  
- 電話撥入式會議需要一台中繼伺服器來在商務用 Skype Server 和 PSTN 閘道之間轉譯信號（和媒體），以及在中繼伺服器與 PSTN 閘道之間轉譯信號與媒體的 PSTN 閘道.
    
   在您可以設定電話撥入式會議之前，您必須先部署企業語音或中繼伺服器，以及至少下列其中一項：
    
  - PSTN 閘道
    
  - IP-PBX
    
  - 會話邊界控制器（SBC）（適用于您透過設定 SIP 主幹來連接的網際網路電話服務提供者）
    
- 您可以在中央網站中部署應用程式服務、會議助理應用程式及會議發佈應用程式，但不能在分支網站中進行。
    
- 您必須在您部署商務用 Skype Server 會議的每個池中部署電話撥入式會議。 您不需要在每個池中指派存取號碼，但您必須在每個池中部署電話撥入式會議功能。 當使用者從某個池中呼叫存取號碼以在不同的池中加入商務用 Skype Server 會議時，此需求支援所記錄的名稱功能。 
    
如需詳細資訊，請參閱[在商務用 Skype Server 中規劃電話撥入式會議](dial-in-conferencing.md)。
  
## <a name="web-conferencing-considerations"></a>網路會議考慮

網路會議需要下列各項： 
  
- 存取儲存網路會議內容所用的檔案存放區。
    
- 與 Office Web Apps Server/Office Online Server 整合，這是在會議期間共用 PowerPoint 檔案所需的。
    
> [!NOTE]
> Office Web Apps Server 的最新小版本命名為「Office Online Server」，而商務用 Skype Server 支援此伺服器。 如需詳細資訊，請參閱[Office Online Server 檔](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)。 
  
商務用 Skype 伺服器提供下列配置 Office Web Apps Server/Office Online Server 的方式。 視您的需求而定，您可以：
  
- **安裝商務用 Skype Server 和 Office Web Apps 伺服器/Office Online Server 內部部署（位於您組織的防火牆之後），且位於相同的網路區域中。** 透過這種拓撲，即可透過您的反向 proxy 伺服器提供 Office Web Apps Server/Office Online 伺服器的外部存取。 在理想的情況下，您應該在與商務用 Skype Server 相同的網路區域中安裝 Office Web Apps Server/Office Online 伺服器。
    
    外部商務用 Skype 用戶端可以使用反向 proxy 伺服器連線到商務用 skype Server 和 Office Web Apps Server/Office Online 伺服器，該伺服器會接受來自網際網路的要求，並將其轉寄給內部網路。 （內部用戶端不需要使用反向 proxy 伺服器，因為他們可以直接連線到 Office Web Apps Server/Office Online Server。）如果您想要使用僅供商務用 Skype 伺服器使用的專用 Office Web Apps Server/Office Online 伺服器群，此拓撲最佳發揮作用。
    
- **使用外部部署的 Office Web Apps Server/Office Online 伺服器。** 在此拓朴中，商務用 Skype Server 是在內部部署，並使用在商務用 Skype Server network 區域外部部署的 Office Web Apps Server/Office Online 伺服器。 當 Office Web Apps Server/Office Online Server 在企業中的多個應用程式間共用，且已部署在需要商務用 Skype Server 的網路中使用 Office Web Apps Server/Office Online Server 的外部介面時，可能會發生這種情況。
    
    您不需要安裝反向 proxy 伺服器;相反地，來自 Office Web Apps Server/Office Online Server 的所有要求都是透過您的邊緣伺服器進行路由。 您的內部和外部商務用 Skype 用戶端都連線至 Office Web Apps Server/Office Online 伺服器（使用外部 URL）。
    
    如果 Office Web Apps Server/Office Online Server 是在您的內部防火牆外部署，請選取 [ **Office Web Apps 伺服器] 部署在**拓撲結構建立器中的外部網路（也就是 [週邊/網際網路]）。
    
如需詳細資訊，請參閱[在商務用 Skype server 中設定與 Office Web Apps server 整合](../../deploy/deploy-conferencing/office-web-app-server.md)。 
  
不論您選取何種拓撲，請務必開啟正確的防火牆埠。 您必須確認無法透過 Office Web Apps Server/Office Online Server、負載平衡器或商務用 Skype Server 上的防火牆封鎖 DNS 名稱、IP 位址和埠。
  
> [!NOTE]
> 提供外部存取 Office Web Apps Server/Office Online Server 的另一個選項，就是在周邊網路中部署伺服器。 如果您選擇這樣做，請記住 Office Web Apps Server/Office Online Server 安裝程式要求伺服器電腦成為您 Active Directory 網域的成員。 除非您的網路原則允許周邊網路中的電腦成為 Active Directory 網域成員，否則建議您不要在周邊網路中安裝 Office Web Apps Server/Office Online 伺服器。 相反地，您應該在內部網路中安裝 Office Web Apps Server/Office Online 伺服器，並透過您的反向 proxy 伺服器提供外部使用者存取權。 
  
## <a name="topology-requirements-for-large-meetings"></a>大型會議的拓撲需求

單一大型會議需要至少一個前端伺服器和一台後端伺服器。 不過，為了提供高可用性，我們建議使用兩個具有鏡像後端伺服器的前端伺服器池，如下圖所示：
  
**大型會議拓撲**

![大型會議拓撲](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
主持大型會議的使用者必須擁有其使用者帳戶駐留在前端池中。 不過，我們不建議您在此池中託管其他使用者帳戶。 相反地，只能在大型會議中使用。 最佳做法是在此池中建立特殊的使用者帳戶，只是用來主持大型會議。 因為大型會議設定已針對效能優化，所以將它當作一般使用者使用時，可能會發生問題，例如在涉及 PSTN 端點時無法將 P2P 會話升級至會議。
  
管理只有兩個前端伺服器的池需要一些特殊的考慮。 如需詳細資訊，請參閱[商務用 Skype server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)與[商務用 skype Server 2015 的參考](../../plan-your-deployment/topology-basics/reference-topologies.md)資料拓撲基礎。
  
此外，如果您想要選擇性地針對大型會議所用的池子提供災害復原備份與容錯移轉，您可以將它與其他資料中心的專用池進行配對。 如需詳細資訊，請參閱[在商務用 Skype Server 中規劃高可用性和災害復原](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
關於拓撲的其他注意事項包括：
  
- 儲存會議內容需要檔案共用，並在已部署並啟用封存伺服器的情況下，儲存存檔檔案。 檔案共用可以專用於該文件庫，或者可以是部署該池之網站上另一個池所使用的相同檔案共用。 如需有關配置檔案共用的詳細資訊，請參閱[在商務用 Skype Server 2015 中建立檔案共用](../../deploy/install/create-a-file-share.md)。
    
- 若要啟用大型會議中的 PowerPoint 簡報功能，必須具備 Office Web Apps Server/Office Online 伺服器。 Office Web Apps Server/Office Online 伺服器可以專用於大型會議池，也可以是部署專用池之網站上其他池所使用的 Office Web Apps 伺服器/Office Online 伺服器。 如需詳細資訊，請參閱[在商務用 Skype server 中設定與 Office Web Apps server 整合](../../deploy/deploy-conferencing/office-web-app-server.md)。 
    
- 前端伺服器的負載平衡需要針對 HTTP 流量進行硬體負載平衡（例如會議內容下載）。 針對 SIP 流量，建議使用 DNS 負載平衡。 如需詳細資訊，請參閱[商務用 Skype 的負載平衡需求](../../plan-your-deployment/network-requirements/load-balancing.md)。 
    
- 如果您想要將監視伺服器用於專用大型會議池，我們建議使用監視伺服器及其在商務用 Skype Server 部署中的所有前端伺服器池中共用的資料庫。 如需詳細資訊，請參閱[在商務用 Skype 伺服器中規劃監視](../../plan-your-deployment/monitoring.md)。
    

