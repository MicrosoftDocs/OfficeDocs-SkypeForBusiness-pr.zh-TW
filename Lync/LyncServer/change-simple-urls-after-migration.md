---
title: 在移轉後變更簡單 URL
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
ms.openlocfilehash: a24eda274734e0c5a27fab30640a363de6653514
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a>在移轉後變更簡單 URL

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-22_

Lync Server 支援三個簡單的 Url：

  - [**開會**] 是用來做為網站或組織中所有會議的基底 URL。 使用 [符合簡單的 URL]，加入會議的連結就很容易理解，且易於溝通及發佈。

  - [**撥**入] 可讓您存取 [電話撥入式會議] 設定網頁。 [撥入] 簡單 URL 包含在所有會議邀請中，讓想要撥入會議的使用者可以存取必要的電話號碼和 PIN 資訊。

  - [系統**管理**] 可讓您快速存取 Lync Server [控制台]。 系統管理員簡易 URL 是貴組織的內部。

遷移至 Lync Server 2013 之後，您必須知道變更對您的 DNS 記錄及證書有何影響，以取得簡單的 Url。 如果舊版 Lync Server 2010 控制器在拓撲中保持使用，則不需要變更您的簡單 Url。 如果 Lync Server 2010 控制器是在遷移之後從拓撲中移除，則必須更新簡單的 URL DNS 記錄，以指向其中一個 Lync Server 2013 池。 不過，每當您變更簡單的 URL 名稱時，您必須在每個控制器和前端伺服器上執行 Enable-CsComputer，以登錄變更。

<div>

## <a name="changing-simple-urls-after-migration"></a>遷移後變更簡單的 Url

**若要更新 [符合簡單 URL]**

1.  在拓撲建立器中，以滑鼠右鍵按一下頂層節點**Lync Server**，然後按一下 [**編輯屬性**]。

2.  選取左窗格中的 [**簡單 url** ]，然後選取 [**會議 url]：** 選取 [認識 url]，然後按一下 [**編輯 URL**]。

3.  更新 URL 至您想要的值，然後按一下 **[確定]** 以儲存編輯的 URL。

**更新管理員簡易 URL**

1.  在拓撲建立器中，以滑鼠右鍵按一下頂層節點**Lync Server**，然後按一下 [**編輯屬性**]。

2.  選取左窗格中的 [**簡單 url** ]，然後在 [**管理存取 URL** ] 方塊中，輸入您要用來管理 Lync Server 2013 [控制台] 的簡單 URL，然後按一下 **[確定]**。
    
    <div>
    

    > [!TIP]  
    > 我們建議您使用最簡單的管理 URL URL。 最簡單的選項就是<STRONG> https://admin。</STRONG>&lt;網域&gt;。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中規劃簡單 URL](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

