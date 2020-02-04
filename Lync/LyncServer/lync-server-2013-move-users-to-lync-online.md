---
title: Lync Server 2013：將使用者移至 Lync Online
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
ms.openlocfilehash: da56c7230f35d2f900f51b53beef98c64d1e750a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a>在 Lync Server 2013 中將使用者移至 Lync Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-29_

在您開始將使用者遷移至 Lync Online 之前，您應該先備份與要移動之帳戶相關聯的使用者資料。 並非所有的使用者資料都會與使用者帳戶一起移動。 如需詳細資訊，請參閱[Lync Server 2013： data 中的備份與還原需求](lync-server-2013-backup-and-restoration-requirements-data.md)。

<div>

## <a name="migrate-user-settings-to-lync-online"></a>將使用者設定遷移至 Lync Online

使用者設定會與使用者帳戶一起移動。 某些內部部署的設定不會與使用者帳戶一起移動。

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a>將試驗使用者移至 Lync Online

在您開始將使用者移至 Lync Online 之前，您可能會想要移動幾個試驗使用者，以確認您的環境已正確設定。 然後，您可以在嘗試移動其他使用者之前，確認 Lync 功能及服務是否如期運作。

若要將內部部署使用者移至 Lync Online 租使用者，請在 Lync Server Management Shell 中使用 Microsoft Office 365 租使用者的系統管理員認證來執行下列 Cmdlet。 將 [username@contoso.com] 取代為您想要移動的使用者資訊。

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

針對**HostedMigrationOverrideUrl**參數所指定的 url 格式，必須是正在執行託管遷移服務之池的 url，格式如下： HTTPS://\<池 FQDN/HostedMigration/hostedmigrationService.svc.\>

您可以透過查看 Office 365 租使用者帳戶的 Lync Online 控制台 URL 來判斷託管遷移服務的 URL。

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

<div>

## <a name="moving-users-to-lync-online"></a>將使用者移至 Lync Online

您可以使用[move-csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) Cmdlet 和– Filter 參數來移動多個使用者，以選取具有指派給使用者帳戶之特定屬性的使用者，例如 RegistrarPool。 然後，您可以將傳回的使用者輸送至[move-csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) Cmdlet，如下列範例所示。

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

您也可以使用– OU 參數來檢索指定 OU 中的所有使用者，如下例所示。

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a>驗證 Lync Online 使用者設定與功能

您可以透過下列方式確認使用者已順利移動：

  - 在 Lync Online [控制台] 中，查看使用者的狀態。 內部部署使用者和線上使用者的視覺指標不同。

  - 執行下列 Cmdlet：
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

