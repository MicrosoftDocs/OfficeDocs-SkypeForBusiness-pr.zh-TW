---
title: 在商務用 Skype Server 中的拓撲產生器中部署轉送伺服器
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 摘要：瞭解如何在商務用 Skype Server 中的拓撲產生器中定義及部署轉送伺服器。
ms.openlocfilehash: 1e7f3b1540d6436c82e173b32252c5e9c59757da
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396045"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a>在商務用 Skype Server 中的拓撲產生器中部署轉送伺服器
 
**總結：** 瞭解如何在商務用 Skype Server 中的拓撲產生器中定義及部署轉送伺服器。
  
企業語音工作負載、撥入式會議和高級企業語音應用程式 (回應群組應用程式、通話駐留應用程式、通話許可控制 (CAC) 等等，在前端集區中皆可使用。 轉送伺服器的功能已內置於前端伺服器中。 不需要個別的獨立轉送伺服器。 
  
唯一例外情況是設定 SIP 主幹以連接至網際網路電話語音服務提供者的會話邊界控制器。 若要將您的企業語音基礎結構連接至 SIP 主幹提供者，則必須部署不同的轉送伺服器。
  
商務用 Skype Server 之間的連線 (前端集區或獨立中繼) 伺服器上的轉送伺服器組合，且閘道是定義為稱為主幹的邏輯關聯。 本節中的主題說明如何定義主幹及如何在連接至 SIP 主幹時，部署獨立的轉送伺服器。
  
## <a name="define-a-mediation-server-in-topology-builder"></a>在拓撲產生器中定義中繼伺服器

您可以在前端集區上新增轉送伺服器做為組合角色，或定義個別獨立的轉送伺服器集區。
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>若要將轉送伺服器新增至前端集區

1. 啟動拓撲產生器：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype Server 2015**]，然後按一下 [**商務用 Skype Server 2015Topology** 產生器]。
    
2. 在 [拓撲產生器] 的主控台樹中，展開您要定義前端集區的網站名稱。
    
3. 在主控台樹中，以滑鼠右鍵按一下您想要的前端集區類型，然後按一下 [ **新增前端集** 區]。
    
4. 完整瀏覽 [定義新前端集區] 精靈，直到到達 [選取組合的伺服器角色] 頁面為止。
    
5. 在 [ **選取組合伺服器角色**] 中，選取 [ **組合轉送伺服器**] 選項。
    
    > [!NOTE]
    > 如果您選取的前端集區類型為 Enterprise Edition，則轉送伺服器元件將會安裝在該前端集區的所有前端伺服器上。 
  
    > [!NOTE]
    > 轉送伺服器所使用的 **下一個躍點集** 區將是轉送伺服器組合所在的前端集區。
  
    > [!NOTE]
    > 轉送伺服器所使用的 **edge 集** 區將是與組合轉送伺服器的前端集區相關聯的相同 edge 集區。
  
6. 按一下 [ **成為預設** ]，使用此前端集區，將通話路由傳送至 PSTN。
    
7. 完成將一或多個對等專案關聯至前端集區時，按一下 **[完成]** 。
    
    > [!NOTE]
    > 在您繼續執行企業語音部署程式的下一個步驟之前，請確定轉送伺服器集區 (（例如，轉送伺服器元件為組合) 的前端集區）是使用您指定的 fqdn。 
  
8. 在 **商務用 Skype Server 2015** 節點上按一下滑鼠右鍵，然後按一下 [**發行拓撲**]。
    
### <a name="to-add-a-standalone-mediation-server"></a>新增獨立的轉送伺服器

1. 啟動拓撲產生器：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype Server 2015**]，然後按一下 [**商務用 Skype Server 2015Topology** 產生器]。
    
2. 在 [拓撲產生器] 的主控台樹中，展開您要定義轉送伺服器的網站名稱。
    
3. 在主控台樹中，以滑鼠右鍵 **按一下 [中繼** 集區] 節點，然後按一下 [ **轉送伺服器集** 區]。
    
4. 在 [ **定義新** 的中繼集區] 中，輸入轉送伺服器集區的完整功能變數名稱 (FQDN) 。
    
5. 接著執行下列其中一項作業：
    
   - 如果您想要在集區中部署多個轉送伺服器以提供高可用性，請選取 [ **多部電腦集** 區]。
    
     > [!NOTE]
     > 您必須 [部署](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) 以支援具有多部轉送伺服器的轉送伺服器集區。
  
   - 如果您只想要在集區中部署一個轉送伺服器，因為您不需要高可用性，請選取 [ **單一電腦集** 區]。 略過下列步驟。
    
6. 如果您在上一個步驟中，在 [定義此集區中的電腦] 項目上選取了 [多部電腦集區]，則可按一下 [電腦 FQDN]、鍵入集區中每一部伺服器的 FQDN，然後按一下 [新增]。 針對您要新增至集區的所有其他轉送伺服器重複此步驟。 在定義集區中的所有電腦之後，按 [下一步]。
    
7. 在 [ **選取下一個躍點]** 頁面上，按一下 **[下一個躍點集區]**，然後按一下將使用此轉送伺服器集區的前端集區 FQDN，然後按 **[下一步]**。
    
8. 在 **[選取 Edge Server]** 頁面上，執行下列其中一項：
    
   - 如果您想要為已啟用企業語音的外部使用者提供 PSTN 連線，請在 [**選取此轉送伺服器使用的 edge 集** 區] 下，按一下要使用此轉送伺服器集區的 edge server 集區的 FQDN，以提供 PSTN 與這些外部使用者的連線能力，然後按 **[下一步]**。
    
   - 如果您不打算為外部使用者啟用企業語音，或是不想要在內部網路以外為使用者提供 PSTN 連線能力，請按 **[下一步]**。
    
9. 在 **商務用 Skype Server 2015** 節點上按一下滑鼠右鍵，然後按一下 [**發行拓撲**]。
    
## <a name="define-the-mediation-server-listening-ports"></a>定義轉送伺服器聆聽埠

遵循此主題中的步驟，使用拓撲產生器定義轉送伺服器或集區將接受來自閘道對等的傳入連線的聆聽埠。
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>修改轉送伺服器的聆聽埠

1. 啟動拓撲產生器：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype Server 2015**]，然後按一下 [**商務用 Skype Server 2015Topology** 產生器]。
    
2. 在 [拓撲產生器] 的主控台樹中，展開 [中繼集區 **] 節點，** 然後以滑鼠右鍵按一下先前建立的轉送伺服器。
    
3. 根據預設，轉送伺服器上的 SIP 聆聽埠為從商務用 Skype Server 的 tls 流量5070，而5067用於來自對等方的 tls 流量 (例如閘道、PBXes 或 SBCs) 。 TCP 連接埠預設是停用的。 如果您的閘道不支援 TLS，則必須啟用 TCP 連接埠。
    
4. 指定所需的 TLS 或 TCP 接聽埠範圍，轉送伺服器將接受來自 PSTN 閘道的傳入連線。
    
    > [!NOTE]
    > 若未勾選 [啟用 TCP 連接埠]，則不一定要輸入 TCP 連接埠範圍。此為選用設定。
  

