---
title: 移動剩餘的使用者
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '您可以使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype Server 管理] 命令介面, 將使用者移至新的商務用 Skype Server 2019 部署。 您必須符合一些需求, 才能確保順利轉換至商務用 Skype Server 2019。 如需有關完成本主題中程式的先決條件的詳細資訊, 請參閱設定要遷移的用戶端。 如需有關移動使用者的詳細步驟, 請參閱階段 4: 將測試使用者移至試驗池。'
ms.openlocfilehash: 8c12ca52e162c4317dabc59d5de9b74082730882
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244783"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>將剩餘的使用者移至商務用 Skype Server 2019

您可以使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype Server 管理] 命令介面, 將使用者移至新的商務用 Skype Server 2019 部署。 您必須符合一些需求, 才能確保順利轉換至商務用 Skype Server 2019。 如需有關完成本主題中程式的先決條件的詳細資訊, 請參閱[設定要遷移的用戶端](configure-clients-for-migration.md)。 如需有關移動使用者的詳細步驟, 請參閱[階段 4: 將測試使用者移至試驗池](phase-4-move-test-users-to-the-pilot-pool.md)。
  
> [!IMPORTANT]
> 您無法使用 Active Directory 使用者和電腦管理單元或舊版管理工具, 將使用者從舊版環境移至商務用 Skype Server 2019。 
  
當您將使用者移至商務用 Skype Server 2019 文件庫時, 該使用者的資料會移至與新的資料庫池相關聯的後端資料庫。 
  
> [!IMPORTANT]
> 這包括舊版使用者建立的作用中會議。 例如, 如果舊版使用者已設定「我的**會議**會議, 則在使用者移動之後, 新的商務用 Skype Server 2019 池中仍會提供該會議。 存取該會議的詳細資料仍會是相同的**會議 URL 與會議 ID**。 唯一的差異是, 會議現在是託管在商務用 Skype Server 2019 池中, 而不是在舊版池中。 
  
> [!NOTE]
> 在商務用 Skype Server 2019 上託管使用者, 不需要您同時部署已升級的用戶端。 只有在使用者升級至新的用戶端軟體時, 才能使用新的功能。 
  
### <a name="post-migration-task"></a>遷移後任務

1. 在您移動使用者之後, 請確認指派給他們的會議原則。 
    
2. 若要確保由2019駐留在舊版安裝中的使用者所組織的會議能與駐留在舊版安裝的聯盟使用者順暢運作, 指派給已遷移使用者的會議原則應該允許匿名參與者。
    
3. 允許匿名參與者的會議原則**允許參與者邀請**在商務用 Skype Server 2019 [控制台] 中選取匿名使用者, 並將**AllowAnonymousParticipantsInMeetings**設定為**True** (在從商務用 Skype Server Management Shell 中的**CsConferencingPolicy** Cmdlet 輸出。 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

