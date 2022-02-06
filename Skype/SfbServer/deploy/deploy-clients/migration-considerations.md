---
title: Skype 房間系統移轉考慮
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: 閱讀此主題以瞭解如何在具有多種版本商務用 Skype Server 和 Lync Server 的環境中部署 Skype 的會議室系統。
---

# <a name="skype-room-system-migration-considerations"></a>Skype 房間系統移轉考慮
 
閱讀此主題以瞭解如何在具有多種版本商務用 Skype Server 和 Lync Server 的環境中部署 Skype 的會議室系統。
  
## <a name="migration-considerations"></a>移轉考量

如果您要在包含不同版本商務用 Skype Server 或 Lync Server 的多集區環境中部署 Skype 的會議室系統，則本節提供指導方針。 
  
Lync server 中的使用者複寫器 (UR) 元件會從 Active Directory 取得使用者物件，並將它們放入 Lync Server 後端 SQL Server 資料庫中。 只有 Lync Server 2013 中的 UR 知道 Skype 的會議室系統物件。 先前版本的 Lync server 和 Office 通訊伺服器的 UR 不會偵測出指派 LRS 物件的 Active Directory 屬性，因此不會察覺到這些物件。 
  
如果 Skype 房間系統帳戶嘗試登入 Lync，並根據 SRV 記錄或 DNS a 記錄的查詢來執行自動探索，而且如果這些帳戶指向舊版的 Lync server 或 Office 通訊伺服器，則 LRS 將會從舊版集區接收未找到404的回應。 舊版集區無法將 Skype 聊天室系統重新導向至其 Lync Server 2013 主集區。 
  
您可以使用下列選項來解決此問題： 
  
- 將您的自動探索 SRV 記錄指向 Lync Server 2013 集區 (_sipinternaltls ._tcp .com) 。
    
- 如果無法使用第一個選項，您必須手動設定 LRS，並在 Skype 的會議室系統主控台應用程式中直接設定，以提供 Lync Server 2013 集區位址。 
    
- 如果在公司網路外部部署 Skype 的會議室系統，且已部署並設定 Lync Edge server 指向舊版集區或 director，則需要次要 Edge server 網站，該網站指向 Lync Server 2013 集區。 如需部署次要 Edge Server 的詳細資訊，請參閱 Edge Server 部署檔。 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Skype 與 Lync Server 2010 集區的聊天室系統互通性

在遷移期間，如果駐留在 Lync Server 2010 集區上的使用者排程會議並邀請 Skype 的會議室系統帳戶，則 Skype 的會議室系統用戶端在出席會議時將具有有限的功能。 
  
當 Skype 會議室系統用戶端加入已由位於 Lync Server 2010 之使用者所組織的排程會議呼叫時，Skype 會議室系統會具備下列會議限制： 
  
- Skype 房間系統無法顯示多視圖影片庫。
    
- 如果 Skype 的會議室系統用戶端是簡報者，它無法在參與者上套用影片鎖定。
    
- Skype 會議室系統無法將1080p 影片解析度顯示 (輸入或輸出) ，即使 Lync Server 2013 會議原則允許，也是如此，因為下列原因： 
    
  - Lync Server 2010 不支援1080p 解析度。
    
  - Skype 的會議室系統一定會受到召集人的影片解析度的會議原則的限制。 因此，即使 Lync 2010 集區支援720p 解析度，只要召集人的原則不支援，Skype 的會議室系統將無法利用720p 解析度。 
    
- Lync 2013 用戶端偵測會議會議室中的 LRS 目前狀態，並自動將其靜音以避免實體會議會議室中的回聲。 這項功能無法在 Lync Server 2010 上主控的會議中運作。
    
- 在 Lync Server 2010 上主控會議的桌面共用效能有一些限制。
    
- 使用者將無法使用 Skype 的會議室系統，加入 Lync 2010 上主控的私人 (限制) 會議。
    

