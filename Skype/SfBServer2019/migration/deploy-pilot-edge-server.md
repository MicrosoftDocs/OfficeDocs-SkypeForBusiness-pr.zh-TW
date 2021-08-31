---
title: 部署試驗 Edge Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 本主題強調在部署商務用 Skype Server 2019 Edge Server 之前，應注意的設定設定。 商務用 Skype Server 2019 的部署和設定程式非常類似商務用 Skype Server 2015。 本節只著重在部署試驗集區時應該考量的要點。 如需詳細步驟，請參閱部署檔中的商務用 Skype Server 2019 部署外部使用者存取，它會說明部署程式，也會提供外部使用者存取的設定資訊。
ms.openlocfilehash: 39ec659c5099a7be9587c630aa487ddeda1df500
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728042"
---
# <a name="deploy-pilot-edge-server"></a>部署試驗 Edge Server

本主題強調在部署商務用 Skype Server 2019 Edge Server 之前，應注意的設定設定。 商務用 Skype Server 2019 的部署和設定程式非常類似商務用 Skype Server 2015。 本節只著重在部署試驗集區時應該考量的要點。 <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
啟動 [定義新 Edge 集區精靈] 逐步完成設定，請檢閱下列步驟中的重要組態設定。請注意，下面只列出了「定義新 Edge 集區精靈」 部分頁面而已。 
  
### <a name="to-define-an-edge-pool"></a>定義 Edge 集區

1. 以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。
    
2. 流覽至商務用 Skype Server 2019 節點。 用滑鼠右鍵按一下 [Edge 集區]，然後按一下 [新增 Edge 集區]。
    
     ![[定義新的 Edge 集區] 對話方塊。](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. Edge 集區可以是 [多部電腦集區] 或 [單一電腦集區]。
    
     ![[定義 Edge 集區 FQDN] 對話方塊。](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. 在「選取功能」頁面上，請勿啟用同盟或 XMPP 同盟。 同盟和 XMPP 同盟目前是透過舊版 Edge Server 路由傳送。 在移轉的後期階段，將會設定這些功能。 

  
5. 繼續完成下列嚮導頁面： **外部 fqdn**、 **定義內部 ip 位址**，以及 **定義外部 ip 位址**。
    
6. 在 [ **定義下一個躍點伺服器** ] 頁面上，選取舊版 Edge 集區的下一個躍點 Director。 
    
     ![[定義下一個躍點] 對話方塊。](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. 在 [ **建立前端或** 中繼集區] 頁面上，請勿在此時間建立集區與此 Edge 集區的關聯。 外部媒體流量目前是透過舊版 Edge Server 路由傳送。 這項設定到了移轉的後期階段還會再調整。 
    
     ![[建立前端集區的關聯] 對話方塊。](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. 按一下 **[完成]**，然後 **發行** 拓撲。 
    
9. 遵循部署檔中的步驟，在新 Edge Server 上安裝檔案、設定憑證，然後啟動服務。 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
請務必遵循部署檔中主題的指導方針。 本節只提供安裝這些伺服器角色時，部分組態設定的指示。 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
現在，您應該會同時部署舊版 Edge server 與商務用 Skype Server 2019 Edge server 部署。 確認部署雙方皆可正常運作、服務已啟用，且您也能管理每個部署，接著，就可以前往下一個階段。 
  

