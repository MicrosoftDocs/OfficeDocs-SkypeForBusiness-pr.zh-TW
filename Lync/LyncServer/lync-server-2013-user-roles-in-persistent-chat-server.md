---
title: Persistent Chat Server 中的 Lync Server 2013： 使用者角色
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
ms.openlocfilehash: 34087f83a53fd1e52c3d67df4ef50411d6517160
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a>Persistent Chat Server in Lync Server 2013 中的使用者角色

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015年-03-19_

Persistent Chat Server 提供的概念適用於常設聊天室類別的允許/拒絕 」 成員和控制項可以存取特定類別中的聊天室。

<div>


> [!IMPORTANT]  
> 允許/拒絕 」 類別中的成員不是<STRONG>成員</STRONG>的角色，由它套用至常設聊天室會議室相同。<BR>搜尋會顯示「允許/拒絕」成員清單中使用者可以執行搜尋的所有開啟和關閉的聊天室。除非執行搜尋的使用者是祕密聊天室的成員，否則不會顯示祕密聊天室。使用者僅能搜尋本身所屬的聊天室，或是他們可以申請成員資格的聊天室。



</div>

「允許/拒絕」成員的概念存在的主要理由就是為了道德管束。舉例來說，道德界線在銀行與金融機構中十分常見，目的在於防範交易者與分析師在執行各項原則與慣例時與他人進行通訊。為了符合這項規定，系統管理員可以建立各種類別，使得某個類別允許交易者建立及使用聊天室，而另一個類別則允許分析師建立及使用不同的聊天室。如果父類別不允許的話，這項限制就是針對系統禁止新增使用者作為聊天室成員而設計的。

以下是四種使用者角色 Persistent Chat Server:

  - **Creator:** 若要建立聊天室的使用權限的使用者。 這些使用者列在某些類別的「建立者」清單中：他們可以在該類別中建立聊天室，也可以根據該類別來指派成員及管理員來管理該聊天室。 此建立聊天室的使用者會自動新增為該聊天室的管理員。
    
    <div>
    

    > [!NOTE]  
    > 擔任建立者純粹提供建立聊天室的權限。同時還會自動晉升為管理員，以便建立者能夠進一步在建立的交談服務上微調成員資格、管理員等等。

    
    </div>
    
    這個角色存在的目的在於提供您控制由誰在組織中建立聊天室的選擇，尤其是，如果您希望集中建立聊天室以執行各項原則與慣例，接著並把聊天室管理工作委派給組織中的其他使用者時。

  - **Manager:** 管理的聊天室內容的使用者。 聊天室管理員可以修改成員清單 (新增及移除成員)，以及修改聊天室管理員清單 (新增及移除管理員)。 聊天室管理員可以將本身新增至成員或簡報者 (適用於視聽聊天室) 清單，以便參與該聊天室活動。 聊天室管理員也可以停用聊天室 (系統管理員可以查詢停用的聊天室以及永久刪除聊天室)。 管理員可以變更聊天室的所有屬性，聊天室類別除外。 常設聊天室管理員可以變更的類別，建立聊天室之後。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果管理員同時擔任其他類別的建立者，則管理員只能變更他們獲得授權所建立之聊天室的類別。

    
    </div>

  - **成員：** 身為成員的聊天室的使用者。 這些使用者可以看到該目錄中的聊天室 （即使聊天室是秘密），以及訂閱聊天室時亦可 （包括中繼資料的選項，例如未閱讀的郵件、 ego 篩選和關鍵字篩選器），並參與聊天室 (可以張貼，除非會議室是其中只有簡報者可以張貼、 取得內容，以及搜尋視聽中心聊天室）。 不聊天室的成員的使用者可以搜尋聊天室，如果它們的類別中，[允許成員] 清單中，但必須要求加入這些聊天室，以存取內容的存取權。 （沒有要求存取或系統內建的核准，這些即可外部電子郵件、 電話或其他形式的連絡人）。

  - **簡報者：** 可以在視聽中心聊天室張貼的使用者。

<div>


> [!NOTE]  
> Persistent Chat Server 可讓使用者建立及管理特定網站的聊天室。 使用者無法，不過，建立或管理在相同拓撲內其他網站上的聊天室。 請務必指定聊天室建立者及管理員在組織中的所有網站。



</div>

下列角色是 for Persistent Chat Server 的系統管理員角色：

  - **常設聊天室系統管理員 (CsPersistentChatAdministrator):** 這是新的角色型存取控制 (RBAC) 角色來管理與管理 Persistent Chat Server。 使用者或安全性群組指定為 CsPersistentChatAdministrator 都能藉由使用遠端 Windows PowerShell cmdlet 來管理 Persistent Chat Server (亦即從 Persistent Chat Server 以外的電腦)。 Persistent Chat Server 檢查 Persistent Chat Administrator Persistent Chat Server 前端伺服器上的 RTC Local 系統管理員本機群組的成員。
    
    CsPersistentChatAdministrator 管理員可以管理聊天室 (修改包括成員資格、管理員、類別在內的所有屬性，以及將聊天室標示為停用)，和建立及管理定義聊天室的建立者與存取者之聊天室類別。 系統管理員也可以將聊天室標記為停用以及清理不再使用的聊天室。 系統管理員不受「建立者」或「允許的成員」之限制。 系統管理員可以建立任何類型的聊天室，以及將本身新增為任何聊天室的成員。 系統管理員可以也修改和管理常設聊天室組態 （集區內容、 全域設定，以及相符性組態），並可以也規劃及實作從舊的 Group Chat 伺服器部署移轉至 Lync Server 2013 常設聊天室伺服器。

  - **Lync 系統管理員：** 負責部署的 Lync Server 2013 的整體企業系統管理員。

  - **Operations Manager:** 負責管理日常營運作業的使用者。

  - **協力廠商開發人員與合作夥伴：** 協力廠商開發人員可擴充系統，特別是針對群組對話、 規範支援和工具、 網路/行動用戶端和 Bot 開發的架構提供道德管束解決方案。

</div>

<span> </span>

</div>

</div>

</div>

