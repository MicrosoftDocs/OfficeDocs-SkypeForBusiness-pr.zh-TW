---
title: 在商務用 Skype Server 的 [拓撲產生器] 中部署轉送伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: '摘要: 瞭解如何在商務用 Skype Server 的 [拓撲建立器] 中定義及部署中繼伺服器。'
ms.openlocfilehash: 61b90bb874d96579d975a1672238a7427350a5dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190087"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a>在商務用 Skype Server 的 [拓撲產生器] 中部署轉送伺服器
 
**摘要:** 瞭解如何在商務用 Skype Server 的 [拓撲建立器] 中定義及部署中繼伺服器。
  
[企業語音工作]、[電話撥入式會議] 和 [高級企業語音應用程式] (回應群組應用程式、通話駐留應用程式、通話許可控制 (CAC) 等) 都可在前端池中使用。 轉送伺服器的功能是內嵌在前端伺服器中。 不需要個別獨立的中繼伺服器。 
  
唯一的例外是如果您將 SIP 主幹設定為連線至網際網路電話服務提供者的會話框線控制器。 若要將企業語音結構連線至 SIP 中繼提供者, 必須部署個別的中繼伺服器。
  
商務用 Skype 伺服器 (在前端池或獨立的中繼伺服器上的中繼伺服器 collocated) 和閘道之間的連線是指稱為主幹的邏輯關聯。 本節中的主題描述如何定義主幹, 以及如果您連線到 SIP 主幹, 如何部署獨立的中繼伺服器。
  
## <a name="define-a-mediation-server-in-topology-builder"></a>在拓撲建立器中定義中繼伺服器

您可以將轉送伺服器新增為前端池的 collocated 角色, 或定義獨立的獨立轉送伺服器池。
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>將中繼伺服器新增到前端池

1. 啟動拓撲產生器: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype server 2015**], 然後按一下 [**商務用 skype server 2015Topology**建立器]。
    
2. 在拓撲建立器中, 在主控台樹狀結構中, 展開您要為其定義前端池的網站名稱。
    
3. 在主控台樹狀結構中, 以滑鼠右鍵按一下您想要的前端池類型, 然後按一下 [**新增前端池 ...**]。
    
4. 流覽 [**定義新的前臺端池**] 嚮導, 直到您到達 [**選取 collocated 伺服器角色**] 頁面。
    
5. 在 [**選取 collocated 伺服器角色**] 中, 核取 [ **Collocate 中繼伺服器**] 的選項。
    
    > [!NOTE]
    > 如果您選取的 [前端] 池類型是 [企業版], 則會將轉送伺服器元件安裝在該前端池的所有前端伺服器上。 
  
    > [!NOTE]
    > 中繼伺服器所使用的**下一個躍點池**將是中繼伺服器正在 Collocated 的前端池。
  
    > [!NOTE]
    > 中繼伺服器所使用的**邊緣池**將是與中繼伺服器所 Collocated 之前端池相關聯的同一個 edge 池。
  
6. 按一下 [**設為預設值**], 使用這個前端池來路由來電至 PSTN。
    
7. 當您完成將一或多個對等專案關聯到前端池之後, 按一下 **[完成]** 。
    
    > [!NOTE]
    > 在您繼續進行企業語音部署程式中的下一個步驟之前, 請確認已將中繼伺服器池 (例如, 擁有中繼伺服器元件 collocated 的前臺端池) 使用您所指定的 Fqdn。 
  
8. 以滑鼠右鍵按一下**商務用 Skype Server 2015**節點, 然後按一下 [**發佈拓撲**]。
    
### <a name="to-add-a-standalone-mediation-server"></a>新增獨立的轉送伺服器

1. 啟動拓撲產生器: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype server 2015**], 然後按一下 [**商務用 skype server 2015Topology**建立器]。
    
2. 在拓撲建立器中, 在主控台樹狀結構中, 展開您要定義轉送伺服器的網站名稱。
    
3. 在主控台樹中, 以滑鼠右鍵按一下 [**轉送緩衝集區**] 節點, 然後按一下 [**轉送伺服器池**]。
    
4. 在 [**定義新的仲介池**] 中, 輸入中繼伺服器池的完整功能變數名稱 (FQDN)。
    
5. 接著, 請執行下列其中一項操作:
    
   - 如果您想要在池中部署多個轉送伺服器來提供高可用性, 請選取 [**多個電腦池**]。
    
     > [!NOTE]
     > 您必須[部署](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing), 才能支援擁有多個轉送伺服器的中繼伺服器池。
  
   - 如果您只想在池中部署一個轉送伺服器, 因為您不需要高可用性, 請選取 [**單一電腦池**]。 略過下列步驟。
    
6. 如果您在上一個步驟中選取了**多個電腦池**, 請在 [**定義此池中的電腦**] 專案中, 按一下 [**電腦 FQDN**], 輸入池中每個伺服器的 FQDN, 然後按一下 [**新增**]。 針對您要新增至池中的所有其他轉送伺服器, 重複此步驟。 在池中定義所有電腦之後, 請按 **[下一步]**。
    
7. 在 [**選取下一個躍點]** 頁面上, 按一下 **[下一個躍點池]**, 然後按一下將使用此中繼伺服器池的前端池 FQDN, 然後按 **[下一步]**。
    
8. 在 [**選取邊緣伺服器**] 頁面上, 執行下列其中一項操作:
    
   - 如果您想要將 PSTN 連線提供給已啟用企業語音的外部使用者, 請在 [**選取此中繼伺服器所使用的 Edge 池**] 底下, 按一下將使用此轉送服務伺服器池的 edge 伺服器池 FQDN, 以提供 pstn 連線至這些外部使用者, 然後按一下 **[下一步]**。
    
   - 如果您不打算為企業語音啟用外部使用者, 或者如果您不想在內部網路外部向使用者提供 PSTN 連線, 請按 **[下一步]**。
    
9. 以滑鼠右鍵按一下**商務用 Skype Server 2015**節點, 然後按一下 [**發佈拓撲**]。
    
## <a name="define-the-mediation-server-listening-ports"></a>定義中繼伺服器偵聽埠

請依照本主題中的步驟, 使用拓撲建立器定義中繼伺服器或池將接受來自閘道對等傳入連線的偵聽埠。
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>修改中繼伺服器偵聽埠

1. 啟動拓撲產生器: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype server 2015**], 然後按一下 [**商務用 skype server 2015Topology**建立器]。
    
2. 在 [拓撲建立器] 中, 展開 [**轉送緩衝集區**] 節點, 然後以滑鼠右鍵按一下先前建立的中繼伺服器。
    
3. 根據預設, 中繼伺服器上的 SIP 偵聽埠為從商務用 Skype Server 提供 TLS 流量的 5070, 而5067則是來自對等 (例如閘道、PBXes 或 SBCs) 的 TLS 流量。 TCP 埠預設為停用。 如果您的閘道不支援 TLS, 您就必須啟用 TCP 埠。
    
4. 指定所需的 TLS 或 TCP 偵聽埠範圍, 中繼伺服器將接受 PSTN 閘道的傳入連線。
    
    > [!NOTE]
    > 如果沒有核取 [**啟用 tcp 埠**], 則不需要輸入 tcp 埠範圍。 此設定是選擇性的。
  

