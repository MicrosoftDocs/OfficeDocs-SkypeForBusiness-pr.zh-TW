---
title: Skype 會議室系統的遷移考慮
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: 請閱讀本主題，瞭解如何在擁有多個版本商務用 Skype Server 和 Lync Server 的環境中部署 Skype 會議室系統。
ms.openlocfilehash: 6524a7312644ec306185b952caf17818d29344af
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774671"
---
# <a name="skype-room-system-migration-considerations"></a>Skype 會議室系統的遷移考慮
 
請閱讀本主題，瞭解如何在擁有多個版本商務用 Skype Server 和 Lync Server 的環境中部署 Skype 會議室系統。
  
## <a name="migration-considerations"></a>遷移考慮

如果您是在包含不同版本商務用 Skype Server 或 Lync Server 的多池環境中部署 Skype 會議室系統，此區段會提供指導方針。 
  
Lync Server 中的使用者複製程式（UR）元件會從 Active Directory 取得使用者物件，並將它們放入 Lync Server 後端 SQL Server 資料庫。 只有 Lync Server 2013 中的 UR 可識別 Skype 室系統物件。 在舊版 Lync Server 和 Office 通訊伺服器的 UR 中，不會偵測到指定 LRS 物件的 Active Directory 屬性，因此無法辨識這些屬性。 
  
如果 Skype 會議室系統帳戶嘗試登入 Lync，並根據 SRV 記錄或 DNS A 記錄查詢來執行自動探索，而如果這些帳戶指向舊版的 Lync Server 或 Office 通訊伺服器，LRS 將會收到404找不到的回應 舊版資源區。 舊版池將無法重新導向 Skype 會議室系統至其 Lync Server 2013 家用版池。 
  
您可以使用下列選項來解決此問題： 
  
- 將您的自動探索 SRV 記錄（_sipinternaltls _tcp）指向 Lync Server 2013 池。
    
- 如果第一個選項無法使用，您必須手動設定 LRS，並在 Skype 會議室系統主控台應用程式中直接設定，以提供 Lync Server 2013 池位址。 
    
- 如果您是在商業網路外部部署 Skype 室系統，且已部署並設定 Lync Edge 伺服器以指向舊版池或控制器，則需要副 Edge 伺服器網站，該網站會指向 Lync Server 2013 池。 如需有關部署副 Edge 伺服器的詳細資訊，請參閱 Edge 伺服器部署檔。 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>使用 Lync Server 2010 池的 Skype 會議室系統互通性

在遷移期間，如果駐留在 Lync Server 2010 擁有者的使用者排程會議並邀請 Skype 室系統帳戶，Skype 聊天室系統用戶端在參加會議時將擁有有限的功能。 
  
當 Skype 會議室系統用戶端加入由駐留在 Lync Server 2010 的使用者所組織的排程會議通話時，Skype 室系統具有下列會議限制： 
  
- Skype 室系統無法顯示多重查看影片庫。
    
- 如果您是簡報者的 Skype 會議室系統用戶端，則無法在參與者上套用視頻鎖。
    
- Skype 室系統無法顯示1080p 影片解析度（入站或出站），即使 Lync Server 2013 會議原則允許，還是由於下列原因所示： 
    
  - Lync Server 2010 不支援1080p 解析度。
    
  - Skype 室系統永遠受到召集人的影片解析度之會議原則的限制。 因此，即使 Lync 2010 池支援720p 解析度，只要召集人原則不支援720p，Skype 室系統就無法利用720p 解析度。 
    
- Lync 2013 用戶端偵測會議室中的 LRS 目前狀態，並自動將自己設為靜音，以避免實體會議室中的回音。 此功能不適用於 Lync Server 2010 上託管的會議。
    
- 在 Lync Server 2010 上託管的會議的桌面共用效能有一些限制。
    
- 使用者將無法加入在 Lync 2010 上託管的私人（受限制）會議與 Skype 會議室系統。
    

