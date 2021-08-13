---
title: 確認已完成使用者複製
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
description: 執行 Move-CsUser Cmdlet 時，可能會發生失敗，因為 Active Directory 網域服務 (AD DS) 和商務用 Skype Server 2019 資料庫之間的使用者資訊因初始複寫不完整而不同步。 成功完成商務用 Skype Server 2019 使用者複寫器服務的初始同步處理所需的時間，取決於主控商務用 Skype Server 2019 集區之 Active Directory 樹系中主控的網域控制站數目。 當第一次啟動商務用 Skype Server 2019 前端伺服器時，就會發生商務用 Skype Server 2019 User 複寫器服務初始同步處理常式。 完成後，則是根據使用者複寫器間隔來進行同步化。 在執行 Move-CsUser Cmdlet 之前，請完成下列步驟來確認已完成使用者複寫。
ms.openlocfilehash: 0fe1c205b04ed32f5ac4281e555d5a44262905aa23b74eb69148d447337b59f7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54325680"
---
# <a name="verify-user-replication-has-completed"></a>確認已完成使用者複製

在執行 **Move-CsUser** Cmdlet 時，如果 Active Directory 網域服務 (AD DS) 和商務用 Skype Server 2019 資料庫之間的使用者資訊不同步，則您可能會遇到失敗，因為初始複寫不完整。 成功完成商務用 Skype Server 2019 使用者複寫器服務的初始同步處理所需的時間，取決於主控商務用 Skype Server 2019 集區之 Active Directory 樹系中主控的網域控制站數目。 當第一次啟動商務用 Skype Server 2019 前端伺服器時，就會發生商務用 Skype Server 2019 User 複寫器服務初始同步處理常式。 之後，同步處理是以使用者複製器間隔為基礎。 完成下列步驟，以確認使用者複寫已完成，再執行 **Move-CsUser** Cmdlet。 
  
### <a name="to-verify-that-user-replication-has-completed"></a>確認使用者複寫已完成

1. 以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。
    
2. 按一下 [開始] 功能表，然後按一下 [執行]。 
    
3. 輸入 **eventvwr.exe**，然後按一下 [確定]。
    
4. 在事件檢視器中，按一下 [**應用程式及服務記錄** 檔] 加以展開，然後選取 [商務用 Skype Server]。 
    
5. 在 [動作] 窗格中，按一下 [篩選目前的記錄]。
    
6. 在 [事件來源] 清單中，按一下 [LS 使用者複寫器]。
    
7. 在中 **\<All Event IDs\>** ，輸入 **30024**，然後按一下 **[確定]**。 
    
8. 在 [篩選的事件] 清單中的 [ **一般** ] 索引標籤上，尋找表明使用者複寫順利完成的專案。 
    

