---
title: 商務用 Skype Server 2015 中的持續性聊天類別、聊天室和使用者角色
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 摘要：閱讀此主題以瞭解商務用 Skype Server 2015 中的 Persistent chat Server 的類別、聊天室和使用者和系統管理員角色。
ms.openlocfilehash: 212e731da29bc327487e0e6512db413546d20670
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857250"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的持續性聊天類別、聊天室和使用者角色
 
**摘要：** 閱讀此主題以瞭解商務用 Skype Server 2015 中的 Persistent chat Server 的類別、聊天室和使用者與系統管理員角色。
  
您可以建立聊天室類別，然後指定類別中的類別和聊天室的存取權，以控制對聊天室的存取。 您也可以指定各種系統管理員角色。 本主題說明下列事項： 
  
- 用於組織聊天室的類別
    
- 聊天室和使用者角色
    
- 系統管理員角色

> [!NOTE] 
> 持續聊天可在商務用 Skype Server 2015 中取得，但在商務用 Skype Server 2019 中已不再支援。 Teams 中提供相同的功能。 如需詳細資訊，請參閱[Microsoft Teams 升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續性聊天，您可以選擇將需要這項功能的使用者遷移至 Teams，或是繼續使用商務用 Skype Server 2015。 
    
## <a name="categories-for-organizing-chat-rooms"></a>用於組織聊天室的類別

類別可讓您組織聊天室，並控制允許哪些使用者和群組建立或加入這些類別中的聊天室。 每個類別都有相關聯的屬性，可決定類別中聊天室的可用選項。 您可以指定使用者是否允許或拒絕存取權，以控制特定類別的存取權。
  
允許和拒絕成員概念的主要原因是道德的背景。 舉例來說，道德界線在銀行與金融機構中十分常見，目的在於防範交易者與分析師在執行各項原則與慣例時與他人進行通訊。 為了符合這項規定，系統管理員可以建立各種類別，使得某個類別允許交易者建立及使用聊天室，而另一個類別則允許分析師建立及使用不同的聊天室。 如果父類別禁止使用者將使用者新增為聊天室的成員。
  
> [!IMPORTANT]
> 類別中的允許和拒絕的成員不是套用至 Persistent 聊天室的 **成員** 角色。 > 搜尋會顯示所有開啟及關閉的聊天室，使用者執行搜尋的使用者就會顯示在 [允許和拒絕的成員] 清單中。 除非執行搜尋的使用者是祕密聊天室的成員，否則不會顯示祕密聊天室。 使用者僅能搜尋本身所屬的聊天室，或是他們可以申請成員資格的聊天室。 
  
## <a name="chat-rooms-and-user-roles"></a>聊天室和使用者角色

除了類別的允許和拒絕成員之外，您也可以指定下列使用者角色，以控制對聊天室的存取：建立者、管理員、成員及簡報者。
  
- 建立 **者**：具有建立聊天室之許可權的使用者。 這些使用者列在某些類別的「建立者」清單中：他們可以在該類別中建立聊天室，也可以根據該類別來指派成員及管理員來管理該聊天室。 此建立聊天室的使用者會自動新增為該聊天室的管理員。
    
    > [!NOTE]
    > 擔任建立者純粹提供建立聊天室的權限。同時還會自動晉升為管理員，以便建立者能夠進一步在建立的交談服務上微調成員資格、管理員等等。 
  
    這個角色存在的目的在於提供您控制由誰在組織中建立聊天室的選擇，尤其是，如果您希望集中建立聊天室以執行各項原則與慣例，接著並把聊天室管理工作委派給組織中的其他使用者時。
    
- **管理員**：是指管理聊天室屬性的使用者。 聊天室管理員可以修改成員清單 (新增及移除成員)，以及修改聊天室管理員清單 (新增及移除管理員)。 聊天室管理員可以將本身新增至成員或簡報者 (適用於視聽聊天室) 清單，以便參與該聊天室活動。 聊天室管理員也可以停用聊天室 (系統管理員可以查詢停用的聊天室以及永久刪除聊天室)。 管理員可以變更聊天室的所有屬性，聊天室類別除外。 只有持續性聊天系統管理員可以在建立聊天室之後變更類別。
    
    > [!IMPORTANT]
    > 如果管理員同時擔任其他類別的建立者，則管理員只能變更他們獲得授權所建立之聊天室的類別。 
  
- **Member**：屬於聊天室成員的使用者。 這些使用者可以在目錄 (中看到聊天室，即使聊天室是機密) ，也可以訂閱聊天室 (（包括中繼資料選項（如未讀郵件、xbox 篩選器和關鍵字篩選器) ），以及參與聊天室 (可以張貼，除非會議室是只有簡報者可以張貼的視聽中心聊天室，否則請 取得內容及搜尋) 。 不是聊天室成員的使用者可以在該類別的 [允許的成員清單] 清單中搜尋聊天室，但需要要求存取權加入這些聊天室才能存取內容。  (系統內沒有內建的要求存取權或核准;這些是透過電子郵件、電話或其他形式的連絡人進行外部完成。 ) 
    
- **簡報者** 可以在視聽聊天室進行張貼的使用者。
    
## <a name="administrator-roles"></a>系統管理員角色

以下是 Persistent Chat Server 的系統管理員角色：
  
- **Persistent Chat administrator**： Persistent chat administrator role 可管理聊天室 (修改所有內容，包括成員資格、經理、類別、以停用的會議室做為停用) ，以及建立及管理聊天室類別，以定義誰可以建立和存取聊天室。 系統管理員也可以將聊天室標記為停用以及清理不再使用的聊天室。 系統管理員不受「建立者」或「允許的成員」之限制。 系統管理員可以建立任何類型的聊天室，以及將本身新增為任何聊天室的成員。 系統管理員也可以修改和管理持續聊天設定 (集區屬性、全域設定及規範設定) ，也可以從較舊的群組聊天伺服器部署規劃及執行遷移，以商務用 Skype Server 2015 Persistent chat server。
    
    persistent chat 管理員可以從遠端 Windows PowerShell Cmdlet (（從 Persistent chat server) 以外的電腦）管理 persistent chat Server。 Persistent Chat Server 會檢查 Persistent chat Administrator 是否為 Persistent Chat Server 前端伺服器上 RTC 本機系統管理員本機群組的成員。
    
- **商務用 Skype Server 2015 系統管理員**：商務用 Skype Server 2015 的整體企業系統管理員負責部署。
    
- **營運管理員**：負責管理日常營運作業的使用者。
    
- **協力廠商開發人員與合作夥伴**：協力廠商開發人員可擴充系統，特別是針對群組對話、規範支援與各項工具、網路/行動用戶端和 Bot 開發的架構，提供道德管束解決方案。
    
## <a name="for-more-information"></a>相關資訊

如需設定和管理聊天室和使用者角色的詳細資訊，請參閱下列主題：
  
- [在商務用 Skype Server 2015 中建立持續性聊天系統管理員](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [在商務用 Skype Server 2015 中管理 Persistent Chat Server 中的類別](../../manage/persistent-chat/categories.md)
    
- [在商務用 Skype Server 2015 中管理 Persistent chat Server 中的聊天室](../../manage/persistent-chat/chat-rooms.md)
    

