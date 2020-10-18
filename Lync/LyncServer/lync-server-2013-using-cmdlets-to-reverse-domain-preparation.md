---
title: Lync Server 2013：使用 Cmdlet 進行反向網域準備
description: Lync Server 2013：使用 Cmdlet 進行反向網域準備。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d26cc97ee934ee959838f38f4e2f52f9bf89566
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580409"
---
# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a>使用 Cmdlet 進行 Lync Server 2013 的反向網域準備

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

使用 **Disable-CsAdDomain** Cmdlet 來反轉網域準備步驟。

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a>若要使用 Cmdlet 來反轉網域準備

1.  以 Domain Admins 群組成員的身分登入網域中的任何伺服器。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  運行：
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    例如：
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    如果 Force 參數存在，即使已啟動網域中的一或多部前端伺服器或 A/V 會議伺服器，也會還原網域準備。 如果 Force 參數不存在，則會在啟用網域中的任何前端伺服器或 A/V 的會議服務器之後終止網域準備復原。
    
    <div>
    

    > [!NOTE]  
    > GlobalSettingsDomainController 參數可讓您指出通用設定的存放位置。 如果您的設定存放在 System 容器 (在升級部署作業期間，當通用設定尚未移轉到 Configuration 容器時的常見現象)，請將網域控制站定義到 Active Directory 樹系根目錄中。 如果全域設定位於 Configuration 容器中 (在全新部署或升級部署作業期間，當設定已經移轉至 Configuration 容器時的常見現象)，您可以在樹系中定義任何網域控制站。 如果您未指定此參數，則指令程式會假設設定會儲存在設定容器中，並參照 AD DS 中的任何網域控制站 &nbsp; 。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[對 Lync Server 2013 執行網域準備](lync-server-2013-running-domain-preparation.md)  


[準備 Lync Server 2013 的網域](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

