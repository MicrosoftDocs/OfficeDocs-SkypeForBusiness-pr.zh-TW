---
title: Lync Server 2013：將 Cmdlet 用於反向網域準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b03ab3218a1568613731efe60eaa95b05a91ebc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a>將 Cmdlet 用於 Lync Server 2013 的反向網域準備

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

使用**Disable CsAdDomain** Cmdlet 來反轉網域準備步驟。

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a>使用 Cmdlet 來反向網域準備

1.  以網域系統管理員群組的成員身分登入網域中的任何伺服器。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  用盡
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    例如：
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    如果 Force 參數存在，即使已啟用網域中的一或多個前端伺服器或 A/V 會議伺服器，也會回滾網域準備。 如果 Force 參數不存在，則在啟用網域中的任何前端伺服器或 A/V 會議伺服器之後，就會終止網域準備復原。
    
    <div>
    

    > [!NOTE]  
    > [參數 GlobalSettingsDomainController] 可讓您指出儲存全域設定的位置。 如果您的設定是儲存在系統容器中（這通常是使用未將全域設定遷移至配置容器的升級部署），您可以在 Active Directory 目錄林的根目錄中定義網網域控制站。 如果全域設定位於 Configuration 容器中 (在全新部署或升級部署作業期間，當設定已經移轉至 Configuration 容器時的常見現象)，您可以在樹系中定義任何網域控制站。 如果您沒有指定此參數，Cmdlet 會假設設定會儲存在配置容器中，並參照 AD&nbsp;DS 中的任何網網域控制站。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[為 Lync Server 2013 執行網域準備](lync-server-2013-running-domain-preparation.md)  


[針對 Lync Server 2013 準備網域](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

