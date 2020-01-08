---
title: Lync Server 2013：編輯或設定簡單 URL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b1439ddb0dafc63b0e70439ee5231477fdbb6be
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a>在 Lync Server 2013 中編輯或設定簡單 URL

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-04_

此程式不需要本機系統管理員或許可權網域群組的成員資格。 您應該以標準使用者的身分登入電腦。

Lync Server 2013 使用簡單的 Url，將內部和外部呼叫直接提供給前端伺服器或主管上的服務（如果已部署）。 如需簡單 Url 的詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的簡單 Url 規劃](lync-server-2013-planning-for-simple-urls.md)。 您可以從數個選項中選取簡單 Url 的格式。 如需這些選項的詳細資訊，請參閱規劃檔中的[Lync Server 2013 簡單 url 的 DNS 需求](lync-server-2013-dns-requirements-for-simple-urls.md)。

根據預設，簡單的 Url 會以下列形式（例如，撥入式簡單 URL）來設定： https://dialin.\<SIP網域\>

<div>

## <a name="to-configure-simple-urls"></a>若要設定簡單的 Url

1.  在拓撲建立器中，以滑鼠右鍵按一下**Lync Server**節點，然後按一下 [**編輯屬性**]。

2.  在 [**簡易 url** ] 窗格中，選取 [**電話存取 url：** （撥入）] 或 [**會議 url：** （見面）] 進行編輯，然後按一下 [**編輯 URL**]。

3.  更新 URL 至您想要的值，然後按一下 **[確定]** 以儲存編輯的 URL。 這裡顯示的範例已修改回撥入式 URL https://pool01.contoso.net/dialin。

4.  如有需要，請使用相同的步驟編輯 [認識 URL]。

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a>定義選用的系統管理員簡易 URL

1.  在拓撲建立器中，以滑鼠右鍵按一下**Lync Server**節點，然後按一下 [**編輯屬性**]。

2.  在 [**管理存取 URL** ] 方塊中，輸入您想要用來管理 Lync Server 2013 [控制台] 的簡單 URL，然後按一下 **[確定]**。
    
    <div>
    

    > [!TIP]  
    > 我們建議您使用最簡單的管理 URL URL。 最簡單的選項就是<STRONG> https://admin。</STRONG>&lt;網域&gt;。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您在初始部署之後變更簡單的 URL，您必須知道哪些變更會影響您的網域名稱系統（DNS）記錄及簡單 Url 的憑證。 如果變更會影響簡單 URL 的基底，則您也必須變更 DNS 記錄和憑證。 例如，從https://lync.contoso.com/Meet lync.contoso.com https://meet.contoso.com變更為 MEET.CONTOSO.COM 的基底 URL，因此您必須將 DNS 記錄和憑證變更為參照 meet.contoso.com。 如果您將簡單的 URL 改https://lync.contoso.com/Meet為https://lync.contoso.com/Meetings[寄件者]，則 LYNC.CONTOSO.COM 的基底 url 會保持不變，因此不需要變更 DNS 或憑證。 不過，每當您變更簡單的 URL 名稱時，您必須在每個主管和前端伺服器上執行<STRONG>Enable-CsComputer</STRONG> Cmdlet，才能註冊變更。

    
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

