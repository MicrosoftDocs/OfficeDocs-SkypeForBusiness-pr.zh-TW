---
title: Lync Server 2013： 將使用者移至 Lync Online
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f490a50ade6c10d37a478729c46a5545970afb1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a>將使用者移至 Lync Online 在 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-05-29_

在開始移轉至 Lync Online 使用者之前，您應該備份要移動的帳戶相關聯的使用者資料。 並非所有使用者資料都移動的使用者帳戶。 如需資訊，請參閱[Lync Server 2013 中的備份和還原需求： 資料](lync-server-2013-backup-and-restoration-requirements-data.md)。

<div>

## <a name="migrate-user-settings-to-lync-online"></a>將使用者設定移轉至 Lync Online

使用者設定都會移與使用者帳戶。 內部部署的某些設定不會移動與使用者帳戶。

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a>將試驗使用者移至 Lync Online

開始將使用者移至 Lync Online 之前，您可能要移動一些試驗使用者，以確認已正確設定您的環境。 然後，您可以驗證該 Lync 功能和服務函式預期，再嘗試移動其他使用者。

若要將內部部署使用者移至 Lync Online 租用戶，執行下列 cmdlet 以 Lync Server 管理命令介面，使用您的 Microsoft Office 365 租用戶的系統管理員認證。 「 Username@contoso.com 」 取代為您想要移動使用者的資訊。

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

格式如**HostedMigrationOverrideUrl**參數必須是主控遷移服務執行，以下列格式的集區的 URL 所指定的 URL: Https://\<集區 FQDN\>/HostedMigration/hostedmigrationService.svc。

您可以透過檢視 URL 的 Office 365 租用戶帳戶的 Lync Online 控制台判斷主控移轉服務的 URL。

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

<div>

## <a name="moving-users-to-lync-online"></a>將使用者移至 Lync Online

您可以移動多位使用者使用[Get-csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet 搭配 – Filter 參數來選取的使用者使用指派給使用者帳戶，例如 RegistrarPool 特定屬性。 您可以再透過管線傳[Move-csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet 時，傳回的使用者在下列範例所示。

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

您也可以使用 – OU 參數來擷取所有使用者在指定之 OU 中，如下列範例所示。

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a>確認 Lync Online 使用者設定及功能

您可以確認使用者已成功移動方式如下：

  - 在 Lync Online Control Panel 中檢視使用者的狀態。 內部部署使用者和 online 使用者視覺標記為不同。

  - 執行下列 Cmdlet：
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

