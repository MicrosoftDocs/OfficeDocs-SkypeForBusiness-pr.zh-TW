---
title: Lync Server 2013： 管理混合部署中的使用者
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
ms.openlocfilehash: 0c6cfa255eddc998047f5b404d59b7e6622fbaae
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a>管理混合 Lync Server 2013 部署中的使用者

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-05-29_

您可以管理使用者設定和原則的使用者移轉至 Lync Online 使用 Microsoft Office 365 線上入口網站中可用的使用者管理功能。 使用您的租用戶系統管理員帳戶來執行管理工作，您必須登入。

<div>

## <a name="moving-users-back-to-on-premises"></a>將使用者移回內部部署

<div class="">


> [!IMPORTANT]  
> 本節僅適用於已建立並啟用 Lync 內部部署，然後移至 Lync Online 的 [從內部部署的使用者。 如果您想要移動的使用者，已建立在 Lync Online （並不屬於啟用 lync 內部部署中），請參閱<A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">移動使用者從 Lync Online lync 內部部署 Lync Server 2013 中</A>。



</div>

  - 執行下列 cmdlet，將使用者移從 Lync Online 回至 Lync 內部部署：
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

**HostedMigrationOverrideUrl**參數所指定的 URL 的格式必須是主控遷移服務執行，以下列格式的集區的 URL:

Https://\<集區 FQDN\>/HostedMigration/hostedmigrationService.svc。 您可以透過檢視 URL 的 Office 365 租用戶帳戶的 Lync Online 控制台判斷主控移轉服務的 URL。

**若要判斷您 Office 365 租用戶主控移轉服務 URL**

1.  Office 365 租用戶系統管理員身分登入。

2.  開啟**Lync 系統管理中心**]。

3.  顯示在**Lync 系統管理中心**，選取與複製最**lync.com**[網址] 列中的 URL。 範例 URL 看起來如下：
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  **Webdir** URL 中取代為**系統管理員**，結果如下：
    
    `https://admin0a.online.lync.com`

5.  將下列字串附加至的 URL: **/HostedMigration/hostedmigrationservice.svc**。
    
    產生的 URL，也就是**HostedMigrationOverrideUrl**的值，應該如下所示：
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

