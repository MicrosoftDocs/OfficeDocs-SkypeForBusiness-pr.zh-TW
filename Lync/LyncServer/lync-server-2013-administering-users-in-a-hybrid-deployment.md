---
title: Lync Server 2013：在混合式部署中管理使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b09ca3c5a80215c0a2d63a018150361671df6859
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a>在混合 Lync Server 2013 部署中管理使用者

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-29_

您可以使用 Microsoft Office 365 Online 入口網站中提供的使用者管理功能，管理遷移至 Lync Online 之使用者的使用者設定和原則。 您必須使用租使用者系統管理員帳戶登入，以執行管理工作。

<div>

## <a name="moving-users-back-to-on-premises"></a>將使用者移回內部部署

<div class="">


> [!IMPORTANT]  
> 本節僅適用于已針對 Lync 內部部署建立並啟用的使用者，然後從內部部署部署移至 Lync Online。 如果您想要移動在 Lync Online 中建立的使用者（而且不會在內部部署中啟用 Lync），請參閱，將<A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">使用者從 Lync Online 移至 Lync Server 2013 中的 lync 內部部署</A>。



</div>

  - 執行下列 Cmdlet，將使用者從 Lync Online 移回到 Lync 內部部署：
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

針對**HostedMigrationOverrideUrl**參數所指定的 url 格式，必須是正在執行裝載遷移服務之集區的 url，格式如下：

Https://\<集區\>FQDN/HostedMigration/hostedmigrationService.svc。 您可以透過查看 Office 365 組織帳戶的 Lync Online 控制台 URL，判斷主控遷移服務的 URL。

**決定 Office 365 組織的主控遷移服務 URL**

1.  以系統管理員身分登入您的 Office 365 組織。

2.  開啟**Lync 系統管理中心**。

3.  在 [ **Lync 系統管理中心**] 顯示時，選取 [位址] 列中的 URL，並將其複製到**lync.com**。 URL 的範例類似下列所示：
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  使用系統**管理員**取代 URL 中的**webdir** ，產生下列結果：
    
    `https://admin0a.online.lync.com`

5.  在 URL: **/HostedMigration/hostedmigrationservice.svc**中附加下列字串。
    
    產生的 URL （ **HostedMigrationOverrideUrl**的值）應如下所示：
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

