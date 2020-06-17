---
title: 移動剩餘的使用者
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
description: 您可以使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面，將使用者移至新的商務用 Skype Server 2019 部署。 您必須符合某些需求，以確保順利轉換為商務用 Skype Server 2019。 如需完成本主題中程式之必要條件的詳細資訊，請參閱設定用戶端進行遷移。 如需移動使用者的詳細步驟，請參閱第4階段：將測試使用者移至試驗集區。
ms.openlocfilehash: 0c4135ed8c3eaae25e57e6af1c67a18eb933b190
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753711"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>將剩餘的使用者移至商務用 Skype Server 2019

您可以使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面，將使用者移至新的商務用 Skype Server 2019 部署。 您必須符合某些需求，以確保順利轉換為商務用 Skype Server 2019。 如需完成本主題中程式之必要條件的詳細資訊，請參閱[設定用戶端進行遷移](configure-clients-for-migration.md)。 如需移動使用者的詳細步驟，請參閱[第4階段：將測試使用者移至試驗集](phase-4-move-test-users-to-the-pilot-pool.md)區。
  
> [!IMPORTANT]
> 您無法使用 Active Directory 使用者及電腦嵌入式管理單元或舊版系統管理工具，將使用者從舊版環境移至商務用 Skype Server 2019。 
  
當您將使用者移至商務用 Skype Server 2019 集區時，使用者的資料會移至與新集區相關聯的後端資料庫。 
  
> [!IMPORTANT]
> 這包括由舊使用者所建立之作用中的會議。 例如，如果舊版使用者已設定「我的**會議**會議」，該會議在使用者移動之後仍會在新的商務用 Skype Server 2019 集區中提供。 存取該會議的詳細資料仍為相同的 **[會議 URL 及會議 ID]**。 唯一不同之處在于，會議現在是在商務用 Skype Server 2019 集區，而不是在舊版集區中主控。 
  
> [!NOTE]
> 在商務用 Skype Server 2019 上的使用者，不需要同時部署已升級的用戶端。 只有當使用者已升級為新的用戶端軟體時，才可使用新功能。 
  
### <a name="post-migration-task"></a>遷移後工作

1. 一旦移除使用者之後，請驗證指派給他們的會議原則。 
    
2. 為了確保由位於商務用 Skype Server 2019 的使用者所組織的會議可與以舊版安裝的同盟使用者順利運作，指派給已遷移使用者的會議原則應該允許匿名參與者。
    
3. 允許匿名參與者的會議原則**可讓參與者邀請**商務用 skype Server 2019 控制台中所選取的匿名使用者，而且**AllowAnonymousParticipantsInMeetings**在商務用 skype server 管理命令介面中從**Get-CsConferencingPolicy**指令程式的輸出中，設定為**True** 。 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

