---
title: 在移轉後變更簡單 URL
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 029fe44d33d41b410d23068551203b1532893354
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499690"
---
# <a name="change-simple-urls-after-migration"></a>在移轉後變更簡單 URL

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-22_

Lync Server 支援三種簡單的 URLs：

  - 「**開會**」是網站或組織中所有會議的基礎 URL。 使用符合簡易 URL 時，加入會議的連結就很容易理解，而且易於進行通訊和發佈。

  - **撥入** 功能可讓您存取電話撥入式會議設定網頁。 撥入簡易 URL 會包含在所有會議邀請中，讓想要撥入會議的使用者可以存取必要的電話號碼和 PIN 碼資訊。

  - 系統**管理員**可讓您快速存取 Lync Server [控制台]。 系統管理員簡易 URL 是您組織內部。

在遷移至 Lync Server 2013 之後，您必須注意變更會如何影響您的 DNS 記錄和憑證，以進行簡單的 URLs。 如果舊版 Lync Server 2010 Director 仍在拓撲中使用，則不需要變更您的簡單 URLs。 若 Lync Server 2010 Director 在遷移之後從拓撲移除，則必須更新簡單 URL DNS 記錄，以指向其中一個 Lync Server 2013 集區。 不過，每當您變更簡易 URL 名稱時，您必須在每個 Director 和前端伺服器上執行 Enable-CsComputer，以註冊變更。

<div>

## <a name="changing-simple-urls-after-migration"></a>在遷移後變更簡單 URLs

**更新符合簡易 URL**

1.  在 [拓撲產生器] 中，以滑鼠右鍵按一下頂端節點 [ **Lync Server**]，然後按一下 [ **編輯屬性**]。

2.  在左窗格中選取 [ **簡單 URLs** ]，然後在 [ **會議 URLs：** 選取 [符合 url]，然後按一下 [ **編輯 URL**]。

3.  將 URL 更新為想要的值，然後按一下 **[確定]** 儲存編輯的 URL。

**更新系統管理員簡易 URL**

1.  在 [拓撲產生器] 中，以滑鼠右鍵按一下頂端節點 [ **Lync Server**]，然後按一下 [ **編輯屬性**]。

2.  在左窗格中選取 [ **簡單 URLs** ]，然後在 [ **管理存取 URL** ] 方塊中，輸入您要用來管理 Lync Server 2013 [控制台] 的簡易 URL，然後按一下 **[確定]**。
    
    <div>
    

    > [!TIP]  
    > 建議您盡可能使用最簡單的 URL 作為 Admin URL。 最簡單的選項是<STRONG> https://admin 。</STRONG> &lt;網域 &gt; 。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃簡易 URLs](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

