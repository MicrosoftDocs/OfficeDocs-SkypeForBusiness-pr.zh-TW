---
title: Lync Server 2013： Persistent Chat Server 中的使用者角色
description: Lync Server 2013： Persistent Chat Server 中的使用者角色。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User roles in Persistent Chat Server
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49361095
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aed64aaa9129e6667cd138bc4365acfb2a64d52c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550849"
---
# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 中 Persistent Chat Server 的使用者角色

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-03-19_

Persistent Chat Server 提供「允許/拒絕」成員的概念，其適用于持續聊天類別及可存取特定類別之聊天室的控制項。

<div>


> [!IMPORTANT]  
> 類別中允許/拒絕的成員與 <STRONG>成員</STRONG> 角色不同，其適用于 Persistent 聊天室。<BR>搜尋會顯示「允許/拒絕」成員清單中使用者可以執行搜尋的所有開啟和關閉的聊天室。除非執行搜尋的使用者是祕密聊天室的成員，否則不會顯示祕密聊天室。使用者僅能搜尋本身所屬的聊天室，或是他們可以申請成員資格的聊天室。



</div>

「允許/拒絕」成員的概念存在的主要理由就是為了道德管束。舉例來說，道德界線在銀行與金融機構中十分常見，目的在於防範交易者與分析師在執行各項原則與慣例時與他人進行通訊。為了符合這項規定，系統管理員可以建立各種類別，使得某個類別允許交易者建立及使用聊天室，而另一個類別則允許分析師建立及使用不同的聊天室。如果父類別不允許的話，這項限制就是針對系統禁止新增使用者作為聊天室成員而設計的。

以下是四個使用者角色 Persistent Chat Server：

  - 建立**者：** 具有建立聊天室之許可權的使用者。 這些使用者列在某些類別的「建立者」清單中：他們可以在該類別中建立聊天室，也可以根據該類別來指派成員及管理員來管理該聊天室。 此建立聊天室的使用者會自動新增為該聊天室的管理員。
    
    <div>
    

    > [!NOTE]  
    > 擔任建立者純粹提供建立聊天室的權限。同時還會自動晉升為管理員，以便建立者能夠進一步在建立的交談服務上微調成員資格、管理員等等。

    
    </div>
    
    這個角色存在的目的在於提供您控制由誰在組織中建立聊天室的選擇，尤其是，如果您希望集中建立聊天室以執行各項原則與慣例，接著並把聊天室管理工作委派給組織中的其他使用者時。

  - **管理員：** 管理聊天室屬性的使用者。 聊天室管理員可以修改成員清單 (新增及移除成員)，以及修改聊天室管理員清單 (新增及移除管理員)。 聊天室管理員可以將本身新增至成員或簡報者 (適用於視聽聊天室) 清單，以便參與該聊天室活動。 聊天室管理員也可以停用聊天室 (系統管理員可以查詢停用的聊天室以及永久刪除聊天室)。 管理員可以變更聊天室的所有屬性，聊天室類別除外。 只有持續性聊天系統管理員可以在建立聊天室之後變更類別。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果管理員同時擔任其他類別的建立者，則管理員只能變更他們獲得授權所建立之聊天室的類別。

    
    </div>

  - **Member：** 屬於聊天室成員的使用者。 這些使用者可以在目錄 (中看到聊天室，即使聊天室是機密) ，也可以訂閱聊天室 (（包括中繼資料選項（如未讀郵件、xbox 篩選器和關鍵字篩選器) ），以及參與聊天室 (可以張貼，除非會議室是只有簡報者張貼、取得內容及搜尋) 的視聽中心聊天室。 不是聊天室成員的使用者可以在該類別的 [允許的成員清單] 清單中搜尋聊天室，但需要要求存取權加入這些聊天室才能存取內容。  (系統內沒有內建的要求存取權或核准;這些是透過電子郵件、電話或其他形式的連絡人進行外部完成。 ) 

  - **簡報者：** 可以張貼至視聽中心聊天室的使用者。

<div>


> [!NOTE]  
> Persistent Chat Server 可讓使用者為特定網站建立及管理聊天室。 不過，使用者無法在相同的拓撲中建立或管理其他網站上的聊天室。 請務必為您組織中的所有網站指定聊天室建立者和主管。



</div>

下列角色是 Persistent Chat Server 的系統管理員角色：

  - **Persistent Chat Administrator (CsPersistentChatAdministrator) ：** 這是新的 Role-Based 存取控制 (RBAC) role，用以管理及管理 Persistent Chat Server。 指定為 CsPersistentChatAdministrator 的使用者或安全性群組，可使用 Windows PowerShell Cmdlet 遠端系統管理 Persistent Chat Server， (也就是從 Persistent Chat Server) 以外的電腦。 Persistent Chat Server 會檢查 Persistent 聊天室系統管理員是否為 Persistent Chat Server 前端伺服器上 RTC 本機系統管理員本機群組的成員。
    
    CsPersistentChatAdministrator 管理員可以管理聊天室 (修改包括成員資格、管理員、類別在內的所有屬性，以及將聊天室標示為停用)，和建立及管理定義聊天室的建立者與存取者之聊天室類別。 系統管理員也可以將聊天室標記為停用以及清理不再使用的聊天室。 系統管理員不受「建立者」或「允許的成員」之限制。 系統管理員可以建立任何類型的聊天室，以及將本身新增為任何聊天室的成員。 系統管理員也可以修改和管理持續聊天設定 (集區屬性、全域設定，以及符合性設定) ，也可以從舊版的群組聊天伺服器部署中規劃及執行遷移至 Lync Server 2013 Persistent Chat Server。

  - **Lync 管理員：** Lync Server 2013 的整體企業系統管理員負責部署。

  - **Operations Manager：** 負責管理日常作業的使用者。

  - **協力廠商開發人員和合作夥伴：** 協力廠商開發人員擴充系統，特別為群組交談、規範支援和工具、web/行動用戶端，以及 Bot 開發的架構提供合乎道德的留言板方案。

</div>

<span> </span>

</div>

</div>

</div>

