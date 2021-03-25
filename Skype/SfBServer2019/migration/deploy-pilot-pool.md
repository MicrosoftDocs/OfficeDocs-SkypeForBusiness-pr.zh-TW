---
title: 部署試驗集區
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 遷移至商務用 Skype Server 2019 所需的第一步，是部署試驗集區。 試驗集區是您使用舊版部署來測試商務用 Skype Server 2019 的共存所在位置。 共存是一種暫時的狀態，會持續進行，直到您將所有使用者和集區移至商務用 Skype Server 2019 為止。
ms.openlocfilehash: a8d9a1bbe5f629a91721ebe530e6a192e3e65b62
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113289"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>部署商務用 Skype Server 2019 試驗集區

遷移至商務用 Skype Server 2019 所需的第一步，是部署試驗集區。 試驗集區是您使用舊版部署來測試商務用 Skype Server 2019 的共存所在位置。 共存是一種暫時的狀態，會持續進行，直到您將所有使用者和集區移至商務用 Skype Server 2019 為止。 
  
當您部署試驗集區時，會用到 [定義新前端集區精靈]。 您應該在您的舊版集區中，在商務用 Skype Server 2019 試驗集區中部署相同的功能和工作負載。 如果您已部署封存伺服器、監控伺服器或 System Center Operations Manager 以封存或監控舊版環境，且您想要在整個遷移期間繼續封存或監控，您也必須在試驗環境中部署這些功能。 您部署以封存或監視舊版環境的版本，將不會在商務用 Skype Server 2019 環境中捕獲資料。 
  
> [!NOTE]
> 下列程序討論在整個試驗集區部署程序中，應考量的功能和設定。 本節只著重在部署試驗集區時應該考量的要點。 <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>部署商務用 Skype Server 2019 試驗集區

1. 以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。
    
2. 展開樹狀目錄，直到您找到 **商務用 Skype Server 2019**  >  **Enterprise Edition 前端** 集區。
    
3. 以滑鼠右鍵按一下 [ **Enterprise Edition 前端** 集區]，然後選取 [ **新增前端集** 區]。
  
4. 輸入集區的完整功能變數名稱 (FQDN) 。 當您定義試驗集區時，您可以選擇部署 Enterprise Edition 前端集區或 Standard Edition server。 商務用 Skype Server 2019 不要求試驗集區的功能符合您舊版集區中部署的功能。
    
    > [!CAUTION]
    > 您為試驗集區定義的集區或伺服器 FQDN 必須是唯一的。 它無法與目前部署的舊版集區或任何其他伺服器的名稱相符。 
  
5. 在「選取功能」頁面上，選取您希望此前端集區擁有的功能之對應核取方塊。 例如，如果您只部署立即訊息 (IM) 和目前狀態功能，您可以選取 [會議] 核取方塊以允許多方 IM，但是您不會選取 [撥入] (PSTN) 會議、Enterprise Voice 或通話許可控制] 核取方塊，因為它們代表語音、影片及共同作業會議功能。 <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. 在 [ **選取組合的伺服器角色** ] 頁面上，建議您選擇在商務用 Skype server 2019 中組合轉送伺服器。 在合併舊版拓撲與商務用 Skype Server 2019 時，我們需要您先組合傳統的轉送伺服器。 在合併拓撲並設定商務用 Skype Server 2019 轉送伺服器之後，您可以決定是否要保留組合轉送伺服器，或在將轉送伺服器角色移2019至獨立伺服器時，將其變更為獨立伺服器。 
   
7. 在試驗集區部署期間，在 [ **關聯伺服器角色與此前端集** 區] 頁面上， *請勿* 選擇 [ **啟用此前端集區的媒體元件使用 Edge 集** 區] 選項。 此為您會在移轉後期階段時才啟用及上線的功能。 目前請將此設定保留清空。 
  
8. 在「選取 Office Web Apps Server」頁面上，按一下 [新增]，並指定應用程式伺服器的 FQDN。
  
9. 在 [ **定義封存 SQL Server 儲存區** ] 頁面上，在為商務用 skype server 封存和監控定義 sql server 存放區時，請選取先前為商務用 skype server 2019 建立的 sql server 實例。 
  
10. 若要發行您的拓撲，請以滑鼠右鍵按一下 [ **商務用 Skype 伺服器** ] 節點，然後按一下 [ **發行拓撲**]。
  
11. 當發行程序完成時，按一下 **[完成]**。

12. 移至下一個稱為「驗證試驗集區與舊版集區共存」的區段之前，您需要安裝已發行拓撲中所定義的商務用 Skype Server 新前端試驗集區，請遵循這裡所述的程式在 [拓撲中的伺服器上安裝商務用 Skype server。](../../SfbServer/deploy/install/install-skype-for-business-server.md)

13. 完成上述步驟後，請移至下一節，以確認試驗集區與舊版集區共存。
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
