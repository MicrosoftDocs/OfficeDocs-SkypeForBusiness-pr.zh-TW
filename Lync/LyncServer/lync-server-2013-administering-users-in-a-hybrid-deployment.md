---
title: Lync Server 2013：管理混合式部署中的使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7804aacb226d06fbf239939658b6592d438a84f9
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40974377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a>在混合式 Lync Server 2013 部署中管理使用者

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-29_

您可以使用 Microsoft Office 365 Online 入口網站中提供的使用者管理功能，來管理遷移至 Lync Online 之使用者的使用者設定和原則。 您必須使用您的租使用者系統管理員帳戶登入，才能執行系統管理工作。

<div>

## <a name="moving-users-back-to-on-premises"></a>將使用者移回內部部署

<div class="">


> [!IMPORTANT]  
> 本節僅適用于為 Lync 內部部署所建立和啟用的使用者，然後從內部部署部署移至 Lync Online。 如果您想要移動在 Lync Online 中建立的使用者（在內部部署部署中不會啟用 Lync），請參閱在<A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Lync Server 2013 中將使用者從 Lync Online 移至 lync 內部部署</A>。



</div>

  - 執行下列 Cmdlet，將使用者從 Lync Online 移回 Lync 內部部署：
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

針對**HostedMigrationOverrideUrl**參數指定的 url 格式，必須是正在執行託管遷移服務之池的 url，格式如下：

Https://\<池 FQDN\>/HostedMigration/hostedmigrationService.svc。 您可以透過查看 Office 365 租使用者帳戶的 Lync Online 控制台 URL 來判斷託管遷移服務的 URL。

**若要為您的 Office 365 租使用者判斷託管的遷移服務 URL**

1.  以系統管理員身分登入您的 Office 365 租使用者。

2.  開啟**Lync 系統管理中心**。

3.  在**Lync 系統管理中心**顯示的狀態下，選取並將網址列中的 URL 複製到**lync.com**。 範例 URL 看起來類似以下所示：
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  將 URL 中的**webdir 為 admin**取代為系統**管理員**，並產生下列結果：
    
    `https://admin0a.online.lync.com`

5.  將下列字串附加到 URL： **/HostedMigration/hostedmigrationservice.svc**。
    
    產生的 URL （即**HostedMigrationOverrideUrl**的值）應如下所示：
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

