---
title: Lync Server 2013：編輯或設定簡單 URLs
description: Lync Server 2013：編輯或設定簡單 URLs。
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
ms.openlocfilehash: f9152a65083f71510f4cdb1189b3982afdd68b4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551629"
---
# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a>在 Lync Server 2013 中編輯或設定簡單 URLs

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-04_

此程序不需要本機系統管理員或已授權網域群組中的成員資格。您應該以標準使用者身分登入電腦。

Lync Server 2013 使用簡易 URLs，將內部和外部呼叫導向前端伺服器或 Director 上的服務（如果已部署）。 如需簡易 URLs 的詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的簡易 URLs](lync-server-2013-planning-for-simple-urls.md) 。 您可以從數個選項中選取簡單 URLs 的格式。 如需這些選項的詳細資訊，請參閱規劃檔中的 [簡易 URLs 在 Lync Server 2013 中的 DNS 需求](lync-server-2013-dns-requirements-for-simple-urls.md) 。

根據預設，會以 (形式設定簡單的 URLs 例如，撥入簡易 URL) ： https://dialin 。\<SIP Domain\>

<div>

## <a name="to-configure-simple-urls"></a>若要設定簡單 URL

1.  在 [拓撲產生器] 中，以滑鼠右鍵按一下 [ **Lync Server** ] 節點，然後按一下 [ **編輯屬性**]。

2.  在 [ **簡易 URLs** ] 窗格中，選取 [ **電話存取 URLs：** (撥入式) 或 **會議 URLs：** (符合) 進行編輯，然後按一下 [ **編輯 URL**]。

3.  將 URL 更新為想要的值，然後按一下 **[確定]** 儲存編輯的 URL。 這裡顯示的範例已修改的撥入 URL https://pool01.contoso.net/dialin 。

4.  必要時，使用相同步驟編輯 Meet URL。

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a>若要定義選用的 Admin 簡單 URL

1.  在 [拓撲產生器] 中，以滑鼠右鍵按一下 [ **Lync Server** ] 節點，然後按一下 [ **編輯屬性**]。

2.  在 [系統 **管理存取 url** ] 方塊中，輸入您要用於管理存取 Lync Server 2013 控制台的簡易 URL，然後按一下 **[確定]**。
    
    <div>
    

    > [!TIP]  
    > 建議您盡可能使用最簡單的 URL 作為 Admin URL。 最簡單的選項是<STRONG> https://admin 。</STRONG> &lt;網域 &gt; 。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您在初始部署之後變更簡單 URL，則必須留意有哪些變更會影響簡單 URL 的網域名稱系統 (DNS) 記錄和憑證。 如果此變更會影響簡單 URL 的基底，您也必須變更 DNS 記錄和憑證。 例如，從 lync.contoso.com 變更 https://lync.contoso.com/Meet 為 https://meet.contoso.com meet.contoso.com 時，您必須變更 DNS 記錄和憑證，以參照 meet.contoso.com。 如果您已將簡易 URL 變更 https://lync.contoso.com/Meet 為 https://lync.contoso.com/Meetings ，lync.contoso.com 的基底 url 會保持不變，因此不需要任何 DNS 或憑證變更。 不過，每當您變更簡易 URL 名稱時，您必須在每個 Director 和前端伺服器上執行 <STRONG>Enable-CsComputer</STRONG> Cmdlet，以登錄變更。

    
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

