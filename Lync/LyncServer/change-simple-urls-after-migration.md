---
title: 移轉後變更簡單 Url
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df0d6666f4ea824d59a97eb1f63b66016c75d547
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42003418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a>移轉後變更簡單 Url

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-22_

Lync Server 支援三個簡單 Url:

  - **符合**用於做為基底 URL 的網站或組織中的所有會議。 Meet 簡單 URL，來加入會議的連結有可更容易理解，且更容易溝通與分送。

  - **撥號對應表中**啟用 [存取電話撥入式會議設定網頁。 撥入簡單 URL 包含所有會議邀請中，讓要撥入會議的使用者可以存取的必要的電話號碼及 pin 碼資訊。

  - **系統管理員**可讓您快速存取 Lync Server Control Panel。 Admin 簡單 URL 是您組織內部。

移轉至 Lync Server 2013 之後，您必須知道如何變更會影響您的 DNS 記錄和憑證簡單 url。 如果舊版的 Lync Server 2010 Director 中保持使用中拓樸，不允許變更簡單 Url 所需。 如果從拓撲移除 Lync Server 2010 Director 移轉之後，必須更新簡單 URL 的 DNS 記錄，以指向下列其中一個 [Lync Server 2013 集區。 每當您變更了簡單 URL 名稱，但是，您必須執行 Enable-cscomputer 上每個 Director 與前端伺服器，以登錄變更。

<div>

## <a name="changing-simple-urls-after-migration"></a>移轉後變更簡單 Url

**更新 Meet 簡單 URL**

1.  在拓撲產生器，以滑鼠右鍵按一下頂端節點 [ **Lync Server**，，，然後按一下 [**編輯內容**。

2.  選取 [**簡單 Url**在左窗格中，然後下方**會議 Url:** 選取 Meet URL，然後按一下 [**編輯 URL**。

3.  將 URL 更新為想要的值，然後按一下 **[確定]** 儲存編輯的 URL。

**更新 Admin 簡單 URL**

1.  在拓撲產生器，以滑鼠右鍵按一下頂端節點 [ **Lync Server**，，，然後按一下 [**編輯內容**。

2.  在左窗格中，然後下方**系統管理存取 URL** ] 方塊中選取 [**簡單 Url** ，輸入您想要管理存取權，Lync Server 2013 控制台，簡單 URL，然後按一下 [**確定]**。
    
    <div>
    

    > [!TIP]  
    > 建議您盡可能使用最簡單的 URL 作為 Admin URL。 最簡單的選項是<STRONG>https://admin。</STRONG>&lt;網域&gt;。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[規劃 Lync Server 2013 中的簡單 Url](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

