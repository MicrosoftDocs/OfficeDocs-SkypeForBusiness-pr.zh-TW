---
title: 確認已完成使用者複製
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 執行 Move-csuser Cmdlet 時，您可能會遇到失敗，因為 Active Directory 網域服務（AD DS）與商務用 Skype Server 2019 資料庫之間的使用者資訊無法同步處理，因為初始複製不完整。 成功完成商務用 Skype Server 2019 [使用者複製程式服務] 的初始同步處理所需的時間，取決於託管在託管商務用 Skype 的 Active Directory 林中的網網域控制站數量Server 2019 pool。 當商務用 Skype Server 2019 前端伺服器第一次啟動時，就會發生 [商務用 Skype Server 2019] 使用者複製程式服務初始同步處理常式。 之後，就會根據使用者複製程式間隔來同步處理。 完成下列步驟以驗證使用者複製已完成，然後再執行 Move-csuser Cmdlet。
ms.openlocfilehash: 31f4f9f1045367e376d4536df54c32be14580312
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812651"
---
# <a name="verify-user-replication-has-completed"></a>確認已完成使用者複製

當您執行**move-csuser** Cmdlet 時，如果 Active Directory 網域服務（AD DS）與商務用 Skype Server 2019 資料庫之間的使用者資訊無法同步處理，則您可能會遇到失敗，因為初始複製不完整。 成功完成商務用 Skype Server 2019 [使用者複製程式服務] 的初始同步處理所需的時間，取決於託管在託管商務用 Skype 的 Active Directory 林中的網網域控制站數量Server 2019 pool。 當商務用 Skype Server 2019 前端伺服器第一次啟動時，就會發生 [商務用 Skype Server 2019] 使用者複製程式服務初始同步處理常式。 之後，同步處理就會以使用者複製程式間隔為基礎。 完成下列步驟以驗證使用者複製已完成，然後再執行**move-csuser** Cmdlet。 
  
### <a name="to-verify-that-user-replication-has-completed"></a>驗證使用者複製已完成

1. 登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。
    
2. 按一下 [**開始**] 功能表，然後按一下 [**執行**]。 
    
3. 輸入**eventvwr.exe**，然後按一下 **[確定]**。
    
4. 在事件檢視器中，按一下 [**應用程式和服務記錄**] 加以展開，然後選取 [商務用 Skype Server]。 
    
5. 在 [**動作**] 窗格中，按一下 [**篩選目前的記錄**]。
    
6. 從 [**事件來源**] 清單中，按一下 [ **LS 使用者複製**]。
    
7. 在** \<所有事件識別碼\>** 中，輸入**30024**，然後按一下 **[確定]**。 
    
8. 在 [篩選的事件] 清單中的 [**一般**] 索引標籤上，尋找指出已成功完成使用者複製的專案。 
    

