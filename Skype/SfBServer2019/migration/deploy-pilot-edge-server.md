---
title: 部署試點邊緣伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本主題重點說明在部署商務用 Skype Server 2019 Edge 伺服器之前, 您應該知道的配置設定。 商務用 skype Server 2019 的部署和設定處理常式與商務用 Skype Server 2015 非常類似。 此區段只會醒目提示您要考慮的重要重點, 做為您的試驗池部署的一部分。 如需詳細步驟, 請參閱部署檔中的商務用 Skype Server 2019 部署外部使用者存取 (描述部署程式), 同時提供外部使用者存取的設定資訊。
ms.openlocfilehash: b416ba38646d05f3d10a7d2643c01924fe57020a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238954"
---
# <a name="deploy-pilot-edge-server"></a>部署試點邊緣伺服器

本主題重點說明在部署商務用 Skype Server 2019 Edge 伺服器之前, 您應該注意的配置設定。 商務用 skype Server 2019 的部署和設定處理常式與商務用 Skype Server 2015 非常類似。 此區段只會醒目提示您要考慮的重要重點, 做為您的試驗池部署的一部分。 <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
當您流覽 [**定義新的邊緣池**] 嚮導時, 請參閱下列步驟中所示的 [金鑰設定] 設定。 請注意, 只有幾頁會顯示 [**定義新的邊緣池**] 嚮導。 
  
### <a name="to-define-an-edge-pool"></a>定義邊緣池

1. 登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。
    
2. 流覽至商務用 Skype Server 2019 節點。 以滑鼠右鍵按一下 [**邊緣池**], 然後按一下 [**新增邊緣池**]。
    
     ![[定義新的 Edge 集區] 對話方塊](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. Edge 池可以是**多個電腦池**或**單一電腦池**。
    
     ![[定義 Edge 集區 FQDN] 對話方塊](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. 在 [**選取功能**] 頁面上, 不要啟用同盟或 XMPP 同盟。 同盟與 XMPP 同盟目前是透過舊版 Edge 伺服器路由。 這些功能將會在稍後的遷移階段進行設定。 

  
5. 繼續完成下列嚮導頁面:**外部 fqdn**、**定義內部 ip 位址**, 以及**定義外部 ip 位址**。
    
6. 在 [**定義下一個躍點伺服器]** 頁面上, 選取舊版 Edge 池下一個躍點的主管。 
    
     ![[定義下一個躍點] 對話方塊](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. 在 [**關聯前端或轉送池**] 頁面上, 請勿在此時將池與此 Edge 池建立關聯。 外部媒體流量目前是透過舊版 Edge 伺服器路由。 此設定將會在稍後的遷移階段進行設定。 
    
     ![[建立前端集區的關聯] 對話方塊](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. 按一下 **[完成]**, 然後**發佈**拓撲。 
    
9. 依照部署檔中的步驟, 在新的 Edge 伺服器上安裝檔案、設定憑證, 然後啟動服務。 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
請務必遵循部署檔中主題中的指導方針。 本節僅提供安裝這些伺服器角色時設定設定的一些指導方針。 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
您現在應該會與商務用 Skype Server 2019 Edge 伺服器部署並行部署舊版 Edge 伺服器。 確認這兩個部署都能正常運作、服務已啟動, 而且您可以在移至下一個階段之前管理每個部署。 
  

