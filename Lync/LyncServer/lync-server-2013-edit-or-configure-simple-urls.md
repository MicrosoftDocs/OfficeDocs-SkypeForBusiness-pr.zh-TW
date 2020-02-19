---
title: Lync Server 2013： 編輯或設定簡單 Url
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1618ca331b66612051b2a824aa5ebd2adfac043a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a>編輯或 Lync Server 2013 中設定簡單 Url

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-02-04_

此程序不需要本機系統管理員或已授權網域群組中的成員資格。您應該以標準使用者身分登入電腦。

Lync Server 2013 使用服務的直接內部和外部來電的簡單 Url Director 或前端伺服器上如果其中一個已部署。 如需簡單 Url 的詳細資訊，請參閱規劃文件中的[Planning for Lync Server 2013 中的簡單 Url](lync-server-2013-planning-for-simple-urls.md) 。 您可以從數個選項您簡單 url 選取的格式。 如需這些選項的詳細資訊，請參閱規劃文件中的[Lync Server 2013 中的簡單 Url 的 DNS 需求](lync-server-2013-dns-requirements-for-simple-urls.md)。

根據預設，會設定簡單 Url (例如，撥入簡單 URL) 的形式：https://dialin.\<SIP網域\>

<div>

## <a name="to-configure-simple-urls"></a>若要設定簡單 URL

1.  在拓撲產生器，以滑鼠右鍵按一下 [ **Lync Server** ] 節點中，，，然後按一下 [**編輯內容]**。

2.  在 [**簡單 Url** ] 窗格中，選取 [**電話存取 Url:** （撥入） 或**會議 Url:** （符合），以編輯，然後按一下 [**編輯 URL**。

3.  將 URL 更新為想要的值，然後按一下 **[確定]** 儲存編輯的 URL。 範例如下所示已修改的撥號對應表中 URL https://pool01.contoso.net/dialin。

4.  必要時，使用相同步驟編輯 Meet URL。

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a>若要定義選用的 Admin 簡單 URL

1.  在拓撲產生器，以滑鼠右鍵按一下 [ **Lync Server** ] 節點中，，，然後按一下 [**編輯內容]**。

2.  在 [**系統管理存取 URL** ] 方塊中，輸入您想要管理存取權，Lync Server 2013 控制台，簡單 URL，然後按一下 [**確定]**。
    
    <div>
    

    > [!TIP]  
    > 建議您盡可能使用最簡單的 URL 作為 Admin URL。 最簡單的選項是<STRONG>https://admin。</STRONG>&lt;網域&gt;。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您在初始部署之後變更簡單 URL，則必須留意有哪些變更會影響簡單 URL 的網域名稱系統 (DNS) 記錄和憑證。 如果此變更會影響簡單 URL 的基底，您也必須變更 DNS 記錄和憑證。 例如，從變更https://lync.contoso.com/Meet以https://meet.contoso.com基底 URL 從變成 lync.contoso.com meet.contoso.com，所以您需要變更 DNS 記錄和憑證，以參照 meet.contoso.com。 如果您變更從簡單 URLhttps://lync.contoso.com/Meet以https://lync.contoso.com/Meetings、 lync.contoso.com 的基底 URL 保持不變，因此沒有 DNS 或需要憑證的變更。 每當您變更了簡單 URL 名稱，但是，您必須執行<STRONG>Enable-cscomputer</STRONG>指令程式上每個 Director 與前端伺服器，以登錄變更。

    
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

